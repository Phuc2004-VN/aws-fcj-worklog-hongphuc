---
title: "Event 1"
date: 2026-05-23
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# Report: AWS Vietnam Community Day 2026

| Event Information | Details |
| :--- | :--- |
| **Event Name** | AWS Vietnam Community Day 2026 (Saturday Meetup) |
| **Date & Time** | May 23, 2026 (09:00 - 12:00) |
| **Location** | 26th Floor, Bitexco Financial Tower, Ho Chi Minh City |
| **Role** | Attendee |

### Event Objectives
The Saturday Meetup - AWS Vietnam Community Day 2026 was a major technology event that I had the opportunity to attend in person on the 26th floor of the Bitexco Financial Tower. The core purpose of this event was to create a networking and learning space for the local AWS community in Vietnam. 

Rather than focusing on dry theory from textbooks, the meetup presented practical stories from enterprises operating large-scale systems like GoTymeX and VPBank. Through these real-world case studies, attendees - ranging from senior systems engineers to students like myself - could learn about system optimization, integrating Generative AI into business workflows, and shaping their own technical skills development path.

### Speakers

| No. | Speaker | Role | Topic |
| :-: | ------- | ---- | ----- |
| 1 | **Tinh Truong** | Platform Engineer @GoTymeX | *Context Is Everything – Making AI Actually Work for You* |
| 2 | **Pham Ng Hai Anh** | AWS Community Builder @G-AsiaPacificVietnam | *Friendly AI Assistant w/ Amazon Quick* |
| 3 | **Nguyen Tuan Thinh** | AWS Champion Instructor, 12x AWS Certified | *From Edge To Origin: CloudFront as Your Foundation* |
| 4 | **Team VIB** | AWS Track Winner @LotusHacks2026 | *36 hours with LotusHacks – Building UTMorpho* |
| 5 | **Duc Dao** | Solution Architect @CloudKinetics | *Non-Determinism of "Deterministic" LLM Settings* |
| 6 | **Vy Lam** | Sr. Business Systems Analyst @VPBank | *Enterprise-Grade Multi-Agent System* |

### Key Highlights

#### Drawbacks of legacy application architectures
While listening to the presentations, I realized that many businesses still struggle with legacy architectures like monolithic systems or centralized servers that distribute content directly without using a CDN. The primary drawback here is high latency. Users in Vietnam accessing US-hosted origin servers often face response times exceeding 200ms, which degrades user experience and consumes excessive international bandwidth. Moreover, exposing the origin server directly to the public internet makes it vulnerable to DDoS attacks and botnets without any edge-level shielding.

In AI applications, legacy designs integrate LLMs via simple, raw prompts without managing context or retaining long-term memory. This causes the AI to give generic answers, suffer from hallucinations, and fail at complex business tasks. Furthermore, assuming that setting `Temperature = 0` guarantees deterministic output leads to logic bugs in production, as parallel GPU optimizations introduce non-determinism during inference. Finally, in banking, manual credit scoring systems are too slow and rigid to parse the unstructured data of startups, delaying crucial funding.

### Transitioning to a modern architecture - Microservice Architecture
To address these limitations, migrating to a modern microservices architecture is essential. In this model, large monolithic systems are broken down into independent services communicating via APIs or events.

A key takeaway from Ms. Vy Lam's session was applying this pattern to AI as a Multi-Agent system. Instead of relying on a single LLM to do everything, the system decomposes tasks among specialized agents that function like independent microservices (e.g., data collection, risk analysis, compliance). This isolates failures and allows independent upgrades without disrupting the entire system.

### Domain-Driven Design (DDD)
DDD serves as a guiding compass to define clear boundaries between microservices or agents. Rather than jumping straight into coding, DDD requires engineers to collaborate with business teams to establish a Ubiquitous Language and map out Bounded Contexts.

This was illustrated by the VIB Team's UTMorpho project at LotusHacks 2026. Within a 36-hour timeframe, applying DDD was critical to define boundary contexts and user interactions, helping them build a successful MVP. Similarly, at VPBank, orchestrating a Virtual Credit Committee using Multi-Agent systems required clear agent boundaries to ensure compliance in a strict banking environment.

### Event-Driven Architecture
An event-driven architecture enables services or agents to communicate asynchronously, achieving loose coupling. When an event occurs (e.g., a customer uploads documents), the system publishes an event, and the interested services automatically capture it to process their respective workloads without synchronous polling.

At the network edge, Amazon CloudFront coupled with CloudFront Functions and Lambda@Edge captures request/response events at edge locations closest to users. This allows us to perform URL rewrites, redirection, or header modifications at the edge under 1ms, eliminating the need to route requests back to a distant origin server.

### Compute Evolution
Compute infrastructure has evolved from bare-metal servers to virtual machines (EC2), containers (ECS, Fargate), and now Serverless (AWS Lambda).

Shifting to serverless compute frees developers from OS management, network configuration, and security patching. The system automatically scales from zero to thousands of concurrent requests, charging only for active execution time. This allows developers to focus entirely on business logic and helps companies optimize operational costs.

### Amazon Q Developer
Amazon Q Developer and the G-AsiaPacific AI assistant suite, Amazon Quick (Quick Chat, Quick Flow, Quick Spaces, Quick Sight), demonstrated how AI can optimize the Software Development Lifecycle (SDLC).

These tools assist with code generation, performance optimization, and writing unit tests. Notably, Quick Sight allows business users with no coding background to query raw database tables and generate analytical dashboards using natural language chat prompts, accelerating business decisions.

### Key Takeaways

#### Design Mindset
- I learned that CloudFront is not just a static cache for images; it is a security shield that protects backend servers (Origin Cloaking) and offloads origin traffic.
- For AI applications, designing a "Second Brain" with long-term memory via RAG is crucial. AI is only as useful as the context it is provided with.
- Technical design must always follow business domains (a business-first approach). Implementing complex tech without understanding the business problem leads to bloated architectures.

#### Technical Architecture
- I mastered advanced CloudFront caching techniques, including multi-layer caching, Regional Edge Caches, and request collapsing to optimize dynamic content delivery.
- I learned to choose between CloudFront Functions (lightweight JS, <1ms execution at edge, for header changes and redirects) and Lambda@Edge (full Node.js/Python runtimes for complex logic).
- I understand the root cause of LLM non-determinism (GPU parallel calculations) and how to set Guardrails to control structured output.

#### Modernization Strategy
- Upgrading legacy applications should be a phased process guided by the 7Rs model and clear ROI assessments to reduce operational risks.
- The VIB Team's UTMorpho project taught me the value of building a solid MVP first to test assumptions quickly, embracing failures, and pivoting when stuck.

### Applying to Work
- In upcoming workshop labs (like the IoT Weather Platform), I will place CloudFront in front of the backend to speed up real-time dashboard updates and secure the origin with AWS Shield.
- I will deploy static front-end apps hosting on S3 with CloudFront, configuring Origin Access Control (OAC) to block direct S3 bucket access.
- I will apply RAG and context memory to build a personal AWS study chatbot to organize my documentation and notes.
- I will integrate Amazon Q Developer in VS Code to assist with code generation, refactoring, and unit tests.

### Event Experience

#### Learning from highly skilled speakers
The presentations were engaging and filled with real-world architectural diagrams. I was particularly impressed by Mr. Nguyen Tuan Thinh's CloudFront talk. As a 12x AWS Certified Champion Instructor, he explained CDN mechanisms and local edge locations in Vietnam using clear, relatable examples that helped me understand the concepts without getting overwhelmed.

#### Hands-on technical exposure
I enjoyed seeing the live demos of the credit scoring Multi-Agent workflow at VPBank. Listening to the VIB Team share their LotusHacks struggles, bugs, and pivots under pressure provided practical insights into teamwork and troubleshooting.

#### Leveraging modern tools
Watching Amazon QuickSight Q generate analytical reports from natural language prompts during the demo was a highlight. It showed how AI is closing the gap between business users and data engineering.

### Networking and discussions
The atmosphere at Bitexco was energetic. During breaks, I spoke with senior systems engineers and AWS Community Builders who shared career advice and AWS study tips. It was inspiring to see the vitality of the local AWS community.

### Lessons learned & Personal Engagement
- **Lessons Learned**:
  + Successful technical communication lies in simplifying abstract concepts into clear, everyday analogies.
  + Edge performance optimization and context-driven AI integrations are critical to building modern cloud solutions.
- **Personal Engagement & Contribution**:
  + Actively participated in discussions and raised questions during Mr. Nguyen Tuan Thinh's CloudFront session to clarify performance trade-offs between CloudFront Functions and Lambda@Edge in real-world scenarios.
  + Networked and shared ideas with local AWS Community Builders to gather insights on career paths and preparation strategies for upcoming community hackathons.

### Event Photos

Here are some of the real moments captured during the AWS Vietnam Community Day 2026 event:

![Slide "What's Next" for UTMorpho project by Team VIB, showing QR codes to access their Devpost and GitHub repositories](/images/4-EventParticipated/4.1-Event1/IMG20260523105858.jpg)
<!-- slide -->
![Slide explaining LLM configuration parameters: Top-P and Top-K with a QR code for interactive visualization](/images/4-EventParticipated/4.1-Event1/IMG20260523111358.jpg)
<!-- slide -->
![Slide showing the research reality: performance of LLMs tested on various NLP tasks](/images/4-EventParticipated/4.1-Event1/IMG20260523111644.jpg)
<!-- slide -->
![Slide explaining the technical root cause of LLM non-determinism, highlighting floating-point non-associativity in IEEE 754 on GPUs and parallel thread execution order](/images/4-EventParticipated/4.1-Event1/IMG20260523112629.jpg)
<!-- slide -->
![Slide proposing mitigation strategies for LLM non-determinism, including multiple runs/voting, structured outputs, and self-hosted models](/images/4-EventParticipated/4.1-Event1/IMG20260523112744.jpg)
<!-- slide -->
![Slide summarizing LLM configuration tips: greedy decoding loop risks, the temperature 0.1 sweet spot, and repeat penalty settings](/images/4-EventParticipated/4.1-Event1/IMG20260523113044.jpg)
<!-- slide -->
![Slide "Tips" for LLM configuration, featuring red handwritten overlay notes emphasizing setting temperature to 0.1 to avoid repetition](/images/4-EventParticipated/4.1-Event1/IMG_20260523_113141.jpg)
<!-- slide -->
![Slide showing the Key Takeaways: designing applications with variance in mind and focusing on thorough testing](/images/4-EventParticipated/4.1-Event1/IMG20260523113240.jpg)
<!-- slide -->
![Slide displaying a QR code referencing the research paper "LLM Settings" by Rebecca J. Passonneau](/images/4-EventParticipated/4.1-Event1/IMG20260523113404.jpg)
<!-- slide -->
![Slide showing the Agenda for enterprise-grade Multi-Agent architecture for credit assessment](/images/4-EventParticipated/4.1-Event1/IMG20260523114740.jpg)
<!-- slide -->
![Slide explaining why multi-agent architecture works, highlighting specialized expertise, checks & balances, and fault tolerance](/images/4-EventParticipated/4.1-Event1/IMG20260523120206.jpg)
<!-- slide -->
![Slide outlining the six pillars of enterprise-grade AI: Security, Data Governance, Network, Operations, Human Factors, and Compliance](/images/4-EventParticipated/4.1-Event1/IMG20260523120612.jpg)
<!-- slide -->
![Slide presenting the proposed deployment approach, detailing steps from local app to AWS services](/images/4-EventParticipated/4.1-Event1/IMG20260523121833.jpg)
<!-- slide -->
![Architecture diagram showing the basic deployment flow from the local developer environment to AWS cloud infrastructure](/images/4-EventParticipated/4.1-Event1/IMG20260523121900.jpg)
<!-- slide -->
![Slide listing the workshop exercises: configuring authentication, implementing Guardrails, MCP, and Terraform](/images/4-EventParticipated/4.1-Event1/IMG20260523122352.jpg)
<!-- slide -->
![Slide listing workshop exercises, overlayed with a red handwritten note highlighting that building a system is not just about making it run, but making it run securely](/images/4-EventParticipated/4.1-Event1/IMG_20260523_123205.jpg)
<!-- slide -->
![Group photo of all participants and speakers at the end of the event](/images/4-EventParticipated/4.1-Event1/event1.jpg)
<!-- slide -->
![My selfie taken at the event before leaving](/images/4-EventParticipated/4.1-Event1/event1.1.jpg)

>The meetup provided valuable knowledge and technology inspiration, serving as a solid asset for my future studies and work.
