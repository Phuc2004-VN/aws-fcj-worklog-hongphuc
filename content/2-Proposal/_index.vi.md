---
title: "Bản đề xuất"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# Hệ thống phân tích và cảnh báo giá cổ phiếu
## Giải pháp AWS Serverless & AI Agent cho Trader

### 1. Tóm tắt điều hành

Dự án đề xuất xây dựng **Stock Alerts System** - hệ thống phân tích, lập luận và cảnh báo giá cổ phiếu tự động dựa trên kiến trúc AWS Serverless kết hợp AI Agent qua Amazon Bedrock. Hệ thống hỗ trợ Trader theo dõi thị trường, tự động thu thập dữ liệu, tính toán các chỉ báo kỹ thuật, phân tích ngữ cảnh bằng mô hình Claude và tạo khuyến nghị có thể kiểm duyệt trước khi gửi cho khách hàng.

Điểm cốt lõi của giải pháp là tách rõ hai nhóm tác vụ:

- **Tính toán định lượng** do code Python trên AWS Lambda xử lý để đảm bảo các chỉ số như RSI, MACD, moving average được tính nhất quán.
- **Lập luận ngôn ngữ và giải thích khuyến nghị** do AI Agent trên Amazon Bedrock thực hiện dựa trên dữ liệu đã được chuẩn hóa.

Cách tiếp cận này giúp giảm rủi ro AI tự bịa dữ liệu hoặc tính toán sai, đồng thời giữ cơ chế **Human-in-the-loop** để Trader kiểm duyệt khuyến nghị trước khi gửi cho khách hàng cuối.

### 2. Tuyên bố vấn đề

#### Vấn đề hiện tại

Trader thường phải xử lý lượng thông tin lớn từ thị trường chứng khoán: giá, khối lượng giao dịch, chỉ báo kỹ thuật, biến động ngành và tin tức vĩ mô. Việc phân tích thủ công tốn thời gian, dễ bỏ lỡ tín hiệu quan trọng và có thể bị ảnh hưởng bởi cảm xúc.

Nếu sử dụng AI thông thường để phân tích tài chính, rủi ro cũng rất đáng kể. Mô hình ngôn ngữ có thể tính sai chỉ báo kỹ thuật, diễn giải thiếu căn cứ hoặc tạo ra thông tin không có thật. Trong lĩnh vực tài chính, các sai lệch này có thể dẫn đến quyết định đầu tư rủi ro.

#### Giải pháp

Hệ thống giải quyết vấn đề bằng cách thiết kế pipeline tách biệt:

- Lambda Ingestion lấy dữ liệu thị trường từ Yahoo Finance hoặc API tài chính.
- Lambda Processing tính toán chỉ báo kỹ thuật bằng logic Python.
- Dữ liệu thô được lưu vào Amazon S3, dữ liệu phân tích và khuyến nghị được lưu vào DynamoDB.
- Amazon Bedrock nhận dữ liệu đã xử lý làm ngữ cảnh để tạo phân tích và khuyến nghị.
- Trader đăng nhập dashboard qua Amazon Cognito, xem lập luận AI, chỉnh sửa hoặc duyệt nội dung trước khi gửi khách hàng.

#### Lợi ích và ROI

Giải pháp giúp giảm đáng kể thời gian tổng hợp dữ liệu của Trader, chuẩn hóa quy trình phân tích và tăng khả năng giám sát nhiều mã cổ phiếu cùng lúc. Nhờ kiến trúc serverless, hệ thống chỉ phát sinh chi phí theo mức sử dụng, phù hợp với giai đoạn học tập, thử nghiệm và mở rộng dần.

### 3. Kiến trúc giải pháp

Hệ thống được thiết kế theo kiến trúc serverless, chia thành các lớp độc lập: frontend, ingestion, processing, AI analysis, database và monitoring.

![Stock Alerts System Architecture](/images/2-Proposal/stock-alerts-architecture.png)

#### Các dịch vụ AWS sử dụng

- **AWS WAF**: lọc request độc hại trước khi đi vào hệ thống.
- **Amazon CloudFront**: phân phối frontend với độ trễ thấp.
- **Amazon S3**: lưu static frontend và raw JSON dữ liệu thị trường.
- **Amazon API Gateway**: cung cấp REST API cho dashboard và manual sync.
- **Amazon Cognito**: xác thực người dùng và cấp JWT token cho Trader.
- **AWS Lambda**: thực hiện ingestion, xử lý dữ liệu, gọi AI và lưu kết quả.
- **Amazon EventBridge**: kích hoạt ingestion theo lịch thị trường.
- **Amazon SQS**: tách rời ingestion và processing, hỗ trợ retry và chống quá tải.
- **Amazon SQS DLQ**: lưu các message xử lý lỗi để điều tra lại.
- **Amazon DynamoDB**: lưu khuyến nghị, dữ liệu time-series và kết quả phân tích.
- **AWS KMS**: mã hóa dữ liệu nhạy cảm trong DynamoDB.
- **AWS Systems Manager Parameter Store**: lưu API key và cấu hình bảo mật.
- **Amazon Bedrock**: cung cấp AI Agent dùng Claude để lập luận và tạo khuyến nghị.
- **Amazon CloudWatch**: thu thập logs, metrics và kích hoạt cảnh báo vận hành.
- **Amazon SNS**: gửi cảnh báo vận hành hoặc thông tin cần chú ý cho Trader/Admin.

#### Luồng xử lý chính

1. Admin hoặc Trader gửi request vào dashboard.
2. AWS WAF kiểm tra và chuyển traffic sạch qua CloudFront.
3. Frontend static được tải từ S3.
4. Dashboard gọi API Gateway và gửi JWT token từ Cognito.
5. API Gateway xác thực token, sau đó kích hoạt Lambda khi cần manual sync.
6. EventBridge kích hoạt ingestion theo lịch để lấy dữ liệu thị trường.
7. Ingestion Lambda gọi API tài chính, lấy secrets từ Parameter Store và lưu raw JSON vào S3.
8. S3 Event Notification đẩy message sang SQS.
9. Processing Lambda đọc message từ SQS, tính toán chỉ báo kỹ thuật và gọi Bedrock để phân tích.
10. Kết quả khuyến nghị được lưu vào DynamoDB với dữ liệu được mã hóa bằng KMS.
11. CloudWatch ghi nhận metrics/logs, kích hoạt SNS nếu có lỗi hoặc vượt ngưỡng.
12. Trader kiểm duyệt khuyến nghị trên dashboard trước khi gửi cho khách hàng.

### 4. Triển khai kỹ thuật

#### Frontend & Dashboard

Frontend được xây dựng bằng JavaScript và triển khai dưới dạng static website trên Amazon S3, phân phối qua CloudFront. Dashboard cho phép Trader đăng nhập, xem danh sách mã cổ phiếu, theo dõi chỉ báo, đọc lập luận AI và duyệt nội dung trước khi gửi.

#### Ingestion & Math Engine

EventBridge kích hoạt Lambda theo lịch thị trường. Lambda lấy dữ liệu từ Yahoo Finance hoặc API tài chính, lưu raw JSON vào S3. Khi object mới xuất hiện, S3 gửi event sang SQS để Processing Lambda xử lý có kiểm soát.

Processing Lambda dùng Python để tính toán chỉ báo kỹ thuật như RSI, MACD và moving average. Việc tính toán bằng code giúp đảm bảo kết quả định lượng không phụ thuộc vào suy luận của AI.

#### AI Analytics Engine

Amazon Bedrock nhận dữ liệu kỹ thuật đã được chuẩn hóa làm context. Prompt được thiết kế để yêu cầu AI xuất JSON có cấu trúc gồm:

- Khuyến nghị hành động.
- Confidence score.
- Chuỗi lập luận logic.
- Các yếu tố rủi ro cần chú ý.

Các tín hiệu có confidence score thấp sẽ bị loại hoặc đưa vào trạng thái cần xem xét thủ công.

#### Database & Security

DynamoDB lưu kết quả phân tích theo mô hình truy vấn time-series. Thiết kế khóa đề xuất:

```text
PK: TICKER#<Mã_Cổ_Phiếu>
SK: TIMESTAMP#<YYYYMMDD-HHMMSS>
```

Dữ liệu được mã hóa bằng AWS KMS. API key và cấu hình nhạy cảm được lưu trong AWS Systems Manager Parameter Store thay vì hard-code trong source code.

#### Observability & Alerting

CloudWatch thu thập logs và metrics từ Lambda, SQS và API Gateway. Khi có lỗi ingestion, message thất bại, retry vượt ngưỡng hoặc chi phí AI có dấu hiệu tăng nhanh, hệ thống có thể gửi cảnh báo qua SNS để Trader/Admin xử lý.

### 5. Lộ trình & mốc triển khai

- **Tháng 5**: Học AWS, tìm hiểu các dịch vụ serverless và AI sẽ sử dụng trong project.
- **Tháng 6**: Thiết kế kiến trúc, vẽ sơ đồ hệ thống, phân chia nhiệm vụ và xác định luồng dữ liệu.
- **Tháng 7**: Triển khai project, kiểm thử ingestion, processing, dashboard, cảnh báo và fix lỗi.

### 6. Ước tính ngân sách

Chi phí hạ tầng được tối ưu theo hướng tận dụng AWS Free Tier cho giai đoạn học tập và thử nghiệm.

| Dịch vụ | Ước tính sử dụng | Chi phí dự kiến |
| --- | --- | --- |
| Amazon EventBridge | Khoảng 8.800 sự kiện/tháng | 0,00 USD trong Free Tier |
| AWS Lambda | Khoảng 17.600 lượt chạy/tháng | 0,00 USD trong Free Tier |
| Amazon SQS | Khoảng 17.600 message/tháng | 0,00 USD trong Free Tier |
| Amazon S3 | Khoảng 200 MB JSON/tháng | 0,00 USD trong Free Tier |
| Amazon DynamoDB | Khoảng 2.200 bản ghi/tháng | 0,00 USD trong Free Tier |
| Amazon API Gateway | Khoảng 5.000 request/tháng | 0,00 USD trong Free Tier |
| Amazon Cognito | 1 tài khoản Trader/Admin | 0,00 USD trong Free Tier |
| AWS SSM Parameter Store | Standard parameters | 0,00 USD |
| Amazon CloudWatch | Logs và metrics dưới 5 GB | 0,00 USD trong Free Tier |
| Amazon Bedrock | Khoảng 2.200 request phân tích/tháng | Chi phí biến đổi theo token |

Với giai đoạn dev/test dùng Claude 3.5 Sonnet, giả định mỗi request dùng khoảng 1.500 input tokens, 2.200 request tương đương khoảng 3,3 triệu input tokens. Chi phí AI ước tính khoảng **19,80 USD/tháng** khi chạy thử nghiệm thực tế. Phần hạ tầng serverless còn lại được thiết kế để tiệm cận **0 USD/tháng** trong phạm vi Free Tier.

### 7. Đánh giá rủi ro

#### Rủi ro 1: Vượt chi phí AI do token tăng đột biến

Khi thị trường biến động mạnh, số lượng mã cổ phiếu cần phân tích có thể tăng, dẫn đến số lần gọi Bedrock nhiều hơn dự kiến.

**Giảm thiểu:** đặt quota số lần gọi Bedrock mỗi ngày, giới hạn danh sách ticker theo ưu tiên, dùng Claude 3.5 Sonnet cho dev/test và đặt AWS Budgets cảnh báo sớm.

#### Rủi ro 2: Nghẽn xử lý khi nhiều file đổ về S3 cùng lúc

Nếu ingestion tạo nhiều file trong cùng thời điểm, Lambda có thể bị kích hoạt dồn dập.

**Giảm thiểu:** sử dụng SQS làm buffer trung gian, giới hạn concurrency của Lambda, retry có kiểm soát và đẩy lỗi sang DLQ.

#### Rủi ro 3: API tài chính lỗi kết nối hoặc bị giới hạn request

Nguồn dữ liệu như yfinance/Yahoo Finance có thể lỗi tạm thời hoặc chặn request khi gọi quá nhiều.

**Giảm thiểu:** retry 2 lần, cache dữ liệu gần nhất trong S3, đưa message lỗi vào DLQ và kích hoạt CloudWatch Alarm.

#### Rủi ro 4: Khuyến nghị AI thiếu chính xác

AI có thể diễn giải quá mức hoặc đưa ra lập luận chưa phù hợp với dữ liệu.

**Giảm thiểu:** tách tính toán định lượng ra khỏi AI, ép output JSON có cấu trúc, dùng confidence score và bắt buộc Trader duyệt trước khi gửi khách hàng.

### 8. Kết quả kỳ vọng

#### Cải tiến kỹ thuật

Hệ thống kỳ vọng xây dựng được workflow bất đồng bộ có khả năng chống lỗi tốt, gồm ingestion theo lịch, xử lý qua SQS, phân tích bằng Bedrock, lưu kết quả vào DynamoDB và cảnh báo qua CloudWatch/SNS.

#### Giá trị thực tiễn

Trader có một trợ lý AI hỗ trợ tổng hợp dữ liệu, giải thích tín hiệu và tạo khuyến nghị có thể kiểm duyệt. Giải pháp giúp tiết kiệm thời gian phân tích, tăng tính nhất quán trong quy trình ra quyết định và vẫn giữ an toàn nhờ cơ chế Human-in-the-loop.

