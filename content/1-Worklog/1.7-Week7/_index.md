---
title: "Week 7 Worklog"
date: 2026-06-07
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Overview of Week 07 Goals and Plan
This week marks a major transition as I began preparing for the final graduation project while continuing to acquire technical skills:
* Attending the guest speaker workshop to learn from their real-world experience.
* Studying and deploying AWS WAF (Web Application Firewall) to protect web applications at the application layer (Layer 7) against SQL Injection and XSS.
* Systematically reviewing all AWS services learned over the last 6 weeks.
* Conducting a quick user survey and collaborating with my team to select a final graduation project topic.

## 2. Tasks to Implement in the Week
Below is the summary of activities performed from June 1st to June 7th, 2026:

| Day / Date | Work Content | Task Details | Results Achieved | Reference Sources |
| --- | --- | --- | --- | --- |
| Mon (Jun 01) | Speaker Workshop | - Speaker workshop: <br> &emsp; + Attended guest speaker presentations <br> &emsp; + Gained career advice and soft skills tips | Học hỏi tư duy giải quyết khủng hoảng và định hướng nghề nghiệp. | Guest Speakers |
| Tue (Jun 02) | AWS WAF Research | - L7 security study: <br> &emsp; + Studied Web Application Firewall mechanics <br> &emsp; + Investigated SQL Injection and XSS threats | Hiểu cách WAF lọc lưu lượng HTTP/HTTPS ở Lớp 7 (Application Layer). | AWS Security Guide |
| Wed (Jun 03) | WAF Configuration | - WAF deployment: <br> &emsp; + Created Web ACL <br> &emsp; + Configured AWS Managed Rules <br> &emsp; + Associated WAF with CloudFront or ALB | Thiết lập hàng rào bảo mật chặn đứng các request độc hại trước khi tới server. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Thu (Jun 04) | Exploit Simulation | - Testing security: <br> &emsp; + Simulated SQLi and XSS payloads against the web app <br> &emsp; + Checked blocks in WAF logs | WAF phát hiện và trả về mã lỗi 403 Forbidden chính xác đối với các request tấn công. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Fri (Jun 05) | Knowledge Review | - Overview review: <br> &emsp; + Reviewed VPC, EC2, IAM, Backup, TGW, Docker, Lambda | Tổng hợp các mảnh ghép kiến trúc để chuẩn bị thiết kế hệ thống lớn. | Personal Notes |
| Sat (Jun 06) | User Research | - Customer research: <br> &emsp; + Interviewed small business owners/users <br> &emsp; + Profiled data management and AI needs | Xác định các bài toán thực tế cần giải quyết bằng công nghệ. | Target Users |
| Sun (Jun 07) | Topic Selection | - Project scoping: <br> &emsp; + Held team meeting to evaluate feasibility <br> &emsp; + Selected graduation project topic | Thống nhất chọn đề tài ứng dụng AI kết hợp AWS để xử lý dữ liệu thông minh. | Team Meeting Notes |

## 3. Results Achieved
During this week's L7 security hardening and final project scoping activities, I gained several key takeaways:

* **Real-World Insights from Guest Speakers:**
  + Attended the workshop and listened to stories regarding production incident resolution, infrastructure risk management, soft skills development, and CV writing.
  + Takeaway: Hearing directly from specialists bridges the gap between classroom theory and industry reality, helping interns understand the professional standards expected of active Cloud Engineers.

* **Application-Layer Web Protection (AWS WAF):**
  + Deployed a Web ACL associated with CloudFront/ALB, enabled AWS Managed Rulesets (Common Rule Set, SQL Database Set), and simulated SQL Injection and XSS exploit attempts.
  + Takeaway: AWS WAF intercepts malicious payloads before they can reach the backend servers. Testing successfully with **403 Forbidden** status codes verified that the application was hardened against common OWASP Top 10 vulnerabilities.
  + FinOps: Deleted the Web ACL immediately after validating the configuration to avoid hourly running fees.

* **Graduation Project Business Scoping:**
  + Surveyed target users regarding document management challenges, assessed technical feasibility within credit limits, and agreed to build an AI-driven intelligent document processing pipeline on AWS.
  + Takeaway: Choosing a topic based on real-world requirements ensures the final project holds functional value. Collaboration helps develop requirements analysis and engineering roadmap skills.
