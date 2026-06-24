---
title: "Worklog Tuần 9"
date: 2026-06-21
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Tổng quan Mục tiêu và Kế hoạch Tuần 09
Tuần 9 tập trung vào việc hoàn thiện tài liệu mô tả chi tiết dự án tốt nghiệp, xây dựng sơ đồ luồng dữ liệu (Data Flow Diagram - DFD) và sơ đồ kiến trúc hệ thống tổng thể trên AWS; đồng thời nghiên cứu phương pháp tích hợp mô hình Học máy/Trí tuệ nhân tạo thông qua dịch vụ **AWS SageMaker** để đưa ra các dự báo hoặc phân tích thông minh vào ứng dụng thực tế.

> **So What:** Việc trực quan hóa luồng dữ liệu bằng DFD và tích hợp SageMaker giúp hiện thực hóa ý tưởng AI thành một giải pháp phần mềm hoàn chỉnh, giải quyết bài toán nghiệp vụ một cách thông minh và tối ưu.

---

## 2. Nhật ký Công việc Chi tiết (Worklog)
Dưới đây là bảng tổng hợp các hoạt động đã thực hiện từ ngày 15/06/2026 - 21/06/2026:

| Thứ / Ngày | Nội dung công việc | Chi tiết nhiệm vụ | Kết quả đạt được | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Thứ 2 (15/06) | Viết tài liệu dự án | Viết tài liệu mô tả chi tiết bài toán kinh doanh, quy trình thu thập dữ liệu và tiêu chí đầu ra. | Hoàn thành dự thảo tài liệu đặc tả dự án tốt nghiệp. | Đặc tả dự án |
| Thứ 3 (16/06) | Thiết kế sơ đồ DFD | Vẽ sơ đồ luồng dữ liệu (DFD) thể hiện quá trình dữ liệu đi từ nguồn vào hệ thống và đầu ra. | Trực quan hóa được các bước xử lý và lưu trữ dữ liệu của ứng dụng. | Draw.io Tool |
| Thứ 4 (17/06) | Hoàn thiện kiến trúc | Hoàn thiện sơ đồ kiến trúc tổng thể trên AWS kết nối các thành phần thu thập, xử lý và AI. | Có bản vẽ kiến trúc chi tiết sẵn sàng trình bày trước hội đồng. | Draw.io Tool |
| Thứ 5 (18/06) | Nghiên cứu SageMaker | Tìm hiểu các tính năng của AWS SageMaker (Studio, Notebooks, Training Jobs, Endpoints). | Hiểu quy trình xây dựng, huấn luyện và triển khai mô hình học máy. | AWS SageMaker Guide |
| Thứ 6 (19/06) | Thiết kế tích hợp AI | Phân tích cách tích hợp mô hình ML (nhập dữ liệu -> gọi SageMaker Endpoint -> trả dự báo). | Xây dựng được luồng tích hợp AI/ML vào kiến trúc ứng dụng web. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Thứ 7 (20/06) | Cấu hình bảo mật AI | Cấu hình thử nghiệm IAM policies cho SageMaker truy cập S3 bucket chứa dữ liệu huấn luyện. | Đảm bảo bảo mật dữ liệu đầu vào cho mô hình AI theo chuẩn Least Privilege. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Chủ Nhật (21/06) | Tổng kết giai đoạn | Kiểm tra lại toàn bộ sơ đồ và tài liệu; gửi báo cáo tuần 9 và chuẩn bị kế hoạch chạy thử. | Hoàn tất hồ sơ thiết kế dự án tốt nghiệp; sẵn sàng bước vào giai đoạn code. | Hồ sơ dự án |

> **So What:** Việc thiết kế luồng dữ liệu mạch lạc và cấu hình quyền truy cập an toàn cho SageMaker giúp tối ưu hóa hiệu suất xử lý dữ liệu và bảo mật tuyệt đối cho tài nguyên AI.

---

### 3. Thiết kế Luồng Dữ liệu (DFD) cho Hệ thống AI
Một hệ thống xử lý dữ liệu thông minh đòi hỏi sơ đồ luồng dữ liệu rõ ràng để xác định các điểm nghẽn (Bottlenecks) và bảo mật dữ liệu ở từng chặng.

**Các thành phần của luồng dữ liệu:**
1. **Data Ingestion (Thu thập):** Người dùng upload tệp tin qua Web Client trỏ trực tiếp đến **Amazon S3** thông qua Presigned URLs để giảm tải cho backend.
2. **Data Processing (Xử lý):** **AWS Lambda** được trigger để trích xuất văn bản và tiền xử lý dữ liệu thô.
3. **Model Inference (Dự đoán):** Gửi dữ liệu đã tiền xử lý đến **Amazon SageMaker Endpoint** để thực hiện dự đoán thông minh.
4. **Data Storage (Lưu trữ):** Lưu kết quả dự đoán vào **Amazon RDS PostgreSQL** để phục vụ hiển thị lên dashboard.

> **So What:** Thiết kế luồng dữ liệu tách biệt giữa thu thập và xử lý giúp hệ thống hoạt động cực kỳ linh hoạt và có khả năng chịu tải cao.

---

### 4. Vận hành Mô hình ML/AI với AWS SageMaker
**AWS SageMaker** cung cấp một nền tảng MLOps toàn diện để quản lý vòng đời của mô hình học máy.

**Các bước triển khai được nghiên cứu:**
* **SageMaker Notebooks:** Dành cho kỹ sư dữ liệu phân tích, làm sạch dữ liệu và huấn luyện mô hình thử nghiệm.
* **SageMaker Training Jobs:** Huấn luyện mô hình tự động trên các instance được tối ưu hóa cho học máy (ví dụ: dòng instance `ml.m5.large`).
* **SageMaker Endpoints:** Triển khai mô hình đã huấn luyện thành một HTTPS API Endpoint hoạt động 24/7 để nhận yêu cầu dự báo thời gian thực từ ứng dụng web.

> **So What:** Sử dụng SageMaker giúp chuẩn hóa quy trình triển khai AI từ môi trường nghiên cứu (Jupyter Notebook) lên môi trường vận hành thực tế (Production API) một cách nhanh chóng.

---

### 5. Thiết lập Tiêu chí Đánh giá Dự án (Technical Success Metrics)
Một dự án tốt cần có các chỉ số cụ thể để đo lường hiệu năng và độ chính xác của hệ thống:

* **Độ chính xác mô hình (Accuracy):** Đạt trên 85% đối với tập dữ liệu kiểm thử.
* **Thời gian phản hồi (Response Latency):** Dưới 2 giây cho mỗi request dự báo từ web.
* **Mức độ sẵn sàng (Availability):** Kiến trúc Multi-AZ đảm bảo độ sẵn sàng của hệ thống đạt 99.9%.

> **So What:** Thiết lập tiêu chí rõ ràng giúp đội ngũ phát triển kiểm thử chất lượng hệ thống một cách khách quan trước khi bàn giao dự án.

---

### 6. Tổng kết và Đánh giá Kết quả Tuần 9

#### 6.1. Kỹ năng Nhóm và Giao tiếp (Soft Skills)
* **Kỹ năng Thiết kế:** Trực quan hóa các khái niệm dữ liệu phức tạp thành sơ đồ luồng dữ liệu trực quan giúp các bên liên quan dễ dàng thảo luận.
* **Đồng lòng:** Hợp tác tốt để chuẩn bị đầy đủ hồ sơ thiết kế dự án.

#### 6.2. Quản trị Tài nguyên và Chi phí (FinOps)
* **Quản lý SageMaker:** Nhận thức rõ SageMaker Endpoints chạy 24/7 sẽ tiêu tốn lượng lớn credit. Do đó, chỉ khởi động Endpoint khi cần chạy thử và xóa ngay lập tức.

#### 6.3. Bảo mật và Quản trị Hệ thống (Security & Infrastructure)
* **Bảo mật dữ liệu AI:** Cấu hình đúng chính sách IAM Role cho phép SageMaker chỉ truy cập đúng bucket S3 chứa dữ liệu dự án.

#### 6.4. Năng lực Kỹ thuật và Tư duy AI (Technical & AI Mindset)
* **Tư duy MLOps:** Làm quen và hiểu sâu sắc quy trình vận hành và triển khai mô hình học máy trên Cloud.

---
**Đánh giá chung:** Hoàn thành xuất sắc mục tiêu tuần 9. Hồ sơ thiết kế dự án tốt nghiệp được nghiệm thu 100% và sẵn sàng cho giai đoạn phát triển mã nguồn.
