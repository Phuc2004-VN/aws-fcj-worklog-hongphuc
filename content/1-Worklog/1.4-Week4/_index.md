---
title: "Week 4 Worklog"
date: 2026-05-17
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Overview of Week 04 Goals and Plan
This week, the focus was on learning how to automate data backups and manage networking at a larger scale:
* Researching and configuring AWS Backup to run automated schedules and send status notifications via AWS SNS.
* Installing and gaining proficiency with the AWS CLI on my local machine.
* Studying and deploying AWS Transit Gateway (TGW) as a centralized hub to route traffic across 4 distinct VPCs.
* Cleaning up all resources after practice to optimize costs.

## 2. Tasks to Implement in the Week
Below is the summary of activities performed from May 11th to May 17th, 2026:

| Day / Date | Work Content | Task Details | Results Achieved | Reference Sources |
| --- | --- | --- | --- | --- |
| Mon (May 11) | Data Security | - Automated backups: <br> &emsp; + Researched AWS Backup <br> &emsp; + Created a Backup Vault and configured automated Backup Plans | Established periodic backup policies for disks and databases. | [AWS Backup Guide](https://000013.awsstudygroup.com/) |
| Tue (May 12) | Backup Alerts | - Alerts configuration: <br> &emsp; + Configured AWS SNS <br> &emsp; + Linked AWS Backup to SNS topic and email | Received automatic email alerts when backup jobs start, complete, or fail. | [AWS Study Group](https://000013.awsstudygroup.com/) |
| Wed (May 13) | Local CLI Setup | - CLI local installation: <br> &emsp; + Installed AWS CLI locally <br> &emsp; + Configured Access/Secret credentials | Proficiently used the command line to manage AWS resources locally. | [AWS CLI Documentation](https://000011.awsstudygroup.com/vi) |
| Thu (May 14) | Transit Gateway Study | - Large-scale routing: <br> &emsp; + Studied AWS Transit Gateway (TGW) <br> &emsp; + Compared it to full-mesh VPC Peering | Understood how TGW functions as an intelligent hub-and-spoke router. | [AWS Networking Guide](https://000020.awsstudygroup.com/) |
| Fri (May 15) | TGW Configuration | - TGW setup: <br> &emsp; + Created a Transit Gateway <br> &emsp; + Created Attachments linking 4 distinct VPCs to TGW | Consolidated network traffic of 4 VPCs through a centralized management gateway. | [AWS Transit Gateway](https://000020.awsstudygroup.com/vi) |
| Sat (May 16) | Routing Verification | - Routing validation: <br> &emsp; + Configured TGW Route Tables <br> &emsp; + Launched EC2 (t3.nano) instances to test ping | Successfully routed traffic; VPCs communicated with each other via Transit Gateway. | [Route Tables](https://000020.awsstudygroup.com/vi/5-routetable/) |
| Sun (May 17) | Cost Optimization | - Summary: <br> &emsp; + Recorded logs and watched additional videos <br> &emsp; + Filled in information for the progress tracking sheet | Understood the concept of deploying a four-VPC connection architecture via AWS Transit Gateway. | AWS Note |

## 3. Results Achieved
During this week's centralized data management and large-scale routing labs, several key takeaways were gained:

* **Automated Data Backups & Alerts (AWS Backup):**
  + Successfully configured Backup Plans to back up EBS volumes and databases, connecting them to AWS SNS to send email notifications whenever a backup job starts, completes, or fails.
  + Takeaway: Automating backups removes human error and reduces the risk of data loss due to system issues or security threats. SNS email notifications allow administrators to respond instantly to backup issues.

* **Speeding Up Work via CLI (AWS CLI):**
  + Installed AWS CLI locally and practiced creating S3 buckets, managing IAM policies, and publishing SNS messages directly from the terminal.
  + Takeaway: Gaining proficiency with the AWS CLI is a necessary baseline for automation and Infrastructure as Code (IaC). Using the terminal executes commands much faster than clicking around the console.

* **Centralized Large-Scale Network Routing (AWS Transit Gateway):**
  + Deployed Transit Gateway (TGW) as a Hub-and-Spoke router to connect 4 distinct VPCs chéo with each other using Transit Gateway attachments. Configured the routing tables and verified that `t3.nano` instances could ping each other across subnets.
  + Takeaway: As VPC counts grow, Transit Gateway reduces network connectivity complexity from quadratic $O(N^2)$ (in full-mesh VPC Peering) to linear $O(N)$. This keeps the network layout clean, secure, and easy to scale.

* **FinOps Practices:**
  + Takeaway: Transit Gateway attachments carry high hourly fees. The routing paths were tested quickly, and the TGW and EC2 instances were deleted right after the lab to optimize credit usage.
