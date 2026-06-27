---
title: "Week 1 Worklog"
date: 2026-04-20
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

## Week 1 Objectives

* Get familiar with the internship environment, learning flow, and note-taking style in First Cloud Journey.
* Understand the foundations of Cloud Computing, AWS Global Infrastructure, and the Well-Architected Framework.
* Practice basic AWS services such as IAM, MFA, VPC, EC2, RDS, and AWS Budgets.
* Build the habit of cleaning up resources after labs to avoid unexpected costs.

---

## Work Completed

| Date | Task | Result | Resources | Notes |
|---|---|---|---|---|
| 20/04/2026 | Got familiar with the program and studied Cloud Computing and AWS basics. | Understood the difference between Cloud and On-Premise, and how AWS organizes Regions, Availability Zones, and Edge Locations. Started taking notes by module for easier review. | [Cloud Journey](https://cloudjourney.awsstudygroup.com/) | Mainly focused on getting started. |
| 21/04/2026 | Studied the Well-Architected Framework and basic AWS tools. | Learned the 6 pillars of the Well-Architected Framework. Explored AWS Management Console, CLI, SDK, and the support case workflow. | [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html) <br> [AWS Support Case Tutorial](https://www.youtube.com/watch?v=95quNuhvMT0) | Started understanding how AWS evaluates a well-designed system. |
| 22/04/2026 | Configured AWS account security with MFA, IAM User, and IAM Group. | Enabled MFA, created IAM users/groups, and tested a few basic authentication issues. This made it clearer why the root account should not be used for daily work. | [AWS Account Security Tutorial](https://www.youtube.com/watch?v=1dG5xutGbr4) <br> [IAM User and Group Tutorial](https://www.youtube.com/watch?v=b9pK1oG534Q) <br> [MFA Setup Tutorial](https://www.youtube.com/watch?v=69iKhwI7k2Y) | Completed account security setup. |
| 23/04/2026 | Practiced an integrated lab with VPC, Security Group, EC2, RDS, and AWS Budgets. | Created a basic cloud environment with networking, compute, and database resources. Set up AWS Budgets alerts to monitor learning-related costs. | [AWS Budgets Lab](https://000007.awsstudygroup.com/vi/3-usage-budget/) | The lab helped connect theory with real AWS operations. |
| 24/04/2026 | Practiced database connection, used Kiro for resource cleanup, and started Module 02. | Connected to and queried the database successfully. Reviewed created resources after the lab to avoid leaving EC2/RDS resources running. | [Cloud Journey](https://cloudjourney.awsstudygroup.com/) <br> [Module 02 Theory](https://www.youtube.com/watch?v=uAQCm4sm_1c) | Moved into the Networking module. |

---

## Weekly Notes

The first week was mostly about building a foundation rather than going deep into one specific service. The most important parts were understanding how AWS organizes resources and why IAM/MFA should be configured from the beginning.

The VPC, EC2, and RDS labs also helped make the deployment flow of a simple cloud application clearer. Concepts like subnet, route table, and security group were easier to understand after configuring them directly.

---

## Challenges Encountered

* AWS Console has many services and menus, so finding the right place to configure things took time at first.
* Networking concepts such as subnet, route table, and security group were easy to mix up when only studying theory.
* There was concern about unexpected costs if EC2, RDS, or related resources were left running.
* I needed to build a cleanup and note-taking habit after each session because it becomes hard to remember created resources later.

---

## Lessons Learned

* AWS Console is easier to use when using search and pinning frequently used services.
* IAM and MFA are foundational and should not be postponed.
* AWS Budgets should be created early to avoid forgotten running resources.
* In AWS labs, cleanup is just as important as creating resources.
