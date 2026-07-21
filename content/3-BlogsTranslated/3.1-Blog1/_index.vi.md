---
title: "Blog 1"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---



## Deploy Backend lên AWS EC2 và lỗi chỉ vì chữ hoa

**Link bài viết:** [Facebook - AWS Study Group FCJ](https://www.facebook.com/groups/awsstudygroupfcj/permalink/2184227519008875/)

Khi triển khai backend từ môi trường local lên AWS EC2, nhiều lỗi không xuất hiện ngay dưới dạng error rõ ràng. Ứng dụng vẫn khởi động, server vẫn chạy, nhưng một vài logic bên trong lại hoạt động sai. Trường hợp trong bài viết này đến từ một chi tiết rất nhỏ: cách viết hoa, viết thường của giá trị trong environment variables.

Trong môi trường local Windows, ứng dụng Node.js đọc file `.env` và xử lý các biến cấu hình bình thường. Tuy nhiên, khi source code được deploy lên EC2 chạy Ubuntu/Linux, một số flag Boolean không còn được hiểu đúng. Các chức năng tự động không chạy, điều kiện kiểm tra trả về sai, và quá trình debug mất khá nhiều thời gian vì hệ thống không báo lỗi trực tiếp.

---

## Environment Variables trong backend

Trong các dự án backend, environment variables thường được dùng để tách cấu hình ra khỏi source code. Thay vì hard-code region, secret key, database password hoặc trạng thái môi trường vào code, developer có thể đặt chúng trong file `.env`.

Ví dụ:

```env
ENV=development
REGION=ap-southeast-1
ENVIRONMENT_AUTO=True
```

Cách làm này giúp ứng dụng dễ chuyển đổi giữa development và production, giảm việc chỉnh sửa source code khi deploy, đồng thời gom cấu hình vào một nơi dễ quản lý hơn. Khi deploy lên EC2, file `.env` thường được copy hoặc tạo thủ công trên server để ứng dụng đọc trong runtime.

---

## Mô hình triển khai ban đầu

Mô hình triển khai ban đầu khá đơn giản: developer đẩy source code và file `.env` từ local lên EC2 thông qua SSH hoặc Git, sau đó chạy backend Node.js trực tiếp trên instance.

![Mô hình deploy backend EC2 với file env](/images/3-BlogsTranslated/3.1-Blog1/ec2-env-file-risk.png)

Luồng triển khai gồm:

- Source code được upload lên EC2.
- File `.env` được tạo hoặc chỉnh sửa trực tiếp trên server.
- Backend server được start bằng Node.js.
- Ứng dụng đọc biến môi trường từ file `.env`.

Mọi thứ tưởng như ổn cho đến khi ứng dụng bắt đầu xử lý các giá trị Boolean.

---

## Lỗi phát sinh sau khi deploy lên EC2

Ở local, flag sau hoạt động đúng:

```env
ENVIRONMENT_AUTO=True
```

Nhưng khi chạy trên EC2 Ubuntu/Linux, một số đoạn kiểm tra điều kiện không còn đúng nữa. Ví dụ:

```js
if (process.env.ENVIRONMENT_AUTO === "true") {
  // run auto configuration
}
```

Trong trường hợp này, giá trị `"True"` và `"true"` không giống nhau. Nếu code chỉ so sánh với chuỗi lowercase `"true"`, điều kiện sẽ fail dù về mặt ý nghĩa người viết `.env` đang muốn bật tính năng đó.

Đây là dạng lỗi dễ bị bỏ qua vì ứng dụng không crash. Nó chỉ khiến business logic chạy sai, ví dụ:

- Không nhận đúng trạng thái môi trường.
- Một số chức năng tự động không hoạt động.
- Config Boolean luôn bị hiểu sai.
- App chạy bất thường nhưng không có stack trace rõ ràng.

---

## Nguyên nhân chính

### 1. Linux và hệ sinh thái runtime xử lý case-sensitive chặt chẽ

Khi deploy từ Windows sang Linux, developer cần cẩn thận hơn với case-sensitive. Bản thân environment variable, tên file, giá trị string và cách framework parse `.env` đều có thể tạo ra khác biệt.

Với Boolean trong `.env`, `True`, `TRUE` và `true` thường chỉ là các chuỗi khác nhau. Nếu code không normalize dữ liệu trước khi so sánh, ứng dụng rất dễ chạy sai logic.

### 2. Quản lý file .env thủ công trên EC2 dễ phát sinh lỗi

Việc tạo file `.env` bằng `nano .env` trên server rất nhanh, nhưng không bền vững khi hệ thống lớn hơn. Cách làm này dễ gặp các vấn đề như:

- Gõ sai tên biến hoặc sai format.
- Thiếu biến giữa các môi trường.
- Khó đồng bộ development, staging và production.
- Có nguy cơ lộ secret nếu instance bị truy cập trái phép.

Các giá trị như database password, API token hoặc secret key không nên được quản lý lâu dài bằng một file nằm trực tiếp trên server.

---

## Cách khắc phục nhanh

Cách xử lý đầu tiên là đồng bộ toàn bộ giá trị Boolean trong `.env` về lowercase:

```env
ENVIRONMENT_AUTO=true
```

Trong code, nên normalize dữ liệu trước khi so sánh:

```js
const autoEnv = process.env.ENVIRONMENT_AUTO?.toLowerCase() === "true";
```

Sau khi chỉnh lại format và ép kiểu rõ ràng, ứng dụng nhận đúng trạng thái môi trường và các chức năng tự động hoạt động ổn định hơn.

---

## Hướng tối ưu theo best practice AWS

Về lâu dài, lưu `.env` trực tiếp trên EC2 không phải là cách tối ưu về bảo mật. Một hướng tốt hơn là đưa cấu hình và secret vào dịch vụ quản lý tập trung như **AWS Systems Manager Parameter Store** hoặc **AWS Secrets Manager**.

![Mô hình sử dụng Parameter Store cho EC2](/images/3-BlogsTranslated/3.1-Blog1/parameter-store-architecture.jpg)

Với mô hình này:

- EC2 instance được gán IAM Role phù hợp.
- Ứng dụng gọi AWS SDK để lấy cấu hình khi runtime.
- Secret không cần nằm trực tiếp trong source code hoặc file `.env` trên server.
- Quyền truy cập được kiểm soát bằng IAM policy.

Ví dụ luồng xử lý:

```text
EC2 Instance -> IAM Role -> AWS Systems Manager Parameter Store
```

Cách tiếp cận này giúp quản lý biến môi trường tập trung hơn, tăng bảo mật, dễ scale và phù hợp hơn với môi trường production.

---

## Bài học rút ra

Một lỗi nhỏ về chữ hoa và chữ thường có thể làm ứng dụng chạy sai hoàn toàn sau khi deploy. Từ trải nghiệm này, có một vài bài học quan trọng:

- Cloud Linux khác local Windows nhiều hơn tưởng tượng.
- Các lỗi nhỏ như sai case, sai kiểu dữ liệu hoặc sai format `.env` có thể tốn nhiều thời gian debug.
- Environment variables không chỉ là cấu hình, mà còn liên quan trực tiếp đến bảo mật, khả năng vận hành và khả năng scale.
- Secret nên được quản lý bằng dịch vụ chuyên dụng thay vì lưu lâu dài trong file trên server.

---

## Kết luận

Qua quá trình deploy backend lên AWS EC2, bài học lớn nhất không chỉ là cách chạy ứng dụng trên cloud, mà còn là cách quản lý cấu hình một cách nhất quán và an toàn. Với những dự án nhỏ, file `.env` có thể đủ để bắt đầu. Tuy nhiên, khi hệ thống tiến gần hơn đến production, nên cân nhắc sử dụng AWS Systems Manager Parameter Store hoặc AWS Secrets Manager để quản lý cấu hình và secret theo hướng bảo mật hơn.

