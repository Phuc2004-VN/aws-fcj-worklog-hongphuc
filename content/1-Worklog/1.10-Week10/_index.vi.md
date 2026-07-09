---
title: "Worklog Tuần 10"
date: 2026-06-28
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Tổng quan Mục tiêu và Kế hoạch Tuần 10
Tuần này tập trung nghiên cứu kiến trúc Serverless, phác thảo giao diện Dashboard, thiết lập luồng API và xây dựng Demo hoàn thiện luồng Ingestion và AI xử lý dữ liệu:
* Nghiên cứu kiến trúc Serverless (AWS Lambda, Amazon API Gateway) và viết bài chia sẻ kinh nghiệm kỹ thuật lên cộng đồng AWS Study Group VN.
* Thiết kế và phác thảo giao diện Dashboard, cấu hình các API endpoint và xác định các dịch vụ AWS cần thiết cho đề tài tốt nghiệp.
* Triển khai viết mã nguồn cho Lambda hàm Ingestion kết hợp Amazon EventBridge để tự động cào dữ liệu lưu vào Amazon S3.
* Tích hợp dịch vụ AWS Bedrock để xử lý ngôn ngữ/AI, kết hợp cơ chế xếp hàng bất đồng bộ với Amazon SQS nhằm ngăn ngừa mất mát dữ liệu và kiểm thử thành công luồng Demo.



## 2. Nhật ký Công việc Chi tiết (Worklog)
Dưới đây là bảng tổng hợp các hoạt động đã thực hiện từ ngày 22/06/2026 - 28/06/2026:

| Thứ / Ngày | Nội dung công việc | Chi tiết nhiệm vụ | Kết quả đạt được | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Thứ 2 (22/06) | Nghiên cứu Serverless | - Nghiên cứu Serverless architecture: <br> &emsp; + Tìm hiểu cách hoạt động của AWS Lambda và Amazon API Gateway <br> &emsp; + Phân tích lợi ích về chi phí và khả năng mở rộng | Hiểu rõ mô hình Serverless và cách tối ưu hóa tài nguyên đám mây. | [AWS documentation](https://aws.amazon.com/vi/lambda/serverless-architectures-learn-more/) |
| Thứ 3 (23/06) | Viết bài chia sẻ kỹ thuật | - Hoàn thiện bài viết chia sẻ: <br> &emsp; + Tổng hợp kiến thức và kinh nghiệm thực tế về Serverless <br> &emsp; + Đăng tải bài viết lên cộng đồng AWS Study Group VN | Chia sẻ kiến thức bổ ích tới cộng đồng và nhận phản hồi từ các thành viên. | [AWS Study Group VN](https://www.facebook.com/groups/awsstudygroupfcj) |
| Thứ 4 (24/06) | Thiết kế Dashboard | - Phác thảo giao diện Dashboard: <br> &emsp; + Vẽ Wireframe hiển thị dữ liệu và kết quả AI phân tích <br> &emsp; + Xác định cấu trúc các trang chính | Có bản thiết kế giao diện thô làm tiền đề phát triển Frontend. | Figma / Draw.io |
| Thứ 5 (25/06) | Xác định kiến trúc & API | - Cấu hình API & AWS Services: <br> &emsp; + Định nghĩa các Endpoint API kết nối Frontend và Backend <br> &emsp; + Thống nhất kiến trúc dịch vụ AWS áp dụng cho đề tài | Hoàn thiện thiết kế hệ thống API và kiến trúc hạ tầng AWS tối ưu. | Tài liệu dự án |
| Thứ 6 (26/06) | Code Ingestion Lambda | - Tìm hiểu trước lập trình hàm Ingestion Lambda: <br> &emsp; + Viết code Lambda cào dữ liệu từ nguồn ngoài <br> &emsp; + Thiết lập Amazon EventBridge trigger định kỳ | Lambda function cào dữ liệu hoạt động tự động và lưu trữ vào S3. | [AWS Lambda Guide](https://aws.amazon.com/vi/lambda/getting-started/) |
| Thứ 7 (27/06) | Tích hợp AI Bedrock & SQS | - Triển khai luồng bất đồng bộ: <br> &emsp; + Tích hợp AWS Bedrock để xử lý dữ liệu bằng AI <br> &emsp; + Cấu hình hàng đợi Amazon SQS để xử lý tin nhắn bất đồng bộ | Tránh nghẽn hệ thống và đảm bảo không mất mát dữ liệu khi tải cao. | [AWS Bedrock Guide](https://docs.aws.amazon.com/bedrock/) |
| Chủ Nhật (28/06) | Kiểm thử Demo & Tổng kết | - Thực hiện End-to-End Test: <br> &emsp; + Chạy thử nghiệm toàn bộ luồng Demo từ cào dữ liệu, xếp hàng SQS đến gọi Bedrock AI <br> &emsp; + Báo cáo kết quả tuần 10 | Luồng Demo hoạt động trơn tru; sẵn sàng cho giai đoạn kiểm thử diện rộng ở tuần 11. | Test local |

## 3. Kết quả đạt được
Qua tuần thực hành thiết kế giao diện Dashboard, cấu hình API và triển khai luồng Demo Serverless tích hợp AI, các kết quả và bài học kinh nghiệm sau đây đã được đúc kết:

* **Ứng dụng mô hình Serverless và viết bài chia sẻ:**
  + Nắm vững kiến thức cốt lõi về AWS Lambda (FaaS) và API Gateway. Hiểu cách API Gateway chuyển hướng request tới Lambda và cách cấu hình CORS, Authorization.
  + Đúc kết: Việc chia sẻ kiến thức lên AWS Study Group VN giúp hệ thống hóa lại lý thuyết một cách sâu sắc hơn thông qua đóng góp và bình luận của cộng đồng.

* **Thiết kế API và giao diện Dashboard:**
  + Xác định được đầy đủ các API Endpoints cần thiết cho hệ thống (CRUD dữ liệu, API trigger AI, API lấy thống kê Dashboard) và phác thảo giao diện thân thiện với người dùng.
  + Đúc kết: Thiết kế API rõ ràng ngay từ đầu giúp việc chia nhỏ công việc lập trình Frontend và Backend song song diễn ra cực kỳ hiệu quả và tránh xung đột dữ liệu.

* **Triển khai luồng Ingestion tự động qua EventBridge & S3:**
  + Lập trình thành công Lambda cào dữ liệu tự động theo lịch (Cron job) được trigger bởi EventBridge Rule, ghi trực tiếp các file JSON thô vào S3 bucket.
  + Đúc kết: EventBridge là giải pháp serverless hoàn hảo thay thế cho các cronjob chạy bằng OS truyền thống trên EC2, loại bỏ chi phí vận hành hạ tầng 24/7.

* **Tích hợp AWS Bedrock & kiến trúc bất đồng bộ với Amazon SQS:**
  + Tích hợp AWS Bedrock (sử dụng mô hình ngôn ngữ lớn như Claude) để phân tích dữ liệu cào về. Sử dụng hàng đợi SQS để điều phối và xử lý bất đồng bộ giữa bước Ingestion và bước AI phân tích.
  + Đúc kết: SQS đóng vai trò là bộ đệm (buffer) rất quan trọng giúp hệ thống có khả năng chịu tải tốt (fault-tolerant). Ngay cả khi Bedrock vượt quá hạn mức request (Rate Limit), các tác vụ vẫn nằm an toàn trong hàng đợi để được xử lý lại (retry) mà không bị mất dữ liệu.
