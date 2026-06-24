---
title: "Worklog Tuần 1"
date: 2026-04-23
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Tổng quan Mục tiêu và Kế hoạch Tuần 01
Bắt đầu lộ trình First Cloud AI Journey (FCAJ) là giai đoạn quan trọng để thiết lập "văn hóa Builder" và định hình tư duy kỹ thuật chuyên nghiệp. Thay vì tiếp cận với tư cách một người dùng cuối, học viên được yêu cầu chuyển đổi sang vai trò **"Builder"** (Người kiến tạo) và **"Troubleshooter"** (Người giải quyết sự cố). Đây là nền tảng cốt lõi trong triết lý vận hành của AWS, nơi mọi vấn đề kỹ thuật đều là cơ hội để tối ưu hóa hệ thống.

Việc thiết lập tài khoản, cấu hình bảo mật đa lớp (MFA) và quản trị nhóm trong tuần đầu tiên không chỉ là các thao tác kỹ thuật đơn thuần, mà là bước chuẩn bị cho mục tiêu **Operational Excellence** (Vận hành xuất sắc). Nếu nền tảng quản trị không vững chắc, rủi ro về an ninh và chi phí sẽ trở thành rào cản lớn trong suốt lộ trình 12 tuần thực tập.

> **So What:** Sự kết hợp giữa lý thuyết điện toán đám mây và thực hành quản trị tài khoản giúp học viên làm quen với mô hình **Pay-as-you-go**. Việc chuyển dịch từ tư duy hạ tầng truyền thống (On-premises) sang Cloud đòi hỏi khả năng kiểm soát tài nguyên thời gian thực để giảm thiểu rủi ro tài chính và vận hành.

---

## 2. Nhật ký Công việc Chi tiết (Worklog)
Dưới đây là bảng tổng hợp các hoạt động đã thực hiện từ ngày 17/04 đến 23/04:

| Thứ / Ngày | Nội dung công việc | Chi tiết nhiệm vụ | Kết quả đạt được | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Thứ 6 (17/04) | Kickoff Workshop | Tham gia khai mạc; tiếp nhận tầm nhìn FCAJ và 06 nguyên tắc Leadership. | Hiểu rõ mục tiêu chương trình; thấm nhuần tư duy Builder & Troubleshooter. |  |
| Thứ 7 (18/04) | Kết nối cộng đồng | Hình thành nhóm 5 thành viên; thiết lập kênh liên lạc WhatsApp/LinkedIn. | Hoàn tất cấu trúc nhóm; sẵn sàng cho các bài Lab đòi hỏi sự phối hợp. | [Web.whatsapp.com](https://web.whatsapp.com/) |
| Chủ Nhật (19/04) | Lý thuyết Cloud cơ bản | Nghiên cứu Global Infrastructure (Region, AZ, Edge Location) và Management Console. | Nắm vững hạ tầng vật lý của AWS; hiểu cách giảm độ trễ qua Edge Locations tại VN. | [Youtube Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox3TSYFbN1DNX7NZgTVXNj3x) |
| Thứ 2 (20/04) | Thiết lập hạ tầng gốc | Tạo tài khoản AWS Free Tier; kích hoạt MFA cho Root Account; nhận $100 credit đầu tiên. | Tài khoản bảo mật đúng Best Practice; sẵn sàng nguồn vốn thực hành. | [AWS Study Group](https://000001.awsstudygroup.com/vi/) |
| Thứ 3 (21/04) | Tối ưu hóa chi phí | Triển khai Task 1 (EC2) và Task 3 (AWS Budgets). | Hoàn thành thiết lập cảnh báo ngân sách để tránh "vung tay quá trán". | [AWS Study Group](https://000001.awsstudygroup.com/vi/) |
| Thứ 4 (22/04) | Hoàn thiện nhiệm vụ tín dụng | Thực hiện Task 2 (Bedrock), Task 4 (Lambda), và Task 5 (RDS Aurora). | Hoàn thành 5 nhiệm vụ để nhận thêm $100 credit; biết cách raise support case. | [AWS Study Group](https://000001.awsstudygroup.com/vi/) |
| Thứ 5 (23/04) | Quản trị IAM & AI Kiro | Nghiên cứu lý thuyết AWS Kiro và quản trị quyền truy cập IAM (User, Group, Role). | Nắm vững nguyên tắc đặc quyền tối thiểu (Least Privilege) và Spec-driven dev. | [AWS Study Group](https://000002.awsstudygroup.com/vi/) |

> **So What:** Trình tự công việc phản ánh sự chuyển dịch từ việc kết nối cộng đồng sang làm chủ hạ tầng. Đây là logic thực tiễn: một Builder cần có đội ngũ hỗ trợ trước khi bắt tay vào quản lý tài nguyên theo mô hình chi phí linh hoạt thay vì đầu tư cố định (CAPEX) như truyền thống.

---

## 3. Chiến lược Kích hoạt và Quản lý $200 AWS Credit
Công việc quản trị chi phí là trụ cột Cost Optimization trong AWS Well-Architected Framework. Sở hữu ngân sách $200 giúp loại bỏ rào cản tài chính khi tiếp cận các dịch vụ cao cấp.

**Quy trình 2 bước nhận $200 Credit:**
- **Giai đoạn 1:** Đăng ký tài khoản AWS Free Tier với thông tin thanh toán hợp lệ để nhận ngay $100 credit tự động vào Billing Console.
- **Giai đoạn 2:** Hoàn thành 5 nhiệm vụ trong widget “Explore AWS” trên Console Home để nhận thêm $100 credit (mỗi nhiệm vụ trị giá $20).

**Chi tiết các dịch vụ triển khai trong nhiệm vụ "kiếm tiền":**

| Nhiệm vụ | Dịch vụ & Cấu hình cụ thể | Mức Credit | Mục tiêu kỹ thuật |
| --- | --- | --- | --- |
| Task 1 | Amazon EC2 (Instance Test) | $20 | Quản lý máy ảo và Key Pair (.pem). |
| Task 2 | Amazon Bedrock (Claude 3 Haiku) | $20 | Trải nghiệm GenAI với model tối ưu hiệu suất/chi phí. |
| Task 3 | AWS Budgets | $20 | Thiết lập ngưỡng cảnh báo (Alert) qua Email. |
| Task 4 | AWS Lambda (Blueprints) | $20 | Triển khai hàm Serverless không cần quản lý máy chủ. |
| Task 5 | Amazon RDS (Aurora PostgreSQL - Easy Create) | $20 | Thiết lập Managed Database chuẩn doanh nghiệp. |

![Thiết lập AWS Budgets thành công](/images/1-Worklog/Week1/budget-success.png)

**Pro Tips từ Architect:**
- Luôn ưu tiên chọn kích thước máy chủ nhỏ nhất (ví dụ: `t3.micro`) để tiết kiệm credit.
- **Clean up ngay lập tức:** Thực hiện Terminate EC2 và Delete DB Cluster ngay sau khi nhận xác nhận hoàn thành task để tránh chi phí duy trì tài nguyên nhàn rỗi.

> **So What:** Việc tối ưu hóa ngân sách $200 cho phép học viên thực nghiệm với Amazon Bedrock – một dịch vụ AI tốn kém – mà không lo ngại về hóa đơn cá nhân, từ đó tập trung hoàn toàn vào việc xây dựng giải pháp AI.

---

## 4. Phân tích Kỹ thuật: Quản trị Danh tính và Truy cập (IAM)
IAM là "chu vi bảo mật" (Security Perimeter) quan trọng nhất trên AWS. Việc thực thi IAM đúng cách giúp ngăn chặn các cuộc tấn công leo thang đặc quyền.

**Thành phần cốt lõi của IAM:**

| Thành phần | Đặc điểm kỹ thuật | Ghi chú từ Source |
| --- | --- | --- |
| **IAM User** | Thực thể định danh cá nhân/ứng dụng. | Không nên sử dụng Root Account cho tác vụ hàng ngày. |
| **IAM Group** | Nhóm người dùng có chung quyền hạn. | Giúp quản trị tập trung (ví dụ: AdminGroup). |
| **IAM Policy** | Tài liệu JSON định nghĩa quyền (Allow/Deny). | Inline Policy: Gán trực tiếp cho 1 User, không thể tái sử dụng. |
| **IAM Role** | Định danh tạm thời (Assume Role). | Cung cấp quyền hạn có thời hạn, tự động luân chuyển credential. |

**Chiến lược "Switch Role" - Best Practice trong Doanh nghiệp:** Thay vì cấp quyền trực tiếp cho người dùng, chúng ta sử dụng `OperatorUser` (không có quyền hạn) và thực hiện Switch Role sang `AdminRole`.
- **Cấu hình:** Cần đính kèm một Inline Policy tên là `AllowSwitchAdminPolicy` vào `OperatorUser`.
- **Kỹ thuật:** Trong JSON policy, phải chỉ định đúng Account ID và ARN của AdminRole để thiết lập Trust Relationship.
- **Giám sát:** Mọi sự kiện chuyển đổi vai trò đều được ghi lại trong AWS CloudTrail, giúp truy vết (Audit) ai đã thực hiện quyền Admin tại thời điểm nào.

> **So What:** Việc áp dụng Nguyên tắc đặc quyền tối thiểu (Least Privilege) và cơ chế Switch Role giúp bảo vệ tài khoản khỏi các rủi ro lộ lọt mật khẩu, đảm bảo chỉ những phiên làm việc cần thiết mới có quyền cao nhất.

---

## 5. Khám phá Hệ sinh thái AWS Kiro (Lý thuyết)
Generative AI đang tái định nghĩa vòng đời phát triển phần mềm (SDLC). AWS Kiro không chỉ là công cụ hỗ trợ viết code mà là một trợ lý kiến trúc toàn diện.

**Các thành phần cốt lõi của Kiro:**
- **Kiro IDE:** Hỗ trợ phát triển từ prototype đến production qua giao diện chat hoặc đặc tả hệ thống.
- **Kiro CI:** Công cụ dòng lệnh kế thừa sức mạnh từ Amazon QCI, cho phép phân tích lỗi và truy vết bug (chase bug) ngay tại Terminal mà không cần mở IDE.
- **Agent Hook:** Tính năng ủy quyền tác vụ tự động. Builder có thể dùng Ngôn ngữ tự nhiên để thiết lập trigger (Ví dụ: *"Mỗi khi lưu file, hãy tự động cập nhật thay đổi vào changelog.md"*).
- **Autonomous Agent:** Các agent có khả năng tự suy nghĩ, lập kế hoạch và thực thi các tác vụ phức tạp end-to-end.
- **Spec-driven Development:** Đây là xu hướng quan trọng nhất. Trong kỷ nguyên AI, việc viết code thuần túy dần được thay thế bằng việc mô tả chi tiết yêu cầu (Spec). Nếu Builder cung cấp một bản đặc tả (Requirement, Architecture) tốt, Kiro sẽ tạo ra mã nguồn chính xác và tối ưu hơn.

*Ghi chú: Trong Tuần 1, học viên chỉ tập trung nghiên cứu lý thuyết để hiểu cách Kiro tóm tắt kiến thức và đẩy nhanh tiến độ dự án.*

---

## 6. Tổng kết và Đánh giá Kết quả Tuần 1
### 6.1. Kỹ năng Nhóm và Giao tiếp (Soft Skills)
- **Thiết lập kết nối:** Hoàn thành định vị thương hiệu cá nhân trên LinkedIn và kết nối thành công với cộng đồng AWS Study Group và mạng lưới FCAJ 2026.
- **Phối hợp đồng đội:** Tham gia hình thành nhóm 5 thành viên, thiết lập quy trình làm việc và kênh liên lạc (WhatsApp/Zalo). Chủ động thảo luận để giải quyết các vấn đề phát sinh trong quá trình thiết lập tài khoản.
- **Tư duy Leadership:** Tiếp nhận và bắt đầu áp dụng 06 nguyên tắc Leadership vào quy trình học tập, đặc biệt là tư duy "Learn and Be Curious" và "Ownership" đối với tài nguyên cá nhân.

### 6.2. Quản trị Tài nguyên và Chi phí (FinOps)
- **Tối ưu hóa ngân sách:** Nắm vững trụ cột Cost Optimization. Đã kích hoạt thành công gói $200 AWS Credit, biến đây thành "nguồn vốn" để thực nghiệm các dịch vụ cao cấp mà không tốn phí cá nhân.
- **Giám sát thời gian thực:** Triển khai **AWS Budgets** với ngưỡng 1$ và cấu hình cảnh báo Email. Điều này giúp chuyển dịch từ quản lý chi phí thụ động sang chủ động (Proactive Monitoring).
- **Quy trình Clean-up:** Thiết lập thói quen kỹ thuật "Dùng xong là xóa" (Terminate EC2, Delete RDS Cluster). Hiểu rõ sự khác biệt giữa tài nguyên tính phí theo giờ và tài nguyên tính phí theo dung lượng lưu trữ.

### 6.3. Bảo mật và Quản trị Hệ thống (Security & Infrastructure)
- **Chu vi bảo mật (Security Perimeter):** Làm chủ **AWS IAM**. Áp dụng thành công nguyên tắc "Least Privilege" (Đặc quyền tối thiểu) bằng cách phân tách quyền hạn giữa AdminGroup và InternGroup.
- **Bảo mật danh tính:** Triển khai MFA cho Root Account và các IAM User. Thực hành chiến lược "Switch Role" – một Best Practice trong doanh nghiệp để giảm thiểu rủi ro lộ lọt Credential.
- **Hạ tầng toàn cầu:** Nắm vững cấu trúc Global Infrastructure (Region, AZ, Edge Location). Hiểu cách chọn Region Singapore (ap-southeast-1) để tối ưu hóa độ trễ cho người dùng tại Việt Nam.

### 6.4. Năng lực Kỹ thuật và Tư duy AI (Technical & AI Mindset)
- **Làm chủ Compute:** Thực hành đa dạng các mô hình tính toán từ máy chủ ảo truyền thống (**EC2**) đến kiến trúc hiện đại không máy chủ (**Serverless Lambda**).
- **Trải nghiệm GenAI:** Tiếp cận sớm với **Amazon Bedrock**. Sử dụng các mô hình như Claude 3 Haiku và Titan Text để hiểu cách tích hợp AI vào ứng dụng thực tế.
- **Dịch chuyển SDLC:** Bắt đầu làm quen với phương pháp **Spec-driven Development**. Hiểu được tầm quan trọng của việc viết bản đặc tả (Spec) tốt để AI (như hệ sinh thái Kiro) có thể tạo ra mã nguồn tối ưu, giúp tăng tốc độ phát triển dự án lên gấp nhiều lần.

---
**Đánh giá chung:** Hoàn thành 100% mục tiêu đề ra. Cảm thấy tự tin hơn trong việc quản trị hạ tầng Cloud và sẵn sàng cho các bài Lab chuyên sâu về dữ liệu và AI trong các tuần tiếp theo.