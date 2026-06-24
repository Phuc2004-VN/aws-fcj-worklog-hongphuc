---
title: "Worklog Tuần 3"
date: 2026-05-10
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Tổng quan Mục tiêu và Kế hoạch Tuần 03
Tuần thứ ba đánh dấu bước tiến quan trọng trong việc thiết lập kiến trúc mạng phức tạp. Tiêu điểm kỹ thuật tuần này là **VPC Peering** kết nối nội bộ hai VPC (Default VPC và HG VPC), cấu hình **Network ACL** bảo mật ở mức subnet, triển khai hệ thống **Route 53 Resolver** (Inbound & Outbound Endpoints) để xử lý định danh DNS và đồng bộ giải pháp định danh với **Microsoft Active Directory** trong mô hình Hybrid Cloud.

> **So What:** Sự phối hợp giữa VPC Peering và Route 53 Resolver giải quyết bài toán lớn của doanh nghiệp: kết nối bảo mật tốc độ cao và phân giải tên miền liền mạch giữa hạ tầng Cloud AWS và On-premises.

---

## 2. Nhật ký Công việc Chi tiết (Worklog)
Dưới đây là bảng tổng hợp các hoạt động đã thực hiện từ ngày 04/05/2026 - 10/05/2026:

| Thứ / Ngày | Nội dung công việc | Chi tiết nhiệm vụ | Kết quả đạt được | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Thứ 2 (04/05) | Hội ngộ văn phòng | Lên văn phòng công ty; gặp gỡ cán bộ hướng dẫn Nguyễn Gia Hưng và thảo luận định hướng. | Thấu hiểu quy định và văn hóa làm việc tại Amazon Vietnam. | Văn phòng AWS VN |
| Thứ 3 (05/05) | Lý thuyết VPC Peering | Nghiên cứu tài liệu VPC Peering; lưu ý điều kiện CIDR không trùng lặp và tính chất phi bắc cầu. | Hiểu nguyên lý kết nối điểm-điểm của VPC Peering. | AWS Documentation |
| Thứ 4 (06/05) | Triển khai Peering | Thiết lập VPC Peering giữa Default VPC và HG VPC; cập nhật Route Tables cả hai đầu. | Giao tiếp thông suốt giữa các EC2 trong hai mạng khác nhau qua Private IP. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Thứ 5 (07/05) | Bảo mật Subnet | Cấu hình Network ACL cho HG VPC; thiết lập Inbound/Outbound Rules; kích hoạt Cross-Peer DNS. | Tăng cường bảo mật ở cấp Subnet; phân giải được tên miền của instance trong VPC đối tác. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Thứ 6 (08/05) | Nghiên cứu Hybrid DNS | Tìm hiểu Route 53 Resolver; phân tích cơ chế hoạt động của Inbound và Outbound Endpoints. | Nắm được kiến trúc phân giải DNS lai (Hybrid DNS Resolution). | AWS Architecture Guide |
| Thứ 7 (09/05) | Cấu hình Resolver | Tạo Inbound/Outbound Endpoints; cấu hình Forwarding Rules để chuyển tiếp truy vấn DNS. | Hệ thống Cloud và On-premises giả lập phân giải được tên miền của nhau. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Chủ Nhật (10/05) | Đồng bộ Identity | Nghiên cứu và kết nối Microsoft AD để phục vụ đồng bộ định danh trong mạng lai. | Nắm vững giải pháp quản lý danh tính tập trung (Centralized Identity Management). | AWS Directory Service |

> **So What:** Các nhiệm vụ trong tuần liên kết chặt chẽ từ kết nối vật lý (Peering) đến định danh mạng (DNS, Active Directory). Đây là nền tảng để vận hành các ứng dụng doanh nghiệp lớn đòi hỏi tính bảo mật tối đa.

---

### 3. Phân tích Kỹ thuật: VPC Peering và DNS Resolution
**VPC Peering** kết nối hai VPC trực tiếp qua mạng xương sống (backbone) của AWS mà không cần đi qua internet công cộng, giúp giảm trễ và tăng bảo mật.

**Những điểm quan trọng khi cấu hình:**
1. **CIDR không trùng lặp:** Hai VPC muốn peer với nhau bắt buộc phải có dải CIDR khác nhau (Ví dụ: `172.31.0.0/16` và `10.0.0.0/16`).
2. **Cập nhật Route Table:** Phải thêm dòng định tuyến trỏ đến dải IP của VPC đối tác thông qua cổng kết nối `pcx-xxxxx`.
3. **Cross-Peer DNS:** Phải kích hoạt cài đặt "Allow DNS resolution from peer" trên cả hai bên để có thể gọi tên miền nội bộ (ví dụ: `ip-10-0-1-10.ap-southeast-1.compute.internal`) thay vì dùng IP tĩnh.

> **So What:** Thiết lập VPC Peering đúng đắn giúp giảm thiểu rủi ro bảo mật do traffic không đi qua internet công cộng, đồng thời duy trì hiệu năng mạng tốt nhất.

---

### 4. Giải pháp Hybrid DNS qua Route 53 Resolver
Khi kết nối AWS Cloud với Datacenter truyền thống, việc phân giải tên miền giữa hai môi trường là rào cản lớn. **Route 53 Resolver** giải quyết triệt để vấn đề này.

**Kiến trúc Resolver:**
* **Inbound Endpoint:** Nhận truy vấn DNS gửi từ On-premises vào AWS Cloud.
* **Outbound Endpoint:** Chuyển tiếp truy vấn DNS từ AWS Cloud ra On-premises.
* **Forwarding Rule:** Quy định tên miền nào (Ví dụ: `*.corp.hutech.edu.vn`) sẽ được chuyển hướng về DNS Server nào của On-premises.

![Kiến trúc Hybrid DNS](/images/1-Worklog/Week3/hybrid-dns.png)

> **So What:** Việc tự động hóa phân giải tên miền lai loại bỏ sự cần thiết của việc cấu hình file `/etc/hosts` thủ công trên hàng ngàn máy chủ, đảm bảo tính mở rộng và linh hoạt của hệ thống.

---

### 5. Microsoft Active Directory trong Mô hình Lai
Sử dụng **AWS Directory Service** để kết nối Microsoft AD. Điều này cho phép áp dụng chính sách Single Sign-On (SSO) và đồng bộ hóa tài khoản nhân viên từ On-premises lên các máy ảo EC2 Windows/Linux trên đám mây.

**Ưu điểm:**
* Đồng bộ hóa chính sách bảo mật (Group Policy).
* Giảm tải quản trị thông tin đăng nhập.
* Kiểm soát tập trung truy cập tài nguyên.

> **So What:** Tích hợp AD là bước đi chiến lược giúp doanh nghiệp di chuyển các ứng dụng kế thừa (Legacy apps) lên Cloud mà không làm gián đoạn hệ thống quản trị người dùng hiện có.

---

### 6. Tổng kết và Đánh giá Kết quả Tuần 3

#### 6.1. Kỹ năng Nhóm và Giao tiếp (Soft Skills)
* **Gặp gỡ Mentors:** Tương tác trực tiếp với các kỹ sư AWS tại văn phòng; tiếp thu cách giải quyết vấn đề thực tế của họ.
* **Hợp tác:** Bàn thảo thiết kế mạng và chia sẻ giải pháp cấu hình Route 53 Resolver với các nhóm khác.

#### 6.2. Quản trị Tài nguyên và Chi phí (FinOps)
* **Quản lý endpoints:** Nhận thức rõ chi phí của Endpoints (tính theo giờ chạy). Đã tắt các Resolver Endpoints ngay sau khi hoàn thành lab để tiết kiệm credit.

#### 6.3. Bảo mật và Quản trị Hệ thống (Security & Infrastructure)
* **Mạng lai:** Cấu hình thành công VPC Peering và thiết lập bảo mật nhiều lớp với Network ACLs và Security Groups.
* **Quản lý phân giải:** Triển khai cơ chế DNS phân giải chéo thành công.

#### 6.4. Năng lực Kỹ thuật và Tư duy AI (Technical & AI Mindset)
* **Tư duy Kiến trúc:** Hiểu sâu sắc cách kết nối các đám mây riêng lẻ để tạo thành một hệ thống thông tin đồng nhất của doanh nghiệp.

---
**Đánh giá chung:** Hoàn thành 100% mục tiêu tuần 3. Mạng liên kết hoạt động tốt, bảo mật chặt chẽ.
