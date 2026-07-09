---
title: "Worklog Tuần 6"
date: 2026-05-31
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Mục tiêu tuần
Tuần này tập trung nâng cao khả năng bảo mật tự động hóa và tối ưu chi phí vận hành máy chủ EC2:
* Tìm hiểu và kích hoạt AWS Security Hub để quét lỗ hổng bảo mật và đánh giá độ tuân thủ tài khoản theo tiêu chuẩn CIS, PCI DSS.
* Nghiên cứu các phương án tối ưu chi phí EC2 (như tag tài nguyên và gán IAM Role cho EC2).
* Lập trình một hàm AWS Lambda bằng Python (Boto3) kết hợp với Amazon EventBridge để lên lịch tự động bật/tắt các máy ảo EC2 thử nghiệm ngoài giờ làm việc.

## 2. Các công việc cần triển khai trong tuần
Dưới đây là bảng tổng hợp các hoạt động đã thực hiện từ ngày 25/05/2026 - 31/05/2026:

| Thứ / Ngày | Nội dung công việc | Chi tiết nhiệm vụ | Kết quả đạt được | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Thứ 2 (25/05) | Nghiên cứu Security Hub | - Lý thuyết Security Hub: <br> &emsp; + Tìm hiểu AWS Security Hub <br> &emsp; + Tìm hiểu tiêu chuẩn CIS AWS Foundations và PCI DSS | Hiểu nguyên lý đánh giá bảo mật tự động hóa và chấm điểm tuân thủ. | [AWS Security Hub Guide](https://000018.awsstudygroup.com/) |
| Thứ 3 (26/05) | Đánh giá bảo mật | - Đánh giá bảo mật: <br> &emsp; + Kích hoạt Security Hub trên console <br> &emsp; + Phân tích các phát hiện (findings) bảo mật tài khoản | Xác định các lỗ hổng cấu hình và lập danh sách ưu tiên khắc phục lỗi. | [AWS Study Group](https://000018.awsstudygroup.com/) |
| Thứ 4 (27/05) | Tối ưu hóa EC2 | - Nghiên cứu tối ưu: <br> &emsp; + Tìm hiểu chiến lược tối ưu chi phí EC2 (Right-sizing, Reserved Instances, Savings Plans) | Hiểu cách chọn đúng cấu hình máy chủ dựa trên tải thực tế. | [AWS Cost Optimization](https://000022.awsstudygroup.com/vi/) |
| Thứ 5 (28/05) | Cấu hình Tag & Role | - Thực hành quản lý: <br> &emsp; + Đặt thẻ Tag phân loại tài nguyên (Env: Dev, Project: FCAJ) <br> &emsp; + Cấu hình IAM Role gắn vào EC2 thay vị dùng access key | Quản trị tài nguyên khoa học; bảo mật thông tin xác thực cho máy chủ. | [Tag & Role](https://000022.awsstudygroup.com/vi/) |
| Thứ 6 (29/05) | Thiết kế Lambda Scheduler | - Thiết kế Serverless Scheduler: <br> &emsp; + Viết code Lambda Python lọc EC2 theo Tag <br> &emsp; + Thiết lập logic gọi start/stop instances | Lập trình logic điều khiển máy chủ tự động bằng code Serverless. | [AWS Lambda Developer Guide](https://000022.awsstudygroup) |
| Thứ 7 (30/05) | Kiểm thử lập lịch | - Thực hành lập lịch: <br> &emsp; + Cấu hình EventBridge Cron Rule <br> &emsp; + Triển khai Lambda và kiểm tra CloudWatch logs | Máy chủ tự động bật vào 8:00 AM và tắt vào 6:00 PM đúng lịch trình chạy thử. | [AWS Study Group](https://000022.awsstudygroup) |
| Chủ Nhật (31/05) | Báo cáo & Dọn dẹp | - Báo cáo & FinOps: <br> &emsp; + Phân tích log CloudWatch <br> &emsp; + Dọn dẹp EventBridge rule thử nghiệm và tắt EC2 | Hoàn thành báo cáo tuần; tài khoản AWS được tối ưu ngân sách tốt. | Cá nhân ghi chép |

## 3. Kết quả đạt được
Qua tuần thực hành về bảo mật tự động và lập lịch tài nguyên, các bài học kinh nghiệm sau đây đã được đúc kết:

* **Đánh giá và nâng cao bảo mật chủ động (AWS Security Hub):**
  + Security Hub đã được kích hoạt và đối chiếu cấu hình tài khoản với tiêu chuẩn CIS AWS Foundations Benchmark. Hệ thống đã tự động cảnh báo các lỗ hổng (như mở SSH port 22 cho toàn bộ IP hoặc thiếu MFA cho Root).
  + Đúc kết: Chuyển dịch giám sát bảo mật từ thủ công sang tự động giúp phát hiện lỗi cấu hình sớm. Bảng điểm Security Score giúp lập kế hoạch khắc phục các lỗ hổng theo độ ưu tiên hợp lý.

* **Bảo mật và quản lý tài nguyên (Tagging & IAM Role cho EC2):**
  + Áp dụng Tagging nhất quán (`Environment: Dev`, `Project: FCAJ`) để lọc tài nguyên và gán IAM Role trực tiếp cho EC2 thay vì nhúng cứng Access/Secret Key trong code.
  + Đúc kết: Việc quản lý tài nguyên khoa học giúp bảo vệ thông tin xác thực và dễ dàng lập trình tự động hóa các tác vụ quản trị.

* **Tự động hóa vận hành và tối ưu chi phí máy chủ (Lambda & EventBridge):**
  + Script Python (Boto3) chạy trên AWS Lambda đã được phát triển và kích hoạt bằng EventBridge Cron Rule để tự động bật EC2 lúc 8:00 AM và tắt lúc 6:00 PM hàng ngày. Theo dõi và sửa lỗi chạy thông qua CloudWatch Logs.
  + Đúc kết: Giải pháp lập lịch tự động giúp tắt máy ảo Dev ngoài giờ hành chính, giúp tiết kiệm tới 60% chi phí chạy máy chủ dư thừa. Đây là ví dụ thực tế tuyệt vời của Operations as Code và Serverless.
