---
title: "Week 7 Worklog"
date: 2026-06-07
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Overview of Week 07 Goals and Plan
This week marks a major transition as preparation began for the final graduation project while continuing to acquire technical skills:
* Attending the guest speaker workshop to learn from their real-world experience.
* Studying and deploying AWS WAF (Web Application Firewall) to protect web applications at the application layer (Layer 7) against SQL Injection and XSS.
* Systematically reviewing all AWS services learned over the last 6 weeks.
* Conducting a quick user survey and collaborating with the team to select a final graduation project topic.

## 2. Tasks to Implement in the Week
Below is the summary of activities performed from June 1st to June 7th, 2026:

| Day / Date | Work Content | Task Details | Results Achieved | Reference Sources |
| --- | --- | --- | --- | --- |
| Mon (Jun 01) | Speaker Workshop | - Speaker workshop: <br> &emsp; + Attended guest speaker presentations <br> &emsp; + Gained career advice and soft skills tips | Learned crisis management mindsets and career development directions. | Guest Speakers |
| Tue (Jun 02) | AWS WAF Research | - L7 security study: <br> &emsp; + Studied Web Application Firewall mechanics <br> &emsp; + Investigated SQL Injection and XSS threats | Understood how WAF filters HTTP/HTTPS traffic at Layer 7 (Application Layer). | [AWS Security Guide](https://000026.awsstudygroup.com/vi/) |
| Wed (Jun 03) | WAF Configuration | - WAF deployment: <br> &emsp; + Created Web ACL <br> &emsp; + Configured AWS Managed Rules <br> &emsp; + Associated WAF with CloudFront or ALB | Established security barriers to block malicious requests before they reach the server. | [AWS Web Application Firewall](https://000026.awsstudygroup.com/vi/) |
| Thu (Jun 04) | Exploit Simulation | - Testing security: <br> &emsp; + Simulated SQLi and XSS payloads against the web app <br> &emsp; + Checked blocks in WAF logs | WAF successfully detected and returned a 403 Forbidden status code for attack requests. | [WAF](https://000022.awsstudygroup) |
| Fri (Jun 05) | Knowledge Review | - Overview review: <br> &emsp; + Reviewed VPC, EC2, IAM, Backup, TGW, Docker, Lambda | Synthesized architectural building blocks to prepare for large-scale system designs. | Personal Notes |
| Sat (Jun 06) | User Research | - Customer research: <br> &emsp; + Interviewed small business owners/users <br> &emsp; + Profiled data management and AI needs | Identified real-world problems to be resolved using technology. | [Target Users](https://dnbvietnam.com/tin-tuc-su-kien/nhieu-doanh-nghiep-viet-gap-ganh-nang-ve-du-lieu.html) |
| Sun (Jun 07) | Topic Selection | - Project scoping: <br> &emsp; + Held team meeting to evaluate feasibility <br> &emsp; + Selected graduation project topic | Agreed on selecting an AI and AWS-based topic for intelligent data processing. | Team Meeting Notes |

## 3. Results Achieved
During this week's L7 security hardening and final project scoping activities, several key takeaways were gained:

* **Real-World Insights from Guest Speakers:**
  + Attended the workshop and listened to stories regarding production incident resolution, infrastructure risk management, soft skills development, and CV writing.
  + Takeaway: Hearing directly from specialists bridges the gap between classroom theory and industry reality, helping interns understand the professional standards expected of active Cloud Engineers.

* **Application-Layer Web Protection (AWS WAF):**
  + Deployed a Web ACL associated with CloudFront/ALB, enabled AWS Managed Rulesets (Common Rule Set, SQL Database Set), and simulated SQL Injection and XSS exploit attempts.
  + Takeaway: AWS WAF intercepts malicious payloads before they can reach the backend servers. Testing successfully with **403 Forbidden** status codes verified that the application was hardened against common OWASP Top 10 vulnerabilities.
  + FinOps: Deleted the Web ACL immediately after validating the configuration to avoid hourly running fees.

* **Graduation Project Business Scoping:**
  + The team surveyed target users regarding document management challenges, assessed technical feasibility within credit limits, and agreed to build an AI-driven intelligent document processing pipeline on AWS.
  + Takeaway: Choosing a topic based on real-world requirements ensures the final project holds functional value. Collaboration helps develop requirements analysis and engineering roadmap skills.
