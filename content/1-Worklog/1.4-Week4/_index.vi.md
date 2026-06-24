---
title: "Worklog Tuần 4"
date: 2026-05-17
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Tổng quan Mục tiêu và Kế hoạch Tuần 04
Tuần 4 tập trung vào quản trị dữ liệu an toàn và tự động hóa hạ tầng quy mô lớn. Học viên được giao nghiên cứu và cấu hình **AWS Backup** cùng **AWS SNS** để tự động hóa sao lưu và gửi cảnh báo; thiết lập môi trường và sử dụng **AWS CLI** cục bộ để quản trị tài nguyên; triển khai **AWS Transit Gateway** để định tuyến tập trung thay cho VPC Peering truyền thống nhằm kết nối 4 VPC riêng biệt và dọn dẹp tài nguyên để tối ưu hóa chi phí.

> **So What:** Khả năng tự động hóa sao lưu (Backup) và hợp nhất định tuyến qua Transit Gateway giúp nâng cao độ tin cậy của hệ thống (Reliability) và giảm thiểu rủi ro vận hành khi quy mô doanh nghiệp mở rộng.

---

## 2. Nhật ký Công việc Chi tiết (Worklog)
Dưới đây là bảng tổng hợp các hoạt động đã thực hiện từ ngày 11/05/2026 - 17/05/2026:

| Thứ / Ngày | Nội dung công việc | Chi tiết nhiệm vụ | Kết quả đạt được | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Thứ 2 (11/05) | Bảo mật dữ liệu | Nghiên cứu AWS Backup; tạo Backup Vault và cấu hình Backup Plan tự động. | Thiết lập chính sách sao lưu định kỳ cho các ổ đĩa và CSDL. | AWS Backup Guide |
| Thứ 3 (12/05) | Cảnh báo sao lưu | Cấu hình AWS SNS; liên kết AWS Backup với SNS topic; đăng ký nhận thông báo qua Email. | Email nhận cảnh báo tự động khi quá trình sao lưu bắt đầu, thành công hoặc lỗi. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Thứ 4 (13/05) | Cấu hình Local CLI | Cài AWS CLI trên máy cá nhân; cấu hình AWS Access Key/Secret Key; dùng CLI tạo và quản trị S3, IAM, SNS. | Sử dụng dòng lệnh thành thạo để quản lý tài nguyên AWS từ local. | AWS CLI Documentation |
| Thứ 5 (14/05) | Nghiên cứu Transit Gateway | Tìm hiểu lý thuyết AWS Transit Gateway (TGW) và so sánh ưu điểm với VPC Peering full-mesh. | Hiểu cách TGW đóng vai trò là Hub-and-Spoke router thông minh. | AWS Networking Guide |
| Thứ 6 (15/05) | Cấu hình Transit Gateway | Khởi tạo Transit Gateway; tạo Attachments để kết nối đồng thời 4 VPC riêng biệt vào TGW. | Hợp nhất đường truyền mạng của 4 VPC thông qua một cổng quản trị trung tâm. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Thứ 7 (16/05) | Kiểm thử định tuyến | Cấu hình Route Tables cho TGW; tạo EC2 (t3.nano) trong các VPC để ping kiểm tra kết nối chéo AZ. | Định tuyến thành công, các VPC giao tiếp được với nhau thông qua Transit Gateway. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Chủ Nhật (17/05) | Tối ưu hóa chi phí | Tiến hành Terminate toàn bộ EC2, xóa Transit Gateway và các bản sao lưu thử nghiệm. | Dọn dẹp tài nguyên triệt để; đảm bảo không hao phí credit dư thừa. | AWS Billing Dashboard |

> **So What:** Việc kết hợp tự động hóa qua CLI và quản lý tập trung qua Transit Gateway giúp giảm thời gian triển khai từ hàng giờ xuống hàng phút, đồng thời đảm bảo hệ thống tuân thủ các quy tắc bảo mật.

---

### 3. Giải pháp Tự động hóa Sao lưu với AWS Backup & SNS
**AWS Backup** cung cấp dịch vụ quản trị và tự động hóa việc sao lưu dữ liệu tập trung trên nhiều dịch vụ AWS khác nhau (EBS, RDS, DynamoDB, EFS).

* **Backup Plan:** Định nghĩa lịch trình (ví dụ: hàng ngày lúc 1:00 AM) và thời gian lưu trữ (Retention period: 7 ngày).
* **Backup Vault:** Nơi lưu trữ các bản sao lưu được mã hóa bằng KMS key để tránh truy cập trái phép.
* **Cơ chế Pub/Sub qua SNS:** Tích hợp với **Amazon SNS** để gửi thông báo trực tiếp qua Email hoặc Chatbot mỗi khi trạng thái sao lưu thay đổi (COMPLETED/FAILED).

> **So What:** Thiết lập sao lưu tự động và giám sát qua SNS đảm bảo tính **Business Continuity** (Kinh doanh liên tục), giúp doanh nghiệp nhanh chóng phục hồi sau sự cố mất mát dữ liệu.

---

### 4. Kết nối Liên mạng với AWS Transit Gateway
Khi số lượng VPC trong hệ thống lớn dẫn (từ 3-4 VPC trở lên), việc kết nối dạng lưới (Full-mesh VPC Peering) sẽ trở nên vô cùng phức tạp và khó quản trị (Cần N*(N-1)/2 kết nối peering).

**Giải pháp với Transit Gateway (TGW):**
* **Hub-and-Spoke Topology:** TGW đóng vai trò là một Router đám mây trung tâm. Các VPC chỉ cần tạo một liên kết (Attachment) duy nhất đến TGW.
* **TGW Route Tables:** Cho phép cấu hình các chính sách định tuyến linh hoạt và cô lập các VPC nếu cần thiết.
* **Khả năng mở rộng:** Dễ dàng thêm VPC mới vào hệ thống mà không cần thiết lập lại các liên kết cũ.

![Kiến trúc Transit Gateway](/images/1-Worklog/Week4/tgw-architecture.png)

> **So What:** Sử dụng Transit Gateway giúp tối giản hóa sơ đồ mạng doanh nghiệp, giảm thiểu số lượng Route Table cần quản lý và tăng độ tin cậy hệ thống mạng.

---

### 5. Tối ưu hóa Chi phí: AWS CLI và Dọn dẹp Tài nguyên
Để tối ưu hóa hạn mức tín dụng thực tập, việc sử dụng các dòng lệnh CLI để truy vấn nhanh và dọn dẹp tài nguyên là rất cần thiết.

**Kỹ thuật tối ưu chi phí trong Lab:**
1. **Lựa chọn Instance nhỏ nhất:** Sử dụng máy ảo `t3.nano` (chỉ có 0.5 GB RAM) cho mục đích kiểm thử mạng.
2. **Xóa tài nguyên ngay:** TGW phát sinh chi phí cố định theo giờ chạy của mỗi Attachment. Vì thế, việc xóa TGW Attachments ngay sau khi kiểm thử ping thành công là bắt buộc.
3. **Câu lệnh CLI hữu dụng để dọn dẹp:**
   * Xóa S3 Bucket: `aws s3 rb s3://my-test-bucket --force`
   * Liệt kê EC2 đang chạy: `aws ec2 describe-instances --query "Reservations[*].Instances[*].[InstanceId,State.Name]"`

> **So What:** Kỹ năng dọn dẹp tài nguyên tự động hóa giúp Builder giữ tài khoản luôn sạch và tránh các hóa đơn ngoài ý muốn.

---

### 6. Tổng kết và Đánh giá Kết quả Tuần 4

#### 6.1. Kỹ năng Nhóm và Giao tiếp (Soft Skills)
* **Tự quản lý:** Phân chia thời gian làm việc khoa học để cân bằng giữa lý thuyết và thực hành cấu hình Transit Gateway phức tạp.
* **Chia sẻ kinh nghiệm:** Hỗ trợ đồng đội sửa lỗi định tuyến trên TGW Route Tables.

#### 6.2. Quản trị Tài nguyên và Chi phí (FinOps)
* **Hành động kịp thời:** Tắt các máy chủ `t3.nano` và xóa Transit Gateway Attachments, tiết kiệm tối đa credit sử dụng.

#### 6.3. Bảo mật và Quản trị Hệ thống (Security & Infrastructure)
* **Tự động bảo vệ:** Thiết lập thành công chính sách sao lưu tự động qua AWS Backup và cơ chế thông báo trạng thái qua SNS.
* **Kiến trúc mạng:** Làm chủ Transit Gateway và kết nối 4 VPC hoạt động ổn định.

#### 6.4. Năng lực Kỹ thuật và Tư duy AI (Technical & AI Mindset)
* **Tự động hóa:** Nâng cao khả năng sử dụng AWS CLI để quản lý tài nguyên nhanh chóng từ terminal máy tính cá nhân.

---
**Đánh giá chung:** Hoàn thành tốt các mục tiêu tuần 4. Hệ thống sao lưu và định tuyến tập trung đã hoạt động đúng thiết kế.
