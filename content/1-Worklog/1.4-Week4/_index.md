---
title: "Week 4 Worklog"
date: 2026-05-12
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

## Week 4 Objectives

* Continue studying Module 04 – Storage on AWS.
* Understand cold data transfer solutions with the Snow Family.
* Understand the hybrid storage model through AWS Storage Gateway.
* Learn Disaster Recovery strategies and centralized backup management with AWS Backup.

---

## Tasks Carried Out

| Day | Task | Start Date | Completion Date | Reference Materials |
| --- | ---- | ---------- | --------------- | ------------------- |
| 2 | Studied Module 04-04 – Snow Family, AWS Storage Gateway, Disaster Recovery Strategies, and AWS Backup | 12/05/2026 | 12/05/2026 | |
| 3 | Researched AWS Cost Explorer API, Billing API, and dashboard architecture in preparation for the AWS management project | 13/05/2026 | 13/05/2026 | https://docs.aws.amazon.com/aws-cost-management/latest/APIReference/Welcome.html |
| 4 | Continued researching IAM Management API, permission models, and AWS resource monitoring for the centralized management dashboard | 14/05/2026 | 14/05/2026 | https://docs.aws.amazon.com/IAM/latest/APIReference/Welcome.html |
| 5 | Studied applied technologies (Prompt Engineering, BMAD) from the community event and cost optimization strategies for AWS services | 15/05/2026 | 15/05/2026 | [Event 1 Report](/4-eventparticipated/4.1-event1/) |
| 6 | Offline due to personal reasons | 16/05/2026 | 16/05/2026 | |

---

## Knowledge & Skills Gained

### 1. Snow Family – Cold Data Transfer

* **Understood the use case**: Identified when physical data migration outperforms network transfer – when Internet bandwidth cannot meet volume or time requirements at Petabyte-to-Exabyte scale.
* **Researched Snowball**: Physical device holding up to **80 TB**; requires installing Snowball Client locally to verify, compress, and encrypt data before the device is shipped to an AWS Region for storage on **S3** or **Glacier**.
* **Researched Snowball Edge**: Upgraded variant with up to **100 TB** capacity plus built-in **Compute resources** for local pre-processing before data is imported into AWS.
* **Researched Snowmobile**: Truck-based solution for migrations up to **100 PB** per vehicle, designed for full data center evacuations at Exabyte scale.

### 2. AWS Storage Gateway – Hybrid Storage

* **Understood the core concept**: A hybrid storage service combining On-premise capacity with AWS cloud storage, leveraging cloud scale and cost efficiency for large, long-retention datasets.
* **Studied File Gateway**: Maps On-premise directories to **Amazon S3** via **NFS/SMB** protocols; objects are accessible directly in S3 for downstream analytics and AWS service integrations.
* **Studied Volume Gateway**: Exposes **iSCSI block storage** to applications; volumes are stored in S3 and can be snapshotted as **EBS Snapshots** (automated via AWS Backup) for Disaster Recovery.
* **Studied Tape Gateway**: Provides a **Virtual Tape Library (VTL)** interface over iSCSI to replace physical tape systems; virtual tapes are stored on **S3** or archived to **Glacier** at low cost.

### 3. Disaster Recovery (DR) Strategies

* **Mastered RTO & RPO**: Understood that **RTO** (max acceptable recovery time) and **RPO** (max acceptable data loss window) are the two metrics that drive DR strategy selection and SLA commitments.
* **Analyzed four DR tiers on AWS**: From lowest to highest availability – **Backup & Restore** → **Pilot Light** (Active-Standby, minimal cloud footprint) → **Low Capacity Active-Active** → **Full Capacity Active-Active**; cost and complexity increase with each tier as RTO/RPO decreases.

### 4. AWS Backup – Centralized Backup Management

* **Understood the service role**: A managed service to configure schedules (**backup schedule**), retention policies (**backup retention**), and monitor backup jobs across multiple AWS resources from a single control plane.
* **Identified supported resources**: EBS, EC2, RDS, DynamoDB, EFS, and AWS Storage Gateway volumes – all manageable through unified Backup Plans and Backup Vaults.

### 5. AWS Management Dashboard Architecture & Cost Explorer API Research *(Day 3)*

* Deepened knowledge of AWS APIs previously explored to prepare for developing the internal AWS Management Dashboard.
* Identified the core problem: The AWS Console is feature-rich but complex when managing multiple users and resources; a centralized dashboard is needed to simplify the view of costs, resource status, and IAM users.
* Researched the overall architecture including the frontend for data visualization, the backend for request processing, and the AWS SDK/API connection layer.
* Investigated the AWS Cost Explorer API:
  * Studied the `GetCostAndUsage` API to retrieve cost data over time.
  * Learned how to group data by service or account.
  * Understood the IAM permissions required to call the Cost Explorer API.
* Differentiated between the AWS Billing API (for overall billing management) and Cost Explorer API (for cost analysis).
* Explored data visualization strategies:
  * Cost trend charts by day/month.
  * Cost breakdown charts by AWS service.
  * Summary cards displaying current resource usage and costs.
* Noted that Cost Explorer data is not real-time, which must be considered in the dashboard design.

### 6. IAM Management API & Dashboard Planning *(Day 4)*

* Continued studying IAM APIs for the user management module of the dashboard.
* Explored APIs for:
  * Listing IAM Users.
  * Checking user groups and policies.
  * Verifying Console or Programmatic Access status.
* Researched the permission model for the dashboard:
  * Understood the Principle of Least Privilege (read-only access) to ensure security when the dashboard accesses AWS data.
  * Referenced centralized identity management on AWS for future expansion.
* Investigated resource monitoring capabilities:
  * EC2 Instance status.
  * Basic CloudWatch metrics.
  * RDS status and other common resources.
* Defined the dashboard implementation strategy:
  * Build an intermediary backend to connect with AWS SDK/APIs.
  * Develop an intuitive UI for cost and resource visualization.
  * Gradually expand to include IAM User management and monitoring.
* Identified technical challenges: Securely handling AWS credentials and implementing data pagination require careful research prior to deployment.

### 7. Exploring Technologies & Cost Optimization from Community Event *(Day 5)*

* Based on the AWS Study Group community sharing event (from Saturday of Week 3), conducted further research on the introduced technologies:
  * **Automated Prompt Engineering & Proptimizer Extension**: Learned how to optimize LLM prompts to improve code quality and productivity when integrating AI into the development workflow.
  * **BMAD Methodology (Build, Measure, Analyze, Deploy)**: Studied the application of this modern software development lifecycle, emphasizing the importance of system measurement and analysis.
* **AWS Cost Optimization**: Researched how to utilize AWS services most cost-effectively based on community best practices. Focused on leveraging the Free Tier, setting up AWS Budgets, and selecting appropriate resources for the internal project to minimize waste.

---

## Difficulties Encountered & Solutions

* **Differentiating DR tiers**: Pilot Light, Low Capacity, and Full Capacity initially appeared similar in concept.
  * *Solution*: Used **RTO/RPO** as the sorting axis – the lower the acceptable downtime, the more "Active-Active" and expensive the strategy; this made the four tiers clearly distinguishable.
* **Selecting the correct Storage Gateway type**: Three gateway types with overlapping descriptions caused initial confusion.
  * *Solution*: Mapped by access protocol – **NFS/SMB → File Gateway**, **iSCSI Block → Volume Gateway**, **iSCSI VTL → Tape Gateway** – each aligns to a distinct workload category.

---

## Lessons Learned

* When network bandwidth is a bottleneck, **Snow Family** provides a reliable physical alternative; Snowball Edge's added Compute capability makes it suitable for Edge Computing use cases beyond simple data transfer.
* DR strategy selection must be grounded in clearly defined **RTO/RPO** targets and budget constraints – there is no universally optimal strategy, only the most appropriate one per business SLA.
* **AWS Backup** consolidates fragmented per-service backup configurations into a single, auditable plane; pairing it with **Retention Policies** enforces data governance while keeping storage costs under control.

---

## Lab Screenshots

*To be updated after completing the lab exercise*
