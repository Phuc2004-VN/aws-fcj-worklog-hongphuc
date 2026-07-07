---
title: "Week 1 Worklog"
date: 2026-04-23
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Weekly Goals
Starting the First Cloud AI Journey (FCAJ), I set up the following goals to adapt to the AWS Cloud environment:
* Forming a 5-member team to support each other during laboratory work.
* Creating an AWS Free Tier account and enabling basic security controls (MFA for the Root Account).
* Activating the full $200 practice credit package and configuring budgets to monitor spending.
* Studying the fundamental concepts of AWS Global Infrastructure (Regions, AZs, Edge Locations) and IAM access management (Users, Groups, Roles).
* Exploring Spec-driven development concepts in the AI Kiro ecosystem.

## 2. Tasks to Implement in the Week
Below is the summary of my daily tasks from April 17th to April 23rd:

| Day / Date | Work Content | Task Details | Results Achieved | Reference Sources |
| :--- | :--- | :--- | :--- | :--- |
| Wed (Apr 17) | Kickoff Workshop | - Kickoff Workshop: <br> &emsp; + Attended the opening ceremony <br> &emsp; + Received the FCAJ vision and 06 Leadership Principles | Hiểu rõ mục tiêu chương trình; thấm nhuần tư duy Builder & Troubleshooter. | |
| Thu (Apr 18) | Community Networking | - Community Networking: <br> &emsp; + Formed a group of 5 members <br> &emsp; + Established WhatsApp/LinkedIn channels | Hoàn tất cấu trúc nhóm; sẵn sàng cho các bài Lab đòi hỏi sự phối hợp. | Web.whatsapp.com |
| Fri (Apr 19) | Basic Cloud Theory | - Basic Cloud Theory: <br> &emsp; + Studied Global Infrastructure (Regions, AZs, Edge Locations) <br> &emsp; + Explored the Management Console | Nắm vững hạ tầng vật lý của AWS; hiểu cách giảm độ trễ qua Edge Locations tại VN. | [Youtube Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox3TSYFbN1DNX7NZgTVXNj3x) |
| Sat (Apr 20) | Root Infrastructure Setup | - Root Infrastructure Setup: <br> &emsp; + Created AWS Free Tier account <br> &emsp; + Activated MFA for Root Account <br> &emsp; + Received first $100 credit | Tài khoản bảo mật đúng Best Practice; sẵn sàng nguồn vốn thực hành. | [AWS Study Group](https://000001.awsstudygroup.com/vi/) |
| Sun (Apr 21) | Cost Optimization | - Cost Optimization: <br> &emsp; + Implemented Task 1 (EC2) <br> &emsp; + Implemented Task 3 (AWS Budgets) | Hoàn thành thiết lập cảnh báo ngân sách để tránh "vung tay quá trán". | [AWS Study Group](https://000001.awsstudygroup.com/vi/) |
| Mon (Apr 22) | Credit Tasks Completion | - Credit Tasks Completion: <br> &emsp; + Performed Task 2 (Bedrock) <br> &emsp; + Performed Task 4 (Lambda) <br> &emsp; + Performed Task 5 (RDS Aurora) | Hoàn thành 5 nhiệm vụ để nhận thêm $100 credit; biết cách raise support case. | [AWS Study Group](https://000001.awsstudygroup.com/vi/) |
| Tue (Apr 23) | IAM Admin & AI Kiro | - IAM Admin & AI Kiro: <br> &emsp; + Studied AWS Kiro theory <br> &emsp; + Managed IAM access (Users, Groups, Roles) | Nắm vững nguyên tắc đặc quyền tối thiểu (Least Privilege) và Spec-driven dev. | [AWS Study Group](https://000002.awsstudygroup.com/vi/) |

## 3. Results Achieved
Through my first week of practice and self-study, I gathered several valuable takeaways:

* **FinOps and Budget Management:**
  + Completed 5 essential tasks on the Console (creating an EC2 instance, calling the Bedrock API via Claude 3, setting up Budgets alerts, running a Serverless Lambda, and launching a managed RDS database) to activate the remaining $100 credit, bringing the total to $200.
  + Learned a key FinOps habit: configure AWS Budgets early (emailing me immediately when costs exceed $1) and terminate active resources (EC2, RDS Aurora) immediately after labs to avoid unnecessary charges.
  
  ![Budgets Configuration Screenshot](/images/1-Worklog/Week1/budget-success.png)
  
* **Account Security (IAM):**
  + Secured my Root Account using MFA and practiced creating IAM Users/Groups to manage access permissions for my teammates.
  + Gained a deep understanding of the **Principle of Least Privilege** – only granting the minimum permissions required for a task and prioritizing IAM Roles over hardcoded Access Keys to keep our system secure.

* **Spec-driven Development (AI Kiro):**
  + Explored the **Spec-driven development** methodology. Instead of writing code manually, I defined the system's specs in structured files, allowing AI Kiro to automatically generate the code and provision the cloud infrastructure.
  + Learned about the changing role of developers: transitioning from a coder who simply types syntax to a System Designer and Reviewer who focuses on high-level logic, speeding up project delivery.
