---
title: "Week 3 Worklog"
date: 2026-05-10
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Overview of Week 03 Goals and Plan
My primary goal this week was to design and build a more complex network architecture that simulates a real-world enterprise environment:
* Visiting the office to meet my Mentor and discuss the internship roadmap.
* Connecting two VPCs (Default VPC and HG VPC) using VPC Peering.
* Configuring Route 53 Resolver (Inbound & Outbound Endpoints) for cross-network DNS resolution in a Hybrid Cloud model.
* Studying Microsoft Active Directory integration for centralized identity management.

## 2. Tasks to Implement in the Week
Below is the summary of activities performed from May 4th to May 10th, 2026:

| Day / Date | Work Content | Task Details | Results Achieved | Reference Sources |
| --- | --- | --- | --- | --- |
| Mon (May 04) | Office Onboarding | - Office onboarding: <br> &emsp; + Visited the office <br> &emsp; + Met mentor Nguyen Gia Hung to discuss goals | Thấu hiểu quy định và văn hóa làm việc tại Amazon Vietnam. | AWS Vietnam Office |
| Tue (May 05) | VPC Peering Theory | - VPC Peering research: <br> &emsp; + Studied VPC Peering mechanics <br> &emsp; + Reviewed non-overlapping CIDR requirements | Hiểu nguyên lý kết nối điểm-điểm của VPC Peering. | AWS Documentation |
| Wed (May 06) | Peering Deployment | - VPC Peering lab: <br> &emsp; + Configured VPC Peering between VPCs <br> &emsp; + Updated Route Tables at both ends | Giao tiếp thông suốt giữa các EC2 trong hai mạng khác nhau qua Private IP. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Thu (May 07) | Subnet Security | - Subnet security config: <br> &emsp; + Configured NACL for HG VPC <br> &emsp; + Set rules and enabled Cross-Peer DNS | Tăng cường bảo mật ở cấp Subnet; phân giải được tên miền của instance trong VPC đối tác. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Fri (May 08) | Hybrid DNS Research | - Hybrid DNS study: <br> &emsp; + Studied Route 53 Resolver <br> &emsp; + Analyzed Inbound/Outbound Endpoints flow | Nắm được kiến trúc phân giải DNS lai (Hybrid DNS Resolution). | AWS Architecture Guide |
| Sat (May 09) | Resolver Config | - DNS configuration: <br> &emsp; + Created Inbound/Outbound Endpoints <br> &emsp; + Set up DNS Forwarding Rules | Hệ thống Cloud và On-premises giả lập phân giải được tên miền của nhau. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Sun (May 10) | Identity Integration | - Directory integration: <br> &emsp; + Studied Microsoft Active Directory (AD) <br> &emsp; + Planned identity synchronization in hybrid network | Nắm vững giải pháp quản lý danh tính tập trung (Centralized Identity Management). | AWS Directory Service |

## 3. Results Achieved
During this week's hybrid networking and DNS resolution labs, I gained several key takeaways:

* **VPC Peering Interconnections:**
  + Configured a VPC Peering connection between the Default VPC and HG VPC, updated Route Tables, and enabled Cross-Peer DNS. Instances in both networks resolved private hostnames and communicated successfully.
  + Takeaway: VPC Peering is a highly efficient way to scale networks securely without exposing traffic to the public internet, reducing latency and transit risks.

* **Hybrid DNS Resolution with Route 53 Resolver:**
  + Configured Route 53 Resolver, setting up **Inbound Endpoints** (for simulated on-premises systems to query AWS DNS) and **Outbound Endpoints** (for forwarding AWS DNS queries to local servers).
  + Takeaway: Route 53 Resolver acts as the core DNS coordinator for Hybrid Cloud setups. It allows hybrid applications to locate resources seamlessly without manually editing hosts files on individual servers.

* **Centralized Identity via Active Directory Integration:**
  + Explored integrating Microsoft Active Directory using AWS Directory Service.
  + Takeaway: Synchronizing corporate Active Directory with the cloud through Single Sign-On (SSO) centralizes user management, eliminating account fragmentation and simplifying security governance.

* **FinOps and Cleanup:**
  + Takeaway: Route 53 Resolver Endpoints incur high hourly charges. Immediately after testing the connectivity, I deleted all Inbound/Outbound Endpoints to conserve our practice budget.
