---
title: "Worklog Tuần 5"
date: 2026-05-24
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Mục tiêu tuần
Tuần này làm quen với công nghệ Container, các giải pháp lưu trữ dữ liệu lai và kết nối cộng đồng:
* Tìm hiểu Docker, thực hành đóng gói ứng dụng (Containerization) và kết nối với cơ sở dữ liệu Amazon RDS.
* Tạo repository trên Amazon ECR để lưu trữ và quản lý Docker image bảo mật.
* Nghiên cứu và cấu hình AWS Storage Gateway (NFS File Share) để đồng bộ dữ liệu local lên Amazon S3.
* Tham dự sự kiện FCAJ Community Day (23/05) để học hỏi và mở rộng kết nối.

## 2. Các công việc cần triển khai trong tuần
Dưới đây là bảng tổng hợp các hoạt động đã thực hiện từ ngày 18/05/2026 - 24/05/2026:

| Thứ / Ngày | Nội dung công việc | Chi tiết nhiệm vụ | Kết quả đạt được | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Thứ 2 (18/05) | Nghiên cứu Container | - Containerization: <br> &emsp; + Học lý thuyết Docker <br> &emsp; + Viết Dockerfile đóng gói ứng dụng web cơ bản | Hiểu quy trình xây dựng Docker Image và cô lập môi trường chạy ứng dụng. | [Docker Documentation](https://000015.awsstudygroup.com/vi) |
| Thứ 3 (19/05) | Triển khai CSDL RDS | - Triển khai cơ sở dữ liệu: <br> &emsp; + Khởi tạo Amazon RDS (PostgreSQL/MySQL) <br> &emsp; + Dùng Docker Compose kết nối Web Container tới RDS | Hoàn thành mô hình ứng dụng Web + DB chuẩn chỉnh, tách biệt máy chủ web và máy chủ dữ liệu. | [RDS](https://000015.awsstudygroup.com/vi) |
| Thứ 4 (20/05) | Quản lý Container Registry | - Quản lý ECR: <br> &emsp; + Tạo Repository trên Amazon ECR <br> &emsp; + Đẩy (push) các container image từ EC2 lên ECR | Lưu trữ container image an toàn trên Cloud; dọn dẹp tài nguyên sau lab. | [Container Registry](https://000016.awsstudygroup.com/vi) |
| Thứ 5 (21/05) | Nghiên cứu Hybrid Storage | - Nghiên cứu lưu trữ lai: <br> &emsp; + Tìm hiểu AWS Storage Gateway <br> &emsp; + So sánh File Gateway, Volume Gateway và Tape Gateway | Mastered data synchronization architectures kết nối on-premises tới AWS. | [AWS Storage Guide](https://000024.awsstudygroup.com/vi) |
| Thứ 6 (22/05) | Storage Gateway Lab | - Thực hành Storage Gateway: <br> &emsp; + Cấu hình NFS File Share trên File Gateway <br> &emsp; + Mount ổ đĩa local và kiểm tra đồng bộ file | Tệp tin ghi vào local drive được tự động đồng bộ hóa lên S3 bucket. | [Storage Gateway](https://000024.awsstudygroup.com/vi) |
| Thứ 7 (23/05) | FCAJ Community Day | - Giao lưu cộng đồng: <br> &emsp; + Tham gia ngày hội FCAJ Community Day <br> &emsp; + Nghe chia sẻ chuyên đề từ AWS experts | Tiếp thu kiến thức về AI, Serverless và mở rộng networking. | Live Event |
| Chủ Nhật (24/05) | Ghi tổng kết | - Ghi chép: <br> &emsp; + Tắt RDS database <br> &emsp; + Giải phóng Storage Gateway VM và ECR repository | Hiểu rõ tài nguyên để tối ưu hóa chi phí. | Cá nhân ghi chép |

## 3. Kết quả đạt được
Qua tuần thứ 5 làm việc với Container, Storage Gateway và giao lưu tại Community Day, các bài học kinh nghiệm sau đây đã được đúc kết:

* **Container hóa ứng dụng và quản lý Registry (Docker & ECR):**
  + Bản thân có thể tự đóng gói thành công ứng dụng web bằng Dockerfile, sử dụng Docker Compose kết nối đến Amazon RDS database chạy trong Custom VPC. Ngoài ra, ECR repository đã được tạo và push image lên registry bảo mật.
  + Đúc kết: Container hóa giúp loại bỏ sự phụ thuộc vào hệ điều hành của máy chủ bên dưới. Lưu trữ image trên ECR là bước chuẩn bị quan trọng chi việc triển khai tự động hóa CI/CD lên các dịch vụ Serverless container như ECS hay Fargate sau này.

* **Giải pháp lưu trữ lai Cloud-Onpremises (AWS Storage Gateway):**
  + Triển khai thành công File Storage Gateway, mount ổ đĩa mạng NFS nội bộ từ máy ảo client và kiểm tra đồng bộ dữ liệu tự động lên S3 bucket.
  + Đúc kết: Storage Gateway cung cấp cầu nối tuyệt vời giúp các ứng dụng On-premises cũ có thể tận dụng không gian lưu trữ Cloud mà không cần viết lại mã nguồn. Đây là giải pháp sao lưu và khắc phục sự cố (Disaster Recovery) rất hiệu quả.

* **Thu hoạch từ FCAJ Community Day:**
  + Tham gia trực tiếp sự kiện cộng đồng, nghe chia sẻ từ các chuyên gia về Amazon Bedrock, GenAI, Serverless và FinOps tối ưu chi phí.
  + Đúc kết: Giao lưu cộng đồng giúp đối chiếu kiến thức lý thuyết đã học với các bài toán thực tế của doanh nghiệp, mở rộng networking phục vụ cơ hội nghề nghiệp tương lai.

* **FinOps thực tế:**
  + Đúc kết: Do Storage Gateway VM và RDS Instance chạy thử nghiệm tốn chi phí khá nhanh, các tài nguyên đã được tắt và dọn dẹp sạch sẽ ngay sau khi test kết nối thành công để bảo toàn credit.
