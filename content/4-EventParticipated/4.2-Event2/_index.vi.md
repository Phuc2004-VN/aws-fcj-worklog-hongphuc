---
title: "Event 2"
date: 2026-06-06
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

# Bài thu hoạch AWS First Cloud Journey AI

| Thông tin sự kiện | Chi tiết |
| :--- | :--- |
| **Tên sự kiện** | AWS First Cloud Journey AI |
| **Thời gian** | 06/06/2026 (Từ 09:00 đến 12:00) |
| **Địa điểm** | Tầng 26, Bitexco Financial Tower, TP. Hồ Chí Minh |
| **Vai trò** | Người tham dự |

### Mục Đích Của Sự Kiện
Sự kiện AWS First Cloud Journey AI là một chương trình chia sẻ công nghệ chuyên sâu tập trung vào trí tuệ nhân tạo (AI), các ứng dụng Cloud-native hiện đại, nghệ thuật làm việc nhóm hiệu quả và hành trình định hướng sự nghiệp trong ngành Công nghệ thông tin mà tôi có cơ hội tham gia trực tiếp tại văn phòng AWS Việt Nam (tầng 26, Bitexco Financial Tower). 

Mục đích cốt lõi của sự kiện lần này là mang lại cho cộng đồng sinh viên và các lập trình viên trẻ một cái nhìn toàn diện về việc ứng dụng các dịch vụ đám mây AWS và AI vào các bài toán thực tiễn. Nội dung trải dài từ việc thiết kế hệ thống game multiplayer thời gian thực, tối ưu đóng gói ứng dụng với Docker, xây dựng kiến trúc tìm kiếm thông tin nâng cao GraphRAG, đến việc tăng cường bảo mật Web bằng mô hình Machine Learning. Bên cạnh các kỹ thuật chuyên sâu, sự kiện còn chia sẻ các nguyên lý làm việc nhóm và công cụ cộng tác hiệu quả giúp tối ưu hóa hiệu suất dự án. Đồng thời, phiên thảo luận và câu chuyện thực tế từ một cựu kỹ sư Helpdesk thăng tiến lên Senior Sysadmin đã giúp bản thân tôi định hình rõ ràng lộ trình học tập, chuẩn bị hành trang kỹ thuật vững chắc để bước vào môi trường doanh nghiệp chuyên nghiệp.

### Danh Sách Diễn Giả

Sự kiện được bắt đầu với phần **AWS AI Director Panel / Q&A** đầy hấp dẫn do Ban giám đốc AWS AI điều phối thảo luận và trả lời câu hỏi trực tiếp. Tiếp đó là danh sách các bài thuyết trình chuyên sâu của các diễn giả:

| STT | Diễn giả | Chức vụ | Chủ đề |
| :-: | -------- | ------- | ------ |
| 1 | **Nguyễn Quốc Bảo** | Cloud Engineer / Game Developer | *Multiplayer in the Cloud: Connecting Godot Clients with AWS WebSockets* |
| 2 | **Huỳnh Bảo** | Junior Cloud Native Developer @Endava Vietnam | *Docker — A containerization technology* |
| 3 | **Việt Phát** | AI Majoring @Swinburne University of Technology | *GraphRAG: Build GraphRAG applications using Amazon Bedrock and Amazon Neptune* |
| 4 | **Lê Hoàng Gia Đại** | Final-year Student @HUTECH University | *WAF + ML for Cyber Attack Detection: Machine Learning-based Network Intrusion Detection System (NIDS) on AWS* |
| 5 | **Trần Trung Vinh** | System Administrator @Central Retail Group | *From IT Helpdesk to Senior Sysadmin* |
| 6 | **Trương Huy Phước** | Presenter / Teamwork Coach | *The Art of Effective Teamwork* |

### Nội Dung Nổi Bật

#### Panel Thảo Luận & Hỏi Đáp Của Giám Đốc AWS AI
Phiên mở màn mang đến không khí thảo luận sôi nổi về sự bùng nổ của trí tuệ nhân tạo và cách thế hệ kỹ sư trẻ nên chuẩn bị bản thân trước làn sóng công nghệ này.
- **Kỹ năng cốt lõi**: Trong bối cảnh AI phát triển vượt bậc, bản thân người học cần đầu tư mạnh mẽ vào tư duy giải quyết vấn đề, thiết kế kiến trúc hệ thống và khả năng kết nối các dịch vụ đám mây linh hoạt. Viết code thủ công đơn thuần sẽ dần bị thay thế, nhưng tư duy phân tích nghiệp vụ và thiết kế giải pháp luôn là kỹ năng sống còn của người kỹ sư trong 5 năm tới.
- **Khoảng cách doanh nghiệp**: Hiện có một khoảng cách lớn giữa kỳ vọng ứng dụng AI của doanh nghiệp và năng lực thực tế của đội ngũ xây dựng. Để thu hẹp khoảng cách này, lập trình viên cần hiểu sâu về các dịch vụ Managed Services của AWS nhằm rút ngắn thời gian phát triển và tối ưu hóa chi phí.
- **Thông điệp cốt lõi**: Đám mây và AI đã hạ thấp rào cản gia nhập thị trường cho các nhà xây dựng công nghệ trẻ. Chỉ cần có ý tưởng và tư duy đúng, một kỹ sư trẻ hoàn toàn có thể tự mình xây dựng các ứng dụng quy mô toàn cầu.

#### Kết Nối Godot Client Với AWS WebSockets (Multiplayer in the Cloud)
Chủ đề này tập trung vào việc thiết kế và lập trình hệ thống game kéo-búa-bao nhiều người chơi thời gian thực, giao tiếp trực tiếp qua giao thức mạng tin cậy.
- **Lựa chọn kiến trúc mạng**:
  + **UDP/ENet**: Thích hợp cho game hành động nhanh (FPS, đua xe) nhờ độ trễ cực thấp, nhưng cực kỳ phức tạp khi phải tự quản lý việc truyền nhận tin cậy.
  + **HTTP Polling**: Thích hợp cho các tác vụ phi thời gian thực như đăng nhập, bảng xếp hạng nhưng độ trễ cao và lãng phí băng thông do cơ chế hỏi-đáp liên tục.
  + **WebSocket**: Lựa chọn tối ưu cho các game theo lượt, sảnh chờ (lobby), hoặc chat nhờ hỗ trợ truyền nhận hai chiều toàn song công (full-duplex) thời gian thực và đảm bảo tính toàn vẹn của dữ liệu.
- **Kiến trúc trên AWS**: Client phát triển bằng Godot Engine sử dụng lớp `WebSocketPeer` kết nối trực tiếp đến API Gateway WebSocket. API Gateway sẽ dựa trên trường `$request.body.action` để điều phối yêu cầu đến AWS Lambda (Node.js 20) xử lý logic và ghi nhận trạng thái vào bảng DynamoDB.
- **Thách thức kỹ thuật**:
  + **Stale Connections**: Người chơi thoát ứng dụng đột ngột khiến connectionId bị hỏng nhưng vẫn tồn tại trong DynamoDB, gây lỗi `GoneException` khi server cố gửi dữ liệu.
  + **DynamoDB Scan Cost**: Việc lạm dụng `ScanCommand` để tìm kiếm đối thủ ghép cặp gây quá tải và làm tăng chi phí vận hành đáng kể khi quy mô người chơi lớn dần.
  + **Stateless Lambda**: Do Lambda hoạt động không lưu trạng thái, toàn bộ trạng thái trò chơi bắt buộc phải được nạp và ghi lại liên tục vào DynamoDB trong mỗi request.
- **Định hướng nâng cấp**: Chuyển đổi sang AWS GameLift để quản lý các máy chủ chuyên dụng (dedicated server) hỗ trợ tính toán vật lý phức tạp và tự động mở rộng linh hoạt.

#### Docker – Công Nghệ Container Hóa (A Containerization Technology)
Diễn giả Huỳnh Bảo đã cung cấp một cái nhìn trực quan và dễ tiếp cận về công nghệ container hóa, giải quyết bài toán môi trường chạy ứng dụng không nhất quán.
- **Hạn chế của Máy ảo (Virtual Machines)**: Mỗi máy ảo đòi hỏi chạy một hệ điều hành riêng biệt, cực kỳ nặng nề, chiếm dụng nhiều tài nguyên CPU, RAM và dung lượng lưu trữ, đồng thời tốn nhiều công sức để vá lỗi, cập nhật định kỳ.
- **Sức mạnh của Docker**: Docker đóng gói ứng dụng cùng toàn bộ thư viện, cấu hình phụ thuộc vào một container siêu nhẹ, dùng chung nhân hệ điều hành của máy chủ. Điều này hiện thực hóa triết lý "Build once, run anywhere", loại bỏ hoàn toàn lỗi "chạy được trên máy tôi nhưng lỗi trên server".
- **Cơ chế lớp ảnh (Layered Image)**: Mỗi dòng lệnh trong `Dockerfile` tạo ra một image layer. Khi build lại ảnh, Docker tận dụng bộ nhớ đệm cache cho những layer không đổi, giúp tăng tốc độ đóng gói ứng dụng lên nhiều lần.
- **Ứng dụng**: Docker là nền tảng cốt lõi để triển khai kiến trúc Microservices, xây dựng các đường ống CI/CD tự động và tối ưu hóa tài nguyên hạ tầng đám mây.

#### GraphRAG: Xây Dựng Ứng Dụng Bằng Amazon Bedrock Và Amazon Neptune
Bài chia sẻ giới thiệu phương pháp tối ưu hóa khả năng tìm kiếm và trả lời câu hỏi của mô hình ngôn ngữ lớn dựa trên cấu trúc đồ thị dữ liệu.
- **Giới hạn của RAG truyền thống**: RAG thông thường dựa trên tìm kiếm vector đơn giản thường gặp khó khăn với các câu hỏi đòi hỏi tư duy bắc cầu nhiều bước (multi-hop reasoning).
- **Giải pháp GraphRAG**: Sử dụng đồ thị tri thức (Knowledge Graph) với các thực thể là đỉnh (nodes) và các quan hệ là cạnh (edges). Khi LLM nhận câu hỏi, hệ thống sẽ thực hiện duyệt đồ thị (graph traversal) qua nhiều tài liệu để trích xuất thông tin có ngữ cảnh liên kết chặt chẽ.
- **Hai hướng tiếp cận trên AWS**:
  + **Fully Managed Route**: Sử dụng Amazon Bedrock Knowledge Bases để tự động chia nhỏ, trích xuất thực thể, tạo nhãn và lưu trữ đồ thị trực tiếp trên Amazon Neptune Analytics để khám phá các mối quan hệ ẩn.
  + **Custom Route**: Dựng pipeline xử lý dữ liệu tùy biến bằng LlamaIndex kết hợp với lưu trữ trên Amazon Neptune, sử dụng ngôn ngữ Cypher Query để thực hiện duyệt đồ thị đa bước phức tạp theo nhu cầu.

#### Kết Hợp WAF + ML Để Phát Hiện Tấn Công Mạng (Cyber Attack Detection)
Chuyên đề an ninh mạng chuyên sâu giới thiệu cách thức xây dựng hệ thống phát hiện xâm nhập mạng NIDS thông minh để bổ trợ cho tường lửa ứng dụng web.
- **Hạn chế của WAF truyền thống**: Hoạt động chủ yếu dựa trên luật định sẵn (Rule-based), do đó rất dễ bị vượt qua bởi các cuộc tấn công zero-day mới, tấn công lai hoặc các hành vi bất thường chưa có trong cơ sở dữ liệu chữ ký.
- **Giải pháp WAF + Machine Learning**:
  + Phát triển NIDS thông minh bằng cách huấn luyện mô hình Machine Learning LightGBM trên bộ dữ liệu chuẩn hóa quốc tế CSE-CIC-IDS2018 trên AWS.
  + Quy trình xử lý dữ liệu phức tạp: Gộp nhiều file CSV lớn, xử lý dữ liệu lỗi (xóa nhãn không hợp lệ, loại bỏ giá trị âm, NaN, vô cực), cân bằng lại các lớp nhãn tấn công thiểu số trước khi đưa vào huấn luyện mô hình.
- **Kiến trúc triển khai thực tế**: VPC chứa các máy chủ EC2 chạy mô hình NIDS kết hợp với Application Load Balancer. Toàn bộ log traffic được đẩy thời gian thực qua Amazon Kinesis Data Firehose về S3. Một AWS Lambda sẽ phân tích và đối chiếu kết quả dự đoán của NIDS với các sự kiện AWS WAF, gửi cảnh báo qua SNS đến Security Hub, GuardDuty và CloudWatch để quản lý tập trung.

#### Hành Trình Từ IT Helpdesk Đến Senior Sysadmin
Câu chuyện đầy cảm hứng từ cựu kỹ sư Helpdesk Trần Trung Vinh mang lại nhiều bài học thực tế quý giá về định hướng nghề nghiệp và tự học công nghệ hạ tầng.
- **Kỹ năng tích lũy từ Helpdesk**: Rèn luyện khả năng chịu đựng áp lực khi xử lý sự cố khẩn cấp, kỹ năng giao tiếp thuyết phục với người dùng và tư duy phân tích nguyên nhân gốc rễ (troubleshooting).
- **Bước ngoặt nghề nghiệp**: Chủ động học sâu về hệ điều hành Linux và mạng máy tính (Networking), tự xây dựng các phòng Lab thực hành ảo hóa tại nhà để hiểu rõ bản chất hoạt động của hệ thống.
- **Triết lý vận hành Sysadmin**:
  + Đảm nhận các công việc quan trọng như phân bổ tài nguyên, vá lỗi bảo mật, lập kế hoạch dung lượng hệ thống.
  + Ghi nhớ nguyên tắc cốt lõi: "Không bao giờ được kiểm thử trực tiếp trên môi trường production" để đảm bảo độ tin cậy tuyệt đối của hệ thống.
  + Chuyển đổi từ hạ tầng vật lý truyền thống sang tư duy đám mây (Cloud Mindset với AWS), sử dụng hạ tầng dạng mã (IaC - Terraform) và văn hóa DevOps tự động hóa với Docker và các đường ống CI/CD.

#### Nghệ Thuật Làm Việc Nhóm Hiệu Quả (The Art of Effective Teamwork)
Diễn giả Trương Huy Phước đã chia sẻ một góc nhìn sâu sắc về khía cạnh kỹ năng mềm, khẳng định rằng sự phối hợp ăn ý giữa con người mới là yếu tố quyết định sự thành bại của mọi dự án công nghệ.
- **4 Quy tắc vàng (The 4 Golden Rules)**:
  + **Rule 1: Mục tiêu rõ ràng & chia sẻ chung (Clear & Shared Goals)**: Toàn đội phải cùng hướng về một đích đến và hiểu rõ mục tiêu chung của dự án.
  + **Rule 2: Đúng người, đúng việc (Right Person, Right Place)**: Phân chia vai trò dựa trên thế mạnh cá nhân để tối ưu hiệu suất làm việc.
  + **Rule 3: Giao tiếp cởi mở & Lắng nghe thấu đáo (Open Communication & Active Listening)**: Tạo môi trường tôn trọng, khuyến khích phản hồi và luôn lắng nghe ý kiến của đồng đội.
  + **Rule 4: Trách nhiệm cá nhân (Personal Accountability)**: Mỗi thành viên phải chủ động hoàn thành phần việc được giao và chịu trách nhiệm với kết quả chung.
- **Bộ công cụ kỹ thuật số hỗ trợ (Digital Tools)**:
  + **Quản lý công việc**: Sử dụng các phần mềm hiện đại như Trello, ClickUP để theo dõi tiến độ và phân công nhiệm vụ trực quan.
  + **Không gian làm việc & giao tiếp**: Kết hợp Google Workspace cho lưu trữ tài liệu, cùng Slack và Discord làm kênh trao đổi nhanh chóng, liên tục.

### Những Gì Học Được

#### Tư Duy Thiết Kế
- Tôi nhận ra rằng việc ứng dụng AI vào doanh nghiệp không chỉ dừng lại ở các chatbot đơn giản, mà cần có sự kết hợp sâu sắc của các cơ sở dữ liệu đồ thị (Graph Database) như Amazon Neptune để giải quyết triệt để các bài toán tìm kiếm thông tin liên kết phức tạp.
- Khi thiết kế các ứng dụng mạng thời gian thực, việc lựa chọn giao thức (UDP hay WebSocket) phải bắt nguồn trực tiếp từ yêu cầu nghiệp vụ và trải nghiệm người dùng mong muốn, đồng thời phải thiết kế cơ chế xử lý lỗi ngắt kết nối đột ngột để hệ thống hoạt động ổn định.
- Tư duy vận hành hệ thống luôn phải đặt tính an toàn và bảo mật lên hàng đầu. Việc kết hợp ML vào WAF giúp tạo ra một hệ thống phòng thủ chủ động, có khả năng tự thích ứng với các mối đe dọa mới thay vì chỉ thụ động chạy theo các luật định sẵn.

#### Kiến Trúc Kỹ Thuật
- Nắm vững cách cấu hình API Gateway WebSocket định tuyến thông tin qua Route Key và quản lý trạng thái kết nối thông qua connectionId trong DynamoDB.
- Hiểu rõ cơ chế xây dựng hình ảnh của Docker dựa trên các lớp ảnh (Image Layers) chồng lên nhau và cách tận dụng cache để tối ưu hóa thời gian build hình ảnh ứng dụng.
- Phân biệt rõ hai mô hình triển khai GraphRAG trên AWS (dùng Bedrock Knowledge Bases + Neptune Analytics quản lý hoàn toàn hoặc dùng LlamaIndex + Neptune tùy biến sâu) để áp dụng linh hoạt theo nguồn lực dự án.
- Hiểu sâu sơ đồ luồng dữ liệu an ninh mạng tích hợp các dịch vụ giám sát và bảo mật của AWS như WAF, Kinesis Firehose, Lambda, Security Hub, GuardDuty, và CloudWatch.

#### Chiến Lược Phát Triển Bản Thân
- Bản thân tôi tự rút ra bài học lớn về việc không nên dàn trải học quá nhiều công cụ cùng lúc. Thay vào đó, tôi cần tập trung đi sâu làm chủ 1-2 công nghệ nền tảng (như Linux và Networking cơ bản) trước khi mở rộng lên Cloud/DevOps.
- Tầm quan trọng của việc xây dựng các bài Lab thực hành cá nhân (Home Labs). Kinh nghiệm thực tiễn có được từ việc tự dựng hệ thống và sửa lỗi có giá trị hơn rất nhiều so với việc chỉ học lý thuyết suông để thi lấy chứng chỉ.
- Luôn giữ vững tinh thần kiên trì, không ngại bắt đầu từ những vị trí thấp nhất như Helpdesk, bởi mỗi trải nghiệm thực tế đều đóng góp tích cực vào sự trưởng thành chuyên môn sau này.
- Thấu hiểu và áp dụng 4 quy tắc vàng trong làm việc nhóm để phối hợp nhịp nhàng, có trách nhiệm với các thành viên khác trong nhóm dự án.

### Ứng Dụng Vào Công Việc
- Tôi sẽ tiến hành thực hành viết Dockerfile đóng gói các ứng dụng web nhỏ đã làm ở trường, áp dụng kỹ thuật tối ưu hóa các lớp ảnh để giảm thiểu dung lượng container và thực hành đẩy lên Amazon ECR.
- Thiết lập một môi trường Lab cá nhân trên máy tính để thực hành cấu hình mạng cơ bản, cài đặt hệ điều hành Linux và viết các script shell tự động hóa đơn giản để củng cố kiến thức nền tảng.
- Thử nghiệm xây dựng một game đơn giản sử dụng Godot Engine và tích hợp với API Gateway WebSocket trên AWS để làm quen với lập trình mạng thời gian thực và quản lý session người dùng.
- Nghiên cứu tài liệu của LlamaIndex và Amazon Bedrock để tự tay dựng một ứng dụng RAG cơ bản chạy local, làm quen với quy trình cắt nhỏ dữ liệu (chunking) và nhúng vector (embedding).
- Đọc thêm tài liệu về AWS WAF để hiểu cách xây dựng các quy tắc tùy biến (custom rules) bảo vệ các API Gateway của các bài thực hành workshop trước đây chống lại tấn công mạng.
- Áp dụng các quy tắc cộng tác nhóm và các công cụ cộng tác trực quan như Trello, Slack vào quá trình học tập nhóm tại trường nhằm tối ưu hóa tiến độ làm việc chung.

### Trải nghiệm trong event

#### Học hỏi từ các diễn giả có chuyên môn cao
Các bài thuyết trình mang tính thực tiễn cao đã giúp tôi học hỏi được nhiều kinh nghiệm quý báu. Bản thân tôi vô cùng ấn tượng trước sự chia sẻ chân thành của anh Trần Trung Vinh về hành trình vượt khó vươn lên từ vị trí Helpdesk. Sự kiên trì tự học hệ thống Lab của anh đã truyền cảm hứng rất lớn cho tôi trong việc tự định hướng lộ trình học tập công nghệ của mình. Bên cạnh đó, bài chia sẻ của anh Trương Huy Phước về 4 quy tắc vàng trong teamwork giúp tôi nhận thức sâu sắc rằng công nghệ chỉ là một nửa của thành công, nửa còn lại nằm ở cách chúng ta giao tiếp và phối hợp trong tập thể.

#### Trải nghiệm kỹ thuật thực tế
Tôi rất thích thú khi được xem trực tiếp bản demo chạy thực tế của hệ thống ghép cặp game kéo-búa-bao qua WebSocket của anh Nguyễn Quốc Bảo và cách hệ thống xử lý các lỗi kết nối mạng. Đồng thời, sơ đồ kiến trúc an ninh mạng tích hợp đầy đủ các dịch vụ bảo mật AWS của anh Lê Hoàng Gia Đại mang lại cho tôi cái nhìn trực quan, sinh động về cách doanh nghiệp bảo vệ hệ thống của họ trong thực tế.

#### Ứng dụng công cụ hiện đại
Tận mắt nhìn thấy sức mạnh của việc kết hợp Machine Learning để tự động hóa phát hiện các cuộc tấn công mạng vượt qua lớp WAF truyền thống. Dashboard theo dõi lưu lượng mạng trực quan và cơ chế cảnh báo tự động thông báo qua SNS giúp tôi nhận ra tiềm năng to lớn của việc ứng dụng công nghệ thông minh vào công tác an ninh an toàn thông tin.

### Kết nối và trao đổi
Không gian sự kiện tại văn phòng AWS vô cùng chuyên nghiệp và cởi mở. Trong giờ giải lao, tôi đã chủ động kết nối, trò chuyện với anh Huỳnh Bảo về môi trường làm việc thực tế tại Endava Vietnam cũng như cách thức hoạt động của phòng lab ITea Lab do anh sáng lập. Buổi trò chuyện cởi mở giúp tôi tự tin hơn trong việc giao tiếp và học hỏi từ những người đi trước trong ngành.

### Bài học rút ra & Đóng góp cá nhân
- **Bài học rút ra**:
  + Một giải pháp công nghệ tốt không nhất thiết phải là giải pháp phức tạp nhất, mà phải là giải pháp giải quyết hiệu quả nhất bài toán nghiệp vụ của doanh nghiệp với chi phí hợp lý.
  + Kiến thức nền tảng vững chắc (Linux, Networking, cấu trúc dữ liệu) luôn là bệ phóng vững chắc nhất giúp người kỹ sư thích ứng nhanh chóng với mọi sự thay đổi công nghệ.
- **Đóng góp và Tương tác cá nhân**:
  + Chủ động tham gia đặt câu hỏi trực tiếp cho diễn giả Việt Phát trong phiên trình bày về GraphRAG để làm rõ sự khác biệt giữa hai phương pháp Custom và Managed trên AWS Neptune.
  + Giao lưu và trao đổi thông tin liên lạc với các diễn giả và các bạn sinh viên cùng tham gia sự kiện để xây dựng mạng lưới học tập đám mây lâu dài.

### Một số hình ảnh khi tham gia sự kiện 

Dưới đây là một số hình ảnh thực tế ghi lại những khoảnh khắc đáng nhớ của bản thân khi tham gia sự kiện AWS First Cloud Journey AI:

![Slide hiển thị 3 câu hỏi thảo luận lớn của Panel thảo luận với Giám đốc AWS AI về xu hướng AI, kỹ năng cần thiết cho lập trình viên trẻ và giải quyết khoảng cách năng lực doanh nghiệp](/images/4-EventParticipated/4.2-Event2/IMG20260606090407.jpg)
<!-- slide -->
![Giám đốc AWS AI trình bày về việc điện toán đám mây và AI giúp hạ thấp rào cản gia nhập thị trường cho các nhà xây dựng công nghệ trẻ](/images/4-EventParticipated/4.2-Event2/IMG20260606091540.jpg)
<!-- slide -->
![Slide tiêu đề phần thuyết trình "Multiplayer in the Cloud: Connecting Godot Clients with AWS WebSockets" của diễn giả Nguyễn Quốc Bảo](/images/4-EventParticipated/4.2-Event2/IMG20260606092843.jpg)
<!-- slide -->
![Slide mục lục (Table of Contents) của chủ đề game multiplayer kết nối qua WebSocket](/images/4-EventParticipated/4.2-Event2/IMG20260606092927.jpg)
<!-- slide -->
![Slide mô tả chi tiết thiết kế Schema cơ sở dữ liệu DynamoDB (DynamoDB Schema) lưu trữ trạng thái người chơi và đối thủ](/images/4-EventParticipated/4.2-Event2/IMG20260606093539.jpg)
<!-- slide -->
![Slide đúc kết các thách thức kỹ thuật (Challenges) như Stale Connections, chi phí DynamoDB Scan và tính stateless của Lambda](/images/4-EventParticipated/4.2-Event2/IMG20260606095009.jpg)
<!-- slide -->
![Slide tiêu đề chủ đề "Docker — A containerization technology" do anh Huỳnh Bảo trình bày](/images/4-EventParticipated/4.2-Event2/IMG20260606095859.jpg)
<!-- slide -->
![Slide chương trình giới thiệu (Agenda) các mục chính của phần chia sẻ Docker](/images/4-EventParticipated/4.2-Event2/IMG20260606100049.jpg)
<!-- slide -->
![Slide phân tích lợi ích của ảo hóa và sự cần thiết của công nghệ container hóa đối với việc tối ưu hóa tài nguyên máy chủ](/images/4-EventParticipated/4.2-Event2/IMG20260606100430.jpg)
<!-- slide -->
![Slide so sánh trực quan (VM vs Container) chi tiết về cấu trúc hệ thống, kích thước và tài nguyên tiêu thụ](/images/4-EventParticipated/4.2-Event2/IMG20260606101230.jpg)
<!-- slide -->
![Slide cảm ơn (Thank You) kết thúc phần trình bày Docker của anh Huỳnh Bảo với hình ảnh nhân vật Kasane Teto](/images/4-EventParticipated/4.2-Event2/IMG20260606103701.jpg)
<!-- slide -->
![Slide chương trình (Agenda) giới thiệu cấu trúc các nội dung của chuyên đề GraphRAG do bạn Việt Phát chia sẻ](/images/4-EventParticipated/4.2-Event2/IMG20260606103959.jpg)
<!-- slide -->
![Slide tiêu đề chuyên đề "WAF + ML for Cyber Attack Detection: Machine Learning-based Network Intrusion Detection System (NIDS) on AWS" của bạn Lê Hoàng Gia Đại](/images/4-EventParticipated/4.2-Event2/IMG20260606105006.jpg)
<!-- slide -->
![Slide giới thiệu chi tiết về chức năng bảo vệ ứng dụng web của AWS WAF (Web Application Firewall)](/images/4-EventParticipated/4.2-Event2/IMG20260606105132.jpg)
<!-- slide -->
![Slide sơ đồ nguyên lý hoạt động của NIDS (How NIDS Works) kết nối giữa Web traffic, ML Model, DB và cảnh báo](/images/4-EventParticipated/4.2-Event2/IMG20260606105920.jpg)
<!-- slide -->
![Sơ đồ kiến trúc hạ tầng đám mây tích hợp AWS WAF, Lambda, S3, Kinesis Firehose, CloudWatch và các dịch vụ bảo mật của AWS](/images/4-EventParticipated/4.2-Event2/IMG20260606110049.jpg)
<!-- slide -->
![Slide tổng hợp các kết quả thực nghiệm, định hướng cải tiến sử dụng Amazon Bedrock và các bài học kinh nghiệm của bạn Lê Hoàng Gia Đại](/images/4-EventParticipated/4.2-Event2/IMG20260606110335.jpg)
<!-- slide -->
![Slide tiêu đề bài chia sẻ "From IT Helpdesk to Senior Sysadmin" của anh Trần Trung Vinh tại Central Retail Group](/images/4-EventParticipated/4.2-Event2/IMG20260606111037.jpg)
<!-- slide -->
![Slide mục lục chương trình (Agenda) chia sẻ lộ trình thăng tiến sự nghiệp từ kỹ sư Helpdesk lên Sysadmin và Cloud/DevOps](/images/4-EventParticipated/4.2-Event2/IMG20260606111212.jpg)
<!-- slide -->
![Slide phân tích những kỹ năng học được từ Helpdesk và bước ngoặt (Turning Point) khi tự xây dựng phòng Lab nghiên cứu](/images/4-EventParticipated/4.2-Event2/IMG20260606111433.jpg)
<!-- slide -->
![Slide đúc kết thực tế vai trò Sysadmin (Realistic View) cùng các bài học xương máu về việc không bao giờ được kiểm thử trên Production](/images/4-EventParticipated/4.2-Event2/IMG20260606111742.jpg)
<!-- slide -->
![Slide lộ trình học tập DevOps hiện đại (Modern DevOps Roadmap) gồm 8 bước từ Linux đến Monitoring & Observability](/images/4-EventParticipated/4.2-Event2/IMG20260606112554.jpg)
<!-- slide -->
![Slide hiển thị thông tin liên hệ và mã QR kết nối (Connect With Me) của diễn giả Trần Trung Vinh](/images/4-EventParticipated/4.2-Event2/IMG20260606113609.jpg)
<!-- slide -->
![Ảnh chụp cuốn sổ tay ghi chú thứ tự trình bày và tóm tắt các diễn giả của sự kiện do tôi ghi lại](/images/4-EventParticipated/4.2-Event2/note.png)

> Sự kiện đã mang lại cho bản thân rất nhiều kiến thức giá trị cùng nguồn cảm hứng công nghệ to lớn, làm chắc chắn cho quá trình học tập và làm việc sau này.
