---
title: "Worklog Tuần 3"
date: 2026-05-10
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---



## FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Mục tiêu tuần
Mục tiêu chính tuần này là tìm hiểu và xây dựng một kiến trúc mạng phức tạp hơn, mô phỏng môi trường thực tế của doanh nghiệp:
* Lên văn phòng công ty gặp Mentor để nhận định hướng công việc.
* Thực hành kết nối hai VPC (Default VPC và HG VPC) thông qua VPC Peering.
* Thiết lập hệ thống Route 53 Resolver (Inbound & Outbound Endpoints) để phân giải DNS trong mô hình Hybrid Cloud.
* Tìm hiểu cách tích hợp Microsoft Active Directory để quản lý danh tính đồng bộ.

## 2. Các công việc cần triển khai trong tuần
Dưới đây là bảng tổng hợp các hoạt động đã thực thực tế từ ngày 04/05/2026 - 10/05/2026:

| Thứ / Ngày | Nội dung công việc | Chi tiết nhiệm vụ | Kết quả đạt được | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Thứ 2 (04/05) | Hội ngộ văn phòng | - Lên văn phòng AWS: <br> &emsp; + Lên văn phòng công ty gặp Mentor Nguyễn Gia Hưng <br> &emsp; + Nhận định hướng và thảo luận văn hóa làm việc | Thấu hiểu quy định và văn hóa làm việc tại Amazon Vietnam. | Văn phòng AWS VN |
| Thứ 3 (05/05) | Lý thuyết VPC Peering | - Nghiên cứu VPC Peering: <br> &emsp; + Nghiên cứu tài liệu VPC Peering <br> &emsp; + Tìm hiểu điều kiện CIDR không trùng lặp và tính phi bắc cầu | Hiểu nguyên lý kết nối điểm-điểm của VPC Peering. | [AWS Documentation](https://000019.awsstudygroup.com/vi/1-introduce/) |
| Thứ 4 (06/05) | Triển khai Peering | - Triển khai VPC Peering: <br> &emsp; + Thiết lập VPC Peering giữa Default VPC và HG VPC <br> &emsp; + Cập nhật Route Tables cả hai đầu | Giao tiếp thông suốt giữa các EC2 trong hai mạng khác nhau qua Private IP. | [AWS Study Group](https://000019.awsstudygroup.com/vi/) |
| Thứ 5 (07/05) | Bảo mật Subnet | - Cấu hình bảo mật nâng cao: <br> &emsp; + Cấu hình Network ACL cho HG VPC <br> &emsp; + Thiết lập Inbound/Outbound Rules <br> &emsp; + Kích hoạt Cross-Peer DNS | Tăng cường bảo mật ở cấp Subnet; phân giải được tên miền của instance trong VPC đối tác. | [AWS Study Group](https://000019.awsstudygroup.com/vi/3-updatenetworkacl/) |
| Thứ 6 (08/05) | Nghiên cứu Hybrid DNS | - Lý thuyết Hybrid DNS: <br> &emsp; + Tìm hiểu Route 53 Resolver <br> &emsp; + Phân tích cơ chế hoạt động của Inbound và Outbound Endpoints | Nắm được kiến trúc phân giải DNS lai (Hybrid DNS Resolution). | [AWS Architecture Guide](https://000010.awsstudygroup.com/) |
| Thứ 7 (09/05) | Cấu hình Resolver | - Thực hành DNS Resolver: <br> &emsp; + Tạo Inbound/Outbound Endpoints <br> &emsp; + Cấu hình Forwarding Rules chuyển tiếp truy vấn | Hệ thống Cloud và On-premises giả lập phân giải được tên miền của nhau. | [AWS Study Group](https://000019.awsstudygroup.com/vi/6-crosspeerdns/) |
| Chủ Nhật (10/05) | Đồng bộ Identity | - Nghiên cứu đồng bộ định danh: <br> &emsp; + Nghiên cứu kết nối Microsoft AD phục vụ định danh mạng lai | Nắm vững giải pháp quản lý danh tính tập trung (Centralized Identity Management). | [AWS Directory Service](https://www.youtube.com/watch?v=N_vlJGAqZxo&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=151) |

## 3. Kết quả đạt được
Qua tuần thực hành kết nối liên VPC và phân giải DNS mạng lai, những bài học kinh nghiệm bổ ích sau đây đã được đúc kết:

* **Thiết lập kết nối liên VPC qua VPC Peering:**
  + VPC Peering đã được cấu hình thành công kết nối Default VPC và HG VPC, cập nhật Route Table và bật Cross-Peer DNS. Các EC2 trong hai VPC đã có thể ping và gọi tên miền nội bộ của nhau mượt mà.
  + Đúc kết: VPC Peering là giải pháp tốt nhất để truyền tải dữ liệu trực tiếp giữa các VPC qua đường truyền riêng an toàn, loại bỏ độ trễ và chi phí định tuyến qua Internet công cộng.

* **Giải pháp phân giải tên miền mạng lai với Route 53 Resolver:**
  + Quá trình thực hành bao gồm cấu hình Route 53 Resolver gồm **Inbound Endpoints** (để mạng On-premise giả lập truy vấn DNS trên AWS) và **Outbound Endpoints** (để AWS chuyển tiếp yêu cầu DNS về On-premise).
  + Đúc kết: Resolver đóng vai trò là "xương sống" đồng bộ hóa sơ đồ tên miền nội bộ giữa hai môi trường Cloud và On-premises. Giúp các ứng dụng lai (Hybrid) giao tiếp liền mạch mà không cần cấu hình file hosts thủ công trên từng máy chủ.

* **Quản lý danh tính tập trung qua Active Directory Integration:**
  + Tìm hiểu cách tích hợp Microsoft Active Directory qua AWS Directory Service.
  + Đúc kết: Tích hợp AD và Single Sign-On (SSO) giúp quản trị tài khoản tập trung, loại bỏ rủi ro quản lý tài khoản rời rạc và đơn giản hóa quy trình cấp quyền bảo mật.

* **FinOps thực tế:**
  + Đúc kết: Dịch vụ Route 53 Resolver Endpoints tính phí theo giờ chạy khá cao. Ngay sau khi hoàn thành lab kiểm thử kết nối, toàn bộ Inbound/Outbound Endpoints đã được chủ động xóa bỏ để bảo toàn credit dự án.
