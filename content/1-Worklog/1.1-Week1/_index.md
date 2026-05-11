---
title: "Week 1 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

## Week 1 Objectives

* Get acquainted with the internship environment and the members of First Cloud Journey.
* Understand the basic concepts of Cloud Computing and AWS.
* Learn how to use the AWS Console and CLI, and become familiar with core services.
* Grasp the principles of security and cost management on AWS.
* Understand system design strategies through the AWS Well-Architected Framework.

---

## Tasks Carried Out

| Day | Task | Start Date | Completion Date | Reference Materials |
| --- | ---- | ---------- | --------------- | ------------------- |
| 2 | Studied Cloud Computing, AWS Global Infrastructure, and the Well-Architected Framework. | 20/04/2026 | 20/04/2026 | https://cloudjourney.awsstudygroup.com/ <br> https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html |
| 3 | Explored the AWS Management Console, CLI, SDK, and AWS Support case creation. | 21/04/2026 | 21/04/2026 | https://cloudjourney.awsstudygroup.com/ <br> https://www.youtube.com/watch?v=95quNuhvMT0 |
| 4 | Configured AWS account security (MFA, IAM User/Group) and resolved authentication issues. | 22/04/2026 | 22/04/2026 | https://www.youtube.com/watch?v=1dG5xutGbr4 <br> https://www.youtube.com/watch?v=b9pK1oG534Q <br> https://www.youtube.com/watch?v=69iKhwI7k2Y |
| 5 | Completed comprehensive labs (VPC, SG, EC2, RDS) and implemented AWS Budgets. | 23/04/2026 | 23/04/2026 | https://cloudjourney.awsstudygroup.com/ <br> https://000007.awsstudygroup.com/vi/3-usage-budget/ |
| 6 | Practiced Database connectivity/queries, utilized Kiro, and started Module 02 theory. | 24/04/2026 | 24/04/2026 | https://cloudjourney.awsstudygroup.com/ <br> https://www.youtube.com/watch?v=uAQCm4sm_1c |

---

## Knowledge & Skills Gained

### 1. Cloud Computing & AWS Foundations

* **Understood Core Concepts**: Grasped the advantages of the Cloud Computing model (on-demand, pay-as-you-go) compared to traditional On-Premise models in terms of scalability and cost.
* **Studied Global Infrastructure**: Comprehended the architecture of Regions, Availability Zones (AZs), and Edge Locations to optimize latency and ensure high availability.
* **Researched Design Frameworks**: Mastered the 6 core pillars of the AWS Well-Architected Framework to design scalable, fault-tolerant, and cost-effective systems.

### 2. Account Management & Security

* **Understood Basic Security Principles**: Learned and applied the Shared Responsibility Model and the Principle of Least Privilege.
* **Practiced IAM Management**: Recognized the risks of using the Root User, enabled MFA, created IAM Users/Groups, and assigned appropriate administrative permissions for daily operations.

### 3. Cost Optimization & Operations

* **Researched Cost Management**: Identified common causes of unexpected billing charges and practiced setting up automated alerts via **AWS Budgets**.
* **Practiced Cleanup Workflows**: Cultivated the habit of reviewing and tearing down unused resources after completing labs to prevent unnecessary charges.
* **Understood Support Procedures**: Learned about the available AWS Support plans and the process of opening a Support Case for authentication issues.

### 4. Networking & Database Overview

* **Studied Basic VPC Architecture**: Gained initial familiarity with Public/Private Subnets, Internet Gateways, NAT Gateways, and Route Tables.
* **Understood Network Security Mechanisms**: Differentiated between Security Groups (Stateful, instance-level protection) and Network ACLs (Stateless, subnet-level protection).
* **Explored RDS Services**: Understood how to provision a managed relational database on the cloud and securely connect it to an EC2 application.

---

## Lab & Practical Experience

### 1. Basic Infrastructure & Security Lab

* **Practiced**: Successfully set up the AWS account, designed a standard IAM User/Group structure, and configured Virtual MFA for the Root User.
* **Configured**: Established spending limits and budget alerts utilizing AWS Budgets.
* **Achieved**: Gained a firm grasp of navigating the AWS Console, effectively preparing the environment for advanced hands-on labs.

### 2. Network & Database Architecture Lab

* **Practiced**: Deployed a miniature network architecture including a VPC, subnet partitioning, and Security Group configurations for web servers.
* **Configured**: Provisioned a basic EC2 instance alongside an RDS instance, successfully establishing database connectivity from the application layer.
* **Achieved**: Completed the first 5 foundational labs and utilized the Kiro tool to automate system review and resource cleanup.

---

## Difficulties Encountered & Solutions

* **Navigating the AWS Console**: The sheer volume of services initially made locating specific menus (like IAM or Billing) time-consuming.
  * *Solution*: Adapted by frequently utilizing the Global Search bar and pinning frequently used services to the navigation header.
* **Controlling Unintended Costs**: While provisioning RDS and EC2 instances, there was concern about incurring unexpected charges due to forgotten resources or exceeding Free Tier limits.
  * *Solution*: Proactively configured AWS Budgets on the first day and developed a strict habit of using the Kiro tool to scan for "orphaned" resources before logging out.

---

## Lessons Learned

* **Security is the Top Priority**: Never utilizing the Root User for daily tasks and strictly enforcing MFA are fundamental, non-negotiable principles when operating in AWS.
* **Automated Cost Control**: AWS charges based on a pay-as-you-go model, meaning relying on memory to shut down instances is risky; it must be paired with AWS Budgets and systematic cleanup protocols.
* **Mastering Network Fundamentals**: Whether deploying EC2 or RDS, everything operates within a VPC. Therefore, a deep understanding of network flows (Subnets, Security Groups) is a prerequisite for working with any other AWS service.

---

## Lab Screenshots

![Setup](/images/Worklog-weak1/setup-virtual-mfa-device.png)

![Create](/images/Worklog-weak1/create-admin-group-and-admin-user.png)

![Done Budget](/images/Worklog-weak1/done-all-lab-budget.png)

![Done All](/images/Worklog-weak1/done-all-5-labs-get-100-credit-aws.png)
