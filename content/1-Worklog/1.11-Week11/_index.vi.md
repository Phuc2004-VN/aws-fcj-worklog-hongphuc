---
title: "Worklog Tuần 11"
date: 2026-07-05
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---



## FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Tổng quan Mục tiêu và Kế hoạch Tuần 11
Tuần này tập trung vào hoạt động tối ưu hóa hạ tầng, thực hiện kiểm thử liên thông hệ thống để xử lý các lỗi phát sinh (bug fixes) và chuẩn bị tổng kết cá nhân kết thúc kỳ thực tập:
* Kiểm thử toàn diện và sửa các lỗi (bug fix) phát sinh trong luồng xử lý dữ liệu.
* Tổng kết, hoàn thiện bộ tài liệu nhật ký công việc (Worklog) cá nhân trong suốt quá trình tham gia bootcamp.

## 2. Nhật ký Công việc Chi tiết (Worklog)
Dưới đây là bảng tổng hợp các hoạt động đã thực hiện từ ngày 29/06/2026 - 05/07/2026:

| Thứ / Ngày | Nội dung công việc | Chi tiết nhiệm vụ | Kết quả đạt được | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Thứ 2 (29/06) | Kiểm thử Ingestion | - Chạy thử nghiệm Lambda cào dữ liệu <br> - Xác minh dữ liệu được ghi đúng định dạng JSON vào S3 | Đảm bảo dữ liệu đầu vào được thu thập và lưu trữ an toàn trong S3. | AWS Lambda Console |
| Thứ 3 (30/06) | Kiểm thử tích hợp AI | - Gửi dữ liệu qua hàng đợi SQS để kích hoạt xử lý Bedrock AI <br> - Kiểm tra lỗi nghẽn hoặc mất mát tin nhắn | Phát hiện một số lỗi phân tích cú pháp ký tự đặc biệt và giới hạn API. | Amazon SQS / CloudWatch Logs |
| Thứ 5 (02/07) | Khắc phục lỗi (Bug Fix) | - Sửa mã nguồn Lambda để xử lý các biệt lệ (Exceptions) khi gọi AI Bedrock <br> - Định cấu hình cơ chế tự động thử lại (Retry logic) | Tránh việc luồng xử lý bị gián đoạn khi gặp lỗi kết nối tạm thời. | AWS Bedrock Guide |
| Thứ 6 (03/07) | Tối ưu hóa hiệu năng | - Điều chỉnh dung lượng bộ nhớ Lambda và cấu hình thời gian Visibility Timeout cho SQS | Giảm thời gian chờ của Lambda và ngăn ngừa việc xử lý trùng lặp. | AWS Lambda Guide |
| Chủ Nhật (05/07) | Tổng kết cá nhân | - Tổng hợp và hoàn thiện bộ tài liệu nhật ký công việc (Worklog) cá nhân từ Tuần 1 đến Tuần 11 | Hệ thống hóa toàn bộ quá trình học tập và hoàn thành bộ tài liệu Worklog. | Thư mục dự án |

## 3. Kết quả đạt được
Qua tuần thực hiện kiểm thử tối ưu hệ thống và tổng kết cá nhân, các kết quả và bài học sau đây đã được đúc kết:

* **Công tác kiểm thử và sửa lỗi hệ thống (Bug Fixing):**
  + Việc kiểm thử liên thông (End-to-End Testing) kết hợp giám sát qua CloudWatch Logs giúp nhanh chóng khoanh vùng các lỗi xử lý dữ liệu bất đồng bộ.
  + Đúc kết: Định cấu hình cơ chế tự động thử lại (Retry) trên SQS là phương án hiệu quả giúp xử lý các sự cố mạng tạm thời một cách mượt mà.

* **Hoàn thiện tài liệu tổng kết cá nhân:**
  + Tổng hợp lại toàn bộ quá trình tham gia chương trình bootcamp giúp đánh giá được tiến độ học tập và hệ thống hóa các kiến thức AWS đã tích lũy.
  + Đúc kết: Việc lưu trữ nhật ký kỹ thuật một cách khoa học giúp tiết kiệm thời gian đáng kể khi lập báo cáo tổng kết thực tập nộp cho nhà trường.
