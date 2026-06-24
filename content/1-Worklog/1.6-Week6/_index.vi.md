---
title: "Worklog Tuần 6"
date: 2026-05-31
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Tổng quan Mục tiêu và Kế hoạch Tuần 06
Tuần 6 tập trung vào quản trị bảo mật tự động hóa và tối ưu hóa chi phí vận hành máy chủ EC2. Học viên được nghiên cứu cách dùng **AWS Security Hub** để đánh giá mức độ tuân thủ bảo mật theo tiêu chuẩn CIS, PCI DSS và Foundational Security; tìm hiểu chiến lược tối ưu chi phí EC2 qua tagging và IAM Roles; xây dựng **AWS Lambda** kết hợp **Amazon EventBridge** để lên lịch trình tự động bật/tắt EC2 nhằm tránh lãng phí.

> **So What:** Kết hợp bảo mật tự động hóa và lập lịch tài nguyên thông minh giúp doanh nghiệp giảm hóa đơn EC2 lên tới 60% khi không làm việc, đồng thời liên tục nâng cao điểm số bảo mật hệ thống.

---

## 2. Nhật ký Công việc Chi tiết (Worklog)
Dưới đây là bảng tổng hợp các hoạt động đã thực hiện từ ngày 25/05/2026 - 31/05/2026:

| Thứ / Ngày | Nội dung công việc | Chi tiết nhiệm vụ | Kết quả đạt được | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Thứ 2 (25/05) | Nghiên cứu Security Hub | Tìm hiểu AWS Security Hub; tìm hiểu các tiêu chuẩn CIS AWS Foundations và PCI DSS. | Hiểu nguyên lý đánh giá bảo mật tự động hóa và chấm điểm tuân thủ. | AWS Security Hub Guide |
| Thứ 3 (26/05) | Đánh giá bảo mật | Kích hoạt Security Hub trên console; phân tích các phát hiện (findings) bảo mật tài khoản. | Xác định các lỗ hổng cấu hình và lập danh sách ưu tiên khắc phục lỗi. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Thứ 4 (27/05) | Tối ưu hóa EC2 | Nghiên cứu các phương pháp tối ưu chi phí EC2 (Right-sizing, Reserved Instances, Savings Plans). | Hiểu cách chọn đúng cấu hình máy chủ dựa trên tải thực tế. | AWS Cost Optimization |
| Thứ 5 (28/05) | Cấu hình Tag & Role | Đặt thẻ Tag phân loại tài nguyên (Env: Dev, Project: FCAJ); cấu hình IAM Role gắn vào EC2 thay vị dùng access key. | Quản trị tài nguyên khoa học; bảo mật thông tin xác thực cho máy chủ. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Thứ 6 (29/05) | Thiết kế Lambda Scheduler | Viết mã nguồn Python (dùng thư viện Boto3) để lọc EC2 theo Tag và gọi lệnh Start/Stop. | Lập trình logic điều khiển máy chủ tự động bằng code Serverless. | AWS Lambda Developer Guide |
| Thứ 7 (30/05) | Kiểm thử lập lịch | Cấu hình EventBridge Cron Rule; triển khai Lambda; kiểm tra logs trên CloudWatch. | Máy chủ tự động bật vào 8:00 AM và tắt vào 6:00 PM đúng lịch trình chạy thử. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Chủ Nhật (31/05) | Báo cáo & Dọn dẹp | Kiểm tra lại log CloudWatch; dọn dẹp các rule EventBridge thử nghiệm và tắt EC2. | Hoàn thành báo cáo tuần; tài khoản AWS được tối ưu ngân sách tốt. | Cá nhân ghi chép |

> **So What:** Việc triển khai Lambda để tự động hóa bật/tắt EC2 thể hiện tư duy kiến trúc Serverless: dùng code để giải quyết bài toán vận hành (Operations as Code).

---

### 3. Đảm bảo An ninh Tài khoản với AWS Security Hub
**AWS Security Hub** cung cấp cái nhìn toàn diện về tình trạng bảo mật của toàn bộ tài nguyên AWS.

**Các tính năng cốt lõi:**
* **Chấm điểm tuân thủ:** Chấm điểm dựa trên các tiêu chuẩn bảo mật chuẩn doanh nghiệp (ví dụ: CIS Benchmark).
* **Tự động thu thập:** Liên kết dữ liệu từ các dịch vụ bảo mật khác như Amazon GuardDuty, Inspector và Macie.
* **Phát hiện lỗi cấu hình:** Ví dụ, cảnh báo nếu Root Account chưa bật MFA, hoặc Security Group mở cổng 22 cho toàn thế giới (`0.0.0.0/0`).

> **So What:** Sử dụng Security Hub giúp Builder chuyển từ cơ chế bảo mật thụ động (chờ xảy ra sự cố) sang bảo mật chủ động (liên tục quét và khắc phục).

---

### 4. Lập lịch tự động bật/tắt EC2 bằng AWS Lambda & EventBridge
Việc duy trì các máy chủ EC2 môi trường phát triển (Development/Testing) hoạt động 24/7 khi không có người sử dụng là một sự lãng phí tài chính lớn.

**Kiến trúc giải pháp tự động hóa:**
1. **Amazon EventBridge (CloudWatch Events):** Đóng vai trò là bộ kích hoạt (Trigger) theo thời gian. Ví dụ: chạy rule vào 18:00 mỗi ngày từ Thứ Hai đến Thứ Sáu.
2. **AWS Lambda (Python/Boto3):** Hàm Serverless thực thi tác vụ. Hàm sẽ truy vấn các instance có tag `Auto-Stop: True`, kiểm tra trạng thái và thực hiện cuộc gọi API `stop_instances()`.
3. **IAM Role:** Cấp quyền đặc quyền tối thiểu cho Lambda để thực thi các hành động `ec2:DescribeInstances`, `ec2:StartInstances`, và `ec2:StopInstances`.

![Kiến trúc Lập lịch EC2](/images/1-Worklog/Week6/lambda-scheduler.png)

> **So What:** Tự động hóa lịch trình hoạt động của hạ tầng (Infrastructure Scheduler) giúp doanh nghiệp tối ưu hóa tối đa chi phí hoạt động thực tế trên đám mây.

---

### 5. Chiến lược Tagging để Quản lý Tài nguyên
Tagging không chỉ giúp quản trị hệ thống mà còn là cơ sở để phân tách hóa đơn chi phí (Cost Allocation Tags).

**Best Practices về Tagging:**
* Phân loại môi trường: `Environment` (Dev, Staging, Prod).
* Phân loại dự án: `Project` (FCAJ-AI).
* Phân loại chủ sở hữu: `Owner` (HongPhuc).

> **So What:** Gán tag nhất quán giúp tự động hóa việc áp dụng chính sách bảo mật, dọn dẹp tài nguyên và kiểm toán tài chính dễ dàng.

---

### 6. Tổng kết và Đánh giá Kết quả Tuần 6

#### 6.1. Kỹ năng Nhóm và Giao tiếp (Soft Skills)
* **Kỷ luật kỹ thuật:** Duy trì thói quen viết code sạch và có giải thích chi tiết trong hàm Lambda.
* **Hỗ trợ đồng đội:** Giúp các thành viên trong nhóm debug lỗi phân quyền IAM Role cho Lambda.

#### 6.2. Quản trị Tài nguyên và Chi phí (FinOps)
* **Tiết kiệm thông minh:** Ứng dụng thành công Lambda Scheduler để tự động tắt máy chủ thử nghiệm ngoài giờ làm việc.

#### 6.3. Bảo mật và Quản trị Hệ thống (Security & Infrastructure)
* **Kiểm soát tuân thủ:** Kích hoạt Security Hub và hiểu rõ các tiêu chí cấu hình bảo mật chuẩn quốc tế.
* **Cấp quyền an toàn:** Sử dụng IAM Role để quản lý quyền hạn của EC2 và Lambda.

#### 6.4. Năng lực Kỹ thuật và Tư duy AI (Technical & AI Mindset)
* **Tư duy Serverless:** Thành thạo sử dụng Boto3 Python để tương tác trực tiếp với API AWS.

---
**Đánh giá chung:** Hoàn thành tốt mục tiêu tuần 6. Tư duy về bảo mật chủ động và tối ưu hóa chi phí tự động hóa được nâng lên tầm cao mới.
