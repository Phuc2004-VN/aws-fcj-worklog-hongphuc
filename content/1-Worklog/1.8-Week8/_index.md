---
title: "Week 8 Worklog"
date: 2026-06-14
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Weekly Goals
This week, our team focused entirely on detailed architectural design and preparing the implementation plan for our graduation project:
* Studying AWS architecture diagram standards and practicing drawing infrastructure setups using Draw.io.
* Discussing business scenarios and target user personas to scope the Minimum Viable Product (MVP) features.
* Utilizing the AWS Pricing Calculator to estimate the monthly operational budget of the system.
* Allocating tasks and setting timelines (milestones) for each team member.

## 2. Tasks to Implement in the Week
Below is the summary of activities performed from June 8th to June 14th, 2026:

| Day / Date | Work Content | Task Details | Results Achieved | Reference Sources |
| --- | --- | --- | --- | --- |
| Mon (Jun 08) | Diagram Training | - Diagram design practice: <br> &emsp; + Reviewed AWS architecture layout guidelines <br> &emsp; + Initialized Draw.io with AWS icon packs | Nắm được nguyên tắc bố cục sơ đồ kiến trúc chuẩn hóa. | AWS Architecture Center |
| Tue (Jun 09) | Infrastructure Draft | - Infrastructure blueprint: <br> &emsp; + Sketched VPC, subnets, and routing tables on Draw.io <br> &emsp; + Mapped out traffic flows | Có sơ đồ trực quan thể hiện dòng đi của dữ liệu từ Client vào AWS. | Draw.io Tool |
| Wed (Jun 10) | Problem Definition | - Project scoping: <br> &emsp; + Met with the team to define business problem <br> &emsp; + Detailed the text analysis use case | Thống nhất mô tả nghiệp vụ và phạm vi dự án. | Team Meeting Notes |
| Thu (Jun 11) | Persona Mapping | - Feature planning: <br> &emsp; + Mapped target user personas <br> &emsp; + Listed features required to solve pain points | Xác định danh sách tính năng ưu tiên (MVP features). | Requirements Doc |
| Fri (Jun 12) | AI Solution Design | - AI integration: <br> &emsp; + Designed pipeline combining S3, EC2, and RDS <br> &emsp; + Linked data flows to AI model | Đề xuất giải pháp kiến trúc tổng thể có tích hợp trí tuệ nhân tạo. | AWS Machine Learning |
| Sat (Jun 13) | Cost Estimation | - Budget modeling: <br> &emsp; + Input resource configurations for EC2 and RDS into AWS Calculator | Dự toán được ngân sách vận hành của kiến trúc, đảm bảo tính kinh tế. | AWS Pricing Calculator |
| Sun (Jun 14) | Project Roadmap | - Tasks delegation: <br> &emsp; + Allocated tasks across infrastructure, backend, and frontend <br> &emsp; + Set milestones on Trello | Thiết lập kế hoạch chạy Sprint rõ ràng cho các tuần tiếp theo. | Trello / Jira |

## 3. Results Achieved
During this week's detailed design, budgeting, and roadmap planning labs, my team gathered several key takeaways:

* **AWS Infrastructure Layout and Architecture Design (Draw.io):**
  + Sketched out our system diagram using Draw.io with the official AWS icon set, organizing resources into Region, VPC, Public Subnets, and Private Subnets. Placed RDS database instances and backend servers in the Private Subnet to prevent public internet access.
  + Takeaway: The architecture diagram functions as the engineering blueprint for the deployment phase. A precise design from the start avoids security and routing issues down the line.

* **MVP Scoping & Project Board Setup:**
  + Mapped out target user requirements and defined MVP feature boundaries (file upload -> text extraction -> call model -> save results in RDS and display them).
  + Takeaway: Defining a clear MVP scope prevents scope creep – the primary cause of project delays. Allocating tasks on Trello maps out clear sprint deadlines for the team.

* **Infrastructure Budget Projections (AWS Pricing Calculator):**
  + Used the AWS Pricing Calculator to estimate monthly running costs. Entering planned resource specifications (EC2 `t3.medium`, RDS PostgreSQL `db.t3.micro`, 50GB S3 storage) generated a monthly run-rate of under $15.
  + Takeaway: Cost modeling controls our credit usage and ensures we build economically viable setups. Budget estimation is a critical FinOps skill for any Cloud Engineer.
