---
title: "Week 5 Worklog"
date: 2026-05-18
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

## Week 5 Objectives

* Begin studying Module 05 – AWS Security Services.
* Understand the Shared Responsibility Model, IAM, Cognito, AWS Organizations, Identity Center, and KMS.
* Research Lab 18 at the documentation level due to Free Tier account limits, practice Lab 22 on EC2 cost optimization with Lambda, then complete Lab 27 on resource management with tags.

---

## Completed Work

| Date | Task | Result | Resources | Notes |
|---|---|---|---|---|
| 18/05/2026 | Studied Module 05: Shared Responsibility Model, IAM, and Cognito. | Understood the security responsibility boundary, IAM access management, and Cognito authentication use cases. | [Module 05-01 - Shared Responsibility Model](https://www.youtube.com/watch?v=tsobAlSg19g&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=151) <br> [Module 05-02 - IAM](https://www.youtube.com/watch?v=N_vlJGAqZxo&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=152) <br> [Module 05-03 - Amazon Cognito](https://www.youtube.com/watch?v=pZ2fgEFK3Vs&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=153) | Completed the first Module 05 theory group. |
| 19/05/2026 | Studied AWS Organizations, AWS Identity Center, AWS KMS, Security Hub, and additional hands-on research. | Understood multi-account management, centralized access, key management, Security Hub concepts, and the Module 05 hands-on direction. | [Module 05-04 - AWS Organizations](https://www.youtube.com/watch?v=5oQY8Rogz9Y&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=154) <br> [Module 05-05 - AWS Identity Center](https://www.youtube.com/watch?v=NW1xrMkNMjU&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=155) <br> [Module 05-06 - AWS KMS](https://www.youtube.com/watch?v=GMihNQojhZc&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=156) <br> [Module 05-07 - AWS Security Hub](https://www.youtube.com/watch?v=clj2E0rNBEs&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=157) <br> [Module 05-08 - Hands-on and Additional Research](https://www.youtube.com/watch?v=0SdpD2GPYz4&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=158) | Completed the second Module 05 theory group. |
| 20/05/2026 | Researched Lab 18 at documentation level due to Free Tier limits. | Understood the Security Hub workflow, finding aggregation, and security status checks in an AWS Account. | [Lab 18 - AWS Security Hub](https://000018.awsstudygroup.com/) | Lab 18 was documentation-only. |
| 21/05/2026 | Continued Lab 22: optimizing EC2 costs with Lambda, EventBridge, and Slack notifications. | Built and tested scheduled EC2 start/stop automation with Lambda and Slack notification. | [Lab 22 - EC2 Cost Optimization](https://000022.awsstudygroup.com/vi/2-prerequiste/) | Completed EC2 automation practice. |
| 22/05/2026 | Off for personal reasons. | No technical work completed. |  | Personal leave. |
| 23/05/2026 | Completed Lab 27: managing resources with tags. | Practiced organizing AWS resources with tags, Resource Groups, and AWS CLI. | [Lab 27 - Resource Tagging](https://000027.awsstudygroup.com/) | Lab 27 was completed. |

---

## Knowledge & Skills Acquired

### 1. Module 05 – AWS Security Services

* **Shared Responsibility Model**: Understood the responsibility boundary between AWS and customers; AWS secures the cloud infrastructure, while customers secure resource configuration, data, IAM, and applications.
* **IAM**: Learned the roles of IAM Users, Groups, Policies, and Roles; understood Least Privilege, Explicit Deny, and how service roles let AWS services access resources without hardcoded credentials.
* **Cognito & Organizations**: Studied Cognito for application user authentication and AWS Organizations for multi-account management, OUs, consolidated billing, and Service Control Policies.
* **Identity Center & KMS**: Understood centralized access management with Permission Sets and how KMS manages keys for encryption at rest.

### 2. Lab 18 – AWS Security Hub

* Researched the Lab 18 flow in Module 05; did not deploy it directly due to Free Tier account limits, so the work was limited to reading and documenting the process.
* Learned how Security Hub aggregates findings, tracks security scores, and supports compliance checks in an AWS Account.

### 3. Lab 22 – Optimize EC2 Cost with Lambda

* Prepared the infrastructure: VPC, Security Group, test EC2 instance, and Slack workspace for notifications.
* Added the `environment_auto=true` tag so Lambda can identify the EC2 instance to start/stop.
* Created the IAM Role `dc-common-lambda-role` for Lambda with EC2 permissions and CloudWatch Logs access.
* Successfully tested the Lambda auto-stop function with `statusCode: 200` and verified the Slack notification.
* Created EventBridge rules `dc-common-lambda-auto-start` and `dc-common-lambda-auto-stop` to run the automation on schedule.

### 4. Lab 27 – Resource Management with Tags

* Completed Lab 27 in Module 05, focusing on using tags to organize, identify, and manage AWS resources.
* Created 2 EC2 instances with tags for testing, including `Name`, `Service`, `Owner`, `Environment`, and `Operating System`.
* Practiced adding, editing, and deleting tags with **Manage tags** in the EC2 Console.
* Filtered EC2 instances by tag, such as `Owner=NTDuc`, to verify resource lookup by metadata.
* Used AWS CLI to create an EBS volume with tags, reinforcing how tagging can be applied outside the Console.
* Created the `MarketingBU` Resource Group based on the `BusinessUnit=Marketing` tag to group related resources.

---

## Challenges & Solutions

* **Separating AWS and customer security responsibilities**: Rechecked the Shared Responsibility Model by service type to avoid confusion.
* **Free Tier limits while studying Lab 18**: Focused on reading the workshop flow, configuration steps, and validation process instead of enabling Security Hub directly.
* **Controlling resources in Lab 22**: Used tags to limit the automation scope and verified results through Lambda test events, EC2 state, and Slack notifications.
* **Managing multiple resources in Lab 27**: Standardized tag keys and values to make resources easier to filter and avoid mismatched tag names across EC2, EBS volumes, and Resource Groups.

---

## Lessons Learned

* IAM is a core foundation for AWS security; Least Privilege should be prioritized and root account usage should be avoided.
* Lambda combined with EventBridge works well for recurring operations such as automatically starting and stopping EC2 instances to reduce costs.
* Tagging helps automation target the correct resources and reduces the risk of affecting unrelated instances.
* Tagging and Resource Groups make AWS resources easier to organize, especially when filtering by owner, environment, project, or business unit.

---

## Practice Screenshots

> Lab 18 has no practice screenshots because the Free Tier account was limited, so this section only records Lab 22 and Lab 27 screenshots.

### Lab 22 – Optimize EC2 Cost with Lambda

![Lab22 Create IAM Role](/images/Worklog-week5/Lab22-%20Create%20IAM%20role%20for%20Lambda%20function.png)

![Lab22 Add Tag EC2](/images/Worklog-week5/Lab22-Add%20tag%20EC2%20instances.png)

![Lab22 Slack Notification Result](/images/Worklog-week5/Lab22-Check%20Lambda%20result%20auto%20and%20stop%202.0.png)

![Lab22 Auto Stop Result](/images/Worklog-week5/Lab22-Check%20Lambda%20result%20auto%20and%20stop.png)

![Lab22 Create EC2 Instance](/images/Worklog-week5/Lab22-Create%20Ec2%20instances%20for%20lambda.png)

![Lab22 EventBridge Auto Start Rule](/images/Worklog-week5/Lab22-Create%20rule%20auto%20start%20lamdba%20auto%20start%20.png)

![Lab22 EventBridge Auto Stop Rule](/images/Worklog-week5/Lab22-Create%20rule%20auto%20stop%20lamdba%20function.png)

![Lab22 Create Security Group](/images/Worklog-week5/Lab22-Create%20security%20groups%20for%20lambda.png)

![Lab22 Create VPC](/images/Worklog-week5/Lab22-Create%20Vpc%20lambda.png)

![Lab22 Create Slack Workspace](/images/Worklog-week5/Lab22-Create%20workspace%20Slack.png)

### Lab 27 – Resource Management with Tags

![Lab27 Create 2 EC2 with tag](/images/Worklog-week5/Lab27-Create%202%20EC2%20with%20tag.png)

![Lab27 Add or Delete tag with Manage tags](/images/Worklog-week5/Lab27-Add%20or%20Delete%20tag%20with%20Manage%20tags.png)

![Lab27 Filter resources by tag](/images/Worklog-week5/Lab27-Filter%20resouces%20by%20tag.png)

![Lab27 Using tag CLI](/images/Worklog-week5/Lab27-Using%20tag%20CLI.png)

![Lab27 Create Resource Group](/images/Worklog-week5/Lab27-Create%20Resource%20Group.png)
