---
title: "Worklog Tuần 1"
date: 2026-04-23
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Mục tiêu tuần
Bắt đầu hành trình First Cloud AI Journey (FCAJ), bản thân đặt ra các mục tiêu để làm quen với môi trường Cloud của AWS:
* Làm quen với các thành viên và lập nhóm 5 người để hỗ trợ nhau làm lab.
* Tạo tài khoản AWS Free Tier và thiết lập bảo mật cơ bản (MFA cho Root Account).
* Nhận đủ $200 credit thực hành và cấu hình ngân sách để kiểm soát chi phí.
* Học các lý thuyết cơ bản về hạ tầng AWS (Region, AZ, Edge Location) cùng quản lý quyền truy cập IAM (User, Group, Role).
* Tìm hiểu phương pháp Spec-driven development trong hệ sinh thái AI Kiro.

## 2. Các công việc cần triển khai trong tuần
Dưới đây là nhật ký công việc chi tiết trong tuần đầu tiên:

| Thứ / Ngày | Nội dung công việc | Chi tiết nhiệm vụ | Kết quả đạt được | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Thứ 6 (17/04) | Kickoff Workshop | - Kickoff Workshop: <br> &emsp; + Tham gia khai mạc <br> &emsp; + Tiếp nhận tầm nhìn FCAJ và 06 nguyên tắc Leadership | Hiểu rõ mục tiêu chương trình; thấm nhuần tư duy Builder & Troubleshooter. |  |
| Thứ 7 (18/04) | Kết nối cộng đồng | - Kết nối cộng đồng: <br> &emsp; + Hình thành nhóm 5 thành viên <br> &emsp; + Thiết lập kênh liên lạc WhatsApp/LinkedIn | Hoàn tất cấu trúc nhóm; sẵn sàng cho các bài Lab đòi hỏi sự phối hợp. | [Web.whatsapp.com](https://web.whatsapp.com/) |
| Chủ Nhật (19/04) | Lý thuyết Cloud cơ bản | - Lý thuyết Cloud cơ bản: <br> &emsp; + Nghiên cứu Global Infrastructure (Region, AZ, Edge Location) <br> &emsp; + Tìm hiểu Management Console | Nắm vững hạ tầng vật lý của AWS; hiểu cách giảm độ trễ qua Edge Locations tại VN. | [Youtube Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox3TSYFbN1DNX7NZgTVXNj3x) |
| Thứ 2 (20/04) | Thiết lập hạ tầng gốc | - Thiết lập hạ tầng gốc: <br> &emsp; + Tạo tài khoản AWS Free Tier <br> &emsp; + Kích hoạt MFA cho Root Account <br> &emsp; + Nhận $100 credit đầu tiên | Tài khoản bảo mật đúng Best Practice; sẵn sàng nguồn vốn thực hành. | [AWS Study Group](https://000001.awsstudygroup.com/vi/) |
| Thứ 3 (21/04) | Tối ưu hóa chi phí | - Tối ưu hóa chi phí: <br> &emsp; + Triển khai Task 1 (EC2) <br> &emsp; + Triển khai Task 3 (AWS Budgets) | Hoàn thành thiết lập cảnh báo ngân sách để tránh "vung tay quá trán". | [AWS Study Group](https://000001.awsstudygroup.com/vi/) |
| Thứ 4 (22/04) | Hoàn thiện nhiệm vụ tín dụng | - Hoàn thiện nhiệm vụ tín dụng: <br> &emsp; + Thực hiện Task 2 (Bedrock) <br> &emsp; + Thực hiện Task 4 (Lambda) <br> &emsp; + Thực hiện Task 5 (RDS Aurora) | Hoàn thành 5 nhiệm vụ để nhận thêm $100 credit; biết cách raise support case. | [AWS Study Group](https://000001.awsstudygroup.com/vi/) |
| Thứ 5 (23/04) | Quản trị IAM & AI Kiro | - Quản trị IAM & AI Kiro: <br> &emsp; + Nghiên cứu lý thuyết AWS Kiro <br> &emsp; + Quản trị quyền truy cập IAM (User, Group, Role) | Nắm vững nguyên tắc đặc quyền tối thiểu (Least Privilege) và Spec-driven dev. | [AWS Study Group](https://000002.awsstudygroup.com/vi/) |

## 3. Kết quả đạt được
Qua tuần đầu thực hành và tự học và bài học rút ra từ kinh nghiệm rất thực tế dưới đây:

* **Quản lý chi phí và ngân sách thực hành (FinOps):**
  + Đã hoàn thành 5 nhiệm vụ cơ bản trên Console (tạo máy ảo EC2, gọi API Amazon Bedrock qua Claude 3, cấu hình cảnh báo Budgets, chạy Serverless Lambda và DB RDS Aurora) để kích hoạt đủ $200 AWS Credit.
  + Đúc kết được thói quen FinOps quan trọng là bật cảnh báo AWS Budgets sớm (gửi email cho ngay khi chi phí vượt quá $1) và tiến hành xóa/terminate tài nguyên (EC2, RDS Aurora) ngay sau khi làm lab xong để tránh phát sinh chi phí ngoài ý muốn.
  
  ![Thiết lập AWS Budgets thành công](/images/1-Worklog/week1/budget-success.png)
  
* **Tư duy bảo mật hệ thống (IAM):**
  + Tự bản thân thiết lập MFA bảo vệ tài khoản Root và thực hành tạo IAM User, Group để quản lý quyền hạn của từng thành viên trong nhóm.
  + Đúc kết được nguyên lý **Least Privilege** (Đặc quyền tối thiểu) - chỉ cấp quyền vừa đủ cho từng công việc và ưu tiên sử dụng IAM Role thay vì nhúng cứng Access/Secret Key trong code để hạn chế tối đa rủi ro bảo mật.

* **Phương pháp phát triển hướng đặc tả (AI Kiro):**
  + Làm quen với phương pháp **Spec-driven development**. Thay vì ngồi code tay từng dòng, học cách mô tả thiết kế và nghiệp vụ hệ thống qua file cấu hình chuẩn, sau đó để AI Kiro tự động sinh mã nguồn và hạ tầng tương ứng.
  + Đúc kết được xu hướng làm việc mới: dịch chuyển từ một người gõ code thuần túy (Coder) sang vai trò thiết kế hệ thống (System Designer) và kiểm duyệt logic (Reviewer) để đẩy nhanh tốc độ triển khai dự án.
