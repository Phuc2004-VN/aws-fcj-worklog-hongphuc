---
title: "Worklog Tuần 9"
date: 2026-06-21
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---



## FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Tổng quan Mục tiêu và Kế hoạch Tuần 09
Tuần này tập trung hoàn thành hồ sơ thiết kế dự án tốt nghiệp và nghiên cứu cách tích hợp mô hình AI/ML lên hạ tầng đám mây:
* Viết tài liệu đặc tả dự án tốt nghiệp (mô tả bài toán, quy trình xử lý và tiêu chí đầu ra).
* Thiết kế sơ đồ luồng dữ liệu (Data Flow Diagram - DFD) để trực quan hóa cách dữ liệu đi qua hệ thống.
* Tìm hiểu quy trình vận hành và triển khai mô hình học máy trên AWS sử dụng AWS SageMaker.
* Thiết lập chính sách bảo mật IAM cho phép các dịch vụ AI truy cập dữ liệu S3 an toàn.

## 2. Nhật ký Công việc Chi tiết (Worklog)
Dưới đây là bảng tổng hợp các hoạt động đã thực hiện từ ngày 15/06/2026 - 21/06/2026:

| Thứ / Ngày | Nội dung công việc | Chi tiết nhiệm vụ | Kết quả đạt được | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Thứ 2 (15/06) | Viết tài liệu dự án | - Biên soạn đặc tả: <br> &emsp; + Tài liệu mô tả chi tiết bài toán kinh doanh <br> &emsp; + Xác định quy trình thu thập dữ liệu và tiêu chí đầu ra | Hoàn thành dự thảo tài liệu đặc tả dự án tốt nghiệp. | Mô tả dự án |
| Thứ 3 (16/06) | Thiết kế sơ đồ DFD | - Thiết kế luồng dữ liệu: <br> &emsp; + Vẽ sơ đồ luồng dữ liệu (DFD) hệ thống AI <br> &emsp; + Mô tả dòng chảy thông tin qua các phân vùng | Trực quan hóa được các bước xử lý và lưu trữ dữ liệu của ứng dụng. | [Draw.io Tool](https://app.diagrams.net/) |
| Thứ 4 (17/06) | Hoàn thiện kiến trúc | - Hoàn thiện sơ đồ kiến trúc: <br> &emsp; + Hoàn thiện sơ đồ kiến trúc tổng thể trên AWS <br> &emsp; + Liên kết các dịch vụ S3, Lambda, EC2, RDS | Có bản vẽ kiến trúc chi tiết sẵn sàng trình bày trước hội đồng. | [Draw.io Tool](https://app.diagrams.net/) |
| Thứ 5 (18/06) | Nghiên cứu SageMaker | - Nghiên cứu SageMaker MLOps: <br> &emsp; + Tìm hiểu AWS SageMaker Studio và Notebooks <br> &emsp; + Phân tích quy trình tạo Training Jobs và deploy Endpoints | Hiểu quy trình xây dựng, huấn luyện và triển khai mô hình học máy. | [AWS SageMaker Guide](https://docs.aws.amazon.com/sagemaker/) |
| Thứ 6 (19/06) | Thiết kế tích hợp AI | - Thiết kế tích hợp AI: <br> &emsp; + Phân tích cơ chế tích hợp mô hình ML <br> &emsp; + Kết nối backend với SageMaker Endpoint | Xây dựng được luồng tích hợp AI/ML vào kiến trúc ứng dụng web. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Thứ 7 (20/06) | Cấu hình bảo mật AI | - Cấu hình bảo mật AI: <br> &emsp; + Thiết lập IAM execution policies cho SageMaker <br> &emsp; + Phân quyền truy cập S3 chứa dữ liệu huấn luyện | Đảm bảo bảo mật dữ liệu đầu vào cho mô hình AI theo chuẩn Least Privilege. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Chủ Nhật (21/06) | Tổng kết giai đoạn | - Đóng gói hồ sơ: <br> &emsp; + Kiểm tra lại toàn bộ sơ đồ và tài liệu dự án <br> &emsp; + Nộp báo cáo và chuẩn bị chạy thử | Hoàn tất hồ sơ thiết kế dự án tốt nghiệp; sẵn sàng bước vào giai đoạn code. | Hồ sơ dự án |

## 3. Kết quả đạt được
Qua tuần thực hành hoàn thiện hồ sơ thiết kế và nghiên cứu tích hợp mô hình học máy (MLOps), các bài học kinh nghiệm sau đây đã được đúc kết:

* **Thiết kế sơ đồ luồng dữ liệu (Data Flow Diagram - DFD) và luồng xử lý:**
  + Vẽ phát thảo sơ đồ DFD thể hiện đường đi của thông tin: Client upload file lên S3 thông qua Presigned URL -> Trigger Lambda để trích xuất văn bản -> Gửi dữ liệu sạch tới SageMaker Endpoint để AI phân tích -> Lưu kết quả vào RDS PostgreSQL và hiển thị lên web.
  + Đúc kết: Việc sử dụng S3 Presigned URL là Best Practice tối ưu giúp Client upload trực tiếp tệp tin lên S3, giảm tải hoàn toàn cho máy chủ Backend khi xử lý nhiều file lớn.

* **Nghiên cứu quy trình MLOps trên AWS SageMaker:**
  + Tự hiểu cách dùng SageMaker Notebooks để thử nghiệm mô hình, chạy Training Jobs và đóng gói mô hình thành một HTTPS Endpoint hoạt động 24/7 (Real-time Inference) để Backend gọi API lấy dự báo.
  + Đúc kết: Đóng gói mô hình thành API chuẩn hóa giúp Backend dễ dàng tích hợp trí tuệ nhân tạo mà không cần tự cài đặt các môi trường máy chủ chạy mô hình phức tạp.

* **Bảo mật và IAM Policy cho dịch vụ AI:**
  + Cấu hình IAM Role chuyên biệt (SageMaker Execution Role) giới hạn quyền truy cập chỉ trong phạm vi S3 bucket của dự án theo đúng nguyên tắc Least Privilege (Đặc quyền tối thiểu).
  + Đúc kết: Phân quyền IAM Role chính xác bảo vệ dữ liệu huấn luyện và model artifacts nhạy cảm của dự án tốt nghiệp khỏi rò rỉ an ninh.

* **Xác định các chỉ số kỹ thuật và FinOps:**
  + Thống nhất các chỉ số thành công kỹ thuật: Độ chính xác mô hình > 85%, thời gian phản hồi API < 2 giây và hệ thống đạt độ sẵn sàng cao (Multi-AZ).
  + Đúc kết: SageMaker Endpoints tính phí chạy liên tục rất đắt. Để bảo toàn credit, Endpoint thử nghiệm đã được xóa ngay sau khi kiểm tra xong kết nối.
