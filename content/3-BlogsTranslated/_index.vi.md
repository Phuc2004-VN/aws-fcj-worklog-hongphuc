---
title: "Các bài blogs đã đăng"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

Trong lúc tham gia chương trình học tập và thực hành điện toán đám mây, ba bài viết đã được biên soạn và chia sẻ với cộng đồng. Đây là những đúc kết thực tế từ quá trình cấu hình hạ tầng, khắc phục lỗi hệ thống và nghiên cứu các mô hình triển khai ứng dụng trên AWS:

### [Blog 1 - Deploy Backend lên AWS EC2 và lỗi chỉ vì chữ hoa](3.1-Blog1/)
Bài viết phân tích sự khác biệt về cách phân biệt chữ hoa/chữ thường trong tệp cấu hình `.env` khi chạy ứng dụng trên môi trường local Windows so với môi trường Ubuntu Linux trên AWS EC2. Lỗi này dẫn đến việc các biến Boolean cấu hình bị hiểu sai, gây ra các lỗi logic âm thầm mà không báo lỗi runtime trực tiếp, từ đó đúc kết ra bài học kinh nghiệm về tính đồng nhất cấu hình môi trường.

### [Blog 2 - AWS Cost & AI: Khi chạy cloud không còn chỉ là vấn đề kỹ thuật](3.2-Blog2/)
Chia sẻ về kinh nghiệm thực tế của bản thân trong tối ưu hóa chi phí vận hành (FinOps) khi tích hợp các dịch vụ AI/ML (Amazon Bedrock, SageMaker, Comprehend) trên AWS. Nội dung nhấn mạnh tầm quan trọng của việc quản lý ngân sách sớm thông qua AWS Budgets và thói quen tắt các tài nguyên thử nghiệm sau khi hoàn thành lab để tránh hóa đơn tăng vọt ngoài ý muốn.

### [Blog 3 - Triển khai ứng dụng Serverless với AWS Lambda và Amazon API Gateway](3.3-Blog3/)
Bài viết hướng dẫn quy trình chuyển đổi từ kiến trúc máy chủ truyền thống (EC2) sang kiến trúc không máy chủ (Serverless) bằng cách sử dụng kết hợp AWS Lambda và Amazon API Gateway. Nội dung phân tích các lợi ích về việc giảm thiểu gánh nặng vận hành hệ thống, khả năng tự động mở rộng theo nhu cầu thực tế và cơ chế tính phí Pay-as-you-go tối ưu chi phí.
