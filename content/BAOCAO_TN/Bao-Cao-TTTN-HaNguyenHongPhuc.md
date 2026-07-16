# BÁO CÁO THỰC TẬP TỐT NGHIỆP

---

### **TRƯỜNG ĐẠI HỌC CÔNG NGHỆ TP.HCM (HUTECH)**
### **KHOA CÔNG NGHỆ THÔNG TIN**

<br>
<br>

<div align="center">

# BÁO CÁO THỰC TẬP TỐT NGHIỆP

## **ĐỀ TÀI: HỆ THỐNG PHÂN TÍCH VÀ CẢNH BÁO GIÁ CỔ PHIẾU (STOCK ALERTS SYSTEM)**
### **GIẢI PHÁP AWS SERVERLESS & AI AGENT CHO TRADER**

</div>

<br>
<br>
<br>

#### **Thông tin sinh viên thực hiện:**
*   **Họ và tên:** Hà Nguyễn Hồng Phúc
*   **Mã số sinh viên (MSSV):** 2280602427
*   **Lớp:** 22DTHE9
*   **Ngành:** Công nghệ thông tin
*   **Chuyên ngành:** Công nghệ phần mềm

#### **Đơn vị thực tập:**
*   **Tên đơn vị:** Công ty TNHH Amazon Web Services Việt Nam (AWS Việt Nam)
*   **Cán bộ hướng dẫn tại đơn vị:** Nguyễn Gia Hưng (Email: hunggia@amazon.com)

#### **Giảng viên hướng dẫn tại trường:**
*   **Họ và tên:** Nguyễn Đắc Dzự Trình (Email: ndd.trinh@hutech.edu.vn)

<br>
<br>

<div align="center">
  
**TP. HỒ CHÍ MINH, NĂM 2026**

</div>

---
\pagebreak

## **LỜI CẢM ƠN**

Lời đầu tiên, em xin gửi lời cảm ơn chân thành và sâu sắc nhất đến Ban Giám hiệu, Ban Chủ nhiệm Khoa Công nghệ thông tin cùng toàn thể Quý Thầy Cô trường **Đại học Công nghệ TP.HCM (HUTECH)**. Trong suốt quá trình học tập tại trường, Thầy Cô đã truyền đạt những kiến thức chuyên môn quý báu, tạo dựng nền tảng tư duy logic và kỹ năng lập trình vững chắc, giúp em có đủ hành trang vững vàng để bước vào môi trường doanh nghiệp thực tế. 

Đặc biệt, em xin gửi lời cảm ơn sâu sắc đến thầy **Nguyễn Đắc Dzự Trình** - Giảng viên hướng dẫn thực tập tại trường, người đã luôn định hướng, sát sao theo dõi, đóng góp ý kiến chuyên môn tận tình và hướng dẫn em hoàn thành các cột mốc báo cáo đúng thời hạn quy định.

Em cũng xin bày tỏ lòng biết ơn chân thành nhất tới Ban Giám đốc và toàn thể các anh chị đồng nghiệp tại **Công ty TNHH Amazon Web Services Việt Nam (AWS Việt Nam)**. Công ty đã tiếp nhận, tạo điều kiện thuận lợi và mở ra cơ hội tuyệt vời để em được học tập và trải nghiệm thực tế trong một môi trường công nghệ điện toán đám mây năng động, chuyên nghiệp hàng đầu thế giới.

Em xin gửi lời cảm ơn đặc biệt đến anh **Nguyễn Gia Hưng** - Cán bộ hướng dẫn trực tiếp tại doanh nghiệp AWS Việt Nam. Anh đã luôn tận tình hướng dẫn, hỗ trợ kỹ thuật, khích lệ tư duy sáng tạo, chia sẻ kinh nghiệm thực tế về tối ưu hóa chi phí (FinOps) và bảo mật đám mây, giúp em hoàn thành tốt các nhiệm vụ được giao cùng dự án tốt nghiệp **Stock Alerts System**.

Dù đã có nhiều nỗ lực học hỏi, nghiên cứu và triển khai hệ thống, bản báo cáo này chắc chắn không tránh khỏi những thiếu sót thiếu chuyên nghiệp trong cách diễn đạt hoặc kỹ thuật. Em rất mong nhận được những nhận xét, đóng góp ý kiến quý báu từ Quý Thầy Cô và các anh chị tại doanh nghiệp để bản thân ngày càng hoàn thiện hơn.

*Em xin chân thành cảm ơn!*

**Sinh viên thực hiện**  
*(Ký và ghi rõ họ tên)*  
**Hà Nguyễn Hồng Phúc**

---
\pagebreak

## **HỒ SƠ XÁC NHẬN THỰC TẬP**

### **1. Phiếu đánh giá của đơn vị thực tập**
Phiếu đánh giá đã được hoàn thành, ký và đóng dấu xác nhận chính thức từ đại diện Công ty TNHH Amazon Web Services Việt Nam:
*   Đường dẫn xem hồ sơ gốc: [Phieu-Danh-gia-cua-Don-vi-TT-HaNguyenHongPhuc.pdf](file:///d:/AWS/aws-fcj-worklog-hongphuc/content/BAOCAO_TN/Phieu-Danh-gia-cua-Don-vi-TT-HaNguyenHongPhuc.pdf)

### **2. Phiếu theo dõi tiến độ Thực tập Tốt nghiệp**
Phiếu theo dõi tiến độ chi tiết của đợt thực tập kéo dài 12 tuần (Từ ngày 17/04/2026 đến ngày 10/07/2026):
*   Đường dẫn xem hồ sơ gốc: [PhieuTheoDoiTDTT_2280602427_HaNguyenHongPhuc_Tuan10.pdf](file:///d:/AWS/aws-fcj-worklog-hongphuc/content/BAOCAO_TN/PhieuTheoDoiTDTT_2280602427_HaNguyenHongPhuc_Tuan10.pdf)

---
\pagebreak

## **MỤC LỤC**

*   **LỜI CẢM ƠN**
*   **HỒ SƠ XÁC NHẬN THỰC TẬP**
*   **DANH MỤC CÁC KÝ HIỆU, CHỮ VIẾT TẮT**
*   **CHƯƠNG 1: GIỚI THIỆU VỀ ĐƠN VỊ THỰC TẬP (AWS VIỆT NAM)**
    *   1.1 Lịch sử hình thành và phát triển
    *   1.2 Lĩnh vực hoạt động và dịch vụ cốt lõi
    *   1.3 Cơ cấu tổ chức hành chính
    *   1.4 Văn hóa doanh nghiệp và môi trường làm việc
*   **CHƯƠNG 2: NỘI DUNG CÔNG VIỆC ĐƯỢC PHÂN CÔNG (THEO TIẾN ĐỘ 12 TUẦN)**
    *   2.1 Vị trí thực tập và mục tiêu chung
    *   2.2 Chi tiết nhật ký công việc theo tuần
*   **CHƯƠNG 3: PHƯƠNG PHÁP THỰC HIỆN DỰ ÁN TỐT NGHIỆP: STOCK ALERTS SYSTEM**
    *   3.1 Tổng quan bài toán kinh doanh và yêu cầu hệ thống
    *   3.2 Sơ đồ kiến trúc và luồng xử lý dữ liệu (Architecture & Data Flow)
    *   3.3 Triển khai hạ tầng kỹ thuật Serverless & AI Agent
*   **CHƯƠNG 4: KẾT QUẢ ĐẠT ĐƯỢC VÀ TỰ ĐÁNH GIÁ**
    *   4.1 Kết quả kiểm thử và nghiệm thu hệ thống
    *   4.2 Xử lý sự cố kỹ thuật thực tế (Bedrock Quota Limit)
    *   4.3 Kết quả tự đúc kết sau đợt thực tập
    *   4.4 Các hoạt động đóng góp cho cộng đồng và doanh nghiệp
    *   4.5 Bản tự đánh giá kết quả thực tập (Bảng 12 tiêu chí)
*   **PHỤ LỤC**

---
\pagebreak

## **DANH MỤC CÁC KÝ HIỆU, CHỮ VIẾT TẮT**

| Ký hiệu / Chữ viết tắt | Ý nghĩa / Tên đầy đủ |
| :-: | --- |
| **AWS** | Amazon Web Services |
| **FCAJ** | First Cloud AI Journey |
| **FCJ** | First Cloud Journey |
| **EC2** | Elastic Compute Cloud |
| **S3** | Simple Storage Service |
| **SQS** | Simple Queue Service |
| **DLQ** | Dead-Letter Queue |
| **RDS** | Relational Database Service |
| **DynamoDB** | Amazon DynamoDB (Database NoSQL) |
| **API** | Application Programming Interface |
| **WAF** | Web Application Firewall |
| **KMS** | Key Management Service |
| **IAM** | Identity and Access Management |
| **FinOps** | Financial Operations (Tối ưu hóa tài chính Cloud) |
| **MFA** | Multi-Factor Authentication (Bảo mật đa nhân tố) |
| **RSI** | Relative Strength Index (Chỉ số sức mạnh tương đối) |
| **MACD** | Moving Average Convergence Divergence |
| **MA** | Moving Average (Đường trung bình động) |

---
\pagebreak

## **CHƯƠNG 1: GIỚI THIỆU VỀ ĐƠN VỊ THỰC TẬP (AWS VIỆT NAM)**

### **1.1 Lịch sử hình thành và phát triển**
Amazon Web Services (AWS) là công ty con của tập đoàn công nghệ đa quốc gia Amazon, chuyên cung cấp các nền tảng điện toán đám mây theo mô hình Pay-as-you-go. Ra đời từ năm 2006, AWS nhanh chóng trở thành đơn vị đi đầu thế giới về dịch vụ đám mây, phục vụ hàng triệu khách hàng từ các dự án startup nhỏ đến các tập đoàn đa quốc gia và các cơ quan chính phủ trên toàn cầu.

Nhận thấy tiềm năng phát triển số mạnh mẽ của thị trường Đông Nam Á, đặc biệt là Việt Nam, Công ty TNHH Amazon Web Services Việt Nam đã được thành lập nhằm mang các giải pháp công nghệ đám mây chuẩn quốc tế đến gần hơn với cộng đồng doanh nghiệp trong nước. AWS Việt Nam đóng vai trò hỗ trợ đắc lực cho các đơn vị nội địa chuyển đổi số, cung cấp tư vấn kỹ thuật chuyên sâu và tổ chức các chương trình đào tạo nâng cao năng lực công nghệ thông tin cho nhân lực Việt Nam.

### **1.2 Lĩnh vực hoạt động và dịch vụ cốt lõi**
AWS Việt Nam hoạt động chính trong lĩnh vực dịch vụ công nghệ thông tin, tập trung vào việc tư vấn và thúc đẩy ứng dụng điện toán đám mây. Các giải pháp dịch vụ cốt lõi do AWS cung cấp và hỗ trợ tại thị trường Việt Nam bao gồm:
1.  **Dịch vụ tính toán đám mây (Compute):** Amazon EC2, AWS Lambda, Elastic Beanstalk.
2.  **Lưu trữ dữ liệu (Storage):** Amazon S3, Amazon EBS, Amazon EFS.
3.  **Cơ sở dữ liệu (Databases):** Amazon RDS (Aurora, MySQL), Amazon DynamoDB.
4.  **Mạng và phân phối nội dung (Networking & CDN):** Amazon VPC, Amazon Route 53, Amazon CloudFront.
5.  **Bảo mật và Danh tính (Security & Identity):** AWS IAM, AWS WAF, AWS KMS, Amazon Cognito.
6.  **Trí tuệ nhân tạo & Học máy (AI/ML):** Amazon Bedrock, Amazon SageMaker, Amazon Comprehend.

### **1.3 Cơ cấu tổ chức hành chính**
Tại Việt Nam, cơ cấu tổ chức của AWS được chia thành các nhóm chuyên môn cốt lõi nhằm tối ưu hóa dịch vụ cho khách hàng:
*   **Bộ phận Kinh doanh & Phát triển thị trường (Sales & Business Development):** Tìm kiếm và làm việc trực tiếp với khách hàng doanh nghiệp để tư vấn các gói giải pháp phù hợp.
*   **Bộ phận Giải pháp Kiến trúc (Solutions Architecture):** Hỗ trợ thiết kế kiến trúc hệ thống đám mây tối ưu, bảo mật và tiết kiệm chi phí cho doanh nghiệp.
*   **Bộ phận Hỗ trợ Kỹ thuật & Vận hành (Technical Support & Operations):** Giải quyết các sự cố kỹ thuật và tối ưu hóa vận hành hệ thống đám mây.
*   **Bộ phận Phát triển Cộng đồng & Đào tạo (Developer Relations & Training):** Tổ chức các workshop, sự kiện công nghệ và các bootcamp học tập như First Cloud AI Journey (FCAJ).

### **1.4 Văn hóa doanh nghiệp và môi trường làm việc**
Văn hóa của AWS được định hình sâu sắc bởi **16 Nguyên tắc Lãnh đạo (Leadership Principles)**, trong đó nổi bật là tư duy *Customer Obsession* (Ám ảnh vì khách hàng) và *Bias for Action* (Thiên hướng hành động). Môi trường làm việc thực tế tại văn phòng AWS Việt Nam (Tọa lạc tại Bitexco Financial Tower, TP.HCM) vô cùng chuyên nghiệp, cởi mở và khuyến khích sự sáng tạo.

Đối với một thực tập sinh, chương trình đào tạo nhấn mạnh vào hai tư duy cốt lõi:
*   **Tư duy Builder:** Tự mình bắt tay vào thiết kế, lập trình và xây dựng các hệ thống từ cơ bản đến phức tạp, không ngại khó khăn và liên tục đổi mới sáng tạo.
*   **Tư duy Troubleshooter:** Rèn luyện khả năng phát hiện lỗi, đọc sâu logs hệ thống và giải quyết triệt để các sự cố vận hành dựa trên phân tích nguyên nhân gốc rễ (Root Cause Analysis).

---
\pagebreak

## **CHƯƠNG 2: NỘI DUNG CÔNG VIỆC ĐƯỢC PHÂN CÔNG (THEO TIẾN ĐỘ 12 TUẦN)**

### **2.1 Vị trí thực tập và mục tiêu chung**
*   **Vị trí:** Học viên Workforce Bootcamp - First Cloud AI Journey (FCAJ) tại AWS Việt Nam.
*   **Mục tiêu chung:** Nghiên cứu và nắm vững các dịch vụ hạ tầng, bảo mật và AI trên đám mây AWS; chuyển hóa các lý thuyết điện toán đám mây đã học trên giảng đường thành các kỹ năng thực tế thông qua các bài lab thực chiến và dự án tốt nghiệp cuối khóa.

### **2.2 Chi tiết nhật ký công việc theo tuần**
Dưới đây là bảng tổng hợp tiến độ công việc trong 12 tuần thực tập (Từ 17/04/2026 đến 10/07/2026) được trích xuất từ phiếu theo dõi tiến độ thực tế:

| Tuần | Thời gian | Nội dung công việc & Nhiệm vụ cụ thể | Kết quả đạt được |
| :-: | :-: | --- | --- |
| **1** | 17/04/2026 -<br>23/04/2026 | - Tham gia Workshop khai mạc chương trình FCAJ, tiếp cận tư duy "Builder" và "Troubleshooter".<br>- Khởi tạo tài khoản AWS Free Tier, kích hoạt bảo mật đa lớp (MFA) và thiết lập AWS Budgets để quản trị chi phí.<br>- Thực hành các nhiệm vụ kỹ thuật cơ bản trên Console: tạo máy ảo EC2, gọi API GenAI (Bedrock), triển khai hàm Lambda, thiết lập database RDS Aurora.<br>- Tìm hiểu hạ tầng vật lý toàn cầu (Region, AZ, Edge Location) và quản trị danh tính IAM theo nguyên tắc đặc quyền tối thiểu (Least Privilege). | - Hiểu rõ cấu trúc chương trình thực tập và kênh liên lạc nhóm.<br>- Kích hoạt tài khoản an toàn với ngân sách được cấu hình sẵn cảnh báo.<br>- Làm quen với giao diện quản trị AWS và hoàn thành các bài lab cơ bản.<br>- Nắm vững nguyên tắc phân quyền IAM bảo mật. |
| **2** | 24/04/2026 -<br>03/05/2026 | - Tiếp tục xem video hướng dẫn kỹ thuật do các Mentors AWS cung cấp.<br>- Thực hành các bài lab liên quan đến thiết lập và quản lý Amazon Virtual Private Cloud (VPC).<br>- Điền thông tin thực tập qua link biểu mẫu của công ty và nhận định hướng lên văn phòng. | - Nắm vững lý thuyết cơ bản về VPC, Subnet, Route Table và Internet Gateway.<br>- Hoàn tất các thủ tục đăng ký hành chính đợt thực tập. |
| **3** | 04/05/2026 -<br>10/05/2026 | - Cấu hình VPC Peering giữa VPC mặc định và HG VPC để kết nối nội bộ bảo mật qua mạng backbone của AWS.<br>- Thiết lập các quy tắc Network ACL (NACLs) và kích hoạt Cross-Peer DNS để tối ưu hóa phân giải tên miền giữa các mạng riêng biệt.<br>- Triển khai Hybrid DNS bằng cách cấu hình Route 53 Resolver (Inbound/Outbound Endpoints).<br>- Thiết lập Forwarding Rules và kết nối Microsoft AD để đồng bộ hóa giải pháp định danh trong mô hình lai. | - Thực hành thành công định tuyến mạng giữa các VPC an toàn.<br>- Kiểm soát lưu lượng ra/vào lớp mạng bằng NACL và bảo mật DNS.<br>- Thiết lập thành công hệ thống DNS kết nối môi trường lai (hybrid).<br>- Nắm vững nguyên lý đồng bộ danh tính Active Directory trên Cloud. |
| **4** | 11/05/2026 -<br>17/05/2026 | - Nghiên cứu dịch vụ AWS Backup và AWS SNS; cấu hình các kế hoạch sao lưu (Backup plan) tự động cho EBS, RDS, DynamoDB, EFS và thiết lập cảnh báo trạng thái qua cơ chế Pub/Sub.<br>- Thực hành cài đặt AWS CLI trên môi trường local, cấu hình credentials và chạy các lệnh quản trị S3, IAM, SNS, VPC.<br>- Nghiên cứu giải pháp AWS Transit Gateway định tuyến tập trung (Hub) thay thế VPC Peering truyền thống; thiết lập Transit Gateway Attachments liên kết 4 VPC riêng biệt.<br>- Cấu hình Transit Gateway Route Tables để thông suốt tuyến đường giữa các Availability Zones; kiểm thử kết nối giữa các EC2 Instance (t3.nano) và giải phóng tài nguyên. | - Thiết lập được quy trình sao lưu tự động và gửi thông báo lỗi qua email.<br>- Thành thạo sử dụng dòng lệnh AWS CLI để quản lý tài nguyên nhanh chóng.<br>- Hiểu và cấu hình được kiến trúc mạng Hub-and-Spoke quy mô lớn.<br>- Tối ưu hóa định tuyến mạng và dọn dẹp tài nguyên để tránh phát sinh chi phí. |
| **5** | 18/05/2026 -<br>24/05/2026 | - Nghiên cứu về Docker và quy trình đóng gói mã nguồn; cấu hình cơ sở dữ liệu Amazon RDS và triển khai ứng dụng đa container bằng Docker Compose trên Amazon EC2.<br>- Thiết lập và cấu hình quyền truy cập cho kho lưu trữ private Amazon Elastic Container Registry (ECR); đẩy Docker Image lên ECR.<br>- Tìm hiểu kiến trúc kết nối dữ liệu lai với AWS Storage Gateway; cấu hình File Shares của File Storage Gateway để đồng bộ tệp tin an toàn từ On-premise lên S3.<br>- Tham gia sự kiện công nghệ "AWS Vietnam Community Day 2026" (ngày 23/05) tại Bitexco Financial Tower. | - Đóng gói và chạy thành công ứng dụng đa container trên đám mây.<br>- Quản lý lưu trữ Docker Image an toàn trên dịch vụ ECR.<br>- Nắm vững cơ chế đồng bộ dữ liệu lai sử dụng Storage Gateway.<br>- Học hỏi kinh nghiệm thực tế về CloudFront và các giải pháp tối ưu hệ thống từ các doanh nghiệp lớn. |
| **6** | 25/05/2026 -<br>31/05/2026 | - Nghiên cứu cơ chế vận hành tự động hóa kiểm tra tuân thủ cấu hình của AWS Security Hub dựa trên các bộ tiêu chuẩn cốt lõi (AWS Foundational Security Best Practices, CIS AWS Foundations Benchmark, PCI DSS).<br>- Tìm hiểu phương thức tối ưu hóa chi phí vận hành cho máy chủ Amazon EC2; cấu hình Tag định danh tài nguyên và thiết lập IAM Role theo đặc quyền tối thiểu.<br>- Xây dựng và triển khai mã nguồn lập trình trên AWS Lambda Function để tự động hóa quy trình bật/tắt máy chủ EC2 theo lịch trình định sẵn nhằm tiết kiệm chi phí. | - Hiểu cách đánh giá điểm bảo mật hệ thống qua Security Hub.<br>- Áp dụng tốt các kỹ năng quản trị tài nguyên và tối ưu hóa FinOps.<br>- Triển khai thành công giải pháp tự động tắt máy ảo ngoài giờ làm việc qua Lambda, giảm lãng phí tài nguyên. |
| **7** | 01/06/2026 -<br>07/06/2026 | - Tham gia sự kiện công nghệ "AWS First Cloud Journey AI" (ngày 06/06) tại Bitexco Financial Tower.<br>- Tìm hiểu sâu về dịch vụ AWS WAF (Web Application Firewall) để bảo vệ ứng dụng Web và API trước các lỗ hổng bảo mật như SQL Injection, XSS; cấu hình các custom rules.<br>- Nghiên cứu, ôn tập các dịch vụ đã học trên AWS và khảo sát nhu cầu người dùng để lựa chọn đề tài dự án tốt nghiệp. | - Tiếp thu kiến thức về WebSockets, GraphRAG và NIDS.<br>- Cấu hình được tường lửa WAF chặn đứng request độc hại.<br>- Định hình được ý tưởng xây dựng dự án tốt nghiệp "Stock Alerts System". |
| **8** | 08/06/2026 -<br>14/06/2026 | - Sử dụng công cụ Draw.io kết hợp bộ thư viện biểu tượng AWS để vẽ sơ đồ kiến trúc hệ thống phân cấp chi tiết từ VPC đến các Subnets.<br>- Thảo luận nhóm để phân tích yêu cầu đề tài dự án, lựa chọn phương án giải quyết nhu cầu thực tế của Trader.<br>- Xác định rõ chân dung khách hàng mục tiêu, các bài toán kỹ thuật cốt lõi và đề xuất tích hợp giải pháp AI (Amazon Bedrock) kết hợp các dịch vụ AWS hiện có.<br>- Lên kế hoạch phát triển dự án, phân chia nhiệm vụ cụ thể giữa các thành viên và xác định các cột mốc nghiên cứu. | - Thiết kế xong sơ đồ kiến trúc thô của dự án tốt nghiệp.<br>- Thống nhất được tài liệu đặc tả yêu cầu chức năng dự án.<br>- Xác định rõ luồng xử lý AI kết hợp tính toán định lượng.<br>- Hoàn tất kế hoạch phân công công việc của nhóm. |
| **9** | 15/06/2026 -<br>21/06/2026 | - Tổng hợp và viết tài liệu mô tả chi tiết bài toán kinh doanh, quy trình thu thập dữ liệu và xác định các tiêu chí kỹ thuật đầu ra cho hệ thống.<br>- Hoàn thiện sơ đồ luồng dữ liệu (Data Flow Diagram - DFD) và sơ đồ kiến trúc hệ thống tổng thể biểu diễn trực quan các tầng xử lý của AWS.<br>- Tìm hiểu các chỉ báo kỹ thuật tài chính phổ biến (RSI, MACD, MA) và nghiên cứu tích hợp mô hình Machine Learning/AI trên AWS SageMaker để hỗ trợ dự đoán. | - Hoàn thành tài liệu phân tích nghiệp vụ hệ thống.<br>- Hoàn thiện sơ đồ kiến trúc chính thức của dự án.<br>- Nắm vững cách thức tích hợp ML/AI trong các hệ thống tài chính. |
| **10** | 22/06/2026 -<br>28/06/2026 | - Nghiên cứu sâu về kiến trúc Serverless (AWS Lambda, API Gateway) và viết bài chia sẻ kinh nghiệm kỹ thuật đăng lên cộng đồng AWS Study Group VN.<br>- Phác thảo giao diện Dashboard (Figma/Draw.io), cấu hình các API endpoint và thống nhất kiến trúc dịch vụ AWS áp dụng cho đề tài.<br>- Triển khai viết mã nguồn cho Lambda hàm Ingestion kết hợp Amazon EventBridge để tự động cào dữ liệu lưu vào Amazon S3.<br>- Tích hợp dịch vụ AWS Bedrock để xử lý ngôn ngữ/AI, kết hợp cơ chế xếp hàng bất đồng bộ với Amazon SQS nhằm ngăn ngừa mất dữ liệu và kiểm thử thành công luồng Demo. | - Đăng tải thành công bài chia sẻ kỹ thuật Serverless lên cộng đồng.<br>- Có bản phác thảo giao diện và định nghĩa API Endpoints rõ ràng.<br>- Triển khai thành công luồng Ingestion lưu dữ liệu thô vào S3.<br>- Kết nối thành công SQS và Bedrock, hoàn thành chạy thử nghiệm luồng Demo bất đồng bộ. |
| **11** | 29/06/2026 -<br>05/07/2026 | - Tập trung kiểm thử toàn diện liên thông hệ thống từ giao diện Dashboard đến backend để phát hiện và sửa các lỗi phát sinh (bug fix) liên quan đến luồng dữ liệu.<br>- Tham gia hội thảo công nghệ lớn "AWS FC Community Day 2026" (ngày 27/06) tại Bitexco Financial Tower.<br>- Thực hiện tổng hợp và hoàn thiện bộ tài liệu nhật ký công việc (Worklog) cá nhân trong suốt quá trình tham gia bootcamp để chuẩn bị tổng kết. | - Khắc phục triệt để các lỗi phân tích cú pháp dữ liệu và cấu hình Lambda.<br>- Tiếp thu kiến thức chuyên sâu về Zero Trust, PrivateLink, VPC Endpoints và giao thức MCP cho AI Agent.<br>- Hoàn thành 100% tài liệu Worklog cá nhân. |
| **12** | 06/07/2026 -<br>10/07/2026 | - Rà soát, dọn dẹp mã nguồn dự án, viết tài liệu hướng dẫn sử dụng (README.md) cho repository và thực hiện bàn giao sản phẩm tốt nghiệp.<br>- Soạn thảo và hoàn thiện báo cáo tổng kết thực tập tốt nghiệp theo biểu mẫu quy định.<br>- Gặp gỡ cán bộ hướng dẫn AWS Việt Nam để tiếp nhận phản hồi, xin nhận xét đánh giá và đóng dấu xác nhận chính thức lên hồ sơ thực tập nộp về trường HUTECH. | - Đóng gói mã nguồn và tài liệu hướng dẫn chuyển giao thành công.<br>- Hoàn thiện dự thảo báo cáo thực tập.<br>- Nhận được phiếu nhận xét thực tập có con dấu đỏ từ AWS Việt Nam.<br>- Đóng gói đầy đủ hồ sơ chuẩn bị nộp về văn phòng Khoa CNTT. |

---
\pagebreak

## **CHƯƠNG 3: PHƯƠNG PHÁP THỰC HIỆN DỰ ÁN TỐT NGHIỆP: STOCK ALERTS SYSTEM**

### **3.1 Tổng quan bài toán kinh doanh và yêu cầu hệ thống**
Trong lĩnh vực giao dịch tài chính chứng khoán, các Trader phải liên tục xử lý một khối lượng thông tin khổng lồ bao gồm: giá cổ phiếu biến động từng giây, khối lượng giao dịch, các chỉ báo kỹ thuật phức tạp (như RSI, MACD, các đường trung bình động MA) cùng các thông tin vĩ mô và tin tức doanh nghiệp. Việc tổng hợp dữ liệu thủ công cực kỳ tốn thời gian, dễ bỏ sót các cơ hội giao dịch quan trọng và dễ bị ảnh hưởng bởi yếu tố tâm lý đám đông.

Để giải quyết bài toán trên, dự án đề xuất xây dựng **Stock Alerts System** - hệ thống phân tích, lập luận và tạo khuyến nghị giá cổ phiếu tự động dựa trên kiến trúc AWS Serverless kết hợp AI Agent thông qua Amazon Bedrock. Hệ thống hướng tới các yêu cầu kỹ thuật cốt lõi sau:
1.  **Tính nhất quán định lượng:** Việc tính toán các chỉ số kỹ thuật (RSI, MACD, MA) bắt buộc phải thực hiện bằng mã nguồn lập trình logic (Python/Node.js) chạy trên AWS Lambda nhằm đảm bảo độ chính xác tuyệt đối, tránh hiện tượng mô hình AI tự tính toán sai lệch.
2.  **Lập luận ngữ cảnh thông minh:** Dùng AI Agent (Claude 3.5 Sonnet trên Amazon Bedrock) đóng vai trò trợ lý phân tích ngôn ngữ, kết hợp các chỉ số kỹ thuật đã tính toán để đưa ra lập luận logic và đề xuất khuyến nghị hành động (MUA/BÁN/THEO DÕI) có chiều sâu.
3.  **Cơ chế Phê duyệt (Human-in-the-loop):** Hệ thống bắt buộc phải giữ vai trò kiểm duyệt của Trader. Khuyến nghị do AI tạo ra chỉ được lưu ở trạng thái chờ duyệt (Pending), Trader sẽ đọc lập luận của AI, chỉnh sửa nếu cần và bấm phê duyệt (Approve) trước khi hệ thống chính thức gửi thông báo qua Email tới khách hàng.
4.  **Tách rời bất đồng bộ (Decoupling):** Sử dụng message queue để tách rời bước thu thập dữ liệu (Ingestion) và bước xử lý/phân tích (Processing/AI), giúp hệ thống có khả năng chịu tải tốt và chống mất mát dữ liệu.

### **3.2 Sơ đồ kiến trúc và luồng xử lý dữ liệu (Architecture & Data Flow)**

Kiến trúc hệ thống được xây dựng hoàn toàn trên nền tảng Serverless của AWS:

```
[Người dùng/Trader] <---> [AWS WAF] ---> [Amazon CloudFront] ---> [S3 Bucket (Frontend)]
                                                 |
                                         (API Request)
                                                 v
[Amazon Cognito] <===================> [Amazon API Gateway]
                                                 |
                                         (Trigger Lambda)
                                                 v
[Amazon EventBridge] ================> [Ingestion-Lambda]
                                                 |
                                         (Lưu raw JSON)
                                                 v
                                        [Amazon S3 (Raw)]
                                                 |
                                         (Event Notification)
                                                 v
                                        [Amazon SQS Queue] <---> [SQS DLQ]
                                                 |
                                         (Trigger Lambda)
                                                 v
                                       [Processing-Lambda] <---> [Amazon Bedrock (Claude)]
                                                 |
                                         (Lưu kết quả & mã hóa KMS)
                                                 v
                                       [Amazon DynamoDB] <---> [Amazon SNS (Mail Alert)]
```

#### **Luồng dữ liệu chính gồm 12 bước liên thông:**
1.  Người dùng/Trader thực hiện đăng nhập và thao tác trên giao diện Web Dashboard.
2.  Yêu cầu được gửi qua **AWS WAF** (Web Application Firewall) để lọc và chặn các request độc hại.
3.  Giao diện Frontend tĩnh được tải nhanh chóng từ **Amazon S3** thông qua mạng phân phối nội dung **Amazon CloudFront**.
4.  Dashboard thực hiện gọi các REST API thông qua **Amazon API Gateway**, kèm theo JWT Token xác thực được cung cấp từ **Amazon Cognito**.
5.  API Gateway kiểm tra tính hợp lệ của token và chuyển tiếp request đến **Ingestion-Lambda**.
6.  Đồng thời, **Amazon EventBridge** cũng có thể kích hoạt Ingestion-Lambda định kỳ theo lịch thị trường (Cron job) để tự động hóa quy trình.
7.  Ingestion-Lambda gọi API tài chính ngoài (Yahoo Finance), lấy các thông tin bảo mật (API Keys, Secrets) từ **AWS SSM Parameter Store**, sau đó lưu trữ file dữ liệu thô (raw JSON) vào **Amazon S3 Bucket** (`production-stock-raw-data-finance`).
8.  Sự kiện thêm file mới trên S3 kích hoạt tính năng Event Notification, tự động gửi một thông báo (message) vào hàng đợi **Amazon SQS Queue**.
9.  **Processing-Lambda** tiêu thụ message từ SQS, đọc file dữ liệu thô tương ứng từ S3, chạy thư viện toán học để tính toán các chỉ báo (RSI, MACD, MA20, MA50) và gửi dữ liệu đã tính toán làm ngữ cảnh (context) sang **Amazon Bedrock**.
10. Bedrock gọi mô hình Claude để lập luận, trả về khuyến nghị dạng cấu trúc JSON (Hành động, Điểm tin cậy, Lập luận, Rủi ro).
11. Processing-Lambda ghi nhận kết quả và lưu vào bảng **Amazon DynamoDB** (`Stock_reports_1`) dưới dạng mã hóa dữ liệu tĩnh (Encryption at-rest) thông qua khóa bảo mật **AWS KMS**.
12. Dashboard cập nhật dữ liệu mới từ DynamoDB. Khi Trader bấm nút phê duyệt khuyến nghị, hệ thống sẽ kích hoạt **Amazon SNS** (hoặc Amazon SES) để tự động gửi thông báo báo cáo chi tiết đến Email khách hàng.

---
\pagebreak

## **CHƯƠNG 4: KẾT QUẢ ĐẠT ĐƯỢC VÀ TỰ ĐÁNH GIÁ**

### **4.1 Kết quả kiểm thử và nghiệm thu hệ thống**
Quá trình kiểm thử liên thông (End-to-End Testing) hệ thống Stock Alerts System đã ghi nhận các kết quả thực tế sau:
1.  **Xác thực người dùng:** Giao diện đăng nhập tích hợp thành công với **Amazon Cognito User Pool**. Chỉ tài khoản Trader được phân quyền mới có thể truy cập thành công vào Dashboard quản trị.
2.  **Giao diện Dashboard:** Hiển thị trực quan danh sách các mã cổ phiếu được theo dõi. Khi chọn một mã mới (ví dụ `VNM`) và nhấn nút "Phân tích" (Analyze), Dashboard gửi thành công request đến API Gateway.
3.  **Xử lý hàng đợi SQS:** Hệ thống ghi nhận message được đưa vào SQS Queue ngay khi Ingestion-Lambda lưu file thô vào S3. Processing-Lambda tự động được kích hoạt, tiêu thụ message và đưa số lượng tin nhắn chờ trong hàng đợi giảm về `0` nhanh chóng, xác nhận luồng xử lý bất đồng bộ hoạt động chính xác.
4.  **Lưu trữ dữ liệu:** Bảng DynamoDB `Stock_reports_1` ghi nhận đầy đủ các bản ghi phân tích mới của mã cổ phiếu `VNM`, bao gồm các chỉ số định lượng (RSI, MACD, MA) đã tính toán và nội dung phân tích ngôn ngữ trả về từ AI Bedrock. Dữ liệu được xác nhận đã được mã hóa an toàn bằng khóa AWS KMS.
5.  **Giám sát vận hành:** Logs trên **Amazon CloudWatch** ghi nhận chi tiết thời gian chạy, dung lượng RAM tiêu thụ và thông tin gỡ lỗi của các hàm Lambda, không phát sinh lỗi logic runtime.

### **4.2 Xử lý sự cố kỹ thuật thực tế (Bedrock Quota Limit)**
Trong quá trình chạy thử nghiệm hệ thống với tần suất cao, hệ thống đã gặp sự cố: Amazon Bedrock trả về lỗi **"Too many tokens per day, please try again" (Token Quota Limit Exceeded)** do tài khoản Free Tier bị giới hạn hạn mức sử dụng mô hình Claude hàng ngày.

#### **Giải pháp khắc phục và tối ưu hóa hệ thống:**
*   **Cơ chế Fallback an toàn (Fallback Mechanism):** Để hệ thống không bị sập (crash) khi API Bedrock bị lỗi, nhóm đã lập trình bổ sung khối lệnh `try-catch` trong Processing-Lambda. Khi gặp lỗi hạn mức Bedrock, hệ thống tự động gán một khuyến nghị mặc định là `"THEO DÕI" (HOLD)` và thiết lập điểm tự tin mặc định là `68`. Do điểm tự tin này thấp hơn ngưỡng tự động gửi đi (`75`), báo cáo sẽ nằm an toàn trên Dashboard ở trạng thái chờ Trader kiểm tra thủ công.
*   **Nâng hạn mức chính thức:** Thực hiện gửi yêu cầu nâng hạn mức (Request Quota) đối với mô hình Claude 3.5 Sonnet v2 trực tiếp trên giao diện quản trị Amazon Bedrock và đã được phê duyệt thành công.
*   **Tối ưu hóa Prompts:** Rút ngắn kích thước prompt gửi đi, cấu trúc lại input dữ liệu dạng bảng rút gọn để tiết kiệm số lượng token đầu vào (Input Tokens), từ đó giảm chi phí vận hành.

### **4.3 Kết quả tự đúc kết sau đợt thực tập**
Kỳ thực tập tại AWS Việt Nam đã mang lại cho em những giá trị phát triển bản thân to lớn:
*   **Về kiến thức lý thuyết:** Củng cố sâu sắc kiến thức về mạng đám mây (VPC, Subnets, DNS Peering, Route 53), kiến trúc không máy chủ (Serverless Lambda, API Gateway), tư duy bảo mật Zero Trust (IAM, WAF, KMS, PrivateLink) và mô hình vận hành tối ưu chi phí (FinOps).
*   **Về kỹ năng thực hành:** Thành thạo thiết kế sơ đồ kiến trúc chuẩn AWS trên Draw.io; biết cách viết mã nguồn Lambda xử lý bất đồng bộ; làm chủ việc cấu hình và quản trị cơ sở dữ liệu NoSQL DynamoDB; rèn luyện khả năng giám sát hệ thống và phân tích logs lỗi qua CloudWatch.
*   **Về kinh nghiệm thực tiễn:** Làm quen với quy trình phát triển sản phẩm Agile/Scrum của nhóm dự án; tích lũy kinh nghiệm xử lý lỗi thực tế liên quan đến cấu hình môi trường (chữ hoa/chữ thường trên Linux EC2); học hỏi tác phong làm việc chuyên nghiệp từ các kỹ sư đám mây tại AWS.

### **4.4 Các hoạt động đóng góp cho cộng đồng và doanh nghiệp**
Bên cạnh công việc nghiên cứu kỹ thuật và phát triển dự án, em đã tích cực tham gia đóng góp chia sẻ kiến thức và kết nối cộng đồng công nghệ:
1.  **Hoạt động biên soạn Blog kỹ thuật:** Đã thực hiện viết và đăng tải 3 bài viết chia sẻ kinh nghiệm thực tế lên cộng đồng **AWS Study Group VN** (với hơn hàng ngàn thành viên theo dõi):
    *   *Blog 1:* Deploy Backend lên AWS EC2 và lỗi chỉ vì chữ hoa (Bài học về sự khác biệt môi trường Windows local và Ubuntu EC2).
    *   *Blog 2:* AWS Cost & AI: Khi chạy cloud không còn chỉ là vấn đề kỹ thuật (Kinh nghiệm FinOps, quản lý ngân sách bằng AWS Budgets).
    *   *Blog 3:* Triển khai ứng dụng Serverless với AWS Lambda và Amazon API Gateway (Hướng dẫn chuyển đổi kiến trúc truyền thống sang Serverless).
2.  **Tham gia các sự kiện công nghệ chuyên sâu:**
    *   *AWS Vietnam Community Day 2026 (Bitexco, 23/05/2026):* Học hỏi các giải pháp Multi-Agent, tối ưu bộ đệm CloudFront và kiểm soát tính phi xác định của LLM trong production.
    *   *AWS First Cloud Journey AI (Bitexco, 06/06/2026):* Học hỏi về lập trình WebSockets với API Gateway, tối ưu Docker Container và kiến trúc GraphRAG trên Bedrock.
    *   *AWS FC Community Day 2026 (Bitexco, 27/06/2026):* Tiếp thu tư duy bảo mật nội bộ an toàn qua Private Subnet, VPC Endpoints, AWS PrivateLink và giao thức kết nối MCP cho AI Agent.

### **4.5 Bản tự đánh giá kết quả thực tập (Bảng 12 tiêu chí)**
Bảng tự đánh giá khách quan về sự phát triển các năng lực chuyên môn và tác phong làm việc của bản thân trong suốt kỳ thực tập:

| STT | Tiêu chí đánh giá chuyên biệt | Minh chứng nội dung công việc thực tế | Tốt | Khá | Trung bình |
| :-: | ----------------------------- | -------------------------------- | :-: | :-: | :--------: |
| 1   | **Kiến thức chuyên môn AWS & Cloud** | Thiết kế sơ đồ kiến trúc hạ tầng dự án Stock Alerts System và cấu hình kết nối mạng. | | **X** | |
| 2   | **Khả năng tự học công nghệ mới** | Chủ động nghiên cứu tích hợp Amazon Bedrock và xử lý lỗi Quota Limit. | **X** | | |
| 3   | **Thực hành kỹ thuật & Code** | Lập trình Lambda cào dữ liệu, xử lý bất đồng bộ SQS và đóng gói Docker container. | | **X** | |
| 4   | **Ý thức bảo mật (Security)** | Áp dụng mã hóa KMS cho DynamoDB, thiết lập WAF Rules và IAM đặc quyền tối thiểu. | **X** | | |
| 5   | **Quản lý chi phí (FinOps)** | Thiết lập cảnh báo ngân sách AWS Budgets và xây dựng Lambda tắt EC2 ngoài giờ làm việc. | **X** | | |
| 6   | **Tinh thần tự giác & Chủ động** | Tự nhận nhiệm vụ nghiên cứu luồng cào dữ liệu và thiết lập database cho nhóm. | **X** | | |
| 7   | **Kỷ luật & Tuân thủ quy trình** | Chấp hành đúng giờ giấc lên văn phòng và quy trình báo cáo tiến độ tuần. | | **X** | |
| 8   | **Kỹ năng làm việc nhóm** | Hợp tác ăn ý với các thành viên để liên thông giao diện Frontend và cơ sở dữ liệu Backend. | **X** | | |
| 9   | **Kỹ năng giao tiếp kỹ thuật** | Biên soạn 3 bài viết blog kỹ thuật chia sẻ cộng đồng và thuyết trình giải pháp nhóm. | | **X** | |
| 10  | **Tư duy giải quyết lỗi (Troubleshooting)** | Định vị lỗi phân tích cú pháp ký tự và xử lý biệt lệ cuộc gọi Bedrock qua CloudWatch Logs. | | **X** | |
| 11  | **Mức độ đóng góp vào dự án tốt nghiệp** | Đóng vai trò chủ chốt trong việc xây dựng luồng dữ liệu Backend và tích hợp AI. | | **X** | |
| 12  | **Tổng thể thái độ & Hiệu quả** | Đánh giá chung về sự trưởng thành kỹ năng và tư duy sau kỳ thực tập. | **X** | | |

*   **Định hướng cải thiện trong tương lai:** Nâng cao hơn nữa tính chủ động trong quản lý thời gian làm việc chuyên nghiệp; rèn luyện thói quen phân tích sâu logs hệ thống tìm nguyên nhân gốc rễ trước khi thực hiện sửa lỗi; tiếp tục học cách đơn giản hóa cách trình bày các giải pháp kỹ thuật phức tạp cho người ngoài ngành dễ nắm bắt.

---
\pagebreak

## **PHỤ LỤC**

### **1. Mã nguồn Lambda Function tiêu biểu (Ingestion-Lambda)**
Dưới đây là đoạn mã nguồn Node.js tiêu biểu cấu hình cào dữ liệu giá cổ phiếu và đẩy message vào hàng đợi SQS:

```javascript
const { S3Client, PutObjectCommand } = require("@aws-sdk/client-s3");
const { SQSClient, SendMessageCommand } = require("@aws-sdk/client-sqs");
const axios = require("axios");

const s3 = new S3Client({});
const sqs = new SQSClient({});

exports.handler = async (event) => {
    try {
        // Lấy mã cổ phiếu từ request API Gateway hoặc EventBridge
        const body = JSON.parse(event.body || "{}");
        const ticker = body.ticker || "VNM";
        
        console.log(`Đang cào dữ liệu cho mã cổ phiếu: ${ticker}`);
        
        // Gọi API tài chính Yahoo Finance (Ví dụ minh họa)
        const response = await axios.get(`https://query1.finance.yahoo.com/v8/finance/chart/${ticker}?interval=1d&range=1mo`);
        const rawData = response.data;
        
        // Lưu file raw JSON vào Amazon S3
        const bucketName = "production-stock-raw-data-finance";
        const keyName = `raw-${ticker}-${Date.now()}.json`;
        
        await s3.send(new PutObjectCommand({
            Bucket: bucketName,
            Key: keyName,
            Body: JSON.stringify(rawData),
            ContentType: "application/json"
        }));
        
        console.log(`Đã lưu dữ liệu thô vào S3: s3://${bucketName}/${keyName}`);
        
        // Đẩy thông điệp thông báo sang Amazon SQS để Processing-Lambda xử lý
        const queueUrl = process.env.SQS_QUEUE_URL;
        await sqs.send(new SendMessageCommand({
            QueueUrl: queueUrl,
            MessageBody: JSON.stringify({
                ticker: ticker,
                s3Bucket: bucketName,
                s3Key: keyName
            })
        }));
        
        console.log(`Đã gửi thông báo sang SQS Queue thành công.`);
        
        return {
            statusCode: 200,
            headers: { "Access-Control-Allow-Origin": "*" },
            body: JSON.stringify({ message: "Thu thập dữ liệu thành công!", ticker, s3Key: keyName })
        };
    } catch (error) {
        console.error("Lỗi Ingestion:", error);
        return {
            statusCode: 500,
            headers: { "Access-Control-Allow-Origin": "*" },
            body: JSON.stringify({ error: "Lỗi thu thập dữ liệu thị trường." })
        };
    }
};
```

---
*(Hết bản báo cáo)*
