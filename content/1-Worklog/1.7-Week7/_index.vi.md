---
title: "Worklog Tuần 7"
date: 2026-06-07
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Mục tiêu tuần
Tuần này đánh dấu bước chuyển giao quan trọng khi mình bắt đầu chuẩn bị cho dự án tốt nghiệp cuối khóa bên cạnh việc tiếp tục học các kiến thức kỹ thuật:
* Tham gia buổi tọa đàm với các diễn giả để học hỏi kinh nghiệm thực tế.
* Tìm hiểu và triển khai AWS WAF (Web Application Firewall) bảo vệ Web application ở tầng ứng dụng (Layer 7) chống SQL Injection và XSS.
* Ôn tập hệ thống hóa toàn bộ các dịch vụ AWS đã học trong 6 tuần qua.
* Thực hiện khảo sát nhu cầu thực tế của người dùng và cùng nhóm thảo luận lựa chọn đề tài dự án tốt nghiệp.

## 2. Các công việc cần triển khai trong tuần
Dưới đây là bảng tổng hợp các hoạt động đã thực hiện từ ngày 01/06/2026 - 07/06/2026:

| Thứ / Ngày | Nội dung công việc | Chi tiết nhiệm vụ | Kết quả đạt được | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Thứ 2 (01/06) | Tọa đàm Diễn giả | - Tọa đàm diễn giả: <br> &emsp; + Tham gia sự kiện chia sẻ kinh nghiệm diễn giả <br> &emsp; + Giao lưu câu chuyện thực tế và định hướng nghề nghiệp | Học hỏi tư duy giải quyết khủng hoảng và định hướng nghề nghiệp. | Diễn giả chương trình |
| Thứ 3 (02/06) | Nghiên cứu AWS WAF | - Nghiên cứu AWS WAF: <br> &emsp; + Tìm hiểu cơ chế bảo vệ của Web Application Firewall <br> &emsp; + Phân tích các cuộc tấn công SQL Injection và XSS | Hiểu cách WAF lọc lưu lượng HTTP/HTTPS ở Lớp 7 (Application Layer). | AWS Security Guide |
| Thứ 4 (03/06) | Cấu hình WAF | - Triển khai WAF: <br> &emsp; + Tạo Web ACL <br> &emsp; + Cấu hình AWS Managed Rules <br> &emsp; + Liên kết WAF với CloudFront hoặc ALB | Thiết lập hàng rào bảo mật chặn đứng các request độc hại trước khi tới server. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Thứ 5 (04/06) | Kiểm thử tấn công | - Thực hành kiểm thử WAF: <br> &emsp; + Mô phỏng gửi SQLi query và XSS script lên Web application <br> &emsp; + Kiểm tra log chặn trên WAF console | WAF phát hiện và trả về mã lỗi 403 Forbidden chính xác đối với các request tấn công. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Thứ 6 (05/06) | Hệ thống hóa kiến thức | - Ôn tập hệ thống: <br> &emsp; + Hệ thống hóa VPC, EC2, IAM, Backup, Transit Gateway, Docker, Security Hub, Lambda | Tổng hợp các mảnh ghép kiến trúc để chuẩn bị thiết kế hệ thống lớn. | Bản ghi cá nhân |
| Thứ 7 (06/06) | Khảo sát nhu cầu | - Khảo sát bài toán thực tế: <br> &emsp; + Phỏng vấn một số người dùng/doanh nghiệp nhỏ về khó khăn dữ liệu | Xác định các bài toán thực tế cần giải quyết bằng công nghệ. | Khách hàng mục tiêu |
| Chủ Nhật (07/06) | Lựa chọn đề tài | - Định hình đề tài: <br> &emsp; + Thảo luận nhóm chốt định hướng đề tài Project | Thống nhất chọn đề tài ứng dụng AI kết hợp AWS để xử lý dữ liệu thông minh. | Biên bản họp nhóm |

## 3. Kết quả đạt được
Qua tuần thực hành bảo mật Layer 7 và bắt đầu định hình đề tài tốt nghiệp, mình đã đúc kết được các bài học kinh nghiệm sau:

* **Tích lũy kinh nghiệm thực tế từ Diễn giả khách mời:**
  + Tham gia buổi tọa đàm và lắng nghe các câu chuyện xử lý khủng hoảng hệ thống, tối ưu hóa hạ tầng production, cách rèn luyện kỹ năng mềm và chuẩn bị hồ sơ tuyển dụng.
  + Đúc kết: Những chia sẻ thực tế giúp rút ngắn khoảng cách giữa lý thuyết và thực tiễn, định hình rõ ràng hơn thái độ làm việc chuyên nghiệp cần có của một Cloud Engineer thực thụ.

* **Bảo vệ ứng dụng Web ở tầng Application (AWS WAF):**
  + Tự tay khởi tạo Web ACL, liên kết với CloudFront/ALB và kích hoạt các bộ quy tắc AWS Managed Rules (Common Rule Set, SQL Database Set). Thực hành gửi các request chứa mã độc SQLi và XSS để kiểm tra phản hồi.
  + Đúc kết: AWS WAF lọc sạch traffic độc hại trước khi chạm tới máy chủ Backend. Việc chặn thành công các request tấn công và trả về mã lỗi **403 Forbidden** xác minh hệ thống được bảo vệ vững chắc theo tiêu chuẩn OWASP Top 10.
  + FinOps: Do Web ACL tính phí cố định theo giờ chạy, mình đã xóa Web ACL ngay sau khi test thành công để bảo toàn credit.

* **Định hình bài toán thực tế cho Dự án Tốt nghiệp:**
  + Nhóm mình đã phỏng vấn người dùng thực tế về khó khăn trong quản lý tài liệu, sau đó thảo luận đánh giá tính khả thi và thống nhất lựa chọn đề tài ứng dụng AI kết hợp AWS để xử lý dữ liệu thông minh.
  + Đúc kết: Lựa chọn đề tài dựa trên nhu cầu thực tế giúp dự án tốt nghiệp có giá trị thực tiễn cao hơn. Quá trình họp nhóm giúp cải thiện khả năng phân tích yêu cầu nghiệp vụ và lập kế hoạch kỹ thuật.
