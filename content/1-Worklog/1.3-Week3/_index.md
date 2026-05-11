---
title: "Week 3 Worklog"
date: 2026-05-05
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

## Week 3 Objectives

* Begin studying Module 03 – Compute on AWS.
* Understand the core concepts of Amazon EC2.
* Learn how to select Instance Types, AMIs, and security mechanisms for EC2.

---

## Tasks Carried Out

| Day | Task | Start Date | Completion Date | Reference Materials |
| --- | ---- | ---------- | --------------- | ------------------- |
| 2 | Studied Module 03 theory – Compute: Amazon EC2, Instance Types, AMI, Key Pair | 05/05/2026 | 05/05/2026 | |
| 3 | Studied EC2 User Data, EC2 Meta Data, and EC2 Auto Scaling | 06/05/2026 | 06/05/2026 | |
| 4 | Completed Lab 13: AWS Backup infrastructure deployment, SNS setup, and backup/restore testing | 07/05/2026 | 07/05/2026 | https://000013.awsstudygroup.com/ |
| 5 | Researched AWS Storage Gateway workshop setup and S3 Static Website & CloudFront. Completed Module 03. | 08/05/2026 | 08/05/2026 | https://000024.awsstudygroup.com/vi/3-cleanup/ <br> https://000057.awsstudygroup.com/ |
| 6 | Began studying Module 04 theory – Storage | 09/05/2026 | 09/05/2026 | |

---

## Knowledge & Skills Gained

### 1. Amazon EC2 (Compute Service)

* **Understood Core Concepts**: Mastered the architecture of EC2 (Elastic Compute Cloud), specifically its flexible resource allocation and rapid provisioning suitable for diverse workloads.
* **Studied Hardware & Virtualization**: Learned to select appropriate configurations via **EC2 Instance Types** (CPU, RAM, Network limits) and understood underlying Hypervisor architectures.
* **Researched Amazon Machine Images (AMI)**: Comprehended the mechanism of mass-provisioning virtual machines using AMIs (incorporating OS, permissions, and block device mapping).
* **Practiced Access Security**: Mastered **Key Pair** (Public/Private Key) management for SSH authentication (Linux) and RDP password decryption (Windows).
* **Analyzed Pricing Models**: Differentiated and selected appropriate **EC2 Pricing Options** (On-demand, Reserved, Savings Plans, Spot) to optimize infrastructure costs.

### 2. EC2 Tooling & Scaling

* **Understood Local Storage Mechanisms**: Distinguished between **Instance Store** (high-speed NVMe, ephemeral storage) and persistent solutions like EBS.
* **Researched Configuration Automation**: Utilized **EC2 User Data** (launch scripts) and retrieved **EC2 Meta Data** to automatically bootstrap server environments upon boot.
* **Studied EC2 Auto Scaling**: Grasped the principles of automated scale-out and scale-in policies to maintain High Availability (HA) under fluctuating demands.

### 3. Extended Compute & Network Storage

* **Studied Amazon Lightsail**: Explored the cost-optimized virtual private server service, complete with bundled bandwidth, ideal for lightweight applications or dev/test environments.
* **Researched File Systems**: Compared **Amazon EFS** (Linux-only) with **Amazon FSx** (Windows/Linux), understanding simultaneous multi-EC2 mounting and usage-based billing mechanisms.
* **Understood Application Migration**: Comprehended the role of the **AWS Application Migration Service (MGN)** in establishing Disaster Recovery Sites by replicating on-premise servers to AWS.

### 4. Amazon S3 (Storage Service)

* **Understood Object Storage**: Mastered object-based storage architecture, WORM (Write Once Read Many) data models, size constraints (5TB max per object), and multipart upload capabilities.
* **Studied Access Point Security**: Recognized the benefits of **S3 Access Points** in designing granular access permissions for multiple applications without overly complicating bucket policies.
* **Analyzed S3 Storage Classes**: Understood data classification for cost optimization across Standard, Infrequent Access (IA), Intelligent Tiering, and Glacier/Deep Archive tiers.
* **Researched Data Lifecycle Automation**: Explored **Object Life Cycle Management** to automate transitions between storage classes, alongside **Cross-Region Replication (CRR)** for robust disaster recovery.

---

## Lab & Practical Experience

### 1. Lab 13: Deploying AWS Backup Infrastructure

* **Practiced**: Created an S3 Bucket, adjusted access policies, and deployed a CloudFormation template to automate the provisioning of the AWS Backup infrastructure.
* **Configured**: Implemented an automated alerting system via **Amazon SNS**, enabling real-time email notifications regarding backup or restore task statuses.
* **Achieved**: Successfully operated an on-demand backup workflow, executed automated restore tests via AWS Lambda, and monitored detailed execution logs using CloudWatch.

### 2. Storage Gateway Workshop & S3 Static Website Research

* **Researched**: Investigated Storage Gateway architecture (cache volumes, SMB file share configurations) to deeply understand hybrid storage models bridging On-premise and AWS Cloud environments.
* **Studied**: Examined the workflow for hosting static websites directly on an **S3 Bucket**, configuring secure public access, and utilizing Versioning to prevent accidental data loss.
* **Understood**: Explored global content delivery acceleration through **Amazon CloudFront**, integrating Origin Access Control (OAC) to maintain secure backend connections.

---

## Difficulties Encountered & Solutions

* **Free Tier Limitations**: During the AWS Storage Gateway research, it was not possible to fully provision a Gateway instance without exceeding the AWS Free Tier limitations.
  * *Solution*: Shifted focus to theoretical analysis, thoroughly reviewing the setup workflow (SMB configurations, cache volumes) through official documentation and AWS demo workshops.
* **S3 Static Website Access Policies**: Encountered initial confusion differentiating between account/bucket-level `Block public access` settings and granular `Bucket Policies`.
  * *Solution*: Proactively researched documentation and successfully configured the bucket by disabling public access blocks and implementing a secure `s3:GetObject` policy for `Principal: "*"`.
* **Complexity in AWS Backup Configurations**: Establishing an automated restore flow via AWS Lambda required highly specific IAM Role permissions, making it prone to "Access Denied" errors.
  * *Solution*: Carefully audited the CloudFormation template and traced the execution progress using CloudWatch Logs to fully grasp how IAM Roles are dynamically granted and assumed.

---

## Lessons Learned

* A solid understanding of **Pricing Options** and **Storage Classes** is the core foundational element to achieving true Cost Optimization when designing cloud architectures.
* In operational environments, deploying **Object Life Cycle Management** and **Auto Scaling** is mandatory to allow systems to adapt dynamically to load variations and data aging, significantly reducing manual intervention.
* When provisioning infrastructure automatically via **CloudFormation**, meticulously reviewing templates and IAM Role creation flows is critical to maintaining strict security postures.

---

## Lab Screenshots

![Create Backup Plan](/images/Worklog-week3/create%20backup%20plan%20(%20lab13).png)

![Create S3 Bucket 01](/images/Worklog-week3/create%20s3%20bucket%2001%20(lab13).png)

![Create S3 Bucket 02](/images/Worklog-week3/create%20s3%20bucket%2002%20(lab13).png)
