---
title: "Week 7 Worklog"
date: 2026-06-07
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Overview of Week 07 Objectives and Plans
Week 7 represents a crucial transition phase from basic technical labs to planning the final Project. Key activities included: attending sharing sessions featuring guest speakers; researching and deploying **AWS WAF (Web Application Firewall)** to protect web applications against SQL Injection and XSS; reviewing previously studied AWS services; and gathering user feedback to select a viable Project topic.

> **So What:** Shielding applications at the application layer (Layer 7) with WAF protects workloads against common web exploits, while gathering real-world feedback ensures the final project solves actual user problems.

---

## 2. Detailed Worklog
Below is the summary of activities performed from 01/06/2026 - 07/06/2026:

| Day / Date | Work Content | Task Details | Results Achieved | Reference Sources |
| --- | --- | --- | --- | --- |
| Mon (Jun 01) | Speaker Workshop | Attended a sharing session; listened to stories regarding project operations and soft skills. | Gained insights into crisis resolution and career path planning. | Guest Speakers |
| Tue (Jun 02) | AWS WAF Research | Studied Web Application Firewall mechanics; analyzed SQL Injection and Cross-Site Scripting (XSS) threats. | Understood how WAF inspects HTTP/HTTPS traffic at Layer 7. | AWS Security Guide |
| Wed (Jun 03) | WAF Configuration | Created Web ACL; configured AWS Managed Rules; associated WAF with CloudFront or ALB. | Blocked malicious payloads from hitting backend servers. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Thu (Jun 04) | Exploit Simulation | Simulated SQLi and XSS payloads against the web app; verified blocks in WAF logs. | WAF successfully intercepted malicious queries, returning 403 Forbidden errors. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Fri (Jun 05) | Knowledge Review | Systematic review of previously studied services (VPC, EC2, IAM, Backup, TGW, Docker, Lambda). | Synthesized architectural blocks to prepare for final system design. | Personal Notes |
| Sat (Jun 06) | User Research | Interviewed small business owners/users regarding data management and AI needs. | Identified real-world business challenges solvable with cloud technology. | Target Users |
| Sun (Jun 07) | Topic Selection | Team meeting; analyzed project feasibility and aligned on final Project topic. | Agreed on an AI-driven data processing pipeline on AWS. | Team Meeting Notes |

> **So What:** Studying Layer 7 security alongside conducting market research prepares students both technically and business-wise to architect the best solution for their Project.

---

### 3. Application Shielding with AWS WAF
Unlike Security Groups and Network ACLs which inspect traffic at Layers 3 & 4, **AWS WAF** operates at Layer 7 (Application Layer) to protect web apps from malicious traffic.

**Key Features:**
* **AWS Managed Rules:** Pre-configured rule sets maintained by AWS security teams (e.g., Common Rule Set, SQL database rule set) for immediate protection.
* **Custom Rules:** Allow custom rules like geo-blocking, rate limiting (to mitigate DDoS), or filtering specific patterns in HTTP headers and request bodies.
* **Target Associations:** Integrates with Amazon CloudFront, Application Load Balancers (ALBs), and Amazon API Gateway.

> **So What:** Implementing AWS WAF blocks application-level exploits, protecting vulnerable code pathways and maintaining high service availability.

---

### 4. Customer Obsession: Gathering User Requirements
A cloud architecture, no matter how modern, is obsolete if it fails to address actual customer problems.

**Topic Selection Pipeline:**
1. **Discover Pain Points:** Interviewed users to discover operational challenges (e.g., manual data extraction, expensive custom AI compute).
2. **Map Cloud Solutions:** Matched challenges with AWS services studied (Lambda for automation, S3 for cheap storage, SageMaker for predictions).
3. **Feasibility Checks:** Ensured the scope solved the problem while remaining doable within skills and the $200 credit limit.

> **So What:** Aligning project design with customer needs (Customer Obsession) ensures practical, business-ready applications rather than simple code exercises.

---

### 5. Architectural Review of Studied AWS Services
To design a holistic solution, Builders must recall the role of each component:

| Category | Primary Service | Role in Final Project |
| --- | --- | --- |
| **Compute** | EC2, Lambda | Runs backend applications; handles serverless processing tasks. |
| **Storage** | S3, Storage Gateway | Stores raw datasets; syncs local office directory data to the cloud. |
| **Database** | RDS | Hosts structured application data and transaction logs. |
| **Networking** | VPC, Transit Gateway | Secures communication paths between application tiers. |
| **Security** | IAM, Security Hub, WAF | Governs access; audit configurations; filters malicious web requests. |

> **So What:** Reviewing these concepts enables the synthesis of individual services into a cohesive, production-grade cloud architecture.

---

### 6. Summary and Evaluation of Week 7 Results

#### 6.1. Soft Skills & Communication
* **Active Listening:** Absorbed experiences from guest speakers, reflecting on professional adaptability.
* **Consensus Building:** Guided team discussions productively to align on the final project direction.

#### 6.2. Resource & Cost Management (FinOps)
* **WAF Cost Awareness:** Recognized that WAF charges are hourly per Web ACL. Removed test Web ACLs immediately after verification.

#### 6.3. Security & Infrastructure
* **App Layer Defense:** Deployed AWS WAF configured with rules defending against SQLi and XSS, completing the security perimeter.

#### 6.4. Technical & AI Mindset
* **Solution-Oriented Mindset:** Transitioned from executing guided labs to designing custom architectures addressing real-world user problems.

---
**Overall Assessment:** Week 7 completed successfully. The final project topic is confirmed, and the team is ready for detailed design.
