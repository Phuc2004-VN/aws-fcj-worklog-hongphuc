---
title: "Event 2"
date: 2026-06-06
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

# Report: AWS First Cloud Journey AI

| Event Information | Details |
| :--- | :--- |
| **Event Name** | AWS First Cloud Journey AI |
| **Date & Time** | June 6, 2026 (09:00 - 12:00) |
| **Location** | 26th Floor, Bitexco Financial Tower, Ho Chi Minh City |
| **Role** | Attendee |

### Event Objectives
The AWS First Cloud Journey AI event was a deep-dive technical sharing session focused on artificial intelligence (AI), modern cloud-native applications, effective teamwork practices, and career path navigation in the Information Technology sector, which I had the opportunity to attend in person at the AWS Vietnam office (26th floor, Bitexco Financial Tower).

The core purpose of this event was to provide students and young developers with a comprehensive perspective on applying AWS cloud services and AI to real-world scenarios. The sessions spanned from designing real-time multiplayer game lobbies and optimizing containerization with Docker, to constructing advanced search architectures using GraphRAG and enhancing web security with Machine Learning models. Alongside deep technical content, the event featured vital discussions on collaboration and project coordination methodologies. Additionally, the panel discussion and the real-life story of a former Helpdesk engineer transitioning to a Senior Sysadmin helped me map out a clear learning path and prepare a solid technical foundation to enter the professional industry.

### Speakers

The event commenced with an engaging **AWS AI Director Panel / Q&A** keynote session moderated by the AWS AI leadership. This was followed by technical and soft skills presentations by the speakers:

| No. | Speaker | Role | Topic |
| :-: | ------- | ---- | ----- |
| 1 | **Nguyen Quoc Bao** | Cloud Engineer / Game Developer | *Multiplayer in the Cloud: Connecting Godot Clients with AWS WebSockets* |
| 2 | **Huynh Bao** | Junior Cloud Native Developer @Endava Vietnam | *Docker — A containerization technology* |
| 3 | **Viet Phat** | AI Majoring @Swinburne University of Technology | *GraphRAG: Build GraphRAG applications using Amazon Bedrock and Amazon Neptune* |
| 4 | **Le Hoang Gia Dai** | Final-year Student @HUTECH University | *WAF + ML for Cyber Attack Detection: Machine Learning-based Network Intrusion Detection System (NIDS) on AWS* |
| 5 | **Tran Trung Vinh** | System Administrator @Central Retail Group | *From IT Helpdesk to Senior Sysadmin* |
| 6 | **Truong Huy Phuoc** | Presenter / Teamwork Coach | *The Art of Effective Teamwork* |

### Key Highlights

#### AWS AI Director Panel / Q&A
The opening session brought about an active discussion on the rapid evolution of artificial intelligence and how the next generation of engineers should prepare themselves for this technological wave.
- **Core Skills**: In an era of automated code assistants, students and developers must invest heavily in system architecture design, problem-solving mindsets, and the ability to seamlessly integrate various cloud services. Manual coding might be partially automated, but business analysis and solution design will remain critical engineering capabilities over the next 5 years.
- **Enterprise Gaps**: There is a significant gap between what enterprises want to achieve with AI and what developers are capable of delivering. To close this gap, engineers should leverage AWS Managed Services to shorten development lifecycles and reduce operational costs.
- **Key Message**: Cloud and AI have lowered the barrier of entry for young builders. With the right idea and design thinking, a young developer can single-handedly build applications on a global scale.

#### Connecting Godot Clients with AWS WebSockets (Multiplayer in the Cloud)
This session focused on designing and programming a real-time multiplayer rock-paper-scissors game communicating directly over a reliable network protocol.
- **Choosing the Network Architecture**:
  + **UDP/ENet**: Best for fast-paced action games (FPS, racing) due to ultra-low latency, but requires complex application-level logic to ensure packet reliability.
  + **HTTP Polling**: Suitable for non-real-time actions (login, leaderboards) but introduces high latency and wastes bandwidth through continuous request-response polling.
  + **WebSocket**: The optimal choice for turn-based games, matchmaking lobbies, or chat systems, offering full-duplex, two-way communication and guaranteed message delivery.
- **Architecture on AWS**: The Godot client uses its built-in `WebSocketPeer` class to connect to API Gateway WebSocket. API Gateway routes messages based on the `$request.body.action` parameter to AWS Lambda (Node.js 20), which processes the game logic and updates session states in DynamoDB.
- **Technical Challenges**:
  + **Stale Connections**: When players disconnect abruptly, stale connection records remain in DynamoDB, resulting in `GoneException` errors when the server attempts to push updates.
  + **DynamoDB Scan Cost**: Using `ScanCommand` to find matching players results in full table scans, causing latency and high operational costs as player numbers grow.
  + **Stateless Lambda**: Since Lambda is stateless, game states must be continuously fetched from and saved back to DynamoDB in every execution loop.
- **Future Improvements**: Transitioning to AWS GameLift for dedicated game servers to handle complex physics calculations and automate server fleet scaling.

#### Docker — A Containerization Technology
Speaker Huynh Bao provided an intuitive, practical guide to containerization, addressing the classic "it works on my machine" compatibility issue.
- **Limitations of Virtual Machines**: Traditional VMs are resource-heavy, as each requires a full guest operating system. This consumes significant CPU, memory, and storage, and requires separate OS patching and maintenance.
- **The Docker Solution**: Docker packages an application and its dependencies into a lightweight container sharing the host OS kernel. This enables the "build once, run anywhere" paradigm, ensuring consistent runs across development, testing, and production.
- **Image Layering**: Every instruction in a `Dockerfile` generates a distinct, immutable image layer. Docker reuses cached layers for unchanged steps during rebuilding, vastly accelerating the packaging workflow.
- **Use Cases**: Containerization forms the foundation of microservice deployments, automated CI/CD pipelines, and cloud-native applications.

#### GraphRAG: Build GraphRAG applications using Amazon Bedrock and Neptune
This session introduced methods to optimize Large Language Model retrievals by structuring unstructured data into knowledge graphs.
- **Limitations of Traditional RAG**: Basic vector-search-based RAG struggles with multi-hop reasoning questions, such as: "Where is the company headquartered that was acquired by the company founded by Jeff Bezos?"
- **The GraphRAG Solution**: A knowledge graph models data as nodes (entities) and edges (relationships). During retrieval, the LLM traverses the graph to follow relationships across multiple documents, extracting highly contextual answers.
- **Implementation Paths on AWS**:
  + **Fully Managed Route**: Utilizing Amazon Bedrock Knowledge Bases to automate chunking, entity extraction, and embedding creation, and storing the resulting graph in Amazon Neptune Analytics for relationship discovery.
  + **Custom Route**: Building a custom pipeline using LlamaIndex for graph construction and storing it on Amazon Neptune, querying the data via Cypher Query Language for multi-hop graph traversal.

#### WAF + ML for Cyber Attack Detection (NIDS on AWS)
An advanced cybersecurity session demonstrating how to build a Machine Learning-based Network Intrusion Detection System (NIDS) to complement traditional firewalls.
- **Limitations of Traditional WAF**: Traditional WAFs rely on rule-based patterns, leaving them vulnerable to novel zero-day attacks, hybrid obfuscation techniques, or anomalous traffic without existing signatures.
- **The ML-based NIDS Solution**:
  + Training a LightGBM model on the standardized CSE-CIC-IDS2018 dataset on AWS, which logs benign traffic alongside common attacks (DoS, SQLi, Bot, Brute Force, DDoS).
  + Crucial Preprocessing Steps: Merging large CSV files, removing corrupted labels, handling missing or infinity values, and balancing classes to improve minority attack detection.
- **AWS Cloud Deployment**: Integrating VPC, EC2 for NIDS models, and Application Load Balancer (ALB). Access logs are streamed via Amazon Kinesis Data Firehose to S3, triggering an AWS Lambda function to cross-reference NIDS predictions with WAF events. Real-time alerts are pushed through SNS to Security Hub, GuardDuty, and CloudWatch.

#### From IT Helpdesk to Senior Sysadmin
An inspiring career transition story from speaker Tran Trung Vinh, proving that self-learning and hands-on practice are key to professional growth.
- **Helpdesk Foundations**: Helpdesk positions teach valuable soft skills, including troubleshooting under pressure, active customer communication, and root-cause analysis.
- **The Turning Point**: Taking the initiative to master Linux systems and networking, building virtualized home labs, and systematically preparing for infrastructure roles.
- **Sysadmin Realities**:
  + Managing server provisioning, security patching, network configuration, and capacity planning.
  + Core Principle: "Never test in production" to safeguard service availability, team trust, and customer satisfaction.
  + Transitioning to DevOps: Moving from manual server operations to cloud architectures (AWS elastic scaling), Infrastructure as Code (Terraform), and automated containers (Docker and CI/CD).

#### The Art of Effective Teamwork
Speaker Truong Huy Phuoc shared valuable insights into the soft skills domain, emphasizing that human collaboration is the ultimate factor determining the success or failure of any technology project.
- **The 4 Golden Rules**:
  + **Rule 1: Clear & Shared Goals**: The entire team must align on the target destination and share a common understanding of project goals.
  + **Rule 2: Right Person, Right Place**: Assign roles based on individual strengths to optimize overall work performance.
  + **Rule 3: Open Communication & Active Listening**: Establish a respectful environment that encourages feedback and active listening among team members.
  + **Rule 4: Personal Accountability**: Each member must take ownership of their assigned tasks and be accountable for the collective outcome.
- **Digital Collaboration Tools**:
  + **Task Management**: Using modern platforms like Trello and ClickUP for visual progress tracking and task allocation.
  + **Communication & Workspace**: Leveraging Google Workspace for document storage, alongside Slack and Discord for rapid, continuous communications.

### Key Takeaways

#### Design Mindset
- I realized that enterprise AI applications go beyond simple chatbot prompts. They require combining graph databases (like Amazon Neptune) with LLMs via GraphRAG to solve complex, interconnected query paths.
- Designing real-time network systems requires choosing protocols based strictly on game mechanics and user experience, while implementing robust error handling for abrupt disconnections.
- Security-first engineering is paramount. Integrating ML with AWS WAF creates a proactive, adaptive defense system rather than relying on reactive rule updates.

#### Technical Architecture
- I mastered how API Gateway WebSocket routes network messages using Route Keys and maintains session states via connectionId records in DynamoDB.
- I understand the layered structure of Docker images and how Docker's caching mechanism optimizes image compile times.
- I learned to distinguish between fully managed GraphRAG (Bedrock + Neptune Analytics) and custom GraphRAG (LlamaIndex + Neptune) to select the right approach based on project constraints.
- I gained a clear understanding of the cloud security log flow integrating WAF, Kinesis Firehose, Lambda, Security Hub, GuardDuty, and CloudWatch.

#### Personal Development
- I learned that it is better to master one or two foundational technologies (such as Linux and Networking) deeply before branching out into complex cloud platforms.
- Hands-on home labs are irreplaceable. The problem-solving experience gained from setting up systems and debugging errors is far more valuable than memorizing exam dumps.
- I will maintain a persistent learning attitude, recognizing that starting in entry-level roles like Helpdesk builds the troubleshooting foundations required for senior roles.
- I understand and will apply the 4 golden rules of teamwork to collaborate smoothly and responsibly with other team members.

### Applying to Work
- I will write a Dockerfile to package my web projects, optimizing image layers to minimize container sizes and practice pushing them to Amazon ECR.
- I will set up a local home lab environment to practice network configuration, Linux administration, and write shell scripts to automate repetitive system tasks.
- I will develop a simple multiplayer game in Godot and integrate it with AWS API Gateway WebSocket and DynamoDB to practice real-time state management.
- I will study LlamaIndex and Bedrock documentations to build a basic RAG system locally, getting hands-on with text chunking and vector embedding.
- I will research AWS WAF custom rules to protect my existing API Gateways from common exploits in future lab assignments.
- I will implement team collaboration rules and project management tools (like Trello, Slack) in group academic projects to streamline work coordination.

### Event Experience

#### Learning from highly skilled speakers
The practical presentations provided invaluable insights. I was deeply inspired by Tran Trung Vinh's journey from a Helpdesk technician to a Senior Sysadmin. His self-taught lab exercises showed me that dedication and structured learning can overcome academic limitations. Additionally, Truong Huy Phuoc's presentation on the 4 golden rules of teamwork taught me that technology is only one part of the puzzle—the other part lies in how effectively we communicate and coordinate as a team.

#### Hands-on technical exposure
I enjoyed watching Nguyen Quoc Bao's Godot multiplayer match-making demo. Seeing how the game state mapped to connectionIds in DynamoDB in real-time, and understanding how they mitigated stale connections, made the network theories highly practical.

#### Leveraging modern tools
Witnessing the integration of Machine Learning models to detect network intrusion bypassing traditional firewalls was eye-opening. The real-time visualization dashboards and SNS alert mechanisms highlighted the potential of combining cloud infrastructure with intelligent algorithms.

#### Networking and discussions
The AWS office environment was highly professional and welcoming. During the networking break, I spoke with Huynh Bao about working at Endava Vietnam and his initiative in founding the ITea Lab for students, which gave me more confidence in connecting with industry peers.

### Lessons learned & Personal Engagement
- **Lessons Learned**:
  + The best solution is not always the most complex; it is the one that solves the business challenge most efficiently while optimizing cost.
  + Strong fundamentals (Linux, Networking, data structures) are the best assets to adapt to rapid technology shifts.
- **Personal Engagement & Contribution**:
  + Actively participated by asking speaker Viet Phat about the performance and cost trade-offs of custom GraphRAG pipelines versus fully managed Amazon Bedrock Knowledge Bases.
  + Connected and exchanged contact info with the speakers and fellow students to build a supportive local cloud learning network.

### Event Photos

Here are some of the real moments captured during the AWS First Cloud Journey AI event:

![Slide showing three discussion questions for the AWS AI Director panel on AI trends, critical skills for young developers, and bridging enterprise capability gaps](/images/4-EventParticipated/4.2-Event2/IMG20260606090407.jpg)
<!-- slide -->
![AWS AI Director presenting on how cloud computing and AI are lowering the barrier of entry for young technology builders](/images/4-EventParticipated/4.2-Event2/IMG20260606091540.jpg)
<!-- slide -->
![Title slide of the presentation 'Multiplayer in the Cloud: Connecting Godot Clients with AWS WebSockets' by speaker Nguyen Quoc Bao](/images/4-EventParticipated/4.2-Event2/IMG20260606092843.jpg)
<!-- slide -->
![Agenda slide (Table of Contents) for the multiplayer game WebSocket connection session](/images/4-EventParticipated/4.2-Event2/IMG20260606092927.jpg)
<!-- slide -->
![Slide detailing the DynamoDB Database Schema design for storing player and opponent matchmaking states](/images/4-EventParticipated/4.2-Event2/IMG20260606093539.jpg)
<!-- slide -->
![Slide summarizing technical challenges including Stale Connections, DynamoDB Scan costs, and Lambda statelesness](/images/4-EventParticipated/4.2-Event2/IMG20260606095009.jpg)
<!-- slide -->
![Title slide of the presentation 'Docker — A containerization technology' by speaker Huynh Bao](/images/4-EventParticipated/4.2-Event2/IMG20260606095859.jpg)
<!-- slide -->
![Agenda slide outlining the main sections of the Docker sharing session](/images/4-EventParticipated/4.2-Event2/IMG20260606100049.jpg)
<!-- slide -->
![Slide analyzing the benefits of virtualization and the need for containerization to optimize server resources](/images/4-EventParticipated/4.2-Event2/IMG20260606100430.jpg)
<!-- slide -->
![Slide comparing Virtual Machines vs Containers in terms of system architecture, size, and resource footprint](/images/4-EventParticipated/4.2-Event2/IMG20260606101230.jpg)
<!-- slide -->
![Kasane Teto themed slide wrapping up the Docker presentation by Huynh Bao](/images/4-EventParticipated/4.2-Event2/IMG20260606103701.jpg)
<!-- slide -->
![Agenda slide introducing the structure of the GraphRAG session by speaker Viet Phat](/images/4-EventParticipated/4.2-Event2/IMG20260606103959.jpg)
<!-- slide -->
![Title slide of the session 'WAF + ML for Cyber Attack Detection: Machine Learning-based Network Intrusion Detection System (NIDS) on AWS' by speaker Le Hoang Gia Dai](/images/4-EventParticipated/4.2-Event2/IMG20260606105006.jpg)
<!-- slide -->
![Slide explaining web application protection capabilities of AWS WAF (Web Application Firewall)](/images/4-EventParticipated/4.2-Event2/IMG20260606105132.jpg)
<!-- slide -->
![System diagram showing how NIDS works, connecting web traffic, machine learning models, databases, and alerting](/images/4-EventParticipated/4.2-Event2/IMG20260606105920.jpg)
<!-- slide -->
![Cloud architecture diagram detailing integration of AWS WAF, Lambda, S3, Kinesis Firehose, CloudWatch, and AWS security services](/images/4-EventParticipated/4.2-Event2/IMG20260606110049.jpg)
<!-- slide -->
![Slide summarizing experimental results, future improvements with Bedrock, and lessons learned by Le Hoang Gia Dai](/images/4-EventParticipated/4.2-Event2/IMG20260606110335.jpg)
<!-- slide -->
![Title slide of the session 'From IT Helpdesk to Senior Sysadmin' by speaker Tran Trung Vinh at Central Retail Group](/images/4-EventParticipated/4.2-Event2/IMG20260606111037.jpg)
<!-- slide -->
![Agenda slide outlining the career progression path from Helpdesk to Sysadmin and Cloud/DevOps](/images/4-EventParticipated/4.2-Event2/IMG20260606111212.jpg)
<!-- slide -->
![Slide highlighting skills learned from Helpdesk and the turning point of building hands-on labs for Linux & Networking](/images/4-EventParticipated/4.2-Event2/IMG20260606111433.jpg)
<!-- slide -->
![Slide detailing Sysadmin role realities and key lessons about never testing on production environments](/images/4-EventParticipated/4.2-Event2/IMG20260606111742.jpg)
<!-- slide -->
![Slide illustrating the Modern DevOps Roadmap with eight key stages from Linux to Monitoring & Observability](/images/4-EventParticipated/4.2-Event2/IMG20260606112554.jpg)
<!-- slide -->
![Contact details and connection QR code slide for speaker Tran Trung Vinh](/images/4-EventParticipated/4.2-Event2/IMG20260606113609.jpg)
<!-- slide -->
![Photo of my hand-written notebook summarizing speaker details and sequence during the event](/images/4-EventParticipated/4.2-Event2/note.png)

> The event provided valuable knowledge and technology inspiration, serving as a solid asset for my future studies and work.
