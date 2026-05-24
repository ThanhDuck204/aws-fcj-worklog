---
title: "Week 1 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

## Week 1 Objectives

* Get acquainted with the internship environment and First Cloud Journey.
* Understand core Cloud Computing and AWS concepts.
* Practice IAM, account security, cost management, and basic networking/database setup.

---

## Tasks Carried Out

| Date | Task | Result | Resources | Notes |
|---|---|---|---|---|
| 20/04/2026 | Studied Cloud Computing, AWS Global Infrastructure, and the Well-Architected Framework. | Understood cloud fundamentals, AWS Regions, AZs, Edge Locations, and the 6 Well-Architected pillars. | [Cloud Journey](https://cloudjourney.awsstudygroup.com/) <br> [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html) | Completed foundational theory. |
| 21/04/2026 | Explored the AWS Management Console, CLI, SDK, and AWS Support case creation. | Practiced basic AWS tools and learned the support case workflow. | [Cloud Journey](https://cloudjourney.awsstudygroup.com/) <br> [AWS Support Case Tutorial](https://www.youtube.com/watch?v=95quNuhvMT0) | Built familiarity with AWS operations. |
| 22/04/2026 | Configured AWS account security with MFA, IAM User/Group, and authentication troubleshooting. | Completed a basic IAM structure and understood common authentication issues. | [AWS Account Security Tutorial](https://www.youtube.com/watch?v=1dG5xutGbr4) <br> [IAM User and Group Tutorial](https://www.youtube.com/watch?v=b9pK1oG534Q) <br> [MFA Setup Tutorial](https://www.youtube.com/watch?v=69iKhwI7k2Y) | Completed account security practice. |
| 23/04/2026 | Completed comprehensive labs covering VPC, Security Groups, EC2, RDS, and AWS Budgets. | Finished the integrated networking/database labs and configured spending alerts. | [Cloud Journey](https://cloudjourney.awsstudygroup.com/) <br> [AWS Budgets Lab](https://000007.awsstudygroup.com/vi/3-usage-budget/) | Completed integrated AWS lab work. |
| 24/04/2026 | Practiced database connectivity and queries, used Kiro, and started Module 02 theory. | Connected to the database successfully, cleaned up resources, and began networking theory. | [Cloud Journey](https://cloudjourney.awsstudygroup.com/) <br> [Module 02 Theory](https://www.youtube.com/watch?v=uAQCm4sm_1c) | Transitioned into Module 02. |

---

## Knowledge & Skills Gained

### 1. Cloud Computing & AWS Foundations

* **Studied Core Concepts**: Understood the advantages of Cloud (on-demand, pay-as-you-go) over On-Premise, and the structure of AWS Global Infrastructure (Regions, AZs, Edge Locations).
* **Researched Well-Architected Framework**: Familiarized with the 6 design pillars for building scalable, fault-tolerant, and cost-efficient systems on AWS.

### 2. Account Security & IAM

* **Practiced IAM Setup**: Enabled MFA on the Root account, created IAM Users/Groups, and applied least-privilege permissions to eliminate Root account usage in daily operations.
* **Configured Cost Controls**: Set up spending alerts via **AWS Budgets** and learned to open Support Cases for authentication issues.

### 3. Networking & Database Overview

* **Studied VPC Architecture**: Learned the fundamentals of Public/Private Subnets, Internet Gateways, NAT Gateways, and Route Tables.
* **Differentiated Security Layers**: Distinguished Security Groups (Stateful, instance-level) from Network ACLs (Stateless, subnet-level).
* **Explored RDS**: Provisioned a managed relational database and connected it to an EC2 instance from the application layer.

---

## Lab & Practical Experience

* **Security Lab**: Successfully configured IAM User/Group structure, enabled Virtual MFA for the Root account, and set up AWS Budgets alerts.
* **Network & Database Lab**: Deployed a VPC with Public/Private Subnets, provisioned EC2 and RDS instances, completed all 5 foundational labs, and used Kiro for automated resource cleanup.

---

## Difficulties Encountered & Solutions

* **AWS Console Navigation**: The large number of services made locating specific menus time-consuming at first.
  * *Solution*: Adopted the Global Search bar and pinned frequently used services to the console header.
* **Unintended Cost Risks**: Concern about unexpected charges from forgotten EC2/RDS resources running past Free Tier.
  * *Solution*: Configured AWS Budgets on day one and used Kiro to scan for orphaned resources before logging out each session.

---

## Lessons Learned

* Never use the Root account for daily operations â€” MFA and scoped IAM Users are non-negotiable security baselines on AWS.
* AWS charges are usage-based; relying on memory to shut down instances is risky. AWS Budgets and consistent cleanup routines are essential.
* VPC is the foundation for every AWS deployment â€” understanding Subnets, Security Groups, and Route Tables is prerequisite knowledge for all other services.

---

## Lab Screenshots

![Setup](/images/Worklog-weak1/setup-virtual-mfa-device.png)

![Create](/images/Worklog-weak1/create-admin-group-and-admin-user.png)

![Done Budget](/images/Worklog-weak1/done-all-lab-budget.png)

![Done All](/images/Worklog-weak1/done-all-5-labs-get-100-credit-aws.png)
