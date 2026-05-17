---
title: "Week 3 Worklog"
date: 2026-05-05
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

## Week 3 Objectives

* Begin studying Module 03 – Compute on AWS.
* Understand core Amazon EC2 concepts: Instance Types, AMI, Key Pair, and pricing models.
* Learn EC2 scaling, managed storage (EFS, FSx), and start Module 04 – Storage.

---

## Tasks Carried Out

| Day | Task | Start Date | Completion Date | Reference Materials |
| --- | ---- | ---------- | --------------- | ------------------- |
| 2 | Studied Module 03 theory – Compute: Amazon EC2, Instance Types, AMI, Key Pair | 05/05/2026 | 05/05/2026 | |
| 3 | Studied EC2 User Data, EC2 Meta Data, and EC2 Auto Scaling | 06/05/2026 | 06/05/2026 | |
| 4 | Completed Lab 13: AWS Backup infrastructure deployment, SNS setup, and backup/restore testing | 07/05/2026 | 07/05/2026 | https://000013.awsstudygroup.com/ |
| 5 | Researched AWS Storage Gateway workshop and S3 Static Website & CloudFront. Completed Module 03. | 08/05/2026 | 08/05/2026 | https://000024.awsstudygroup.com/vi/3-cleanup/ <br> https://000057.awsstudygroup.com/ |
| 6 | Began studying Module 04 theory – Storage on AWS | 09/05/2026 | 09/05/2026 | |

---

## Knowledge & Skills Gained

### 1. Amazon EC2 (Compute)

* **Understood EC2 Architecture**: Grasped flexible resource allocation and fast provisioning via **EC2 Instance Types** (CPU, RAM, Network) and **AMI** (OS, permissions, block device mapping).
* **Practiced Access Security**: Managed **Key Pairs** for SSH (Linux) and RDP password decryption (Windows).
* **Analyzed Pricing Models**: Compared **EC2 Pricing Options** (On-demand, Reserved, Savings Plans, Spot) to select cost-appropriate strategies per workload.

### 2. EC2 Tooling & Scaling

* **Studied Storage Types**: Distinguished **Instance Store** (high-speed NVMe, ephemeral) from persistent EBS storage.
* **Researched Automation**: Used **EC2 User Data** (launch scripts) and **EC2 Meta Data** to auto-bootstrap server environments.
* **Understood Auto Scaling**: Learned automated scale-out/in policies to maintain High Availability under varying loads.

### 3. Extended Compute & Storage

* **Studied File Systems**: Compared **Amazon EFS** (Linux-only) with **Amazon FSx** (Windows/Linux) for simultaneous multi-EC2 mounting.
* **Researched Application Migration**: Understood how **AWS MGN** replicates on-premise servers to AWS for Disaster Recovery.

### 4. Amazon S3 (Storage)

* **Understood Object Storage**: Mastered WORM model, 5TB object size limit, multipart upload, and **S3 Access Points** for granular permissions.
* **Analyzed S3 Storage Classes**: Learned cost optimization across Standard, IA, Intelligent Tiering, and Glacier/Deep Archive.
* **Researched Lifecycle Automation**: Understood **Object Lifecycle Management** for automatic tier transitions and **Cross-Region Replication (CRR)** for disaster recovery.

---

## Lab & Practical Experience

* **Lab 13 – AWS Backup**: Created S3 Bucket, deployed CloudFormation template, configured **Amazon SNS** alerts, and successfully ran an on-demand backup and automated restore via AWS Lambda; monitored logs in CloudWatch.
* **Storage Gateway & S3 Workshop**: Researched Storage Gateway architecture (SMB file share, cache volume); hosted a static website on S3 with public access policy and Versioning enabled; explored **Amazon CloudFront** with Origin Access Control (OAC).

---

## Difficulties Encountered & Solutions

* **Free Tier Limitations on Storage Gateway**: Could not fully provision a Gateway instance within Free Tier limits.
  * *Solution*: Focused on theoretical analysis and walkthrough documentation (SMB configuration, cache volumes) via official AWS workshops.
* **S3 Static Website Access Policies**: Confused between account-level `Block public access` and granular `Bucket Policy` settings.
  * *Solution*: Researched documentation and successfully configured `s3:GetObject` for `Principal: "*"` alongside disabling public access blocks.
* **IAM Complexity in AWS Backup**: Automated restore via Lambda required highly specific IAM Role permissions, frequently causing "Access Denied" errors.
  * *Solution*: Audited the CloudFormation template and traced execution via CloudWatch Logs to understand how IAM Roles were dynamically assigned.

---

## Lessons Learned

* Understanding **Pricing Options** and **Storage Classes** is foundational to Cost Optimization when designing cloud architectures.
* **Object Lifecycle Management** and **Auto Scaling** are essential operational tools – they remove manual overhead and keep systems adaptive by design.
* When using **CloudFormation**, always review the template and IAM Role flows carefully to avoid silent permission errors during automated provisioning.

---

## Lab Screenshots

![Create Backup Plan](/images/Worklog-week3/create%20backup%20plan%20(%20lab13).png)

![Create S3 Bucket 01](/images/Worklog-week3/create%20s3%20bucket%2001%20(lab13).png)

![Create S3 Bucket 02](/images/Worklog-week3/create%20s3%20bucket%2002%20(lab13).png)
