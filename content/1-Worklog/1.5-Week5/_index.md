---
title: "Week 5 Worklog"
date: 2026-05-18
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

## Week 5 Objectives

* Start Module 05 about AWS security services.
* Understand the Shared Responsibility Model, IAM, Cognito, Organizations, Identity Center, KMS, and Security Hub.
* Study Lab 18 at documentation level because of Free Tier limitations.
* Practice Lab 22 about automatically starting/stopping EC2 to optimize cost.
* Complete Lab 27 about resource management with tags.

---

## Work Completed

| Date | Task | Result | Resources | Notes |
|---|---|---|---|---|
| 18/05/2026 | Studied Shared Responsibility Model, IAM, and Cognito. | Understood the security responsibility boundary between AWS and users. Reviewed IAM User, Group, Policy, Role, and Cognito as an authentication option for applications. | [Module 05-01](https://www.youtube.com/watch?v=tsobAlSg19g&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=151) <br> [Module 05-02](https://www.youtube.com/watch?v=N_vlJGAqZxo&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=152) <br> [Module 05-03](https://www.youtube.com/watch?v=pZ2fgEFK3Vs&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=153) | Completed the first theory group of Module 05. |
| 19/05/2026 | Studied Organizations, Identity Center, KMS, Security Hub, and hands-on overview. | Learned multi-account management, centralized access control, and KMS encryption. Security Hub was recorded at overview level because direct activation needs cost consideration. | [Module 05-04](https://www.youtube.com/watch?v=5oQY8Rogz9Y&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=154) <br> [Module 05-05](https://www.youtube.com/watch?v=NW1xrMkNMjU&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=155) <br> [Module 05-06](https://www.youtube.com/watch?v=GMihNQojhZc&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=156) <br> [Module 05-07](https://www.youtube.com/watch?v=clj2E0rNBEs&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=157) | Took detailed notes on permissions and encryption. |
| 20/05/2026 | Studied Lab 18 about AWS Security Hub. | Read the lab flow and understood how Security Hub aggregates findings, tracks security score, and supports account security posture checks. | [Lab 18 - AWS Security Hub](https://000018.awsstudygroup.com/) | Documentation only, not enabled directly to avoid cost. |
| 21/05/2026 | Practiced Lab 22: EC2 cost optimization with Lambda, EventBridge, and Slack. | Created a test EC2 instance, tagged it for Lambda filtering, implemented scheduled start/stop automation, and checked Slack notifications. | [Lab 22 - EC2 Cost Optimization](https://000022.awsstudygroup.com/vi/2-prerequiste/) | Completed the main automation flow. |
| 22/05/2026 | Personal leave. | No learning activity. |  | Day off. |
| 23/05/2026 | Completed Lab 27 about resource management with tags. | Practiced tagging EC2/EBS, filtering resources by metadata, and creating Resource Groups based on tags. | [Lab 27 - Resource Tagging](https://000027.awsstudygroup.com/vi/) | Tagging is useful for both management and automation. |

---

## Weekly Notes

This week focused on security and resource operations. I realized that IAM is not only about creating users or assigning permissions, but also the foundation for AWS services to work together safely.

Lab 22 was practical because scheduled EC2 start/stop can be applied immediately to reduce learning costs. Lab 27 also showed that tags are not just labels; they can support filtering, management, permission scope, and automation.

---

## Challenges Encountered

* Shared Responsibility Model can be confusing for managed services because AWS and customer responsibilities change depending on the service type.
* Lab 18 could not be practiced directly because of Free Tier limitations, so I only read the flow and took notes.
* Lab 22 required coordinating EC2 tags, IAM Role, Lambda, EventBridge, and Slack, so each step had to be checked during debugging.
* In Lab 27, inconsistent tag naming can make resource filtering and Resource Group creation fail easily.

---

## Lessons Learned

* Shared Responsibility Model helps clarify what AWS manages and what users must configure.
* Lambda with EventBridge is suitable for scheduled operations such as EC2 start/stop.
* Tagging should be standardized early to make resource management easier later.
* Security Hub is useful, but cost and scope should be considered before enabling it in a learning account.

---

## Practice Screenshots

### Lab 22 - Optimize EC2 Cost with Lambda

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

### Lab 27 - Resource Management with Tags

![Lab27 Create 2 EC2 with tag](/images/Worklog-week5/Lab27-Create%202%20EC2%20with%20tag.png)

![Lab27 Add or Delete tag with Manage tags](/images/Worklog-week5/Lab27-Add%20or%20Delete%20tag%20with%20Manage%20tags.png)

![Lab27 Filter resources by tag](/images/Worklog-week5/Lab27-Filter%20resouces%20by%20tag.png)

![Lab27 Using tag CLI](/images/Worklog-week5/Lab27-Using%20tag%20CLI.png)

![Lab27 Create Resource Group](/images/Worklog-week5/Lab27-Create%20Resource%20Group.png)
