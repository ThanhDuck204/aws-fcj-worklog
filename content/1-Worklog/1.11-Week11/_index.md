---
title: "Week 11 Worklog"
date: 2026-06-29
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

## Week 11 Objectives

* Continue connecting individual AWS services into the project.
* Write Blog 2 and finalize its content for approval.
* Adjust the project architecture due to Free Tier limitations.
* Write a support case to AWS for assistance.

---

## Work Completed

| Date | Task | Result | Resources | Notes |
|---|---|---|---|---|
| 29/06/2026 | Project work — connecting individual AWS services. | Continued integrating AWS services such as Cognito, DynamoDB, and S3 into the project. Resolved connection errors and ensured smooth communication between services. | [GitHub Worklog](https://github.com/ThanhDuck204/aws-fcj-worklog) | Service connection |
| 30/06/2026 | Continued project work — connecting individual AWS services. | Completed pending connections, reviewed the entire integration flow, and ensured services communicated correctly according to the designed architecture. | [GitHub Worklog](https://github.com/ThanhDuck204/aws-fcj-worklog) | Service connection |
| 01/07/2026 | Wrote Blog 2 — AWS Nitro Enclaves. | Completed the research blog post about AWS Nitro Enclaves and how to run traditional web applications inside an Enclave environment. The post was approved. | [Facebook Post](https://www.facebook.com/groups/awsstudygroupfcj/?multi_permalinks=2198943464203947) <br> [AWS China Blog](https://aws.amazon.com/cn/blogs/china/running-traditional-web-application-migration-practices-in-aws-nitro-enclaves/) <br> [GitHub Worklog](https://github.com/ThanhDuck204/aws-fcj-worklog) | Blog writing |
| 02/07/2026 | Adjusted project architecture due to Free Tier limits and wrote a support case. | Reviewed the current architecture, adjusted the design to fit Free Tier constraints (only using services within the free tier). Wrote a support case to AWS for technical assistance. | [GitHub Worklog](https://github.com/ThanhDuck204/aws-fcj-worklog) | Architecture adjustment |
| 03/07/2026 | Continued connecting AWS services into the project. | Continued integrating and configuring AWS services, resolving errors, and ensuring connections were stable. | [GitHub Worklog](https://github.com/ThanhDuck204/aws-fcj-worklog) | Service connection |

---

## Weekly Notes

This week focused primarily on connecting AWS services into the project. The first two days were spent linking each service together and resolving integration errors.

Mid-week, I wrote Blog 2 about AWS Nitro Enclaves — a very interesting topic about security on AWS. The post was approved, completing this task successfully.

However, a major issue arose later in the week: the AWS account was limited to Free Tier, so many services from the original architecture could not be deployed. I had to redesign the architecture to fit within these constraints, while also writing a support case to AWS for assistance. This was an important real-world lesson about considering budget limitations during the architecture design phase.

---

## Challenges Encountered

* The process of connecting AWS services encountered many configuration errors, requiring step-by-step debugging and fixing.
* Blog 2 required translation and synthesis from Chinese documentation, taking time to ensure accuracy.
* Discovered the AWS account was limited to Free Tier late in the week — many services from the original architecture could not be deployed.
* Had to redesign the entire architecture to only use Free Tier-eligible services.
* Writing a support case in English with complete technical details to get timely AWS assistance.

---

## Lessons Learned

* Integrating multiple AWS services simultaneously requires patience and a solid understanding of each service's configuration.
* Translating and synthesizing technical documentation from Chinese to Vietnamese helps deepen understanding of the topic.
* Project architecture should account for budget and account limitations from the start, not just theoretical design.
* AWS Free Tier has many limitations — thorough checking is needed before selecting services for the architecture.
* Support cases are an important channel for technical issues with AWS — presenting the problem clearly with steps already tried helps get faster assistance.
