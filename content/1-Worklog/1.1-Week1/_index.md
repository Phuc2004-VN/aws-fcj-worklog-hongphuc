---
title: "Week 1 Worklog"
date: 2026-04-23
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Overview of Week 01 Objectives and Plans
The opening week of the First Cloud AI Journey (FCAJ) is a crucial phase for establishing the "Builder Culture" and shaping a professional technical mindset. Rather than approaching as an end-user, students are required to transition into the roles of a **"Builder"** and a **"Troubleshooter."** This is the core foundation of AWS's operational philosophy, where every technical issue is seen as an opportunity for system optimization.

Setting up accounts, configuring Multi-Factor Authentication (MFA), and managing groups in the first week are not just simple technical tasks, but preparations for **Operational Excellence**. Without a solid management foundation, security and cost risks will become significant barriers throughout the 12-week internship.

> **So What:** The combination of cloud computing theory and account management practice helps students familiarize themselves with the **Pay-as-you-go** model. Shifting from an on-premises infrastructure mindset to the Cloud requires the ability to control resources in real-time to mitigate financial and operational risks.

---

## 2. Detailed Worklog
Below is the summary of activities performed from April 17th to April 23rd:

| Day / Date | Work Content | Task Details | Results Achieved | Reference Sources |
| :--- | :--- | :--- | :--- | :--- |
| Wed (Apr 17) | Kickoff Workshop | Attended the opening ceremony; received the FCAJ vision and 06 Leadership Principles. | Understood program goals; embraced the Builder & Troubleshooter mindset. | |
| Thu (Apr 18) | Community Networking | Formed a group of 5 members; established WhatsApp/LinkedIn communication channels. | Completed group structure; ready for collaborative Lab sessions. | Web.whatsapp.com |
| Fri (Apr 19) | Basic Cloud Theory | Studied Global Infrastructure (Regions, AZs, Edge Locations) and the Management Console. | Mastered AWS physical infrastructure; understood latency reduction via Edge Locations in VN. | [Youtube Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox3TSYFbN1DNX7NZgTVXNj3x) |
| Sat (Apr 20) | Root Infrastructure Setup | Created AWS Free Tier account; activated MFA for Root Account; received first $100 credit. | Account secured according to Best Practices; practice funds ready. | [AWS Study Group](https://000001.awsstudygroup.com/vi/) |
| Sun (Apr 21) | Cost Optimization | Implemented Task 1 (EC2) and Task 3 (AWS Budgets). | Completed budget alert setup to prevent unexpected spending. | [AWS Study Group](https://000001.awsstudygroup.com/vi/) |
| Mon (Apr 22) | Credit Tasks Completion | Performed Task 2 (Bedrock), Task 4 (Lambda), and Task 5 (RDS Aurora). | Completed 5 tasks to earn an additional $100 credit; learned how to raise support cases. | [AWS Study Group](https://000001.awsstudygroup.com/vi/) |
| Tue (Apr 23) | IAM Admin & AI Kiro | Studied AWS Kiro theory and IAM access management (Users, Groups, Roles). | Mastered the Principle of Least Privilege and Spec-driven development. | [AWS Study Group](https://000002.awsstudygroup.com/vi/) |

> **So What:** The sequence of work reflects the transition from community connection to infrastructure mastery. This is practical logic: a Builder needs a support team before managing resources under a flexible cost model instead of traditional fixed investment (CAPEX).

---

## 3. Strategy for Activating and Managing $200 AWS Credits
From the perspective of a Senior Solutions Architect, cost management is the Cost Optimization pillar of the AWS Well-Architected Framework. Possessing a $200 budget removes financial barriers when accessing premium services.

**The 2-step process to receive $200 Credits:**
1. **Phase 1:** Register for an AWS Free Tier account with valid billing information to automatically receive $100 credits in the Billing Console.
2. **Phase 2:** Complete 5 tasks in the “Explore AWS” widget on the Console Home to receive an additional $100 credits ($20 per task).

**Details of services deployed for credit tasks:**

| Task | Service & Configuration | Credit Amount | Technical Goal |
| :--- | :--- | :--- | :--- |
| Task 1 | Amazon EC2 (Instance Test) | $20 | Manage VMs and Key Pairs (.pem). |
| Task 2 | Amazon Bedrock (Claude 3 Haiku) | $20 | Experience GenAI with cost-optimized models. |
| Task 3 | AWS Budgets | $20 | Set up Email Threshold Alerts. |
| Task 4 | AWS Lambda (Blueprints) | $20 | Deploy Serverless functions without server management. |
| Task 5 | Amazon RDS (Aurora PostgreSQL) | $20 | Set up Enterprise-grade Managed Database. |

![Credits Earned Screenshot](/images/1-Worklog/Week1/budget-success.png)

**Pro Tips from the Architect:**
- Always prioritize the smallest instance sizes (e.g., `t3.micro`) to save credits.
- **Immediate Clean-up:** Terminate EC2 and Delete DB Clusters right after receiving task confirmation to avoid idle resource costs.

![AWS Budgets Configuration](/images/1-Worklog/Week1/budget-success.png)

> **So What:** Optimizing the $200 budget allows students to experiment with Amazon Bedrock – an expensive AI service – without worrying about personal bills, thereby focusing entirely on building AI solutions.

---

## 4. Technical Analysis: Identity and Access Management (IAM)
IAM is the most important **Security Perimeter** on AWS. Proper IAM implementation prevents privilege escalation attacks.

**Core Components of IAM:**
- **IAM User:** Identity for a person or application. Do not use the Root Account for daily tasks.
- **IAM Group:** A collection of users with common permissions. Facilitates centralized management (e.g., AdminGroup).
- **IAM Policy:** A JSON document defining permissions (Allow/Deny).
- **IAM Role:** Temporary identity (Assume Role). Provides time-limited permissions with automatic credential rotation.

**"Switch Role" Strategy - Corporate Best Practice:** Instead of granting direct permissions, we use an `OperatorUser` (with no permissions) and perform a Switch Role to an `AdminRole`.
- **Audit:** All role-switching events are recorded in AWS CloudTrail for traceability.

> **So What:** Applying the Principle of Least Privilege and the Switch Role mechanism protects the account from credential leaks, ensuring only necessary sessions have elevated privileges.

---

## 5. Exploring the AWS Kiro Ecosystem (Theory)
Generative AI is redefining the Software Development Life Cycle (SDLC). AWS Kiro is more than a coding tool; it is a comprehensive architectural assistant.

- **Spec-driven Development:** This is the most significant trend. In the AI era, pure coding is gradually replaced by detailed requirements (Specs). If a Builder provides a high-quality specification, AI will generate more accurate and optimized source code.
- **Kiro CI:** A command-line tool inheriting power from Amazon Q, allowing bug chasing and error analysis directly at the Terminal.
- **Agent Hook:** Automated task delegation. Builders can use **Natural Language** to set triggers (e.g., *"Every time I save a file, automatically update changelog.md"*).

---

## 6. Summary and Evaluation of Week 1 Results

### 6.1. Soft Skills & Communication
- **Networking:** Successfully positioned my personal brand on LinkedIn and connected with the AWS Study Group and FCAJ 2026 network.
- **Team Coordination:** Participated in forming a 5-member group and established effective communication workflows.

### 6.2. Resource & Cost Management (FinOps)
- **Budget Optimization:** Mastered Cost Optimization. Activated $200 AWS Credits to experiment with premium services for free.
- **Proactive Monitoring:** Implemented **AWS Budgets** with a $1 threshold and configured Email alerts.

### 6.3. Security & Infrastructure
- **Security Perimeter:** Mastered **AWS IAM**. Successfully applied "Least Privilege" by separating permissions between AdminGroup and InternGroup.
- **Identity Protection:** Implemented MFA for the Root Account and all IAM Users.

### 6.4. Technical & AI Mindset
- **Compute Mastery:** Experienced diverse computing models from traditional virtual servers (**EC2**) to modern **Serverless Lambda**.
- **GenAI Exposure:** Early access to **Amazon Bedrock** using models like Claude 3 Haiku and Titan Text.

---
**Overall Assessment:** 100% of goals achieved. Feeling more confident in Cloud infrastructure management and ready for advanced Data and AI Labs in the coming weeks.