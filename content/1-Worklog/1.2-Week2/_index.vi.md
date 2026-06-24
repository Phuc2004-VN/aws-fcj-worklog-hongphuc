---
title: "Worklog Tuần 2"
date: 2026-05-03
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Tổng quan Mục tiêu và Kế hoạch Tuần 02
Bắt đầu từ tuần thứ hai, học viên đi sâu vào tìm hiểu dịch vụ **Amazon Virtual Private Cloud (VPC)** và củng cố kỹ năng quản trị chi phí cùng **AWS Budgets**. Việc chuyển đổi từ môi trường Cloud mặc định sang môi trường mạng tùy chỉnh được kiểm soát chặt chẽ là điều kiện tiên quyết để đảm bảo tính an toàn dữ liệu và tối ưu hóa chi phí. Đồng thời, đây cũng là tuần hoàn thành thủ tục đăng ký thông tin thực tập chính thức và chuẩn bị tinh thần lên văn phòng làm việc.

> **So What:** Hiểu rõ cách phân chia dải mạng và kiểm soát lưu lượng giúp học viên nắm được xương sống của thiết kế hệ thống trên AWS. Việc cấu hình đúng VPC giúp ngăn chặn rủi ro lộ lọt thông tin ngay từ tầng mạng cơ sở.

---

## 2. Nhật ký Công việc Chi tiết (Worklog)
Dưới đây là bảng tổng hợp các hoạt động đã thực hiện từ ngày 24/04/2026 - 03/05/2026:

| Thứ / Ngày | Nội dung công việc | Chi tiết nhiệm vụ | Kết quả đạt được | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Thứ 6 (24/04) | Đăng ký thông tin | Điền link khảo sát thông tin thực tập và nhận hướng dẫn chuẩn bị lên văn phòng. | Hoàn tất thủ tục hành chính; sẵn sàng onboarding tại văn phòng. | Link đăng ký của AWS |
| Thứ 7 (25/04) | Nghiên cứu VPC cơ bản | Xem video hướng dẫn AWS; nghiên cứu lý thuyết IP Address, CIDR Block, Subnet. | Nắm được cách phân chia địa chỉ IP và dải mạng trong VPC. | Video từ Ban tổ chức |
| Chủ Nhật (26/04) | Thiết kế sơ đồ mạng | Vẽ nháp mô hình mạng gồm Public Subnet và Private Subnet. | Hình dung được luồng đi của traffic từ Internet vào mạng nội bộ. | AWS Documentation |
| Thứ 2 (27/04) | Quản lý ngân sách | Thực hành cấu hình cảnh báo ngân sách AWS Budgets nâng cao cho tài nguyên mạng. | Thiết lập cảnh báo ngưỡng chi phí để kiểm soát phí NAT Gateway và VPN. | AWS Billing Console |
| Thứ 3 (28/04) | Khởi tạo VPC | Tạo Custom VPC với CIDR `10.0.0.0/16` cùng Public và Private Subnets. | Cấu hình thành công phân vùng mạng riêng cô lập. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Thứ 4 (29/04) | Định tuyến mạng | Cấu hình Route Tables, Internet Gateway (IGW) và gắn vào Public Subnet. | Giúp các tài nguyên trong Public Subnet kết nối được ra ngoài Internet. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Thứ 5 (30/04) | Tìm hiểu bảo mật mạng | Nghiên cứu sự khác biệt giữa Security Groups (Stateful) và Network ACL (Stateless). | Nắm vững hai bức tường lửa bảo vệ EC2 và Subnet. | AWS Security Guide |
| Thứ 6 (01/05) | Ngày lễ Quốc tế Lao động | Tự học các best practices về thiết kế High Availability (HA) cho VPC. | Hiểu cách triển khai Subnet trên nhiều Availability Zones (AZs). | AWS Architecture Center |
| Thứ 7 (02/05) | Kiểm thử EC2 & VPC | Tạo EC2 trong Public Subnet; SSH thành công qua Internet; tạo EC2 trong Private Subnet. | Xác minh cấu hình định tuyến và bảo mật hoạt động chính xác. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Chủ Nhật (03/05) | Báo cáo tuần | Tổng hợp nhật ký công việc tuần 2 và chuẩn bị kế hoạch tuần tiếp theo. | Hoàn thiện tài liệu lưu trữ tiến độ thực tập. | Bản ghi cá nhân |

> **So What:** Công việc tuần này tập trung vào mạng và hành chính. Sự chuẩn bị này giúp tạo nền tảng vững chắc để thực thi các bài lab nâng cao về VPC Peering và Hybrid DNS ở tuần sau.

---

### 3. Phân tích Chuyên sâu: Cấu trúc VPC và Định tuyến Mạng
Amazon Virtual Private Cloud (VPC) cho phép Builder khởi dựng một mạng ảo riêng biệt trên đám mây.

**Cơ chế hoạt động của Public & Private Subnets:**
* **Public Subnet:** Có Route Table định tuyến traffic `0.0.0.0/0` đi qua **Internet Gateway (IGW)**. Thích hợp cho các tài nguyên cần giao tiếp trực tiếp với internet như Load Balancers hoặc Web Servers.
* **Private Subnet:** Route Table không có đường truyền trực tiếp ra Internet. Các tài nguyên (như Databases, Backend Services) được bảo vệ cô lập và chỉ có thể truy cập Internet gián tiếp qua **NAT Gateway** đặt tại Public Subnet.

![Sơ đồ VPC cơ bản](/images/1-Worklog/Week2/vpc-schema.png)

> **So What:** Việc phân chia rõ ràng giữa Public và Private Subnet giúp giảm thiểu diện tích tấn công (Attack Surface) từ bên ngoài, cô lập triệt để dữ liệu nhạy cảm khỏi internet.

---

### 4. Quản trị Chi phí (FinOps) với AWS Budgets
Khi làm việc với VPC, các dịch vụ như NAT Gateway có thể phát sinh chi phí theo giờ và theo dung lượng xử lý dữ liệu. Vì vậy, việc thiết lập AWS Budgets là cực kỳ quan trọng.

**Giải pháp giám sát chi phí:**
* **Cảnh báo ngưỡng:** Đặt cảnh báo ở mức 50%, 80% và 100% của ngân sách hàng tháng (ví dụ: $10).
* **Thông báo tức thời:** Gửi email cảnh báo ngay khi chi phí thực tế hoặc dự báo vượt ngưỡng, giúp Builder đưa ra quyết định tắt tài nguyên nhàn rỗi kịp thời.

> **So What:** Áp dụng FinOps giúp Builder không chỉ giỏi kỹ thuật mà còn có tư duy kinh doanh, quản lý tài chính hiệu quả trên Cloud.

---

### 5. AWS CLI cho VPC (Thực hành nâng cao)
Sử dụng dòng lệnh giúp tăng tốc quá trình vận hành hạ tầng mạng.

**Các câu lệnh CLI hữu ích:**
* Tạo VPC: `aws ec2 create-vpc --cidr-block 10.0.0.0/16`
* Liệt kê các Subnet: `aws ec2 describe-subnets --filters "Name=vpc-id,Values=vpc-xxxxx"`
* Kiểm tra Route Tables: `aws ec2 describe-route-tables`

> **Pro Tip:** Hãy viết script bash/powershell để tự động hóa việc tạo VPC nhằm giảm thiểu sai sót thủ công.

---

### 6. Tổng kết và Đánh giá Kết quả Tuần 2

#### 6.1. Kỹ năng Nhóm và Giao tiếp (Soft Skills)
* **Kết nối nhóm:** Tương tác thường xuyên qua WhatsApp và Zalo để hỗ trợ các thành viên giải quyết lỗi khi thiết lập VPC.
* **Hành chính:** Hoàn tất việc đăng ký thông tin thực tập đầy đủ và đúng hạn.

#### 6.2. Quản trị Tài nguyên và Chi phí (FinOps)
* **Quản lý ngân sách:** Tạo Budget cụ thể cho dịch vụ VPC và EC2, kiểm soát chi phí của NAT Gateway trong quá trình thực hành.

#### 6.3. Bảo mật và Quản trị Hệ thống (Security & Infrastructure)
* **Bảo mật mạng:** Nắm vững cách thiết lập Security Groups để chỉ cho phép các cổng cần thiết (Port 22 cho SSH, Port 80/443 cho HTTP/HTTPS).
* **Hạ tầng mạng:** Tự tay tạo Custom VPC đầu tiên và hiểu rõ cơ chế định tuyến.

#### 6.4. Năng lực Kỹ thuật và Tư duy AI (Technical & AI Mindset)
* **Tư duy mạng:** Chuyển đổi tư duy từ mạng cục bộ (On-premises network) sang mạng ảo hóa linh hoạt trên Cloud.

---
**Đánh giá chung:** Hoàn thành xuất sắc mục tiêu tuần 2. Cấu trúc mạng VPC hoạt động ổn định và sẵn sàng kết nối liên mạng.
