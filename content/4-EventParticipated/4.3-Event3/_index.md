---
title: "Event 3"
date: 2026-06-27
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---

# Report: AWS FC Community Day – Solutions for Enterprise AI Agents & Security

| Event Information | Details |
| :--- | :--- |
| **Event Name** | AWS FC Community Day 2026 |
| **Date & Time** | June 27, 2026 (09:00 - 12:00) |
| **Location** | 26th and 36th Floor, Bitexco Financial Tower, Ho Chi Minh City |
| **Attendance Mode** | Online (YouTube Livestream) |
| **Role** | Attendee |

### Event Objectives

The AWS FC Community Day was a monthly technology seminar series organized to create a space for networking, sharing practical knowledge, and providing real-world perspectives from large enterprise environments to the local developer and student community.

The core objective of this particular meetup was to deeply analyze infrastructure issues, operational cost optimization, and strict security shielding when deploying AI Agents into production at the enterprise level (Enterprise-Grade). The agenda spanned across several breakthrough solutions: from applying Multi-Agent platforms to monitor and handle cloud infrastructure incidents, building real-time Vietnamese Voice AI pipelines, integrating DevOps AI Agents to automate incident response workflows, using Amazon Q (Quick) assistant to automate HR operations, to setting up private network connectivity (Private Security) connecting to MCP servers via VPC Endpoints.

### Speakers

The event brought together a lineup of high-quality speakers, including founders, security specialists, and cloud engineers with extensive hands-on experience in the industry:

| No. | Speaker | Role | Topic |
| :-: | :--- | :--- | :--- |
| 1 | **Steve Tran** | Founder @ *Cloud Thinker* (Ex-AWS Solution Architect) | *Agentic Platform for Cloud Infrastructure: Cloud career progression, Single-Agent vs. Multi-Agent architectures, and FinOps cost optimization* |
| 2 | **Hieu Nghi, Kiet & Trung Do** | Cloud Engineers @ *Renova Cloud* & CEO @ *R AI* | *Voice AI Agents: Building intelligent voice agent systems, real-time Vietnamese speech processing, and banking tool calling scenarios* |
| 3 | **Nguyen Nguyen & Bao** | Cloud Engineers @ *Cloud Kinetics* | *DevOps AI Agent: Automating categorization, root cause investigation, and reducing MTTR/MTTD of infrastructure via Agent Space* |
| 4 | **Truong (Wren) & Minh Anh** | AI Solutions Team @ *Noventics* | *HR Intelligent Automation via Amazon Q: Achieving 99% accuracy in CV parsing, rating candidates based on competency framework, and building no-code pipelines* |
| 5 | **Toan Nguyen & Hieu Nghi** | AWS Security Builder @ *AWS Community* | *Private Security for AI Agents: Establishing secure private network connectivity between Amazon Q and MCP servers via VPC Endpoints* |

### Key Highlights

#### Multi-Agent platform for cloud infrastructure monitoring & FinOps optimization

Speaker Steve Tran shared his inspiring career path and solutions to address the complexity of migrating to cloud microservices as systems scale.
- **Career path story:** He shared about dropping out of college at 19 to work at a Contact Center (during 2018-2019), struggling with bulky physical servers and constant hardware failures. After lacking foundational knowledge and failing Azure certification exams 3-4 times, he redirected his focus to successfully conquering AWS documentation to become a Solution Architect at AWS, before eventually founding Cloud Thinker.
- **Solving "Technical Debt":** In large enterprises, especially in the banking and financial sectors (BFSI), systems serving millions of users always carry technical debt accumulated over generations. The speed at which AI can read logs and investigate incidents is measured in minutes, whereas humans would take hours.
- **Single-Agent vs. Multi-Agent architecture:** The Cloud Thinker team spent nearly 2 years researching and optimizing this challenge. Although a well-designed Single Super Agent can complete over 95% of tasks, a Multi-Agent (specialized agents) architecture is superior. It narrows the Context Window, allows choosing smaller (low-parameter) models for simple tasks to optimize costs, and supports strict role-based access control (RBAC).
- **Automated risk guardrails:** Unlike general automated coding assistants that might query databases directly and accidentally delete schemas, Cloud Thinker's agentic platform implements strict multi-layer approval (Layer Approval) before pushing any changes to Production. The system also leverages AI to run automated FinOps almost 100% of the time, replacing manual monitoring of usage dashboards to continuously optimize cloud infrastructure costs.

#### Voice AI Agents – Building enterprise-grade Vietnamese voice agents

The session presented by the R AI and Renova Cloud teams explained how to develop intelligent voice assistants in strict banking environments (such as VPBank, VIB).
- **The Vietnamese language challenge (Low-resource Language):** Current Speech-to-Speech models worldwide mostly support English well. Vietnamese is a low-resource language for training data, which discourages major tech corporations from investing heavily in it.
- **Optimized 3-step pipeline architecture:** To overcome this, they implemented a practical pipeline: Speech-to-Text (STT) -> LLM -> Text-to-Speech (TTS). The STT model captures speech and streams it directly into text for the LLM. The LLM processes the prompt based on the banking context to generate the text response, which is then streamed straight to the TTS module to output a voice response back to the customer.
- **Addressing complex Vietnamese language nuances:**
  - *Gender detection:* Vietnamese requires appropriate address pronouns (anh/chị) based on voice gender; misidentifying this causes a very poor user experience.
  - *Interruption algorithm:* Auxiliary models must be trained to understand when a customer pauses to think (e.g., stopping briefly while reading a phone number) to prevent the AI from interrupting them or continuously talking when interrupted.
  - *Regional accents:* Feeding 10% to 20% of specific regional accents (Central, Northern) into the training dataset ensures the AI does not get "paralyzed" during recognition.
- **Practical Tool Calling integration:** The system allows taking actions rather than just answering questions. When a customer calls to lock their card, the AI automatically triggers a function to verify candidate identity and executes the card lock command in real-time. If the customer exhibits frustration beyond the AI's capacity to handle, it naturally transfers (passes) the call to a human operator.

#### DevOps AI Agent – Automating infrastructure incident response on AWS

This topic presented by the Cloud Kinetics team introduced a solution to automate root cause analysis whenever critical system errors occur, minimizing the pressure on SRE/DevOps teams.
- **Data fragmentation pain point:** When a website slows down or fails, engineers must manually log into multiple scattered sources like CloudWatch and CloudTrail to find logs. This leads to context loss and drives MTTD/MTTR very high.
- **6 Core Pillars of the DevOps AI Agent:**
  1. *Context Learning:* Based on the concept of Agent Space (a logical container defining resources via tags). The AI automatically learns the infrastructure and outputs a topology mapping representing how it understands the cloud system.
  2. *Control:* Restricting agent access strictly using tags or establishing private connections.
  3. *Integration:* Expanding the agent's investigative capabilities via the Model Context Protocol (MCP). For instance, the agent cannot SSH directly into private EC2 instances to read private application logs, but an integrated MCP tool allows it to query databases to collect evidence.
  4. *Collaboration:* Seamless interaction via Web UI, Slack, or ServiceNow.
  5. *Convenience:* Fast activation directly within the AWS Console.
  6. *Cost-effective:* Pricing is based on execution seconds (about $0.083 per second) rather than infrastructure tokens.
- **4-Step Automated Incident Response Workflow:** Trigger Alert -> Propose logical hypotheses -> Prove hypotheses using gathered log data to perform Root Cause Analysis (RCA) -> Recommend mitigation plans (Mitigation Plan) without executing them automatically to ensure safety (Safety First); the final decision remains with humans.
- **Proven efficiency via case studies:** Western Governors University (WGU, serving nearly 200,000 students) integrated Dynatrace with the agent, reducing incident resolution time from 2 hours to 28 minutes (a 77% improvement in MTTR). Zenchef reduced misconfiguration search times by 75% down to 20 minutes. KDDI Japan shortened resolution times from weeks to days.

#### Revolutionizing HR workflows using Amazon Q intelligent assistant

Speakers Wren and Minh Anh shared a fresh perspective on using AI to solve non-technical human resource challenges in the digital era.
- **Traditional HR challenges:** Manual CV screening takes a lot of time and risks missing key talent. Candidate evaluations are often heavily influenced by subjective bias rather than structured competency frameworks. Furthermore, there is a very high risk of internal data leakage when HR personnel upload employee personal data to public AI platforms.
- **Amazon Q (Quick Ecosystem) solution:** An intelligent agentic assistant that supports diverse connectors (Google Workspace, Microsoft SharePoint, OneDrive, Gmail), relational databases, and S3 files to extract information. All data is protected securely within local zones in Vietnam.
- **HR department automation workflow:**
  - *Skill learning:* By simply uploading a `.md` document, Amazon Q automatically learns and generates an *HR Talent Review Assistant* skill, including Python scripts and PDF/Docx parsers.
  - *Automated JD generation:* The AI automatically creates detailed Job Descriptions (JD) based on department requests.
  - *CV screening and scoring:* The AI automatically scans folders containing CVs (supporting 99% accurate OCR, even for scanned files), matching them with JDs to classify fit levels (*Strong, Good, Low, Very Low*). It generates HTML Talent Review reports outlining strengths, weaknesses, and suggesting a salary benchmark.
  - *Workflow automation:* Automatically checks the Hiring Manager's calendar availability to schedule interviews, drafts email responses, and builds tracking applications (No-code App Building) using chat commands.

#### Establishing secure private network connectivity (Private Security) for AI Agents via VPC Endpoints

The final deep-dive technical session by Toan Nguyen and Hieu Nghi focused on data protection and preventing cybersecurity threats when AI connects to external systems.
- **Risks of Public Endpoints:** When Amazon Q connects to third-party MCP servers (like Zalo, WhatsApp, Jira) over the public internet, it exposes dangerous attack surfaces vulnerable to Man-in-the-Middle attacks or DDoS.
- **Closed private network architecture:** To fully adhere to Zero Trust principles, all MCP servers must reside in private subnets.
- **Security flow mechanics:** Place Amazon Q into the virtual network using a **VPC Connection** via Interface Endpoints (AWS PrivateLink). The data flows from Amazon Q -> VPC Connection -> Authenticates via Amazon Cognito -> Forwards to an Application Load Balancer (ALB) encrypted with TLS certificates via AWS Certificate Manager (ACM) -> Routes accurately to the MCP Server using Route 53 Resolver for internal DNS resolution. This entire path is private within AWS, ensuring zero bytes leak to the public internet.

### Key Takeaways

#### Design Mindset
- **Defense-in-depth security mindset:** An enterprise software system running in production cannot operate on a "just makes it run" basis. The architecture must integrate closed network security from the edge (VPC Endpoints) to protect sensitive client data.
- **"Human-in-the-loop" AI philosophy:** For critical tasks involving production environments (like DevOps agents proposing code changes) or financial decisions (FinOps), AI serves as a productivity accelerator. The final approval layer always remains with humans to guarantee absolute safety.
- **Design based on bounded contexts:** Segregating architectures into Multi-Agents limits the context window and optimizes costs by using smaller models for simple tasks and larger models for complex logic.

#### Technical Architecture
- Mastered the 3-step Voice AI streaming pipeline (STT -> LLM -> TTS) for low-resource languages, using auxiliary models to handle interruptions and speaker gender identification.
- Understood secure enterprise-grade infrastructure components, including the internal DNS resolution of Route 53 Resolver, end-to-end encryption using ALB and ACM, and integrating the Model Context Protocol (MCP) to extend AI agent context to third-party tools.

#### Professional Growth Strategy
- **Foundations matter:** Steve Tran's career path proved there are no shortcuts in Cloud/DevOps. To excel, one must master Linux operating systems, networking fundamentals, and practical operations before diving into AI technologies.
- **Resume optimization:** Understanding AI-driven CV screening mechanisms (like Amazon Q) helps in writing structured resumes highlighting core keywords that match JD requirements.

### Applying to Work
- **Apply containerization and tagging:** Continue using Docker to package modules in university projects, applying the least-privilege principle by labeling resources with tags, similar to DevOps Agent Spaces.
- **Hands-on automation practice:** Utilize the free trial of the DevOps AI Agent tool to experience automatic topology mapping and incident log analysis directly on the AWS Console.
- **Optimize team collaboration:** Integrate recommended digital collaboration tools (Trello/ClickUp for task management, Discord/Slack for continuous information stream) into software engineering group projects to mirror enterprise workflows.
- **Build a smart study assistant:** Explore Amazon Q documentation to configure a personal chat agent, loading markdown slides and course textbooks to quickly extract key study facts and prepare for exams.

### Event Experience

#### Learning from highly skilled speakers
I was highly impressed by Steve Tran's practical and straightforward presentation. His openness about past struggles with Azure and real-world trade-offs in startup environments helped a final-year student like me appreciate that architectures are chosen to serve business requirements and cost efficiency (citing case studies of F88 and FPT). Furthermore, Truong Huy Phuoc's session on the 4 golden rules of teamwork reminded me that technology is only half the equation; the other half is communication and collaboration.

#### Hands-on technical exposure
The most exciting moment was the live demonstration by Kiet showing the Voice Agent running on Amazon Bedrock Agent Core and Knowledge Bases. Watching the bot query custom product specs for MacBook Pro and reply in smooth English was highly inspiring. Additionally, the deep-dive on Vietnamese text streaming challenges by Trung Do (CEO of R AI) regarding interruptions and gender detection was extremely eye-opening.

#### Leveraging modern tools
Seeing Amazon Q parse scanned CVs and output a structured candidate comparison report in HTML was a highlight. Moreover, the detailed breakdown of private network infrastructure costs (ALB, Route 53 Resolver, EC2) totaling 250 to 350 USD per month shared by Toan Nguyen during the Q&A helped shape my understanding of real-world solution design and cost estimation.

### Networking and discussions
Although participating via Livestream, I could feel the dynamic atmosphere of the event being held at the AWS office in Bitexco. During and after the session, I connected on LinkedIn with speaker Toan Nguyen to ask for more resources regarding VPC Connection network configurations and interacted with fellow attendees. The session helped expand my learning network and built my confidence in communicating with industry veterans.

### Lessons learned & Personal Engagement
- **Lessons Learned**:
  + A successful enterprise tech system is not measured by the complexity of its AI models, but by how effectively it addresses business pain points (minimizing MTTR, absolute security) at the lowest cost.
  + Participating in events like AWS Community Day is a golden opportunity for Software Engineering students to stay updated on technology trends and gain industry perspective before graduating.
- **Personal Engagement & Contribution**:
  + Actively followed via Livestream and asked speaker Toan Nguyen questions during the Private Security Q&A session to clarify the operational costs of deploying private networks (ALB, Route 53 Resolver, EC2) in real-world scenarios.
  + Exchanged LinkedIn contacts with Swinburne students and speakers to share cloud learning resources and form study groups.

### Event Photos

Here are some real photos capturing memorable moments during the AWS FC Community Day event at the AWS Vietnam office:


![Opening slide introducing the monthly AWS FC Community Day event series at Bitexco](/images/4-EventParticipated/4.3-Event3/IMG20260620130023.jpg)
