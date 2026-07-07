---
title: "Worklog Tuần 4"
date: 2026-05-17
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Mục tiêu tuần
Tuần này mình tập trung học cách tự động hóa sao lưu dữ liệu và quản trị mạng ở quy mô lớn hơn:
* Tìm hiểu và cấu hình dịch vụ AWS Backup để sao lưu tự động và gửi cảnh báo trạng thái qua AWS SNS.
* Cài đặt và sử dụng thành thạo bộ công cụ AWS CLI ngay tại máy cá nhân.
* Nghiên cứu và triển khai AWS Transit Gateway (TGW) để định tuyến tập trung, liên kết đồng thời 4 VPC khác nhau.
* Dọn dẹp tài nguyên sau thực hành để tối ưu chi phí.

## 2. Các công việc cần triển khai trong tuần
Dưới đây là bảng tổng hợp các hoạt động đã thực hiện từ ngày 11/05/2026 - 17/05/2026:

| Thứ / Ngày | Nội dung công việc | Chi tiết nhiệm vụ | Kết quả đạt được | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Thứ 2 (11/05) | Bảo mật dữ liệu | - Thực hành AWS Backup: <br> &emsp; + Nghiên cứu AWS Backup <br> &emsp; + Tạo Backup Vault <br> &emsp; + Cấu hình Backup Plan tự động | Thiết lập chính sách sao lưu định kỳ cho các ổ đĩa và CSDL. | AWS Backup Guide |
| Thứ 3 (12/05) | Cảnh báo sao lưu | - Tích hợp cảnh báo: <br> &emsp; + Cấu hình AWS SNS <br> &emsp; + Liên kết AWS Backup với SNS topic <br> &emsp; + Đăng ký nhận thông báo qua Email | Email nhận cảnh báo tự động khi quá trình sao lưu bắt đầu, thành công hoặc lỗi. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Thứ 4 (13/05) | Cấu hình Local CLI | - Cài đặt CLI local: <br> &emsp; + Cài AWS CLI trên máy cá nhân <br> &emsp; + Cấu hình AWS Access Key/Secret Key <br> &emsp; + Dùng CLI tạo và quản trị S3, IAM, SNS | Sử dụng dòng lệnh thành thạo để quản lý tài nguyên AWS từ local. | AWS CLI Documentation |
| Thứ 5 (14/05) | Nghiên cứu Transit Gateway | - Học định tuyến tập trung: <br> &emsp; + Tìm hiểu lý thuyết AWS Transit Gateway (TGW) <br> &emsp; + So sánh ưu điểm với VPC Peering full-mesh | Hiểu cách TGW đóng vai trò là Hub-and-Spoke router thông minh. | AWS Networking Guide |
| Thứ 6 (15/05) | Cấu hình Transit Gateway | - Triển khai TGW: <br> &emsp; + Khởi tạo Transit Gateway <br> &emsp; + Tạo Attachments kết nối đồng thời 4 VPC vào TGW | Hợp nhất đường truyền mạng của 4 VPC thông qua một cổng quản trị trung tâm. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Thứ 7 (16/05) | Kiểm thử định tuyến | - Kiểm thử liên mạng: <br> &emsp; + Cấu hình Route Tables cho TGW <br> &emsp; + Tạo EC2 (t3.nano) trong các VPC để ping kiểm tra kết nối | Định tuyến thành công, các VPC giao tiếp được với nhau thông qua Transit Gateway. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Chủ Nhật (17/05) | Tối ưu hóa chi phí | - Thực hành FinOps: <br> &emsp; + Tiến hành Terminate toàn bộ EC2 <br> &emsp; + Xóa Transit Gateway và các bản sao lưu thử nghiệm | Dọn dẹp tài nguyên triệt để; đảm bảo không hao phí credit dư thừa. | AWS Billing Dashboard |

## 3. Kết quả đạt được
Qua tuần thực hành quản trị dữ liệu và định tuyến mạng tập trung, mình đã đúc kết được các bài học kinh nghiệm sau:

* **Tự động hóa sao lưu và quản lý rủi ro dữ liệu (AWS Backup):**
  + Mình đã cấu hình thành công Backup Plan tự động sao lưu ổ đĩa EBS và CSDL, liên kết với AWS SNS để gửi thông báo Email mỗi khi Backup Job hoàn thành hoặc lỗi.
  + Đúc kết: Sao lưu tự động giúp loại bỏ sai sót của con người và giảm thiểu nguy cơ mất dữ liệu do Ransomware. Cảnh báo email giúp đội ngũ quản trị phản ứng tức thì với các sự cố sao lưu.

* **Sử dụng dòng lệnh để tăng tốc độ làm việc (AWS CLI):**
  + Tự tay cài đặt CLI và thực hành tạo S3 bucket, cấu hình IAM, gửi message qua SNS trực tiếp trên Terminal của máy local.
  + Đúc kết: AWS CLI là kỹ năng cơ bản bắt buộc để hướng tới tự động hóa hạ tầng (Infrastructure as Code - IaC). Sử dụng CLI giúp thực thi lệnh hàng loạt nhanh hơn nhiều so với việc click thủ công trên web console.

* **Định tuyến mạng tập trung quy mô lớn (AWS Transit Gateway):**
  + Triển khai Transit Gateway (TGW) làm cổng Hub-and-Spoke kết nối 4 VPC chéo với nhau thông qua Transit Gateway Attachments và cấu hình bảng định tuyến cho máy ảo `t3.nano` ping thông suốt.
  + Đúc kết: Khi số lượng VPC tăng lên, TGW giảm độ phức tạp của sơ đồ kết nối từ cấp số nhân $O(N^2)$ (của VPC Peering full-mesh) xuống tuyến tính $O(N)$. Điều này giúp sơ đồ mạng cực kỳ sạch sẽ, dễ bảo mật và dễ mở rộng lên hàng trăm VPC.

* **FinOps thực tế:**
  + Đúc kết: Transit Gateway tính phí theo số lượng attachment khá đắt đỏ. Mình đã nhanh chóng kiểm tra định tuyến và xóa bỏ TGW, terminate các máy ảo EC2 `t3.nano` ngay sau bài lab để tránh tiêu hao credit ngoài ý muốn.
