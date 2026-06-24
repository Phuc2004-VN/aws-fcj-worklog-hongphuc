---
title: "Week 4 Worklog"
date: 2026-05-17
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Overview of Week 04 Objectives and Plans
Week 4 focuses on secure data management and large-scale infrastructure automation. Students researched and configured **AWS Backup** and **AWS SNS** to automate backups and alerts; installed and leveraged local **AWS CLI** to manage resources; deployed **AWS Transit Gateway** as a centralized hub routing across 4 distinct VPCs; and cleaned up all resources to optimize costs.

> **So What:** Automating backups and consolidating routing through Transit Gateway boosts system Reliability and reduces operational complexity as the enterprise scales up.

---

## 2. Detailed Worklog
Below is the summary of activities performed from 11/05/2026 - 17/05/2026:

| Day / Date | Work Content | Task Details | Results Achieved | Reference Sources |
| --- | --- | --- | --- | --- |
| Mon (May 11) | Data Security | Researched AWS Backup; created a Backup Vault and configured automated Backup Plans. | Established scheduled backup policies for volumes and databases. | AWS Backup Guide |
| Tue (May 12) | Backup Alerts | Configured AWS SNS; linked AWS Backup to SNS topic; subscribed email address. | Received automated emails on backup job status (start, success, failure). | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Wed (May 13) | Local CLI Setup | Installed AWS CLI locally; configured AWS Access/Secret keys; managed S3, IAM, SNS. | Gained proficiency in executing AWS commands from a local terminal. | AWS CLI Documentation |
| Thu (May 14) | Transit Gateway Study | Studied AWS Transit Gateway (TGW) theory; compared it to full-mesh VPC Peering. | Understood TGW's function as a smart Hub-and-Spoke cloud router. | AWS Networking Guide |
| Fri (May 15) | TGW Configuration | Created a Transit Gateway; created Attachments linking 4 distinct VPCs to TGW. | Consolidated network routes of 4 VPCs through a single hub. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Sat (May 16) | Routing Verification | Configured TGW Route Tables; launched EC2 (t3.nano) instances to test cross-AZ connectivity. | Routing verified; instances in different VPCs communicated via Transit Gateway. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Sun (May 17) | Cost Optimization | Terminated all EC2 instances, deleted Transit Gateway, and cleaned up test backups. | Released all temporary resources to prevent credit exhaustion. | AWS Billing Dashboard |

> **So What:** Combining CLI automation with centralized routing via Transit Gateway slashes setup time from hours to minutes while strictly enforcing organizational compliance policies.

---

### 3. Automated Backup Architecture: AWS Backup & SNS
**AWS Backup** provides a fully managed, policy-based backup service to centralize and automate data protection across AWS resources (EBS, RDS, DynamoDB, EFS).

* **Backup Plan:** Defines schedules (e.g., daily at 1:00 AM) and lifecycle policies (Retention: 7 days).
* **Backup Vault:** An encrypted container (via KMS keys) hosting backup recovery points securely.
* **SNS Notification Integration:** Connects with **Amazon SNS** to push state change events (COMPLETED/FAILED) to Admin emails or Chatbots.

> **So What:** Setting up automated backups with SNS monitoring guarantees **Business Continuity**, allowing rapid disaster recovery in case of data loss events.

---

### 4. Consolidated Cloud Routing with AWS Transit Gateway
As the number of VPCs scales (from 3-4 upwards), interconnecting them via full-mesh VPC Peering creates a complex web of configurations (requiring N*(N-1)/2 peering links).

**Transit Gateway (TGW) Advantage:**
* **Hub-and-Spoke Topology:** TGW acts as a central cloud router. Each VPC requires only a single attachment to the TGW.
* **TGW Route Tables:** Allows flexible routing policies, enabling or restricting inter-VPC traffic from a single control point.
* **Scalability:** Easily attach new VPCs without configuring complex peerings with existing VPCs.

![Transit Gateway Architecture](/images/1-Worklog/Week4/tgw-architecture.png)

> **So What:** Implementing Transit Gateway simplifies enterprise network diagrams, slashes routing table maintenance, and enhances network reliability.

---

### 5. Cost Optimization: AWS CLI and Resource Clean-up
To maximize the value of educational credits, using CLI commands to inspect and clean up infrastructure is highly recommended.

**Cost Control Techniques in Practice:**
1. **Right-sizing Instances:** Deployed `t3.nano` instances (0.5 GiB RAM) strictly to verify network paths.
2. **Immediate Deletion:** TGW charges per active attachment hour. Terminating attachments immediately after ping tests is mandatory.
3. **Helpful Cleanup CLI Commands:**
   * Delete S3 bucket: `aws s3 rb s3://my-test-bucket --force`
   * List running EC2s: `aws ec2 describe-instances --query "Reservations[*].Instances[*].[InstanceId,State.Name]"`

> **So What:** Automated resource cleanup skills enable Builders to keep accounts lean and avoid unexpected bills.

---

### 6. Summary and Evaluation of Week 4 Results

#### 6.1. Soft Skills & Communication
* **Self-Management:** Structured learning hours efficiently to balance theory and complex Transit Gateway configuration labs.
* **Knowledge Sharing:** Assisted peers in troubleshooting routing mismatch errors inside TGW Route Tables.

#### 6.2. Resource & Cost Management (FinOps)
* **Decisive Action:** Promptly terminated all `t3.nano` instances and deleted TGW attachments to optimize credit consumption.

#### 6.3. Security & Infrastructure
* **Automated Protection:** Successfully configured AWS Backup plans linked to SNS alerts for robust data protection.
* **Network Consolidation:** Mastered Transit Gateway configuration, establishing connectivity across 4 isolated networks.

#### 6.4. Technical & AI Mindset
* **Automation Drive:** Enhanced local terminal command capabilities, leveraging AWS CLI to query and modify resources efficiently.

---
**Overall Assessment:** Week 4 goals achieved successfully. Backup routines and centralized routing are running as intended.
