---
title: "Worklog Tuần 7"
date: 2026-06-07
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Tổng quan Mục tiêu và Kế hoạch Tuần 07
Tuần 7 là giai đoạn chuyển tiếp quan trọng từ các bài thực hành kỹ thuật cơ bản sang giai đoạn thiết kế và chuẩn bị cho dự án lớn (Project). Các công việc trọng tâm gồm: tham gia Workshop chia sẻ kinh nghiệm từ diễn giả; nghiên cứu và triển khai dịch vụ **AWS WAF (Web Application Firewall)** để bảo vệ ứng dụng web khỏi các lỗi SQL Injection và XSS; tiến hành ôn tập tổng hợp toàn bộ các dịch vụ AWS đã học và khảo sát nhu cầu người dùng thực tế để chọn đề tài Project phù hợp.

> **So What:** Bảo vệ ứng dụng ở tầng ứng dụng (Lớp 7) với WAF giúp hệ thống đứng vững trước các cuộc tấn công mạng phổ biến, đồng thời việc kết nối thực tế giúp định hình đề tài Project có giá trị ứng dụng cao.

---

## 2. Nhật ký Công việc Chi tiết (Worklog)
Dưới đây là bảng tổng hợp các hoạt động đã thực hiện từ ngày 01/06/2026 - 07/06/2026:

| Thứ / Ngày | Nội dung công việc | Chi tiết nhiệm vụ | Kết quả đạt được | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Thứ 2 (01/06) | Tọa đàm Diễn giả | Tham gia sự kiện chia sẻ kinh nghiệm; nghe các câu chuyện thực tế về vận hành dự án và kỹ năng mềm. | Học hỏi tư duy giải quyết khủng hoảng và định hướng nghề nghiệp. | Diễn giả chương trình |
| Thứ 3 (02/06) | Nghiên cứu AWS WAF | Tìm hiểu cơ chế bảo vệ của Web Application Firewall; phân tích các cuộc tấn công SQL Injection và Cross-Site Scripting (XSS). | Hiểu cách WAF lọc lưu lượng HTTP/HTTPS ở Lớp 7 (Application Layer). | AWS Security Guide |
| Thứ 4 (03/06) | Cấu hình WAF | Tạo Web ACL; cấu hình AWS Managed Rules (Common Rule Set, SQL database set); liên kết WAF với CloudFront hoặc ALB. | Thiết lập hàng rào bảo mật chặn đứng các request độc hại trước khi tới server. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Thứ 5 (04/06) | Kiểm thử tấn công | Mô phỏng gửi SQLi query và XSS script lên Web application; kiểm tra log chặn trên WAF console. | WAF phát hiện và trả về mã lỗi 403 Forbidden chính xác đối với các request tấn công. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Thứ 6 (05/06) | Hệ thống hóa kiến thức | Ôn tập tổng thể các dịch vụ (VPC, EC2, IAM, Backup, Transit Gateway, Docker, Security Hub, Lambda). | Tổng hợp các mảnh ghép kiến trúc để chuẩn bị thiết kế hệ thống lớn. | Bản ghi cá nhân |
| Thứ 7 (06/06) | Khảo sát nhu cầu | Phỏng vấn một số người dùng/doanh nghiệp nhỏ về khó khăn trong quản lý dữ liệu và AI. | Xác định các bài toán thực tế cần giải quyết bằng công nghệ. | Khách hàng mục tiêu |
| Chủ Nhật (07/06) | Lựa chọn đề tài | Thảo luận nhóm; đánh giá tính khả thi và chốt định hướng đề tài Project. | Thống nhất chọn đề tài ứng dụng AI kết hợp AWS để xử lý dữ liệu thông minh. | Biên bản họp nhóm |

> **So What:** Việc nghiên cứu bảo mật Lớp 7 kết hợp khảo sát thực tế giúp học viên chuẩn bị cả về mặt kỹ thuật lẫn nghiệp vụ để bắt tay vào xây dựng giải pháp tối ưu nhất cho Project.

---

### 3. Phòng thủ Tầng Ứng dụng với AWS WAF (Web Application Firewall)
Khác với Security Groups và Network ACLs hoạt động ở tầng mạng (Lớp 3 & 4), **AWS WAF** hoạt động ở Lớp 7 (Application Layer) để bảo vệ ứng dụng khỏi các lỗi bảo mật phổ biến.

**Các tính năng quan trọng:**
* **AWS Managed Rules:** Bộ luật được viết sẵn bởi các chuyên gia AWS (như Core Rule Set, SQL database rule set) giúp bảo vệ hệ thống tức thời mà không cần cấu hình phức tạp.
* **Custom Rules:** Cho phép viết luật tùy chỉnh để chặn IP theo quốc gia (Geoblocking), giới hạn tần suất request (Rate limiting để chống DDoS), hoặc lọc chuỗi ký tự cụ thể trong HTTP Header/Body.
* **Tích hợp:** Liên kết trực tiếp với Amazon CloudFront, Application Load Balancer (ALB), hoặc Amazon API Gateway.

> **So What:** Triển khai AWS WAF giúp ngăn chặn các cuộc tấn công khai thác lỗ hổng mã nguồn ứng dụng web, giữ cho hệ thống luôn hoạt động an toàn và liên tục.

---

### 4. Tầm quan trọng của việc Khảo sát Người dùng trong Phát triển Dự án
Một hệ thống kỹ thuật dù hiện đại đến đâu cũng vô ích nếu không giải quyết được vấn đề thực tế của khách hàng.

**Quy trình xác định đề tài của nhóm:**
1. **Lắng nghe khách hàng:** Phỏng vấn người dùng để ghi nhận các điểm đau (Pain points - ví dụ: tốn thời gian xử lý dữ liệu thủ công, chi phí máy chủ AI cao).
2. **Khớp nối công nghệ:** Đối chiếu các khó khăn đó với các dịch vụ AWS đã học (Sử dụng Lambda để tự động hóa, S3 để lưu trữ rẻ, SageMaker để dự báo).
3. **Đánh giá tính khả thi:** Đảm bảo đề tài vừa giải quyết được vấn đề thực tế vừa nằm trong năng lực kỹ thuật và hạn mức ngân sách $200 credit.

> **So What:** Tư duy hướng khách hàng (Customer Obsession) giúp tạo ra các dự án thực tiễn, có giá trị thương mại thay vì chỉ là bài tập kỹ năng.

---

### 5. Review Hệ thống Dịch vụ AWS đã học
Để thiết kế một giải pháp tổng thể, Builder cần nắm rõ vai trò của từng thành phần:

| Nhóm | Dịch vụ chính | Vai trò trong dự án cuối khóa |
| --- | --- | --- |
| **Compute** | EC2, Lambda | Chạy server backend, chạy script xử lý serverless. |
| **Storage** | S3, Storage Gateway | Lưu trữ dữ liệu thô, đồng bộ dữ liệu từ văn phòng. |
| **Database** | RDS | Lưu trữ thông tin người dùng và dữ liệu có cấu trúc. |
| **Networking** | VPC, Transit Gateway | Thiết lập đường truyền nội bộ an toàn giữa các dịch vụ. |
| **Security** | IAM, Security Hub, WAF | Bảo vệ danh tính, kiểm tra cấu hình, chặn tấn công web. |

> **So What:** Việc ôn tập giúp kết nối các dịch vụ riêng lẻ thành một giải pháp kiến trúc hoàn chỉnh.

---

### 6. Tổng kết và Đánh giá Kết quả Tuần 7

#### 6.1. Kỹ năng Nhóm và Giao tiếp (Soft Skills)
* **Kỹ năng Lắng nghe:** Lắng nghe chia sẻ của các diễn giả để đúc kết bài học về sự thích ứng trong công việc.
* **Đồng thuận nhóm:** Thảo luận văn minh, tôn trọng ý kiến các thành viên để chốt đề tài.

#### 6.2. Quản trị Tài nguyên và Chi phí (FinOps)
* **Tiết kiệm chi phí:** Nhận biết được cấu hình WAF đi kèm chi phí cố định theo giờ chạy của Web ACL. Đã xóa Web ACL thử nghiệm ngay sau khi hoàn tất lab.

#### 6.3. Bảo mật và Quản trị Hệ thống (Security & Infrastructure)
* **Bảo vệ ứng dụng:** Cấu hình thành công AWS WAF chặn đứng SQL Injection và XSS, hoàn thiện bức tường bảo mật lớp ứng dụng.

#### 6.4. Năng lực Kỹ thuật và Tư duy AI (Technical & AI Mindset)
* **Tư duy Giải pháp:** Chuyển dịch từ việc làm theo các bài lab có sẵn sang tự thiết kế giải pháp giải quyết nhu cầu thực tế của người dùng.

---
**Đánh giá chung:** Tuần 7 hoàn thành xuất sắc. Đề tài Project đã được xác định và sẵn sàng cho bước thiết kế kiến trúc chi tiết.
