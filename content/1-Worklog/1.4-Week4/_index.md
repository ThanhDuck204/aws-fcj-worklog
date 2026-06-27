---
title: "Week 4 Worklog"
date: 2026-05-11
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

## Week 4 Objectives

* Continue Module 04 about Storage on AWS.
* Learn Snow Family, Storage Gateway, Disaster Recovery, and AWS Backup.
* Research Cost Explorer API, Billing API, and IAM API for the AWS Management Dashboard idea.
* Review Event 1 content about Prompt Engineering, Proptimizer, and BMAD.

---

## Work Completed

| Date | Task | Result | Resources | Notes |
|---|---|---|---|---|
| 11/05/2026 | Studied Snow Family, Storage Gateway, Disaster Recovery, and AWS Backup. | Understood how AWS supports large-scale data transfer, hybrid storage, and centralized backup. Recorded RTO/RPO to compare disaster recovery strategies. | [Module 04-04 - Snow Family and Storage Gateway](https://www.youtube.com/watch?v=YXn8Q_Hpsu4&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=106) | DR needs to be connected to real scenarios. |
| 12/05/2026 | Researched AWS Cost Explorer API, Billing API, and AWS management dashboard architecture. | Understood how to retrieve cost data with `GetCostAndUsage`, distinguish Cost Explorer API from Billing API, and sketch a backend layer for the dashboard. | [AWS Cost Management API](https://docs.aws.amazon.com/aws-cost-management/latest/APIReference/Welcome.html) | Started shaping a cost monitoring dashboard direction. |
| 13/05/2026 | Researched IAM API and permission model for the dashboard. | Learned how to list users, groups, policies, and roles through IAM API. Noted that read-only permissions should be used if the dashboard is only for observation. | [IAM API Reference](https://docs.aws.amazon.com/IAM/latest/APIReference/Welcome.html) | IAM permission scope needs care. |
| 14/05/2026 | Reviewed Event 1: Proptimizer Extension, BMAD methodology, and AWS cost optimization. | Learned how structured prompts and BMAD can help break down requirements, plus a few AWS cost optimization practices. | [Event 1 Reflection](/4-eventparticipated/4.1-event1/) | Connected event content to learning and lab workflow. |
| 15/05/2026 | Wrote the Event 1 reflection and summarized weekly notes. | Completed the reflection and collected key ideas about Prompt Engineering, BMAD, and how to apply them to learning/project work. | [Event 1 Reflection](/4-eventparticipated/4.1-event1/) | Finished the week with a summary. |

---

## Weekly Notes

This week was not only about learning more AWS services, but also about thinking how AWS API data could be used to build a management dashboard. It connected cloud knowledge with a more product-oriented direction.

With Cost Explorer and IAM API, I realized that using an API is not only about calling an endpoint. It also requires understanding permissions, returned data limits, time grouping, and how to display data clearly.

---

## Challenges Encountered

* Disaster Recovery strategies were easy to mix up when only remembering their names, so RTO/RPO had to be used for comparison.
* Cost Explorer API and Billing API have different scopes, so documentation was needed to understand where each type of data comes from.
* IAM API is directly related to access control, so dashboard design needs to be careful with permissions.
* Event 1 introduced new ideas such as Proptimizer and BMAD, which needed to be summarized in a way that could apply to my workflow.

---

## Lessons Learned

* Disaster Recovery should be evaluated using RTO/RPO instead of only the model name.
* Cost Explorer API is useful for cost data grouped by day, service, or tag.
* An AWS management dashboard should start with read-only access to reduce risk.
* Prompt Engineering and BMAD are useful when requirements need to be broken down before implementation.
