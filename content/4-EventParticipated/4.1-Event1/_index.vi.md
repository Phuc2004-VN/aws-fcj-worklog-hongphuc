---
title: "Event 1"
date: 2026-05-23
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# Bài thu hoạch AWS Vietnam Community Day 2026

| Thông tin sự kiện | Chi tiết |
| :--- | :--- |
| **Tên sự kiện** | AWS Vietnam Community Day 2026 (Gặp gỡ Thứ Bảy) |
| **Thời gian** | 23/05/2026 (Từ 09:00 đến 12:00) |
| **Địa điểm** | Tầng 26, Bitexco Financial Tower, TP. Hồ Chí Minh |
| **Vai trò** | Người tham dự |

### Mục Đích Của Sự Kiện
Sự kiện Gặp gỡ Thứ Bảy - AWS Vietnam Community Day 2026 là ngày hội công nghệ lớn mà tôi có cơ hội tham gia trực tiếp tại tầng 26 của tòa nhà Bitexco Financial Tower. Mục đích cốt lõi của sự kiện lần này là tạo không gian giao lưu, gắn kết cho cộng đồng những người làm việc hoặc đang học tập trong hệ sinh thái đám mây AWS tại Việt Nam. 

Thay vì chỉ tập trung vào lý thuyết sách vở, sự kiện hướng tới việc chia sẻ các câu chuyện thực tiễn từ các doanh nghiệp đang vận hành hệ thống lớn như GoTymeX hay VPBank. Qua đó, người tham gia -từ các kỹ sư lâu năm cho đến các bạn sinh viên như tôi - có thể học hỏi thêm nhiều kiến thức mới về tối ưu hệ thống, ứng dụng Generative AI vào công việc và định hình rõ ràng hơn lộ trình phát triển kỹ năng kỹ thuật của bản thân.

### Danh Sách Diễn Giả

| STT | Diễn giả | Chức vụ | Chủ đề |
| :-: | -------- | ------- | ------ |
| 1 | **Tinh Truong** | Platform Engineer @GoTymeX | *Context Is Everything – Making AI Actually Work for You* |
| 2 | **Pham Ng Hai Anh** | AWS Community Builder @G-AsiaPacificVietnam | *Friendly AI Assistant w/ Amazon Quick* |
| 3 | **Nguyen Tuan Thinh** | AWS Champion Instructor, 12x AWS Certified | *From Edge To Origin: CloudFront as Your Foundation* |
| 4 | **Team VIB** | AWS Track Winner @LotusHacks2026 | *36 hours with LotusHacks – Building UTMorpho* |
| 5 | **Duc Dao** | Solution Architect @CloudKinetics | *Non-Determinism of "Deterministic" LLM Settings* |
| 6 | **Vy Lam** | Sr. Business Systems Analyst @VPBank | *Enterprise-Grade Multi-Agent System* |

### Nội Dung Nổi Bật

#### Đưa ra các ảnh hưởng tiêu cực của kiến trúc ứng dụng cũ
Khi lắng nhe chia sẻ từ các diễn giả, tôi nhận ra rất nhiều doanh nghiệp hiện nay vẫn đang chật vật với những hệ thống cũ chạy theo kiểu Monolith truyền thống hoặc phân phối nội dung trực tiếp từ một server duy nhất mà không qua mạng phân phối CDN. Điểm yếu lớn nhất ở đây là độ trễ mạng cực kỳ cao. Người dùng tại Việt Nam khi truy cập các ứng dụng có server đặt ở Mỹ thường phải đợi hơn 200ms để tải trang. Điều này không chỉ gây ức chế cho người dùng mà còn làm hao tốn băng thông quốc tế của doanh nghiệp. Hơn thế nữa, việc mở cổng cho người dùng kết nối trực tiếp vào máy chủ gốc (Origin) biến server thành miếng mồi ngon cho các cuộc tấn công DDoS hoặc mã độc từ botnet mà không có lớp lá chắn bảo vệ ở biên mạng.

Ở góc độ ứng dụng trí tuệ nhân tạo, các hệ thống cũ tích hợp AI theo dạng thô sơ—chỉ gửi các câu lệnh (prompt) đơn lẻ mà không có hệ thống quản lý ngữ cảnh hay bộ nhớ dài hạn. Điều này làm cho AI phản hồi rất ngô nghê, thường xuyên xảy ra lỗi ảo tưởng (hallucination) và không giải quyết được các tác vụ phức tạp của doanh nghiệp. Ngoài ra, việc lầm tưởng rằng thiết lập nhiệt độ bằng 0 (Temperature = 0) là LLM sẽ trả ra kết quả hoàn toàn giống nhau cũng gây ra nhiều lỗi logic nghiêm trọng khi đưa ứng dụng vào môi trường production thực tế do các cơ chế tối ưu hóa song song trên GPU hoạt động bất đồng bộ. Cuối cùng, đối với nghiệp vụ tài chính ngân hàng, hệ thống đánh giá thủ công hoặc phân tích dữ liệu cũ quá chậm chạp, không thể xử lý nổi nguồn dữ liệu lớn và phi cấu trúc của các doanh nghiệp khởi nghiệp, gây cản trở việc tiếp cận nguồn vốn.

### Chuyển đổi sang kiến trúc ứng dụng mới - Microservice Architecture
Để khắc phục những hạn chế của hệ thống cũ, xu hướng dịch chuyển sang kiến trúc Microservices hiện đại là tất yếu. Trong mô hình này, một ứng dụng khổng lồ sẽ được bẻ nhỏ thành nhiều dịch vụ độc lập, giao tiếp với nhau qua API hoặc các luồng sự kiện. 

Một điểm cực kỳ thú vị mà tôi học được từ phần trình bày của chị Vy Lam là việc áp dụng mô hình này vào thiết kế AI dưới dạng hệ thống Multi-Agent (Đa tác nhân). Thay vì cố bắt một mô hình LLM gánh vác toàn bộ công việc, hệ thống phân rã thành nhiều Agent chuyên biệt như những microservices độc lập: một Agent thu thập dữ liệu khởi nghiệp, một Agent phân tích rủi ro tín dụng và một Agent kiểm tra tính tuân thủ pháp lý. Cách thiết kế này giúp cô lập lỗi tốt hơn, dễ dàng nâng cấp từng thành phần độc lập mà không ảnh hưởng tới toàn bộ hệ thống chung.

### Domain-Driven Design (DDD)
Thiết kế hướng tên miền (DDD) đóng vai trò nền tảng giúp phân chia ranh giới rõ ràng cho các dịch vụ trong hệ thống Microservices hoặc các tác nhân trong mô hình Multi-Agent. Thay vì nhảy vào viết code ngay, DDD yêu cầu các kỹ sư phải làm việc chặt chẽ với bộ phận nghiệp vụ để thống nhất một ngôn ngữ chung (Ubiquitous Language) và phân chia hệ thống thành các Bounded Contexts (ngữ cảnh giới hạn) độc lập.

Điều này thể hiện rất rõ qua bài chia sẻ của nhóm VIB khi tham gia LotusHacks 2026. Trong vòng 36 tiếng ngắn ngủi, nếu không áp dụng DDD để phân tách ranh giới các nghiệp vụ của sản phẩm UTMorpho và xác định rõ thực thể nào tương tác với nhau, bản thân họ chắc chắn sẽ bị rối và không thể hoàn thành sản phẩm đúng hạn. Tương tự, tại VPBank, việc thiết lập "Ủy ban tín dụng ảo" bằng Multi-Agent đòi hỏi ranh giới trách nhiệm của từng Agent phải cực kỳ rõ ràng để đảm bảo tính tuân thủ trong môi trường ngân hàng nghiêm ngặt.

### Event-Driven Architecture
Kiến trúc hướng sự kiện giúp các dịch vụ hoặc các Agent trong hệ thống hoạt động bất đồng bộ, giảm thiểu sự phụ thuộc trực tiếp lẫn nhau. Khi một sự kiện xảy ra (ví dụ: khách hàng tải lên một bộ tài liệu mới), hệ thống sẽ phát đi một sự kiện và các dịch vụ quan tâm sẽ tự động bắt lấy để xử lý công việc của mình mà không cần server chính phải liên tục gửi yêu cầu kiểm tra.

Ở mức độ hạ tầng mạng, Amazon CloudFront kết hợp với CloudFront Functions và Lambda@Edge cho phép bắt các sự kiện yêu cầu (request) và phản hồi (response) ngay tại các trạm biên (Edge Locations) gần người dùng nhất. Nhờ đó, chúng ta có thể thực hiện rewrite URL, redirect hoặc điều chỉnh header trực tiếp tại Edge với độ trễ dưới 1ms, loại bỏ hoàn toàn việc phải gửi request ngược về server gốc ở xa.

### Compute Evolution
Hạ tầng tính toán đã đi một chặng đường dài từ việc sử dụng các máy chủ vật lý cồng kềnh, chuyển sang máy ảo đám mây (EC2), container (ECS, Fargate) và giờ đây là Serverless (AWS Lambda). 

Khi dịch chuyển sang mô hình Serverless, chúng ta không cần phải lo lắng về việc quản trị hệ điều hành, cấu hình mạng hay vá lỗi bảo mật định kỳ cho máy chủ. Hệ thống sẽ tự động scale linh hoạt từ 0 đến hàng ngàn request đồng thời và chỉ tính phí trên thời gian chạy thực tế của code. Sự tiến hóa này giúp các lập trình viên tập trung hoàn toàn vào việc viết logic nghiệp vụ, đồng thời giúp doanh nghiệp tối ưu chi phí vận hành ở mức tối đa.

### Amazon Q Developer
Amazon Q Developer cùng bộ giải pháp AI từ G-AsiaPacific như Amazon Quick (bao gồm Quick Chat, Quick Flow, Quick Spaces, Quick Sight) mang lại cho bản thân tôi góc nhìn mới về cách ứng dụng AI hỗ trợ quy trình phát triển phần mềm (SDLC).

Nhờ các trợ lý AI này, việc viết mã nguồn, tối ưu hóa code và viết unit test trở nên nhanh chóng hơn rất nhiều. Đặc biệt, công cụ Quick Sight cho phép người dùng nghiệp vụ không có kiến thức lập trình vẫn có thể dễ dàng truy vấn dữ liệu thô và dựng nên các dashboard phân tích báo cáo trực quan chỉ bằng cách trò chuyện với AI bằng ngôn ngữ tự nhiên, giúp doanh nghiệp ra quyết định kinh doanh nhanh hơn gấp nhiều lần.

### Những Gì Học Được

#### Tư Duy Thiết Kế
- Tôi nhận ra rằng CloudFront không đơn giản chỉ là công cụ lưu trữ đệm cho hình ảnh hay file tĩnh như bản thân từng nghĩ. Nó thực chất là một lớp bảo mật biên vững chắc, giúp ẩn giấu toàn bộ hệ thống backend (Origin Cloaking) và giảm tải tối đa cho server gốc.
- Khi xây dựng các ứng dụng AI, tư duy thiết kế hệ thống phải đi liền với việc xây dựng ngữ cảnh (Context) và trí nhớ dài hạn ("Second Brain") thông qua kỹ thuật RAG. AI chỉ thực sự hữu ích khi nó có đủ thông tin và dữ liệu phù hợp với nghiệp vụ cụ thể.
- Thiết kế kỹ thuật luôn luôn phải bắt đầu từ nghiệp vụ thực tế (Business-first). Việc cố gắng áp đặt công nghệ phức tạp vào khi chưa hiểu rõ bài toán nghiệp vụ sẽ chỉ tạo ra một kiến trúc cồng kềnh và không hiệu quả.

#### Kiến Trúc Kỹ Thuật
- Nắm vững các kỹ thuật caching nâng cao của CloudFront như multi-layer caching, Regional Edge Caches, và request collapsing để tối ưu hóa đường truyền dữ liệu động.
- Phân biệt rõ ràng mục đích sử dụng của CloudFront Functions (chạy script JavaScript siêu nhẹ tại Edge, độ trễ cực thấp <1ms, dùng cho thay đổi header hoặc chuyển hướng nhanh) và Lambda@Edge (hỗ trợ đầy đủ thư viện Node.js/Python để xử lý logic phức tạp hơn).
- Hiểu rõ nguồn gốc của tính phi xác định trong LLM (do GPU tối ưu hóa các phép tính dấu phẩy động song song) và cách áp dụng các Guardrails để kiểm soát kết quả đầu ra, đảm bảo hệ thống tự động hoạt động ổn định.

#### Chiến Lược Hiện Đại Hóa
- Việc nâng cấp hệ thống cũ lên Cloud/AI cần được thực hiện từng bước một theo lộ trình rõ ràng (Phased Approach) dựa trên mô hình đánh giá 7Rs và tính toán ROI kỹ lưỡng, tránh tâm lý nôn nóng đập đi xây lại toàn bộ.
- Bài học từ dự án UTMorpho của nhóm VIB cho bản thân tôi thấy tầm quan trọng của việc định hình sản phẩm khả dụng tối thiểu (MVP) để thử nghiệm nhanh chóng, sẵn sàng chấp nhận các lỗi phát sinh và xoay hướng sản phẩm linh hoạt khi thị trường yêu cầu.

### Ứng Dụng Vào Công Việc
- Trong các bài thực hành workshop tiếp theo (ví dụ như dự án IoT Weather Platform), tôi sẽ thử cấu hình Amazon CloudFront đứng trước backend để kiểm chứng khả năng tăng tốc độ tải dữ liệu biểu đồ thời tiết thời gian thực và bảo vệ hệ thống bằng AWS Shield.
- Tôi sẽ triển khai thử nghiệm mô hình hosting website tĩnh sử dụng kết hợp CloudFront và Amazon S3, cấu hình Origin Access Control (OAC) để chặn hoàn toàn truy cập trực tiếp từ internet vào S3, tăng cường tính bảo mật cho trang web cá nhân của bản thân.
- Áp dụng kiến thức RAG và quản lý ngữ cảnh để xây dựng một công cụ tìm kiếm tài liệu AWS cá nhân, giúp việc ôn thi các chứng chỉ AWS sau này hiệu quả hơn.
- Tích hợp sâu Amazon Q Developer vào IDE viết code hàng ngày (VS Code) để tận dụng AI trong việc gợi ý mã nguồn, tối ưu hóa thuật toán và viết test cases tự động.

### Trải nghiệm trong event

#### Học hỏi từ các diễn giả có chuyên môn cao
Các bài thuyết trình của các anh chị diễn giả rất cuốn hút vì chứa đựng nhiều kinh nghiệm thực tế xương máu. Tôi vô cùng ấn tượng với phần chia sẻ về CloudFront của anh Nguyễn Tuấn Thịnh. Với 12 chứng chỉ AWS và danh hiệu AWS Champion Instructor, anh đã giải thích cơ chế phân phối dữ liệu từ Mỹ về Việt Nam qua các ví dụ thực tế rất sinh động và trực quan, giúp một sinh viên như tôi có thể nắm bắt bản chất vấn đề một cách nhanh chóng mà không bị ngợp bởi các thuật ngữ phức tạp.

#### Trải nghiệm kỹ thuật thực tế
Tôi được xem trực tiếp các bản demo chạy thực tế của hệ thống Multi-Agent chấm điểm tín dụng và cách điều phối công việc giữa các Agent trong Ủy ban tín dụng ảo của VPBank. Đồng thời, những chia sẻ chân thực của nhóm VIB về những khó khăn, lỗi hệ thống gặp phải trong đêm thi LotusHacks và cách họ vượt qua áp lực thời gian mang lại cho bản thân tôi nhiều kinh nghiệm quý báu về kỹ năng làm việc nhóm và giải quyết vấn đề dưới áp lực cao.

#### Ứng dụng công cụ hiện đại
Tận mắt chứng kiến sức mạnh của Amazon QuickSight Q và bộ trợ lý AI thông minh trong phần demo của anh Phạm Nguyễn Hải Anh. Chỉ bằng việc nhập các câu hỏi tự nhiên như "Doanh thu tháng trước tăng trưởng thế nào?", AI đã tự động phân tích dữ liệu thô và xuất ra biểu đồ trực quan trong tích tắc. Đây thực sự là bước tiến lớn giúp thu hẹp khoảng cách giữa người dùng nghiệp vụ và kỹ thuật dữ liệu.

### Kết nối và trao đổi
Không gian sự kiện tại Bitexco vô cùng rộng mở và náo nhiệt. Trong giờ giải lao, tôi đã tranh thủ trò chuyện với một vài anh chị kỹ sư hệ thống đi trước và các anh chị AWS Community Builders. Mọi người rất thân thiện và nhiệt tình giải đáp những thắc mắc của tôi về cơ hội nghề nghiệp cũng như cách học AWS hiệu quả. Buổi gặp gỡ giúp bản thân tôi cảm nhận rõ nét sự năng động và phát triển mạnh mẽ của cộng đồng AWS tại Việt Nam.

### Bài học rút ra & Đóng góp cá nhân
- **Bài học rút ra**:
  + Một bài trình bày kỹ thuật thành công không nằm ở việc khoe khoang công nghệ phức tạp, mà nằm ở việc diễn giả có thể đơn giản hóa những khái niệm trừu tượng thành những câu chuyện thực tế gần gũi với người nghe.
  + Việc tối ưu hóa hệ thống từ biên mạng và tích hợp trí tuệ nhân tạo có ngữ cảnh là hai yếu tố then chốt tạo nên lợi thế cạnh tranh cho các ứng dụng công nghệ hiện đại.
- **Đóng góp và Tương tác cá nhân**:
  + Tích cực trao đổi, thảo luận và đặt câu hỏi cho diễn giả Nguyễn Tuấn Thịnh trong phiên chia sẻ về CloudFront, cụ thể là tìm hiểu sâu hơn về sự khác biệt hiệu năng giữa CloudFront Functions và Lambda@Edge khi chạy thực tế.
  + Chủ động kết nối với các AWS Community Builders tại sự kiện để học hỏi kinh nghiệm thực tế, cách học AWS hiệu quả và tìm kiếm cơ hội tham gia các thử thách công nghệ tiếp theo.

### Một số hình ảnh khi tham gia sự kiện

Dưới đây là một số hình ảnh thực tế ghi lại những khoảnh khắc đáng nhớ của bản thân khi tham gia sự kiện AWS Vietnam Community Day 2026:

![Slide "What's Next" giới thiệu dự án UTMorpho của nhóm VIB với mã QR truy cập Devpost và GitHub](/images/4-EventParticipated/4.1-Event1/IMG20260523105858.jpg)
<!-- slide -->
![Slide giới thiệu các tham số cấu hình mô hình ngôn ngữ lớn (LLM): Top-P và Top-K cùng mã QR trải nghiệm trực quan](/images/4-EventParticipated/4.1-Event1/IMG20260523111358.jpg)
<!-- slide -->
![Slide phân tích thực tế nghiên cứu hiệu năng của các mô hình LLM trên nhiều tác vụ xử lý ngôn ngữ tự nhiên (NLP) khác nhau](/images/4-EventParticipated/4.1-Event1/IMG20260523111644.jpg)
<!-- slide -->
![Slide giải thích nguyên nhân kỹ thuật gây ra tính phi xác định ở LLM từ phép tính dấu phẩy động IEEE 754 trên GPU và thứ tự thực thi thread song song](/images/4-EventParticipated/4.1-Event1/IMG20260523112629.jpg)
<!-- slide -->
![Slide đề xuất các chiến lược giảm thiểu tính phi xác định của LLM như chạy nhiều lần, định dạng đầu ra cấu trúc và tự host model](/images/4-EventParticipated/4.1-Event1/IMG20260523112744.jpg)
<!-- slide -->
![Slide tổng hợp các mẹo (Tips) cấu hình mô hình LLM: rủi ro lặp của greedy decoding, giá trị tối ưu nhiệt độ và repeat penalty](/images/4-EventParticipated/4.1-Event1/IMG20260523113044.jpg)
<!-- slide -->
![Slide "Tips" cấu hình LLM có thêm ghi chú màu đỏ về việc chọn nhiệt độ 0.1 để tránh lặp nội dung](/images/4-EventParticipated/4.1-Event1/IMG_20260523_113141.jpg)
<!-- slide -->
![Slide tổng kết các bài học cốt lõi (Key Takeaways) về việc thiết kế ứng dụng thích ứng với độ lệch và chú trọng kiểm thử](/images/4-EventParticipated/4.1-Event1/IMG20260523113240.jpg)
<!-- slide -->
![Slide hiển thị mã QR liên kết đến bài báo nghiên cứu chuyên sâu về các thiết lập của mô hình ngôn ngữ lớn (LLM Settings)](/images/4-EventParticipated/4.1-Event1/IMG20260523113404.jpg)
<!-- slide -->
![Slide chương trình (Agenda) giới thiệu cấu trúc đa tác nhân (Multi-Agent) cấp doanh nghiệp ứng dụng trong thẩm định tín dụng](/images/4-EventParticipated/4.1-Event1/IMG20260523114740.jpg)
<!-- slide -->
![Slide phân tích lý do kiến trúc đa tác nhân hoạt động hiệu quả nhờ tính chuyên môn hóa, kiểm tra chéo và khả năng chịu lỗi](/images/4-EventParticipated/4.1-Event1/IMG20260523120206.jpg)
<!-- slide -->
![Slide giới thiệu 6 trụ cột của hệ thống AI cấp doanh nghiệp: Bảo mật, Quản trị dữ liệu, Mạng, Vận hành, Con người và Tuân thủ](/images/4-EventParticipated/4.1-Event1/IMG20260523120612.jpg)
<!-- slide -->
![Slide đề xuất quy trình triển khai ứng dụng Multi-Agent chi tiết qua từng bước từ local app đến hạ tầng AWS](/images/4-EventParticipated/4.1-Event1/IMG20260523121833.jpg)
<!-- slide -->
![Sơ đồ kiến trúc mô tả luồng triển khai cơ bản (Basic Deployment Flow) từ môi trường local lên hạ tầng cloud AWS](/images/4-EventParticipated/4.1-Event1/IMG20260523121900.jpg)
<!-- slide -->
![Slide danh sách các bài thực hành workshop từ cơ bản đến nâng cao bao gồm xác thực, Guardrails, MCP và Terraform](/images/4-EventParticipated/4.1-Event1/IMG20260523122352.jpg)
<!-- slide -->
![Slide bài thực hành workshop có thêm ghi chú màu đỏ nhấn mạnh việc xây dựng hệ thống không chỉ cần chạy được mà phải an toàn](/images/4-EventParticipated/4.1-Event1/IMG_20260523_123205.jpg)
<!-- slide -->
![Bức ảnh tập thể các thành viên chụp chung lưu niệm khi kết thúc sự kiện](/images/4-EventParticipated/4.1-Event1/event1.jpg)
<!-- slide -->
![Bức ảnh selfie của tôi tại sự kiện trước khi ra về](/images/4-EventParticipated/4.1-Event1/event1.1.jpg)

>Sự kiện đã mang lại cho bản thân rất nhiều kiến thức giá trị cùng nguồn cảm hứng công nghệ to lớn, làm chắc chắn cho quá trình học tập và làm việc sau này.
