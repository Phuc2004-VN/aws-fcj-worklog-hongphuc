---
title: "Week 9 Worklog"
date: 2026-06-21
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

# FIRST CLOUD AI JOURNEY (FCAJ)

## 1. Overview of Week 09 Goals and Plan
This week, I focused on finalizing our graduation project design documentation and researching how to integrate AI/ML models into our cloud infrastructure:
* Writing the project specification document (defining business goals, data flows, and output expectations).
* Designing the Data Flow Diagram (DFD) to visualize how data traverses through the system.
* Studying the machine learning lifecycle and deployment workflow on AWS using AWS SageMaker.
* Configuring secure IAM policies to allow AI services to access S3 data safely.

## 2. Tasks to Implement in the Week
Below is the summary of activities performed from June 15th to June 21st, 2026:

| Day / Date | Work Content | Task Details | Results Achieved | Reference Sources |
| --- | --- | --- | --- | --- |
| Mon (Jun 15) | Project Documentation | - Project specifications: <br> &emsp; + Documented business problems <br> &emsp; + Defined data collection and output goals | Hoàn thành dự thảo tài liệu đặc tả dự án tốt nghiệp. | Project Specifications |
| Tue (Jun 16) | DFD Design | - Data flows mapping: <br> &emsp; + Drafted the Data Flow Diagram (DFD) for AI system <br> &emsp; + Outlined ingestion and processing paths | Trực quan hóa được các bước xử lý và lưu trữ dữ liệu của ứng dụng. | Draw.io Tool |
| Wed (Jun 17) | Architecture Finalization | - Infrastructure mapping: <br> &emsp; + Finalized the overall AWS architecture diagram <br> &emsp; + Connected S3, web servers, and AI tiers | Có bản vẽ kiến trúc chi tiết sẵn sàng trình bày trước hội đồng. | Draw.io Tool |
| Thu (Jun 18) | SageMaker Research | - MLOps study: <br> &emsp; + Studied AWS SageMaker features <br> &emsp; + Explored Studio, Notebooks, and Endpoints | Hiểu quy trình xây dựng, huấn luyện và triển khai mô hình học máy. | AWS SageMaker Guide |
| Fri (Jun 19) | AI Integration Design | - API designs: <br> &emsp; + Modeled backend API queries to SageMaker Endpoint <br> &emsp; + Defined payload formats | Xây dựng được luồng tích hợp AI/ML vào kiến trúc ứng dụng web. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Sat (Jun 20) | AI Security Config | - Security boundaries: <br> &emsp; + Configured prototype IAM policies for SageMaker <br> &emsp; + Restricted S3 reads to model datasets | Đảm bảo bảo mật dữ liệu đầu vào cho mô hình AI theo chuẩn Least Privilege. | [AWS Study Group](https://cloudjourney.awsstudygroup.com/) |
| Sun (Jun 21) | Milestone Review | - Milestone review: <br> &emsp; + Consolidated diagrams and documentation <br> &emsp; + Submitted Week 9 report | Hoàn tất hồ sơ thiết kế dự án tốt nghiệp; sẵn sàng bước vào giai đoạn code. | Project Documents |

## 3. Results Achieved
During this week's graduation project specification and machine learning operations (MLOps) labs, I gained several key takeaways:

* **Data Flow Diagram (DFD) and Pipeline Design:**
  + Mapped out our system DFD showing the data lifecycle: Client uploads files directly to S3 via Presigned URLs -> Lambda is triggered to extract clean text -> Text is sent to the SageMaker Endpoint for AI predictions -> Results are stored in RDS PostgreSQL and loaded onto the web interface.
  + Takeaway: Using S3 Presigned URLs is a major AWS Best Practice that allows clients to upload files directly to S3. This eliminates file-handling load from our API backend servers.

* **MLOps workflows with AWS SageMaker:**
  + Researched using SageMaker Notebooks for prototyping models, launching Training Jobs, and deploying the model to an active HTTPS Endpoint (Real-time Inference) for API consumption.
  + Takeaway: Hosting the model as an active API endpoint allows the backend to query AI predictions easily without needing complex server runtimes.

* **Security Boundaries for AI Services (IAM Policies):**
  + Created a dedicated SageMaker Execution Role, restricting access policies exclusively to our project S3 buckets (following Least Privilege principles).
  + Takeaway: Setting tight IAM constraints secures our training data and model artifacts from unauthorized access.

* **Technical Success Metrics and Cost Controls:**
  + Aligned on target metrics: Model Accuracy > 85%, API latency < 2 seconds, and Multi-AZ high availability.
  + Takeaway: SageMaker Endpoints run continuously and consume credit quickly. To save our budget, I deleted the test endpoint immediately after verification.
