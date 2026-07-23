---
title: "Blog 3"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

## Triển khai ứng dụng Serverless với AWS Lambda và Amazon API Gateway

**Link bài viết:** [Facebook - AWS Study Group FCJ](https://www.facebook.com/groups/awsstudygroupfcj/permalink/2203965220368438/)

Sau khi đã triển khai backend trên Amazon EC2 và tìm hiểu cách tối ưu chi phí khi vận hành hệ thống trên AWS, nhóm bắt đầu đặt ra một câu hỏi mới: liệu có thể triển khai API mà không cần tự quản lý máy chủ hay không?

EC2 mang lại rất nhiều quyền kiểm soát. Người dùng có thể chủ động cấu hình hệ điều hành, cài runtime, quản lý networking, storage và security group. Tuy nhiên, đi kèm với đó là nhiều công việc vận hành như theo dõi trạng thái instance, cập nhật phần mềm, vá lỗi hệ điều hành, khởi động hoặc tắt server, và tự thiết kế khả năng mở rộng.

Khi tìm hiểu thêm về các mô hình triển khai ứng dụng trên AWS, nhóm tiếp cận với một kiến trúc khác: **Serverless Computing**. Điểm hấp dẫn của mô hình này là developer có thể tập trung nhiều hơn vào code và logic nghiệp vụ, trong khi phần hạ tầng phía sau được AWS quản lý.

## Serverless là gì?

Serverless không có nghĩa là hoàn toàn không có server. Server vẫn tồn tại, nhưng người dùng không trực tiếp quản lý chúng.

Với mô hình serverless, AWS đảm nhiệm các phần như:

- Cấp phát tài nguyên.
- Khởi động môi trường chạy.
- Tự động mở rộng theo lưu lượng.
- Cập nhật hệ điều hành và runtime phía sau.
- Quản lý khả năng chịu tải.

Nhờ vậy, developer có thể tập trung vào việc phát triển tính năng thay vì quản trị hạ tầng. Đây cũng là lý do serverless thường được sử dụng cho REST API, backend mobile app, chatbot, IoT, event processing hoặc AI pipeline.

## Kiến trúc triển khai

Trong mô hình serverless cơ bản, người dùng gửi HTTP request đến **Amazon API Gateway**. API Gateway đóng vai trò entry point, tiếp nhận request và chuyển tiếp đến **AWS Lambda**. Lambda xử lý nghiệp vụ, đọc/ghi dữ liệu với **Amazon DynamoDB** nếu cần, sau đó trả kết quả ngược lại thông qua API Gateway.

![Kiến trúc Serverless Lambda API Gateway](/images/3-BlogsTranslated/3.3-Blog3/serverless-lambda-api-gateway.png)

Các thành phần chính gồm:

- **Amazon API Gateway**: tiếp nhận HTTP/REST request từ client.
- **AWS Lambda**: chạy function xử lý nghiệp vụ.
- **Amazon DynamoDB**: lưu trữ dữ liệu theo mô hình NoSQL.
- **AWS IAM Role**: cấp quyền để Lambda truy cập các dịch vụ cần thiết.
- **Amazon CloudWatch**: thu thập log, metrics và hỗ trợ quan sát hệ thống.

Khác với EC2, người dùng không cần tạo hoặc duy trì máy chủ chạy liên tục. Function chỉ được kích hoạt khi có request hoặc event.

## Vì sao Serverless hấp dẫn?

### Không cần quản lý server

Đây là điểm khác biệt lớn nhất so với EC2. Với EC2, người dùng phải quan tâm đến instance, CPU, RAM, hệ điều hành, update, security patch và scaling. Với Lambda, AWS chịu trách nhiệm phần lớn các công việc này.

### Tự động mở rộng

Khi ứng dụng nhận nhiều request cùng lúc, Lambda có thể tự động tạo thêm môi trường thực thi để xử lý. Khi lưu lượng giảm, tài nguyên sẽ được thu hồi. Điều này giúp giảm nhu cầu dự đoán trước số lượng server cần chạy.

### Thanh toán theo mức sử dụng

Với Lambda, chi phí được tính theo số lần gọi function và thời gian thực thi. Nếu function không chạy, gần như không phát sinh chi phí compute. Cách tính này rất khác với EC2, nơi instance vẫn phát sinh chi phí theo thời gian chạy dù không có request nào.

Mô hình này phù hợp với các hệ thống có lưu lượng không ổn định, ứng dụng thử nghiệm, MVP, API nội bộ hoặc các bài thực hành nghiên cứu.

## Một số hạn chế cần lưu ý

### Cold Start

Khi Lambda không được sử dụng trong một khoảng thời gian, môi trường thực thi có thể bị giải phóng. Request đầu tiên sau đó cần thêm thời gian để khởi tạo function. Hiện tượng này được gọi là cold start.

Đối với các API yêu cầu phản hồi cực nhanh và ổn định, cold start là yếu tố cần cân nhắc khi thiết kế.

### Giới hạn thời gian thực thi

Lambda phù hợp với các tác vụ ngắn và event-driven. Nếu ứng dụng cần chạy liên tục, xử lý nền phức tạp hoặc duy trì kết nối lâu dài, EC2 hoặc ECS có thể phù hợp hơn.

### Phụ thuộc vào dịch vụ cloud

Khi sử dụng Lambda, kiến trúc thường gắn với các dịch vụ như API Gateway, IAM, CloudWatch, DynamoDB và EventBridge. Điều này giúp tích hợp rất thuận tiện trong AWS, nhưng cũng làm tăng mức độ phụ thuộc vào nền tảng cloud.

## Góc nhìn chi phí

Sau khi tìm hiểu AWS Cost Management, nhóm nhận thấy serverless mang lại một góc nhìn tối ưu chi phí rất rõ.

Ở mô hình EC2:

- Server hoạt động liên tục.
- Chi phí tính theo thời gian chạy.
- Cần tự quản lý scaling.

Trong khi đó với Lambda:

- Không có request thì gần như không phát sinh chi phí compute.
- Hệ thống tự động mở rộng khi cần.
- Không cần duy trì server chạy 24/7.

Tuy nhiên, serverless không phải lúc nào cũng rẻ hơn. Nếu hệ thống có lưu lượng rất lớn, function chạy lâu hoặc API Gateway nhận request liên tục, tổng chi phí Lambda và API Gateway có thể cao hơn so với EC2 hoặc ECS. Vì vậy, lựa chọn kiến trúc cần dựa trên đặc điểm workload thực tế.

## Bài học rút ra

Serverless không thay thế hoàn toàn EC2. Đây là một lựa chọn kiến trúc khác, phù hợp với một nhóm bài toán khác.

Nếu cần toàn quyền kiểm soát hệ điều hành, cấu hình đặc biệt, tiến trình chạy lâu dài hoặc môi trường runtime tùy chỉnh sâu, EC2 vẫn là lựa chọn hợp lý.

Ngược lại, nếu mục tiêu là triển khai nhanh, ít quản trị hạ tầng, tự động mở rộng và tối ưu chi phí cho API có lưu lượng biến động, AWS Lambda kết hợp Amazon API Gateway là một mô hình rất đáng cân nhắc.

Điều quan trọng nhất là không nên nhìn dịch vụ theo hướng “dịch vụ nào tốt hơn”, mà nên hiểu mỗi dịch vụ AWS được thiết kế để giải quyết một nhóm bài toán cụ thể. Hiểu đúng đặc điểm của từng dịch vụ sẽ giúp chọn kiến trúc phù hợp ngay từ đầu.

## Kết luận

Thông qua việc tìm hiểu mô hình serverless, nhóm có thêm một góc nhìn hiện đại hơn về cách xây dựng ứng dụng trên AWS. Việc kết hợp Amazon API Gateway với AWS Lambda giúp giảm đáng kể khối lượng công việc liên quan đến quản trị hạ tầng, đồng thời tận dụng khả năng tự động mở rộng và cơ chế thanh toán theo mức sử dụng.

Đối với các dự án học tập, API có lưu lượng không ổn định, MVP hoặc ứng dụng cần triển khai nhanh, đây là một kiến trúc đáng để trải nghiệm. Trong các bước tiếp theo, nhóm có thể tiếp tục tìm hiểu cách kết hợp Lambda với Amazon DynamoDB, Amazon S3 và Amazon EventBridge để xây dựng hệ thống serverless hoàn chỉnh hơn.

