---
title: "Week 4 Worklog"
date: 2026-05-17
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Overview of Week 04 Goals and Plan
This week, I focused on learning how to automate data backups and manage networking at a larger scale:
* Researching and configuring AWS Backup to run automated schedules and send status notifications via AWS SNS.
* Installing and gaining proficiency with the AWS CLI on my local machine.
* Studying and deploying AWS Transit Gateway (TGW) as a centralized hub to route traffic across 4 distinct VPCs.
* Cleaning up all resources after practice to optimize costs.

## 2. Tasks to Implement in the Week
Below is the summary of activities performed from May 11th to May 17th, 2026:

| Day / Date | Work Content | Task Details | Results Achieved | Reference Sources |
| --- | --- | --- | --- | --- |
| Mon (May 11) | Data Security | - Automated backups: <br> &emsp; + Researched AWS Backup <br> &emsp; + Created a Backup Vault and configured automated Backup Plans | Thiết lập chính sách sao lưu định kỳ cho các ổ đĩa và CSDL. | AWS Backup Guide |
| Tue (May 12) | Backup Alerts | - Alerts configuration: <br> &emsp; + Configured AWS SNS <br> &emsp; + Linked AWS Backup to SNS topic and email | Email nhận cảnh báo tự động khi quá trình sao lưu bắt đầu, thành công hoặc lỗi. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Wed (May 13) | Local CLI Setup | - CLI local installation: <br> &emsp; + Installed AWS CLI locally <br> &emsp; + Configured Access/Secret credentials | Sử dụng dòng lệnh thành thạo để quản lý tài nguyên AWS từ local. | AWS CLI Documentation |
| Thu (May 14) | Transit Gateway Study | - Large-scale routing: <br> &emsp; + Studied AWS Transit Gateway (TGW) <br> &emsp; + Compared it to full-mesh VPC Peering | Hiểu cách TGW đóng vai trò là Hub-and-Spoke router thông minh. | AWS Networking Guide |
| Fri (May 15) | TGW Configuration | - TGW setup: <br> &emsp; + Created a Transit Gateway <br> &emsp; + Created Attachments linking 4 distinct VPCs to TGW | Hợp nhất đường truyền mạng của 4 VPC thông qua một cổng quản trị trung tâm. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Sat (May 16) | Routing Verification | - Routing validation: <br> &emsp; + Configured TGW Route Tables <br> &emsp; + Launched EC2 (t3.nano) instances to test ping | Định tuyến thành công, các VPC giao tiếp được với nhau thông qua Transit Gateway. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Sun (May 17) | Cost Optimization | - Budget optimization: <br> &emsp; + Terminated all EC2 instances <br> &emsp; + Deleted Transit Gateway and test backups | Dọn dẹp tài nguyên triệt để; đảm bảo không hao phí credit dư thừa. | AWS Billing Dashboard |

## 3. Results Achieved
During this week's centralized data management and large-scale routing labs, I gained several key takeaways:

* **Automated Data Backups & Alerts (AWS Backup):**
  + Successfully configured Backup Plans to back up EBS volumes and databases, connecting them to AWS SNS to send email notifications whenever a backup job starts, completes, or fails.
  + Takeaway: Automating backups removes human error and reduces the risk of data loss due to system issues or security threats. SNS email notifications allow administrators to respond instantly to backup issues.

* **Speeding Up Work via CLI (AWS CLI):**
  + Installed AWS CLI locally and practiced creating S3 buckets, managing IAM policies, and publishing SNS messages directly from my terminal.
  + Takeaway: Gaining proficiency with the AWS CLI is a necessary baseline for automation and Infrastructure as Code (IaC). Using the terminal executes commands much faster than clicking around the console.

* **Centralized Large-Scale Network Routing (AWS Transit Gateway):**
  + Deployed Transit Gateway (TGW) as a Hub-and-Spoke router to connect 4 distinct VPCs chéo with each other using Transit Gateway attachments. Configured the routing tables and verified that `t3.nano` instances could ping each other across subnets.
  + Takeaway: As VPC counts grow, Transit Gateway reduces network connectivity complexity from quadratic $O(N^2)$ (in full-mesh VPC Peering) to linear $O(N)$. This keeps the network layout clean, secure, and easy to scale.

* **FinOps Practices:**
  + Takeaway: Transit Gateway attachments carry high hourly fees. I tested the routing paths quickly and deleted the TGW and EC2 instances right after the lab to optimize credit usage.
