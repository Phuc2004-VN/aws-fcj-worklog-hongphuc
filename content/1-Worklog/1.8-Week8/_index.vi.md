---
title: "Worklog Tuần 8"
date: 2026-06-14
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Tổng quan Mục tiêu và Kế hoạch Tuần 08
Tuần 8 là tuần bắt tay vào thiết kế kiến trúc chi tiết cho dự án tốt nghiệp (Project). Các công việc trọng tâm bao gồm: học cách sử dụng công cụ **Draw.io** kết hợp thư viện biểu tượng AWS chuẩn hóa để vẽ sơ đồ hạ tầng phân cấp; thảo luận chi tiết để làm rõ bài toán kinh doanh và yêu cầu chức năng; phân tích đối tượng người dùng, thiết lập bài toán kỹ thuật cốt lõi; và lên kế hoạch phát triển cụ thể, phân chia công việc giữa các thành viên.

> **So What:** Một sơ đồ kiến trúc hạ tầng trực quan và kế hoạch phân công rõ ràng là tấm bản đồ dẫn đường giúp toàn đội phối hợp nhịp nhàng, giảm thiểu xung đột cấu hình khi triển khai thực tế.

---

## 2. Nhật ký Công việc Chi tiết (Worklog)
Dưới đây là bảng tổng hợp các hoạt động đã thực hiện từ ngày 08/06/2026 - 14/06/2026:

| Thứ / Ngày | Nội dung công việc | Chi tiết nhiệm vụ | Kết quả đạt được | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Thứ 2 (08/06) | Học thiết kế diagram | Nghiên cứu tài liệu hướng dẫn thiết kế kiến trúc AWS; làm quen với Draw.io và bộ icon AWS. | Nắm được nguyên tắc bố cục sơ đồ kiến trúc chuẩn hóa. | AWS Architecture Center |
| Thứ 3 (09/06) | Vẽ sơ đồ hạ tầng | Vẽ bản thảo đầu tiên của hệ thống trên Draw.io; phân rõ các vùng VPC, Public Subnet, Private Subnet. | Có sơ đồ trực quan thể hiện dòng đi của dữ liệu từ Client vào AWS. | Draw.io Tool |
| Thứ 4 (10/06) | Họp định hình bài toán | Thảo luận nhóm; xác định bài toán thực tế dự án sẽ giải quyết (ví dụ: tối ưu hóa xử lý văn bản bằng AI). | Thống nhất mô tả nghiệp vụ và phạm vi dự án. | Biên bản họp nhóm |
| Thứ 5 (11/06) | Chân dung khách hàng | Định nghĩa đối tượng sử dụng; phân tích các tính năng cần có để đáp ứng yêu cầu người dùng. | Xác định danh sách tính năng ưu tiên (MVP features). | Tài liệu nghiệp vụ |
| Thứ 6 (12/06) | Tích hợp giải pháp AI | Nghiên cứu cách kết hợp dịch vụ AWS (S3, EC2, RDS) với các mô hình AI/ML để giải quyết bài toán cốt lõi. | Đề xuất giải pháp kiến trúc tổng thể có tích hợp trí tuệ nhân tạo. | AWS Machine Learning |
| Thứ 7 (13/06) | Tính toán chi phí | Dùng công cụ AWS Pricing Calculator để dự toán chi phí vận hành hàng tháng của hệ thống. | Dự toán được ngân sách vận hành của kiến trúc, đảm bảo tính kinh tế. | AWS Pricing Calculator |
| Chủ Nhật (14/06) | Kế hoạch hành động | Phân chia công việc (ai làm infra, ai làm backend/AI, ai làm docs) và đặt các mốc thời gian. | Thiết lập kế hoạch chạy Sprint rõ ràng cho các tuần tiếp theo. | Trello / Jira board |

> **So What:** Thiết kế bài bản trong tuần này giúp loại bỏ các lỗi mơ hồ về mặt yêu cầu hệ thống, đảm bảo mọi thành viên đều hiểu rõ mục tiêu chung của dự án.

---

### 3. Thiết kế Sơ đồ Kiến trúc Chuẩn hóa với Draw.io
Một sơ đồ kiến trúc tốt cần tuân thủ các tiêu chuẩn của AWS để bất kỳ kỹ sư nào cũng có thể đọc hiểu.

**Các nguyên tắc thiết kế đã áp dụng:**
* **Bố cục Phân cấp:** Vẽ từ ngoài vào trong: Region -> VPC -> Availability Zones -> Subnets -> Resources.
* **Sử dụng đúng Thư viện Biểu tượng:** Sử dụng bộ icon AWS chính thức mới nhất. Không dùng các biểu tượng tự vẽ hoặc lỗi thời.
* **Chú thích rõ ràng:** Các mũi tên biểu thị hướng đi của dữ liệu hoặc kết nối (ví dụ: HTTP Port 443, JDBC Port 5432).

> **So What:** Thiết kế trực quan rõ ràng giảm thiểu thời gian giải thích kiến trúc giữa các thành viên và giúp người đánh giá dễ dàng nắm bắt giải pháp kỹ thuật.

---

### 4. Định hình MVP (Minimum Viable Product) cho Dự án
Việc tập trung vào các tính năng cốt lõi giúp đội ngũ hoàn thành dự án đúng hạn mà không bị sa đà vào các yêu cầu phụ.

**Các bước phân tích tính năng:**
1. **Chân dung người dùng:** Xác định hành vi, thói quen và nhu cầu sử dụng của người dùng cuối.
2. **Xác định Core Feature:** Tính năng bắt buộc phải có để giải quyết vấn đề (Ví dụ: Upload file -> AI phân tích -> Lưu kết quả).
3. **Ưu tiên triển khai:** Đặt thứ tự ưu tiên theo ma trận Impact vs Effort để phân chia công việc chạy sprint.

> **So What:** Xác định đúng MVP giúp tối ưu hóa nỗ lực phát triển của nhóm, đảm bảo dự án chạy thử nghiệm thành công trong thời gian ngắn.

---

### 5. Dự toán Chi phí Hạ tầng qua AWS Pricing Calculator
Một kiến trúc tốt phải đi kèm tính tối ưu về mặt kinh tế. Nhóm đã sử dụng công cụ tính toán của AWS để dự phòng ngân sách.

**Các thông số giả định:**
* **EC2:** Sử dụng 1 instance `t3.medium` chạy ứng dụng.
* **RDS:** 1 database instance `db.t3.micro` để lưu trữ dữ liệu.
* **S3:** Khoảng 50 GB lưu trữ dữ liệu tệp tin.
* **AWS Budgets:** Thiết lập cảnh báo để giữ tổng chi phí thực tế dưới $15/tháng.

> **So What:** Việc tính toán chi phí trước giúp doanh nghiệp tránh bất ngờ khi nhận hóa đơn và đưa ra các điều chỉnh kiến trúc phù hợp ngay từ đầu.

---

### 6. Tổng kết và Đánh giá Kết quả Tuần 8

#### 6.1. Kỹ năng Nhóm và Giao tiếp (Soft Skills)
* **Kế hoạch phối hợp:** Thiết lập bảng phân công công việc cụ thể trên Trello; phân chia công việc minh bạch, rõ ràng.
* **Tư duy Kiến trúc sư:** Cùng nhau phản biện để tối ưu hóa thiết kế hệ thống.

#### 6.2. Quản trị Tài nguyên và Chi phí (FinOps)
* **Quản lý ngân sách:** Dự báo chi tiết chi phí của dự án trước khi khởi tạo tài nguyên thật, giảm thiểu rủi ro vượt hạn mức credit.

#### 6.3. Bảo mật và Quản trị Hệ thống (Security & Infrastructure)
* **Thiết kế mạng an toàn:** Thiết kế hệ thống tuân thủ nguyên tắc bảo mật của AWS: đặt CSDL và backend hoàn toàn trong Private Subnet.

#### 6.4. Năng lực Kỹ thuật và Tư duy AI (Technical & AI Mindset)
* **Trực quan hóa:** Thành thạo sử dụng Draw.io để mô hình hóa ý tưởng kỹ thuật thành sơ đồ chi tiết.

---
**Đánh giá chung:** Hoàn thành tốt mục tiêu tuần 8. Bản thiết kế kiến trúc và kế hoạch phân công công việc đã sẵn sàng để triển khai.
