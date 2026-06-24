---
title: "Week 3 Worklog"
date: 2026-05-10
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Overview of Week 03 Objectives and Plans
The third week marks a significant milestone in deploying complex network architectures. This week's technical focus is **VPC Peering** connecting the Default VPC and HG VPC, **Network ACL** configuration for subnet security, implementing **Route 53 Resolver** (Inbound & Outbound Endpoints) for DNS management, and integrating with **Microsoft Active Directory** in a Hybrid Cloud model.

> **So What:** Combining VPC Peering and Route 53 Resolver solves a major enterprise challenge: secure high-speed connections and seamless DNS resolution between AWS Cloud and On-premises.

---

## 2. Detailed Worklog
Below is the summary of activities performed from 04/05/2026 - 10/05/2026:

| Day / Date | Work Content | Task Details | Results Achieved | Reference Sources |
| --- | --- | --- | --- | --- |
| Mon (May 04) | Office Onboarding | Visited the office; met mentor Nguyen Gia Hung and discussed internship direction. | Aligned on office guidelines and Amazon Vietnam culture. | AWS Vietnam Office |
| Tue (May 05) | VPC Peering Theory | Studied VPC Peering docs; focused on non-overlapping CIDR requirements and non-transitive nature. | Understood point-to-point connection mechanics. | AWS Documentation |
| Wed (May 06) | Peering Deployment | Configured VPC Peering between Default VPC and HG VPC; updated Route Tables at both ends. | Successful communication between EC2 instances in both VPCs via Private IPs. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Thu (May 07) | Subnet Security | Configured NACL for HG VPC; set Inbound/Outbound rules; enabled Cross-Peer DNS. | Hardened subnet-level security; resolved DNS hostnames of peered instances. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Fri (May 08) | Hybrid DNS Research | Studied Route 53 Resolver; analyzed Inbound and Outbound Endpoints flow. | Grasped the architecture of Hybrid DNS Resolution. | AWS Architecture Guide |
| Sat (May 09) | Resolver Config | Created Inbound/Outbound Endpoints; set up Forwarding Rules to route DNS queries. | Cloud and simulated On-premise systems resolved each other's DNS queries. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Sun (May 10) | Identity Integration | Studied and connected Microsoft AD to support identity synchronization in hybrid network. | Mastered centralized identity management concepts. | AWS Directory Service |

> **So What:** This week's tasks progressed from physical connection (Peering) to network identification (DNS, Active Directory). This forms the blueprint for running large-scale enterprise apps requiring maximum security.

---

### 3. Technical Analysis: VPC Peering and DNS Resolution
**VPC Peering** links two VPCs directly through AWS's private backbone network without traversing the public internet, minimizing latency and maximizing security.

**Critical Configuration Points:**
1. **Non-overlapping CIDRs:** Peering VPCs must have distinct CIDR blocks (e.g., `172.31.0.0/16` and `10.0.0.0/16`).
2. **Route Table Updates:** Explicit routes pointing to the peer VPC's CIDR block must be added, targeting the `pcx-xxxxx` peering connection.
3. **Cross-Peer DNS:** Enable "Allow DNS resolution from peer" on both sides to resolve internal DNS hostnames (e.g., `ip-10-0-1-10.ap-southeast-1.compute.internal`) instead of using private IPs directly.

> **So What:** Proper VPC Peering eliminates security vulnerabilities of public internet routing while maintaining the highest network throughput.

---

### 4. Hybrid DNS Solution via Route 53 Resolver
When bridging AWS Cloud with a traditional Datacenter, domain resolution between both environments is a challenge. **Route 53 Resolver** addresses this seamlessly.

**Resolver Architecture:**
* **Inbound Endpoint:** Receives DNS queries sent from On-premises into AWS Cloud.
* **Outbound Endpoint:** Forwards DNS queries originating from AWS Cloud to On-premises.
* **Forwarding Rule:** Defines which domains (e.g., `*.corp.hutech.edu.vn`) should be routed to specific On-premises DNS servers.

![Hybrid DNS Architecture](/images/1-Worklog/Week3/hybrid-dns.png)

> **So What:** Automated hybrid DNS resolution removes the need to manually configure `/etc/hosts` files on thousands of servers, ensuring scalability and operational simplicity.

---

### 5. Microsoft Active Directory in Hybrid Model
Using **AWS Directory Service** to integrate Microsoft AD enables Single Sign-On (SSO) and synchronizes employee credentials from On-premises to EC2 Windows/Linux instances on the cloud.

**Key Benefits:**
* Synchronized security settings (Group Policy Objects).
* Reduced administration overhead for identity management.
* Centralized access control to enterprise resources.

> **So What:** AD integration is a strategic step that allows companies to migrate legacy apps to the Cloud without disrupting existing user directory structures.

---

### 6. Summary and Evaluation of Week 3 Results

#### 6.1. Soft Skills & Communication
* **Mentor Engagement:** Interacted directly with AWS engineers at the office, observing their real-world troubleshooting approaches.
* **Collaboration:** Shared architecture design ideas and Route 53 configuration tips with other student groups.

#### 6.2. Resource & Cost Management (FinOps)
* **Endpoint Management:** Aware of active Endpoint charges (billed hourly). Terminated Resolver Endpoints immediately post-lab to preserve credits.

#### 6.3. Security & Infrastructure
* **Hybrid Networking:** Built a functional VPC Peering setup and established multi-layered security with Network ACLs and Security Groups.
* **Resolution Control:** Successfully executed cross-VPC DNS resolution.

#### 6.4. Technical & AI Mindset
* **Architectural Thinking:** Deeply understood how to connect isolated VPCs to construct a unified enterprise IT infrastructure.

---
**Overall Assessment:** 100% of Week 3 targets completed successfully. The federated network functions perfectly and securely.
