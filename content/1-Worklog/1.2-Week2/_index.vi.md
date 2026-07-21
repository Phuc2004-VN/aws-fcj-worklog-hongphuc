---
title: "Worklog Tuần 2"
date: 2026-05-03
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---



## FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Mục tiêu tuần
Tuần này tập trung vào thiết lập mạng Custom VPC và hoàn tất các thủ tục hành chính:
* Hoàn tất đăng ký thông tin thực tập sinh của công ty.
* Nghiên cứu lý thuyết mạng cơ bản (IP Address, CIDR Block, Subnet).
* Thực hành khởi tạo một Custom VPC, phân chia Public/Private Subnet.
* Cấu hình Internet Gateway và Route Tables để định tuyến cho Public Subnet.
* Phân biệt Security Groups (Stateful) và Network ACLs (Stateless).
* Tạo máy chủ EC2 ở cả Public và Private Subnet để kiểm tra kết nối.

## 2. Các công việc cần triển khai trong tuần
Dưới đây là bảng tổng hợp các hoạt động đã thực hiện từ ngày 24/04/2026 - 03/05/2026:

| Thứ / Ngày | Nội dung công việc | Chi tiết nhiệm vụ | Kết quả đạt được | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Thứ 6 (24/04) | Đăng ký thông tin | - Đăng ký thông tin: <br> &emsp; + Điền link khảo sát thông tin thực tập <br> &emsp; + Nhận hướng dẫn chuẩn bị lên văn phòng | Hoàn tất thủ tục hành chính; sẵn sàng onboarding tại văn phòng. | [Link đăng ký của AWS](https://hcm-rules.awsfcaj.com/2-instructions/2.4-moving/) |
| Thứ 7 (25/04) | Nghiên cứu VPC cơ bản | - Học lý thuyết VPC: <br> &emsp; + Xem video hướng dẫn AWS <br> &emsp; + Nghiên cứu IP Address, CIDR Block, Subnet | Nắm được cách phân chia địa chỉ IP và dải mạng trong VPC. | [Video từ hướng dẫn](https://www.youtube.com/watch?v=BPuD1l2hEQ4&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=26)|
| Chủ Nhật (26/04) | Thiết kế sơ đồ mạng | - Vẽ sơ đồ mạng: <br> &emsp; + Vẽ nháp mô hình Public Subnet và Private Subnet | Hình dung được luồng đi của traffic từ Internet vào mạng nội bộ. | [AWS Documentation](https://aws.amazon.com/vi/architecture/)|
| Thứ 2 (27/04) | Quản lý ngân sách | - Cấu hình ngân sách mạng: <br> &emsp; + Thiết lập AWS Budgets nâng cao cho NAT Gateway và VPN | Thiết lập cảnh báo ngưỡng chi phí để kiểm soát phí NAT Gateway và VPN. | [AWS Billing Console](https://000007.awsstudygroup.com/vi/) |
| Thứ 3 (28/04) | Khởi tạo VPC | - Khởi tạo VPC: <br> &emsp; + Tạo Custom VPC với CIDR `10.0.0.0/16` <br> &emsp; + Phân chia Public và Private Subnets | Cấu hình thành công phân vùng mạng riêng cô lập. | [AWS Study Group](https://000003.awsstudygroup.com/vi/) |
| Thứ 4 (29/04) | Định tuyến mạng | - Cấu hình định tuyến: <br> &emsp; + Tạo Route Tables, Internet Gateway (IGW) <br> &emsp; + Gắn IGW vào Public Subnet | Giúp các tài nguyên trong Public Subnet kết nối được ra ngoài Internet. | [AWS Study Group](https://000003.awsstudygroup.com/vi/) |
| Thứ 5 (30/04) | Tìm hiểu bảo mật mạng | - Tìm hiểu bảo mật mạng: <br> &emsp; + Nghiên cứu sự khác biệt giữa Security Groups và Network ACL | Nắm vững hai bức tường lửa bảo vệ EC2 và Subnet. | [AWS Security Guide](https://000003.awsstudygroup.com/vi/3-prerequisite/3.5-createsecuritygroup/) |
| Thứ 6 (01/05) | Ngày lễ Quốc tế Lao động | - Tự học VPC nâng cao: <br> &emsp; + Tìm hiểu best practices thiết kế High Availability (HA) cho VPC | Hiểu cách triển khai Subnet trên nhiều Availability Zones (AZs). | [AWS Architecture Center](https://000019.awsstudygroup.com/) |
| Thứ 7 (02/05) | Kiểm thử EC2 & VPC | - Thực hành kiểm thử: <br> &emsp; + Tạo EC2 trong Public Subnet và test SSH <br> &emsp; + Tạo EC2 trong Private Subnet và kiểm tra kết nối | Xác minh cấu hình định tuyến và bảo mật hoạt động chính xác. | [AWS Study Group](https://000019.awsstudygroup.com/vi/2-prerequiste/2.3-createec2/) |
| Chủ Nhật (03/05) | Báo cáo tuần | - Báo cáo tuần: <br> &emsp; + Tổng hợp nhật ký công việc tuần 2 <br> &emsp; + Chuẩn bị kế hoạch tuần tiếp theo | Hoàn thiện tài liệu lưu trữ tiến độ thực tập. | Bản ghi cá nhân |

## 3. Kết quả đạt được
Qua tuần thực hành thiết lập Custom VPC, các bài học kinh nghiệm quan trọng sau đây đã được đúc kết:

* **Tự tay thiết kế và chia dải IP mạng (VPC & Subnetting):**
  + Quá trình thực hành giúp nắm rõ cách hoạt động của hệ thống địa chỉ IP và dải mạng **CIDR**. Bằng việc tạo Custom VPC dải `10.0.0.0/16`, hệ thống mạng đã được chia nhỏ thành các Public Subnets (cho máy chủ web, Load Balancer cần ra ngoài Internet) và Private Subnets (cho Database, Backend cần ẩn đi).
  + Đúc kết: Việc lập kế hoạch chia dải IP mạng cẩn thận ngay từ đầu giúp tránh xung đột IP và cản trở việc mở rộng mạng lưới liên kết doanh nghiệp sau này.

* **Cấu hình định tuyến và kiểm thử kết nối:**
  + Internet Gateway (IGW) đã được thiết lập và liên kết bảng định tuyến (Route Table) trỏ ra Internet cho Public Subnet. Máy ảo EC2 trong Public Subnet kết nối được Internet, còn EC2 trong Private Subnet thì hoàn toàn cô lập để bảo mật.
  + Đúc kết: Việc kiểm chứng đường truyền chéo giữa các phân vùng mạng giúp hiểu rõ luồng traffic hoạt động trên thực tế.

* **Bảo vệ mạng bằng 2 lớp tường lửa Security Groups và Network ACLs:**
  + Tự tay cấu hình Security Groups (Stateful - ở cấp độ máy chủ, tự mở chiều ra nếu chiều vào được cho phép) và Network ACLs (Stateless - ở cấp độ Subnet, phải cấu hình thủ công cả 2 chiều).
  + Đúc kết: Áp dụng mô hình phòng thủ chiều sâu (Defense-in-Depth) bằng tường lửa hai lớp là best practice thiết yếu. Ngay cả khi một lớp bị cấu hình sai, tài nguyên vẫn được bảo vệ bởi lớp còn lại.

* **Quản trị chi phí NAT Gateway và VPN (FinOps):**
  + Đúc kết: Các tài nguyên mạng như NAT Gateway hoặc VPN Gateway sinh phí rất nhanh theo giờ. AWS Budgets đã được cấu hình nâng cao ở các ngưỡng 50%, 80%, 100% để gửi thông báo khẩn cấp, bảo toàn credit thực hành.
