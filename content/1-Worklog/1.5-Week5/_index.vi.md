---
title: "Worklog Tuần 5"
date: 2026-05-24
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Tổng quan Mục tiêu và Kế hoạch Tuần 05
Tuần 5 tập trung vào công nghệ Container và giải pháp lưu trữ hỗn hợp (Hybrid Storage). Học viên đã nghiên cứu cách đóng gói ứng dụng với **Docker/Docker Compose** và chạy trên máy chủ EC2 kết nối cơ sở dữ liệu **Amazon RDS**; thiết lập kho chứa ảnh **Amazon Elastic Container Registry (ECR)** bảo mật; nghiên cứu giải pháp kết nối dữ liệu **AWS Storage Gateway** (File Storage Gateway File Shares) để đồng bộ tệp tin từ On-premise lên Amazon S3; và tham gia sự kiện lớn **FCAJ Community Day** vào ngày 23/05.

> **So What:** Việc làm chủ Docker kết hợp với AWS Storage Gateway giúp học viên liên kết các ứng dụng container hiện đại với các giải pháp lưu trữ dữ liệu truyền thống, tăng cường tính cơ động và khả năng đồng bộ dữ liệu lai.

---

## 2. Nhật ký Công việc Chi tiết (Worklog)
Dưới đây là bảng tổng hợp các hoạt động đã thực hiện từ ngày 18/05/2026 - 24/05/2026:

| Thứ / Ngày | Nội dung công việc | Chi tiết nhiệm vụ | Kết quả đạt được | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Thứ 2 (18/05) | Nghiên cứu Container | Học lý thuyết Docker; viết Dockerfile để đóng gói một ứng dụng web NodeJS/Python cơ bản. | Hiểu quy trình xây dựng Docker Image và cô lập môi trường chạy ứng dụng. | Docker Documentation |
| Thứ 3 (19/05) | Triển khai CSDL RDS | Khởi tạo Amazon RDS (PostgreSQL/MySQL); dùng Docker Compose chạy ứng dụng đa container trên EC2 kết nối đến RDS. | Hoàn thành mô hình ứng dụng Web + DB chuẩn chỉnh, tách biệt máy chủ web và máy chủ dữ liệu. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Thứ 4 (20/05) | Quản lý Container Registry | Tạo Repository trên Amazon ECR; cấu hình quyền IAM; thực hiện Push Docker Image từ EC2 lên ECR. | Lưu trữ Docker Image an toàn trên Cloud; dọn dẹp tài nguyên thử nghiệm để tránh tính phí. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Thứ 5 (21/05) | Nghiên cứu Hybrid Storage | Tìm hiểu AWS Storage Gateway; phân tích các loại File Gateway, Volume Gateway và Tape Gateway. | Nắm được kiến trúc đồng bộ dữ liệu giữa hệ thống tại doanh nghiệp và đám mây AWS. | AWS Storage Guide |
| Thứ 6 (22/05) | Thực hành Storage Gateway | Cấu hình File Share trên File Storage Gateway; mount ổ đĩa mạng NFS từ Client ảo hóa; đồng bộ tệp tin lên S3. | Tệp tin ghi vào ổ đĩa local được tự động đồng bộ hóa và lưu trữ an toàn trên S3 bucket. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Thứ 7 (23/05) | FCAJ Community Day | Tham gia ngày hội cộng đồng FCAJ; nghe chia sẻ từ các chuyên gia AWS; mở rộng mạng lưới kết nối. | Tiếp thu kiến thức thực tế về AI, Serverless và các bài học thành công từ doanh nghiệp. | Sự kiện trực tiếp |
| Chủ Nhật (24/05) | Tổng kết & Dọn dẹp | Tắt RDS DB, giải phóng Storage Gateway VM và ECR repository để tối ưu hóa ngân sách. | Hoàn tất dọn dẹp tài nguyên; hệ thống báo cáo tuần được cập nhật đầy đủ. | Cá nhân ghi chép |

> **So What:** Sự kết hợp giữa Docker ECR và Storage Gateway phản ánh xu hướng kiến trúc hiện đại: ứng dụng chạy dưới dạng container nhẹ và dữ liệu được đồng bộ hóa thông minh trên đám mây.

---

### 3. Đóng gói Ứng dụng với Docker & Lưu trữ trên Amazon ECR
Đóng gói (Containerization) là bước quan trọng để di chuyển ứng dụng lên Cloud mà không lo ngại về sự không tương thích môi trường.

**Quy trình triển khai:**
1. **Dockerfile:** Viết mã nguồn đặc tả môi trường (Base image, dependencies, ports, start command).
2. **Docker Compose:** Định nghĩa mối quan hệ giữa Web App và CSDL Amazon RDS để chạy cục bộ trên EC2 chỉ với 1 câu lệnh `docker-compose up -d`.
3. **Amazon ECR:** Đóng vai trò là kho chứa Docker Image bảo mật. Builder thực hiện đăng nhập (`aws ecr get-login-password`) và đẩy ảnh lên ECR để phục vụ triển khai tự động sau này.

> **So What:** Sử dụng Docker giúp tối giản hóa quy trình triển khai phần mềm (CI/CD) và bảo đảm tính đồng nhất giữa môi trường phát triển (Dev) và vận hành thực tế (Prod).

---

### 4. Đồng bộ Dữ liệu với AWS Storage Gateway
Đối với các doanh nghiệp chưa thể chuyển dịch hoàn toàn lên Cloud, **AWS Storage Gateway** cung cấp giải pháp cầu nối lưu trữ lai.

**File Storage Gateway:**
* Cung cấp giao thức chia sẻ file phổ biến như **NFS** hoặc **SMB** cho các máy chủ On-premises.
* Mỗi tệp tin được ghi vào thư mục chia sẻ sẽ được tự động chuyển đổi thành một object lưu trữ trên **Amazon S3**.
* Có cơ chế đệm cache cục bộ (local cache) để người dùng truy cập dữ liệu thường xuyên với độ trễ cực thấp.

![Mô hình File Storage Gateway](/images/1-Worklog/Week5/storage-gateway.png)

> **So What:** Storage Gateway giúp doanh nghiệp tận dụng dung lượng lưu trữ khổng lồ và chi phí rẻ của Amazon S3 mà không cần thay đổi mã nguồn các ứng dụng On-premises hiện có.

---

### 5. Bài học từ FCAJ Community Day 2026
Sự kiện diễn ra vào ngày 23/05 quy tụ đông đảo các kỹ sư, đối tác và sinh viên FCAJ.

**Các điểm chính đúc kết được:**
* **Generative AI trên AWS:** Cách áp dụng Amazon Bedrock để giải quyết các bài toán xử lý văn bản và tự động hóa quy trình nghiệp vụ thực tế.
* **Tư duy Serverless:** Chuyển dịch từ việc quản lý máy chủ sang việc viết code tối ưu hiệu suất, giúp giảm chi phí hạ tầng đến 70%.
* **Networking:** Gặp gỡ và học hỏi lộ trình học tập, làm việc của các cựu học viên và các kỹ sư giải pháp (Solutions Architects).

> **So What:** Kết nối cộng đồng giúp học viên cập nhật xu hướng công nghệ mới nhất và định hình rõ định hướng nghề nghiệp tương lai.

---

### 6. Tổng kết và Đánh giá Kết quả Tuần 5

#### 6.1. Kỹ năng Nhóm và Giao tiếp (Soft Skills)
* **Kết nối cộng đồng:** Tham gia tích cực tại FCAJ Community Day; giao lưu và học hỏi từ các đội nhóm khác.
* **Hợp tác:** Phối hợp nhóm tốt trong việc thiết kế sơ đồ triển khai container.

#### 6.2. Quản trị Tài nguyên và Chi phí (FinOps)
* **Tối ưu hóa tài nguyên:** Hiểu rõ cơ chế tính phí của Storage Gateway VM và lập tức xóa bỏ tài nguyên sau khi kết thúc bài thực hành.

#### 6.3. Bảo mật và Quản trị Hệ thống (Security & Infrastructure)
* **Bảo mật container:** Áp dụng IAM policies để phân quyền đẩy/kéo hình ảnh trên Amazon ECR.
* **Hạ tầng lai:** Triển khai thành công hệ thống đồng bộ tệp tin thông qua NFS File Share.

#### 6.4. Năng lực Kỹ thuật và Tư duy AI (Technical & AI Mindset)
* **Tư duy Container:** Thành thạo Docker Compose và quy trình đóng gói ứng dụng độc lập môi trường.

---
**Đánh giá chung:** Tuần 5 hoàn thành xuất sắc. Kỹ năng container hóa và lưu trữ hỗn hợp được củng cố vững chắc.
