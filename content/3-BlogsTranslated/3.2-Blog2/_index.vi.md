---
title: "Blog 2"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---



## AWS Cost & AI: Khi chạy cloud không còn chỉ là vấn đề kỹ thuật

**Link bài viết:** [Facebook - AWS Study Group FCJ](https://www.facebook.com/groups/awsstudygroupfcj/permalink/2199844680780492/)

Trong quá trình học và thực hành trên AWS, giai đoạn đầu thường xoay quanh các câu hỏi kỹ thuật: làm sao deploy application lên EC2, cấu hình backend như thế nào, server có chạy ổn không, API có phản hồi đúng không. Tuy nhiên, khi hệ thống bắt đầu hoạt động ổn định hơn, một vấn đề khác xuất hiện rõ ràng hơn: chi phí vận hành trên cloud.

Song song với việc triển khai backend, nhóm cũng bắt đầu tìm hiểu các dịch vụ AI trên AWS như **Amazon Bedrock**, **Amazon SageMaker** và một số AWS AI Services như **Amazon Comprehend**. Từ đó, nhóm nhận ra rằng cloud không chỉ là “deploy được hay không”, mà còn là “chạy như vậy tốn bao nhiêu tiền mỗi ngày”.

---

## Bối cảnh hệ thống thực hành

Hệ thống thực hành ban đầu khá đơn giản:

- EC2 Ubuntu chạy backend Node.js.
- Một số API xử lý logic ứng dụng.
- Request và logging được dùng liên tục trong quá trình test.
- Một số thử nghiệm mở rộng có liên quan đến AI service.

Ở giai đoạn đầu, vì còn nằm trong AWS Free Tier, nhóm khá chủ quan với suy nghĩ rằng EC2 nhỏ có thể chạy thoải mái. Nhưng khi thời gian test tăng lên, nhiều yếu tố bắt đầu ảnh hưởng đến chi phí: EC2 uptime 24/7, log phát sinh liên tục, EBS tăng dung lượng theo thời gian, tài nguyên phụ trợ quên tắt, và các API AI được gọi nhiều hơn dự kiến.

![Kiến trúc thực hành AWS Cost và AI](/images/3-BlogsTranslated/3.2-Blog2/aws-cost-ai-architecture.png)

---

## Free Tier không có nghĩa là miễn phí mãi

Một hiểu lầm phổ biến khi mới dùng AWS là nghĩ Free Tier đồng nghĩa với không tốn tiền. Thực tế, Free Tier chỉ miễn phí trong một giới hạn nhất định về thời gian và mức sử dụng. Khi vượt ngưỡng, AWS sẽ bắt đầu tính phí ngay.

Trong quá trình thực hành, chi phí có thể phát sinh từ các tình huống rất quen thuộc:

- EC2 chạy liên tục mà không shutdown.
- Tạo thêm tài nguyên để test nhưng quên xóa.
- EBS volume vẫn tồn tại sau khi không còn dùng instance.
- Log và request tăng dần theo thời gian.
- Dịch vụ AI phát sinh chi phí theo request hoặc lượng dữ liệu xử lý.

Điểm quan trọng là các khoản nhỏ này có thể cộng dồn. Nếu không theo dõi thường xuyên, người dùng rất dễ phát hiện muộn.

---

## Khi AI được đưa vào hệ thống

Khác với EC2, chi phí của các dịch vụ AI thường không chỉ phụ thuộc vào thời gian chạy. Nhiều dịch vụ AI tính phí theo số request, số token, hoặc lượng dữ liệu được phân tích.

Ví dụ:

- **Amazon Comprehend** có thể tính theo lượng text được xử lý.
- **Amazon Bedrock** thường liên quan đến input/output token khi gọi model.
- **Amazon SageMaker** có thể phát sinh chi phí theo instance, endpoint, notebook hoặc training job.

Một API call nhỏ có thể không đáng kể. Nhưng khi test liên tục, prompt dài hơn, dữ liệu nhiều hơn hoặc gọi model nhiều lần, chi phí có thể tăng nhanh hơn dự kiến. Vì vậy, khi đưa AI vào hệ thống, cần thiết kế giới hạn sử dụng ngay từ đầu.

---

## Nguyên nhân khiến chi phí tăng nhanh

### 1. Chưa kiểm soát tốt tài nguyên đang chạy

Trong giai đoạn học, nhóm thường tập trung vào việc “làm cho chạy được” nên dễ bỏ qua trạng thái tài nguyên. EC2 không được stop sau giờ test, EBS volume không được dọn, hoặc một số tài nguyên phụ trợ vẫn còn chạy dù không còn cần thiết.

### 2. Thiếu monitoring chi phí

Ban đầu nhóm chưa sử dụng đầy đủ các công cụ như **AWS Budgets**, **Billing Alarm** hoặc **Cost Explorer**. Khi thiếu dashboard và cảnh báo, rất khó biết hệ thống đang tiêu bao nhiêu tiền mỗi ngày.

### 3. Thử nghiệm AI chưa có giới hạn rõ ràng

Các thử nghiệm với AI service nếu không có sandbox riêng, không giới hạn số request và không đặt budget alert thì rất dễ vượt mức dự kiến. Với AI, việc “test thêm vài lần” có thể tạo ra chi phí rõ rệt hơn so với các dịch vụ hạ tầng cơ bản.

---

## Hướng giải quyết và tối ưu chi phí

### Kiểm soát EC2 và tài nguyên phụ trợ

Nhóm bắt đầu thay đổi cách sử dụng EC2 theo hướng chỉ bật khi cần test, stop instance sau khi sử dụng và xóa các resource không còn cần thiết. Với các môi trường học tập, có thể dùng lịch tự động để tắt instance ngoài giờ làm việc.

### Thiết lập AWS Cost Management

Các công cụ quản lý chi phí nên được bật sớm:

- **AWS Budgets** để đặt ngưỡng chi phí.
- **Billing Alarm** để nhận cảnh báo khi vượt mức.
- **Cost Explorer** để theo dõi chi phí theo ngày, theo service và theo tag.

Những công cụ này giúp chuyển từ việc “đợi hóa đơn” sang chủ động quan sát chi phí.

### Tách môi trường AI sandbox

Thay vì thử AI trực tiếp trong luồng chính của hệ thống, nên tạo môi trường sandbox riêng cho các thí nghiệm. Môi trường này cần có giới hạn request, giới hạn quyền truy cập và budget alert riêng để giảm rủi ro phát sinh chi phí ngoài ý muốn.

### Hiểu logic tính phí của từng service

Mỗi dịch vụ AWS có cách tính phí khác nhau:

- EC2 thường tính theo thời gian chạy.
- Storage tính theo dung lượng lưu trữ.
- AI service tính theo request, token hoặc dữ liệu xử lý.
- Load Balancer, NAT Gateway, endpoint hoặc log cũng có thể tạo chi phí phụ.

Vì vậy, không thể dùng một cách suy nghĩ chung cho mọi dịch vụ. Trước khi bật một service mới, cần đọc pricing model và xác định giới hạn sử dụng.

---

## Góc nhìn thực tế về AWS AI

AWS AI rất mạnh ở khả năng tích hợp với hệ sinh thái AWS. Backend có thể gọi service thông qua SDK, kết hợp với IAM, VPC Endpoint, logging và monitoring. Tuy nhiên, sức mạnh này đi kèm trách nhiệm kiểm soát chi phí.

Đặc biệt với generative AI, câu hỏi không chỉ là “có gọi được model không”, mà còn là:

- Mỗi request tốn bao nhiêu?
- Prompt có cần dài như vậy không?
- Có nên cache kết quả không?
- Có cần giới hạn số lần gọi API không?
- Có cảnh báo khi vượt budget chưa?

Nếu các câu hỏi này được đặt ra từ đầu, hệ thống sẽ dễ vận hành hơn khi mở rộng.

---

## Bài học rút ra

Cloud không chỉ là kỹ thuật deploy, mà còn là vận hành. Một hệ thống chạy được nhưng không được theo dõi chi phí thì vẫn chưa thật sự sẵn sàng.

AI cũng không “miễn phí” như cảm giác ban đầu. Càng test nhiều, prompt càng dài, dữ liệu càng lớn thì chi phí càng cần được kiểm soát.

Monitoring nên là phần bắt buộc, không phải phần thêm sau. Không có monitoring đồng nghĩa với việc không biết hệ thống đang tiêu bao nhiêu, không kiểm soát được scale và dễ vượt budget mà không nhận ra.

Automation cũng là một bước nâng cấp tư duy. Thay vì tắt EC2 thủ công, có thể dùng scheduler, EventBridge hoặc lifecycle automation để chuyển từ cách dùng AWS thủ công sang cách vận hành có kiểm soát.

---

## Kết luận

Qua quá trình thực hành AWS Cost và tìm hiểu thêm các dịch vụ AI, nhóm hiểu rõ hơn rằng AWS không chỉ là nơi deploy ứng dụng. Đây là một hệ sinh thái cần được quản lý như một hệ thống vận hành thực tế, trong đó chi phí, hiệu năng và thiết kế kiến trúc luôn đi cùng nhau.

Từ một backend chạy trên EC2 đến các thử nghiệm với AI service, bài học quan trọng nhất là phải thiết kế hệ thống theo hướng cost-aware ngay từ đầu. Khi đó, cloud không chỉ chạy được, mà còn chạy một cách bền vững và có kiểm soát.

