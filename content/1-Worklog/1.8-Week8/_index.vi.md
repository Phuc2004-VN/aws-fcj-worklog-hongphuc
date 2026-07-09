---
title: "Worklog Tuần 8"
date: 2026-06-14
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Mục tiêu tuần
Tuần này tập hoàn toàn vào việc thiết kế kiến trúc chi tiết và chuẩn bị kế hoạch triển khai dự án tốt nghiệp:
* Nghiên cứu cách vẽ sơ đồ hạ tầng AWS chuẩn hóa bằng Draw.io.
* Thảo luận làm rõ yêu cầu nghiệp vụ, chân dung người dùng để định hình các tính năng cốt lõi (MVP) của dự án.
* Sử dụng công cụ AWS Pricing Calculator để dự toán chi phí vận hành hàng tháng của hệ thống.
* Phân chia công việc và thiết lập mốc thời gian hoàn thành (Milestones) cho từng thành viên.

## 2. Các công việc cần triển khai trong tuần
Dưới đây là bảng tổng hợp các hoạt động đã thực hiện từ ngày 08/06/2026 - 14/06/2026:

| Thứ / Ngày | Nội dung công việc | Chi tiết nhiệm vụ | Kết quả đạt được | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Thứ 2 (08/06) | Học thiết kế diagram | - Học thiết kế diagram: <br> &emsp; + Nghiên cứu tài liệu hướng dẫn vẽ kiến trúc AWS <br> &emsp; + Cài đặt công cụ Draw.io và import bộ icon AWS | Nắm được nguyên tắc bố cục sơ đồ kiến trúc chuẩn hóa. | [AWS Architecture Center](https://www.youtube.com/watch?v=l8isyDe-GwY&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=2) |
| Thứ 3 (09/06) | Vẽ sơ đồ hạ tầng | - Thiết kế sơ đồ hạ tầng: <br> &emsp; + Phác thảo bản vẽ kiến trúc đầu tiên của hệ thống <br> &emsp; + Thiết lập phân vùng VPC, Public/Private Subnets | Có sơ đồ trực quan thể hiện dòng đi của dữ liệu từ Client vào AWS. | [Draw.io Tool](https://app.diagrams.net/) |
| Thứ 4 (10/06) | Họp định hình bài toán | - Định hình bài toán: <br> &emsp; + Thảo luận nhóm làm rõ yêu cầu nghiệp vụ dự án tốt nghiệp <br> &emsp; + Xác định quy trình xử lý dữ liệu thông minh | Thống nhất mô tả nghiệp vụ và phạm vi dự án. | Biên bản họp nhóm |
| Thứ 5 (11/06) | Chân dung khách hàng | - Thiết kế tính năng: <br> &emsp; + Định nghĩa đối tượng người dùng dự kiến <br> &emsp; + Thiết lập danh sách tính năng tối giản đáp ứng người dùng | Xác định danh sách tính năng ưu tiên (MVP features). | Tài liệu nghiệp vụ |
| Thứ 6 (12/06) | Tích hợp giải pháp AI | - Nghiên cứu tích hợp AI: <br> &emsp; + Kết hợp S3, EC2, RDS với mô hình học máy trên Cloud <br> &emsp; + Đề xuất quy trình gọi API phân tích văn bản | Đề xuất giải pháp kiến trúc tổng thể có tích hợp trí tuệ nhân tạo. | [AWS Machine Learning](https://aws.amazon.com/what-is/artificial-intelligence/) |
| Thứ 7 (13/06) | Tính toán chi phí | - Dự toán chi phí: <br> &emsp; + Sử dụng AWS Pricing Calculator để lên cấu hình và ước tính giá | Dự toán được ngân sách vận hành của kiến trúc, đảm bảo tính kinh tế. | [AWS Pricing Calculator](https://calculator.aws/#/) |
| Chủ Nhật (14/06) | Kế hoạch hành động | - Kế hoạch vận hành: <br> &emsp; + Phân chia công việc (hạ tầng, backend/AI, frontend, docs) <br> &emsp; + Cấu hình board Trello quản lý tiến độ | Thiết lập kế hoạch chạy Sprint rõ ràng cho các tuần tiếp theo. | Tài liệu nhóm |

## 3. Kết quả đạt được
Qua tuần thực hiện thiết kế chi tiết kiến trúc hạ tầng và dự án tốt nghiệp, các bài học kinh nghiệm sau đây đã được đúc kết:

* **Thiết kế sơ đồ kiến trúc hạ tầng đám mây (Draw.io):**
  + Sử dụng Draw.io với bộ icon AWS chuẩn hóa để phác thảo sơ đồ hệ thống. Bố cục phân chia rõ ràng: Region -> VPC -> Public/Private Subnet -> các tài nguyên. Theo đúng Best Practice bảo mật, CSDL RDS và các máy chủ Backend được đặt hoàn toàn trong Private Subnet để ngăn ngừa truy cập trực tiếp từ Internet.
  + Đúc kết: Sơ đồ kiến trúc chính là bản vẽ hướng dẫn (blueprint) định hướng cho cả nhóm khi triển khai. Thiết kế chuẩn xác ngay từ đầu giúp tránh lỗi cấu hình định tuyến và phân cấp bảo mật khi chạy thực tế.

* **Định hình các tính năng cốt lõi (MVP) và quản lý tiến độ:**
  + Xác định các tính năng bắt buộc cho sản phẩm chạy thử (MVP): người dùng upload file -> trích xuất văn bản -> gọi AI model phân tích -> lưu kết quả vào RDS và hiển thị giao diện.
  + Đúc kết: Làm rõ phạm vi MVP giúp nhóm tránh được lỗi phình to tính năng (scope creep) – nguyên nhân hàng đầu gây trễ hạn dự án. Phân chia công việc cụ thể trên board Trello giúp các thành viên phối hợp trơn tru.

* **Dự toán chi phí vận hành hạ tầng (AWS Pricing Calculator):**
  + Sử dụng công cụ AWS Pricing Calculator để chạy thử dự báo chi phí vận hành. Bằng cách chọn cấu hình tài nguyên tối ưu (EC2 `t3.medium`, RDS PostgreSQL `db.t3.micro`, 50GB S3), tổng chi phí hàng tháng ước tính dưới $15, đảm bảo không vượt quá credit.
  + Đúc kết: Dự toán chi phí giúp kiểm soát tốt ngân sách thử nghiệm, đảm bảo tính kinh tế và hiệu quả cho hệ thống. Đây là kỹ năng FinOps thiết yếu đối với một Cloud Engineer.
