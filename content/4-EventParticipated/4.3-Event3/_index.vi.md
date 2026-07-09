---
title: "Event 3"
date: 2026-06-27
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---

# Bài thu hoạch AWS FC Community Day – Solutions for Enterprise AI Agents & Security

| Thông tin sự kiện | Chi tiết |
| :--- | :--- |
| **Tên sự kiện** | AWS FC Community Day 2026 |
| **Thời gian** | 27/06/2026 (Từ 13:00 đến 17:30) |
| **Địa điểm** | Tầng 26 và Tầng 36, Bitexco Financial Tower, TP. Hồ Chí Minh (Có Livestream trên YouTube) |
| **Vai trò** | Người tham dự |

### Mục Đích Của Sự Kiện

Sự kiện AWS FC Community Day là chuỗi hội thảo công nghệ được tổ chức định kỳ hàng tháng nhằm tạo không gian kết nối, chia sẻ kiến thức, kinh nghiệm thực tế và cung cấp góc nhìn thực chiến từ môi trường doanh nghiệp lớn đến với cộng đồng lập trình viên và sinh viên trẻ. 

Mục đích cốt lõi của số sự kiện lần này là mổ xẻ chuyên sâu các bài toán hạ tầng, tối ưu chi phí vận hành và thiết lập lá chắn an ninh nghiêm ngặt khi đưa các mô hình AI Agents (Tác nhân thông minh) vào môi trường Production cấp doanh nghiệp (Enterprise-Grade). Nội dung chương trình trải dài qua các giải pháp đột phá: từ việc ứng dụng nền tảng Multi-Agent để giám sát và xử lý incident của hạ tầng đám mây, xây dựng đường ống Voice AI xử lý ngôn ngữ tiếng Việt thời gian thực, tích hợp DevOps AI Agent để tự động hóa quy trình ứng phó sự cố, ứng dụng trợ lý thông minh Amazon Q (Quick) hỗ trợ tự động hóa phòng quản trị nhân sự, cho đến cơ chế bảo mật kết nối mạng khép kín riêng tư (Private Security) kết hợp máy chủ MCP Server.

### Danh Sách Diễn Giả

Sự kiện quy tụ dàn diễn giả chất lượng cao là các nhà sáng lập, chuyên gia bảo mật và kỹ sư đám mây có thâm niên thực chiến dày dặn trong ngành:

| STT | Diễn giả | Chức vụ | Chủ đề |
| :-: | :--- | :--- | :--- |
| 1 | **Steve Trần** | Founder @ *Cloud Thinker* (Ex-AWS Solution Architect) | *Agentic Platform for Cloud Infrastructure: Hành trình thăng tiến sự nghiệp đám mây, kiến trúc Single-Agent vs Multi-Agent và tối ưu chi phí FinOps* |
| 2 | **Hiếu Nghị, Kiệt & Trung Đỗ** | Cloud Engineers @ *Renova Cloud* & CEO @ *R AI* | *Voice AI Agents: Xây dựng hệ thống tổng đài thoại thông minh, xử lý dữ liệu tiếng Việt thời gian thực và kịch bản gọi công cụ (Tool calling) ngân hàng* |
| 3 | **Nguyên Nguyễn & Bảo** | Cloud Engineers @ *Cloud Kinetics* | *DevOps AI Agent: Tự động hóa quy trình phân loại, điều tra Root Cause và giảm thiểu chỉ số MTTR/MTTD hạ tầng thông qua Agent Space* |
| 4 | **Trường (Wren) & Minh Anh** | AI Solutions Team @ *Noventics* | *HR Intelligent Automation via Amazon Q: Giải pháp bóc tách CV chính xác 99%, chấm điểm ứng viên theo khung năng lực và xây dựng No-code Pipeline* |
| 5 | **Toàn Nguyễn & Hiếu Nghị** | AWS Security Builder @ *AWS Community* | *Private Security for AI Agents: Thiết lập kết nối mạng khép kín kết nối Amazon Q tới máy chủ MCP qua VPC Endpoints bảo mật* |

### Nội Dung Nổi Bật

#### Nền tảng Multi-Agent giám sát hạ tầng đám mây & tối ưu chi phí FinOps

Diễn giả Steve Trần mang đến câu chuyện career path đầy cảm hứng cùng giải pháp giải quyết bài toán phức tạp hóa kiến trúc khi doanh nghiệp tăng trưởng quy mô hệ thống và dịch chuyển sang Microservices trên đám mây.
- **Câu chuyện định hướng sự nghiệp:** Anh chia sẻ việc từng nghỉ học đại học năm 19 tuổi để làm việc tại một Contact Center (năm 2018-2019) và chật vật vận hành các cụm server vật lý cồng kềnh với rủi ro sập phần cứng liên tục. Sau khi hổng kiến thức nền tảng và thi trượt chứng chỉ Azure 3-4 lần, anh đã chuyển hướng chinh phục thành công hệ thống tài liệu sạch sẽ của AWS để trở thành Solution Architect tại chính AWS trước khi thành lập Cloud Thinker.
- **Giải quyết bài toán "Nợ công nghệ" (Tech Debt):** Trong các doanh nghiệp lớn thuộc khối tài chính, ngân hàng (BFSI), hệ thống phục vụ hàng triệu user luôn tồn tại những món nợ công nghệ qua nhiều thế hệ. Tốc độ đọc log và điều tra sự cố của AI tính bằng phút, trong khi con người phải tốn bằng giờ.
- **Kiến trúc Single-Agent vs Multi-Agent:** Team Cloud Thinker đã dành gần 2 năm nghiên cứu để tối ưu hóa bài toán này. Mặc dù một con Single Super Agent thiết kế đủ tốt có khả năng hoàn thành trên 95% tác vụ, nhưng kiến trúc Multi-Agent (Tác nhân chuyên biệt) vượt trội hơn nhờ thu hẹp được Context Window, cho phép chọn các mô hình nhỏ (trọng số thấp) cho tác vụ đơn giản để tối ưu chi phí, và hỗ trợ phân quyền kiểm soát nghiêm ngặt theo vai trò (Role-based Access Control).
- **Lá chắn ngăn chặn rủi ro tự động:** Khác với các công cụ coding tự động thông thường dễ gặp drama tự truy cập database để xóa schema, hệ thống Agentic của Cloud Thinker thiết kế nhiều tầng phê duyệt (Layer Approval) khắt khe trước khi áp dụng bất kỳ thay đổi nào lên môi trường Production. Hệ thống cũng ứng dụng AI để chạy tự động hóa FinOps gần như 100%, thay thế con người liên tục theo dõi dashboard sử dụng nhằm tối ưu hóa chi phí hạ tầng đám mây.

#### Voice AI Agents – Xây dựng hệ thống tổng đài thoại tiếng Việt cấp doanh nghiệp

Phiên chia sẻ của team R AI và Renova Cloud làm sáng tỏ phương pháp phát triển các trợ lý giọng nói thông minh trong môi trường ngân hàng nghiêm ngặt (VPBank, VIB).
- **Thách thức của tiếng Việt (Low-resource Language):** Các mô hình chuyển đổi trực tiếp từ giọng nói sang giọng nói (Speech-to-Speech) hiện nay trên thế giới hầu như chỉ hỗ trợ tốt tiếng Anh. Tiếng Việt là ngôn ngữ nghèo tài nguyên dữ liệu huấn luyện, khiến các tập đoàn lớn không mặn mà đầu tư.
- **Kiến trúc đường ống 3 bước tối ưu:** Để khắc phục, giải pháp thực tế được triển khai theo pipeline: Speech-to-Text (STT) -> LLM -> Text-to-Speech (TTS). Mô hình STT bắt giọng nói và stream trực tiếp thành văn bản vào LLM, LLM xử lý prompt dựa trên cấu trúc ngữ cảnh ngân hàng để xuất ra câu trả lời dưới dạng text, sau đó stream thẳng qua bộ TTS để chuyển đổi thành giọng nói phản hồi khách hàng.
- **Xử lý các bài toán hóc búa của tiếng Việt:**
  - *Nhận diện giới tính:* Tiếng Việt bắt buộc phải xưng hô "anh/chị" dựa theo giọng nói, nếu nhận diện sai sẽ gây trải nghiệm rất tệ cho người dùng.
  - *Thuật toán ngắt lời (Interruption):* Phải huấn luyện các mô hình phụ để hiểu ngữ cảnh khi nào khách hàng dừng nói để suy nghĩ (ví dụ: đang đọc số điện thoại rồi dừng lại chút ít) nhằm ngăn chặn tình trạng AI nhảy vào miệng khách hàng hoặc AI nói tràn lan không dừng khi bị ngắt lời.
  - *Giọng vùng miền (Accent):* Nạp vào tập dữ liệu từ 10% đến 20% giọng vùng miền đặc thù (miền Trung, miền Bắc) để AI không bị "tê liệt" khi nhận diện.
- **Ứng dụng Tool Calling thực tế:** Hệ thống cho phép thực hiện hành động trực tiếp thay vì chỉ trả lời câu hỏi suông. Khi khách hàng gọi điện yêu cầu khóa thẻ, AI sẽ tự động kích hoạt chức năng kiểm tra thông tin căn cước công dân và thực thi lệnh khóa thẻ ngân hàng thời gian thực. Nếu khách hàng có dấu hiệu bực tức vượt quá khả năng xử lý, AI sẽ chủ động chuyển cuộc gọi (pass) sang cho điện thoại viên (Human) một cách tự nhiên nhất.

#### DevOps AI Agent – Tự động hóa quy trình ứng phó sự cố hạ tầng trên AWS

Chuyên đề từ team Cloud Kinetics giới thiệu giải pháp tự động hóa điều tra Root Cause mỗi khi hệ thống phát sinh lỗi nghiêm trọng, giảm tải tối đa áp lực cho đội ngũ SRE/DevOps.
- **Nỗi đau fragmentation dữ liệu:** Khi website bị chậm hoặc lỗi, các kỹ sư phải chật vật truy cập thủ công vào hàng loạt nơi rời rạc như CloudWatch, CloudTrail để tìm log, dẫn đến thất thoát ngữ cảnh (Context loss) và đẩy chỉ số MTTD/MTTR lên rất cao.
- **6 Trụ cột cốt lõi của DevOps AI Agent:**
  1. *Context Learning:* Dựa trên khái niệm Agent Space (một container logic định nghĩa tài nguyên qua các tag). AI sẽ tự học hạ tầng và xuất ra một mô hình sơ đồ Topology đại diện cho cách nó hiểu hệ thống đám mây.
  2. *Control:* Giới hạn quyền tiếp cận của Agent nghiêm ngặt theo tag hoặc thiết lập kết nối khép kín Private Connection.
  3. *Integration:* Mở rộng năng lực điều tra của Agent thông qua giao thức Model Context Protocol (MCP). Ví dụ, Agent không thể tự SSH vào EC2 để đọc log ứng dụng kín, nhưng tích hợp MCP tool giúp nó chạy truy vấn thẳng vào database để lấy chứng cứ.
  4. *Collaboration:* Tương tác mượt mà thông qua giao diện Web, Slack hoặc ServiceNow.
  5. *Convenience:* Kích hoạt nhanh chóng ngay trên giao diện AWS Console.
  6. *Cost-effective:* Giá tính theo thời gian thực thi tác vụ (khoảng 0.083 USD cho 1 giây), không tính theo số lượng token hạ tầng.
- **Quy trình 4 bước xử lý sự cố tự động:** Kích hoạt tự động qua Trigger Alert -> Đưa ra các giả thuyết logic -> Chứng minh giả thuyết dựa trên dữ liệu log thu thập được để tìm ra Root Cause Analysis (RCA) -> Đề xuất bản vá (Mitigation Plan) nhưng không tự ý thực thi để đảm bảo tính an toàn hệ thống (Safety First), quyền quyết định thuộc về con người.
- **Case-study minh chứng hiệu quả:** Trường đại học trực tuyến WGU (phục vụ gần 200,000 học sinh) tích hợp Dynatrace với Agent giúp giảm thời gian xử lý sự cố từ 2 tiếng xuống còn 28 phút (nhanh hơn 77% MTTR). Ứng dụng Zenchef giảm 75% thời gian tìm lỗi cấu hình sai xuống còn 20 phút. Tập đoàn viễn thông KDDI Nhật Bản rút ngắn thời gian xử lý từ nhiều tuần xuống còn vài ngày.

#### Cách mạng hóa quy trình quản trị nhân sự HR bằng trợ lý thông minh Amazon Q

Diễn giả Trường (Wren) và Minh Anh mang đến góc nhìn mới mẻ về việc dùng AI giải quyết bài toán nhân sự phi kỹ thuật trong kỷ nguyên số.
- **Thách thức của ngành HR truyền thống:** Quy trình lọc hồ sơ (Screening CV) bằng tay tốn rất nhiều thời gian và dễ bỏ sót các nhân tài cốt lõi. Quá trình đánh giá ứng viên thường bị chi phối nặng nề bởi cảm tính cá nhân thay vì dựa trên một bộ khung chuẩn hóa. Đồng thời, rủi ro rò rỉ dữ liệu bảo mật nội bộ cực cao khi nhân sự tùy tiện đẩy thông tin cá nhân của nhân viên lên các nền tảng AI công cộng.
- **Giải pháp Amazon Q (Quick Ecosystem):** Là một trợ lý Agentic thông minh hỗ trợ kết nối đa dạng (Google Workspace, Microsoft Sharepoint, OneDrive, Gmail) và các Relational Database, file S3 để bóc tách thông tin. Toàn bộ dữ liệu được bảo vệ an toàn nhờ vùng dữ liệu Local Zone đặt tại Việt Nam.
- **Quy trình tự động hóa phòng nhân sự:**
  - *Học kỹ năng:* Chỉ cần nạp một file tài liệu định dạng `.md`, Amazon Q sẽ tự động học và sinh ra kỹ năng *HR Talent Review Assistant* bao gồm tập lệnh chạy Python, đọc PDF/Docx.
  - *Tạo JD tự động:* AI tự động sinh bộ khung mô tả công việc (JD) chi tiết dựa trên yêu cầu phòng ban.
  - *Sàng lọc và chấm điểm hồ sơ:* AI tự động quét thư mục chứa CV (hỗ trợ OCR chính xác đến 99% kể cả file scan), so khớp với JD để phân loại các mức độ (*Strong, Good, Low, Very Low*). Xuất ra báo cáo Talent Review bằng file HTML phân tích rõ điểm mạnh, điểm yếu của từng ứng viên và dự phóng khung lương phù hợp.
  - *Tự động hóa luồng việc:* Tự động kiểm tra lịch trống (Calendar) của Hiring Manager để hẹn lịch phỏng vấn, viết nháp mail phản hồi và xây dựng ứng dụng theo dõi pipeline tuyển dụng (No-code App Building) chỉ bằng vài câu lệnh trò chuyện.

#### Thiết lập kết nối khép kín bảo mật (Private Security) cho AI Agent qua VPC Endpoint

Phiên kỹ thuật chuyên sâu cuối cùng của diễn giả Toàn Nguyễn và Hiếu Nghị tập trung vào bài toán bảo vệ dữ liệu, ngăn chặn hiểm họa an ninh mạng khi AI kết nối với thế giới bên ngoài.
- **Rủi ro từ Public Endpoint:** Khi Amazon Q kết nối tới các máy chủ MCP của bên thứ ba (như Zalo, WhatsApp, Jira) thông qua internet công cộng, hệ thống sẽ lộ ra các bề mặt tấn công nguy hiểm, dễ bị tấn công Man-in-the-middle đứng giữa đánh cắp gói tin hoặc bị tấn công từ chối dịch vụ DDoS.
- **Kiến trúc mạng nội bộ khép kín:** Để tuân thủ triệt để nguyên tắc **Zero Trust**, toàn bộ máy chủ MCP Server bắt buộc phải đặt trong vùng mạng kín (Private Subnet).
- **Cơ chế vận hành luồng bảo mật:** Đưa Amazon Q vào trong mạng ảo thông qua giải pháp **VPC Connection** sử dụng các cổng kết nối nội bộ Interface Endpoint (AWS PrivateLink). Luồng dữ liệu đi từ Amazon Q -> VPC Connection -> Xác thực qua Amazon Cognito -> Chuyển tiếp tới Application Load Balancer (ALB) được mã hóa chứng chỉ số TLS qua AWS Certificate Manager (ACM) -> Định tuyến chính xác tới MCP Server nhờ hệ thống phân giải tên miền nội bộ **Route 53 Resolver**. Toàn bộ luồng đi này hoàn toàn là private bên trong hạ tầng AWS, không một byte dữ liệu nào bị lọt ra ngoài môi trường internet công cộng.

### Những Gì Học Được

#### Tư duy thiết kế
- **Tư duy phòng thủ an ninh tầng sâu (Security-first):** Một hệ thống phần mềm Enterprise vận hành trong thực tế không bao giờ có tiêu chí "chỉ cần chạy được là đủ". Kiến trúc thiết kế bắt buộc phải tích hợp các giải pháp an ninh khép kín từ biên mạng (VPC Endpoints) để bảo vệ toàn vẹn dữ liệu nhạy cảm của khách hàng.
- **Triết lý "AI hỗ trợ con người" (Human-in-the-loop):** Đối với các tác vụ nhạy cảm liên quan trực tiếp tới môi trường Production (như tự động sửa code hạ tầng DevOps Agent) hoặc quyết định tài chính (FinOps), AI chỉ đóng vai trò là trợ lý đắc lực đề xuất phương án và tăng tốc sản xuất. Quyền phê duyệt cuối cùng (Approval Layer) luôn thuộc về con người để đảm bảo tính an toàn tuyệt đối.
- **Thiết kế hệ thống dựa trên sự thấu hiểu ranh giới:** Việc phân tách kiến trúc Multi-Agent giúp cô lập các vùng dữ liệu (Context Window), tối ưu hóa chi phí vận hành bằng cách gán đúng model nhỏ cho việc dễ và model lớn cho việc khó.

#### Kiến trúc kỹ thuật
- Làm chủ đường ống xử lý Voice AI nâng cao: Hiểu rõ kiến trúc streaming dữ liệu 3 bước (STT -> LLM -> TTS) để giải bài toán ngôn ngữ nghèo tài nguyên như tiếng Việt, kết hợp các model phụ để xử lý kịch bản ngắt lời và nhận diện giới tính người dùng.
- Nắm vững cơ chế vận hành hạ tầng an toàn cấp doanh nghiệp: Hiểu sâu vai trò phân giải tên miền nội bộ của Route 53 Resolver, cơ chế mã hóa đầu cuối của ALB kết hợp ACM, và cách tích hợp giao thức MCP (Model Context Protocol) để mở rộng không giới hạn không gian tri thức của AI Agent tới các nền tảng bên thứ ba.

#### Chiến lược phát triển bản thân
- **Kiên trì bồi đắp kiến thức gốc (Foundations Matter):** Bài học từ career path của anh Steve Trần chứng minh rằng không có lối đi tắt trong ngành Cloud/DevOps. Muốn đi xa, bắt buộc phải làm chủ kiến trúc hệ điều hành Linux, hiểu sâu bản chất mạng máy tính (Networking) và quy trình vận hành thực tế trước khi học các công nghệ AI thượng tầng.
- **Rèn luyện kỹ năng viết CV chuẩn hóa:** Hiểu được cơ chế sàng lọc hồ sơ tự động (OCR/Screening CV) của các nền tảng AI như Amazon Q để có chiến lược viết CV làm nổi bật các keyword công nghệ cốt lõi sát với mô tả công việc (JD) của doanh nghiệp nhằm vượt qua vòng gửi xe.

### Ứng Dụng Vào Công Việc
- **Nâng cấp tư duy đóng gói và quản lý tài nguyên:** Tiếp tục ứng dụng Docker để đóng gói các module dịch vụ trong đồ án trường học, đồng thời áp dụng nguyên tắc quản lý phân quyền đặc quyền tối thiểu (Least Privilege) dựa trên hệ thống gán thẻ (Tags) tương tự cấu trúc Agent Space của DevOps Agent.
- **Thực hành xây dựng kịch bản automation cơ bản:** Tận dụng tài khoản free của bộ công cụ DevOps AI Agent để trực tiếp lên AWS Console trải nghiệm cách hệ thống tự động vẽ sơ đồ Topology và phân tích log sự cố.
- **Tối ưu hóa quy trình làm việc nhóm:** Tích hợp bộ công cụ số được gợi ý từ sự kiện (Trello/ClickUp để quản lý task, Discord/Slack để stream thông tin liên tục) vào quá trình làm đồ án nhóm Kỹ thuật Phần mềm để nâng cao hiệu suất cộng tác theo chuẩn quy trình doanh nghiệp.
- **Tự xây dựng bộ công cụ học tập thông minh:** Nghiên cứu tài liệu hướng dẫn (Documentation) của Amazon Q để thử cấu hình một chat agent cá nhân, nạp toàn bộ slide bài giảng và sách giáo trình định dạng `.md` hoặc PDF để AI tự trích xuất thông tin, hỗ trợ ôn thi học kỳ hiệu quả.

### Trải nghiệm trong event

#### Học hỏi từ các diễn giả có chuyên môn cao
Bản thân cực kỳ ấn tượng với phong cách trình bày thực chiến, gãy gọn của anh Steve Trần. Việc anh chia sẻ thẳng thắn về những thất bại trong quá khứ khi học Azure và những bài toán "đau thương", các điểm trade-off khi khởi nghiệp giúp sinh viên năm cuối như tôi gạt bỏ được tâm lý ảo tưởng về công nghệ, hiểu rằng mọi kiến trúc được chọn đều phải phục vụ lợi ích kinh tế và bài toán thực tế của khách hàng. Bên cạnh đó, bài chia sẻ của anh Trương Huy Phước về 4 quy tắc vàng trong teamwork giúp tôi nhận thức sâu sắc rằng công nghệ chỉ là một nửa của thành công, nửa còn lại nằm ở cách chúng ta giao tiếp và phối hợp trong tập thể.

#### Trải nghiệm kỹ thuật thực tế
Khoảnh khắc thú vị nhất là phiên chạy thử nghiệm trực tiếp (Live Demonstration) bộ đôi Voice Agent cấu hình trên nền tảng hạ tầng Amazon Bedrock Agent Core kết hợp Knowledge Bases của bạn Kiệt. Việc xem con bot tự động trích xuất dữ liệu domain hẹp về cấu hình MacBook Pro và phản hồi bằng giọng nói tiếng Anh mượt mà mang lại nguồn cảm hứng rất lớn. Tiếp đó là phần phân tích chuyên sâu về giải pháp stream text tiếng Việt của anh Trung Đỗ (CEO R AI) giúp tôi mở mang tầm mắt về cách xử lý các biến số "rìa" như việc ngắt lời hay đoán giới tính khách hàng.

#### Ứng dụng công cụ hiện đại
Tận mắt nhìn thấy quy trình Amazon Q bóc tách file scan CV và xuất ra một trang báo cáo HTML phân tích benchmark năng lực ứng viên sắc bén của team Noventics. Cơ chế tính toán chi phí vận hành mạng private (ALB, Route 53 Resolver, EC2) dao động từ 250 đến 350 USD một tháng được anh Toàn Nguyễn mổ xẻ tường tận trong phiên QA giúp tôi định hình được tư duy tối ưu hóa chi phí hạ tầng của một kiến trúc sư giải pháp thực thụ.

### Kết nối và trao đổi
Không gian sự kiện tại văn phòng AWS Bitexco vô cùng náo nhiệt và cởi mở. Trong giờ giải lao giữa hiệp, tôi đã tranh thủ giao lưu với các bạn sinh viên trường Swinburne và chủ động kết nối LinkedIn với anh Toàn Nguyễn để hỏi thêm về tài liệu cấu hình mạng kết nối VPC Connection. Buổi trò chuyện giúp tôi mở rộng mạng lưới học tập và tự tin hơn trong việc học hỏi từ những người đi trước.

### Bài học rút ra & Đóng góp cá nhân
- **Bài học rút ra**:
  + Một hệ thống công nghệ Enterprise thành công không nằm ở việc sử dụng những mô hình AI phức tạp nhất, mà nằm ở khả năng giải quyết triệt để nỗi đau của doanh nghiệp (giảm chỉ số MTTR, bảo mật dữ liệu tuyệt đối) với mức chi phí tối ưu nhất.
  + Tham gia các ngày hội lớn như AWS Community Day là cơ hội vàng để sinh viên Kỹ thuật Phần mềm liên tục cập nhật dòng chảy công nghệ, trang bị cho mình cả "đồ chơi" kỹ thuật lẫn tư duy nghiệp vụ thực tế trước khi ra trường.
- **Đóng góp và Tương tác cá nhân**:
  + Tích cực tham gia thảo luận và đặt câu hỏi cho diễn giả Toàn Nguyễn trong phiên chia sẻ về Private Security để làm rõ chi tiết chi phí vận hành mạng private (ALB, Route 53 Resolver, EC2) trong môi trường thực tế.
  + Giao lưu, kết nối LinkedIn với các diễn giả và các bạn sinh viên Swinburne để chia sẻ tài liệu và cùng nhau hỗ trợ học tập công nghệ đám mây.

### Một số hình ảnh khi tham gia sự kiện

Dưới đây là một số hình ảnh thực tế ghi lại những khoảnh khắc đáng nhớ của bản thân khi tham gia sự kiện AWS FC Community Day 2026 tại văn phòng AWS Việt Nam:

````carousel
![Slide mở màn giới thiệu chuỗi sự kiện định kỳ hàng tháng AWS FC Community Day tại Bitexco](/images/4-EventParticipated/4.3-Event3/IMG20260620130023.jpg)
<!-- slide -->
![Founder Steve Trần chia sẻ carry path bản thân và giải pháp cấu hình hệ thống Multi-Agent chuyên biệt](/images/4-EventParticipated/4.3-Event3/IMG20260620131540.jpg)
<!-- slide -->
![Slide đúc kết bài toán cốt lõi tối ưu chi phí FinOps tự động hóa bằng AI của công ty Cloud Thinker](/images/4-EventParticipated/4.3-Event3/IMG20260620134512.jpg)
<!-- slide -->
![Chuyên đề thiết kế hệ thống Voice AI và các thành phần cốt lõi xử lý âm thanh tiếng Việt thời gian thực](/images/4-EventParticipated/4.3-Event3/IMG20260620140506.jpg)
<!-- slide -->
![Sơ đồ kiến trúc đường ống 3 bước STT-LLM-TTS xử lý giọng nói tích hợp Tool Calling ngân hàng](/images/4-EventParticipated/4.3-Event3/IMG20260620141830.jpg)
<!-- slide -->
![Bạn Kiệt thực hiện phần Live Demo trợ lý thoại thông minh truy vấn cấu hình sản phẩm Apple MacBook Pro](/images/4-EventParticipated/4.3-Event3/IMG20260620144520.jpg)
<!-- slide -->
![Slide phân tích bài toán xử lý ngắt lời Interruption và accent vùng miền đặc thù của CEO R AI Trung Đỗ](/images/4-EventParticipated/4.3-Event3/IMG20260620150212.jpg)
<!-- slide -->
![Slide giới thiệu chuyên đề DevOps AI Agent giúp giảm thiểu chỉ số MTTR/MTTD hạ tầng của team Cloud Kinetics](/images/4-EventParticipated/4.3-Event3/IMG20260620153045.jpg)
<!-- slide -->
![Sơ đồ mô tả 6 trụ cột cốt lõi của một hệ thống DevOps Agent vận hành trong môi trường Enterprise](/images/4-EventParticipated/4.2-Event2/IMG20260620154812.jpg)
<!-- slide -->
![Hình ảnh giao diện Topology hệ thống tự động học và ánh xạ gần 300 mối quan hệ tài nguyên của DevOps Agent](/images/4-EventParticipated/4.3-Event3/IMG20260620160230.jpg)
<!-- slide -->
![Bảng thống kê 3 use-case thành công thực tế của trường đại học WGU, Zenchef và tập đoàn KDDI Nhật Bản](/images/4-EventParticipated/4.3-Event3/IMG20260620161559.jpg)
<!-- slide -->
![Slide trình bày các thách thức của phòng HR truyền thống và giải pháp tự động hóa thông minh từ team Noventics](/images/4-EventParticipated/4.3-Event3/IMG20260620163506.jpg)
<!-- slide -->
![Trình diễn giao diện Amazon Q bóc tách dữ liệu CV xuất báo cáo Talent Review Report trực quan dạng HTML](/images/4-EventParticipated/4.3-Event3/IMG20260620165040.jpg)
<!-- slide -->
![Slide tiêu đề chuyên đề bảo mật mạng khép kín Private Security cho AI Agent kết nối MCP Server](/images/4-EventParticipated/4.3-Event3/IMG20260620170012.jpg)
<!-- slide -->
![Sơ đồ kiến trúc bảo mật toàn diện tích hợp Route 53 Resolver, PrivateLink, Cognito và ALB mã hóa TLS](/images/4-EventParticipated/4.3-Event3/IMG20260620171545.jpg)
<!-- slide -->
![Màn hình thực hiện các câu lệnh truy vấn dữ liệu latency hệ thống thời gian thực qua mạng private của anh Toàn Nguyễn](/images/4-EventParticipated/4.3-Event3/IMG20260620172530.jpg)
<!-- slide -->
![Ảnh chụp cuốn sổ tay ghi chú cá nhân tóm tắt lại toàn bộ luồng đi và các keyword quan trọng của sự kiện](/images/4-EventParticipated/4.3-Event3/event3_note.png)
<!-- slide -->
![Bức ảnh tập thể toàn bộ diễn giả và khách mời chụp chung lưu niệm tại sảnh văn phòng AWS Bitexco](/images/4-EventParticipated/4.3-Event3/event3_group.jpg)
````

> Sự kiện đã đem lại những bài học công nghệ đắt giá cùng cơ hội giao lưu tuyệt vời, giúp tôi tự tin định hình và phát triển năng lực của mình trên con đường chinh phục điện toán đám mây và AI.