---
title: "Week 8 Worklog"
date: 2026-06-08
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

## Week 8 Objectives

* Continue working with the team at the company to review the AI Meeting Workforce Platform progress.
* Receive improvement feedback from team members and adjust the project direction.
* Discuss the architecture diagram, main processing flow, and how AWS services work together.
* Estimate potential AWS costs for the MVP phase.
* Explore additional technologies, algorithms, and optimization techniques to make the project more stable.
* Research AWS blog content related to Kiro and prepare a blog post for the group.
* Continue project implementation based on the feedback and improvements agreed by the team.

---

## Completed Work

| Date | Task | Result | Resources | Notes |
|---|---|---|---|---|
| 08/06/2026 | Went to the company to discuss and work with the team on the project; continued receiving improvement feedback. | Reviewed the current progress of the AI Meeting Workforce Platform with the team, identified stable parts and areas that still need improvement. Collected feedback about user flows, module organization, meeting data processing, and preparation for future AWS integration. | None | Focused on teamwork and aligning the next improvement direction. |
| 08/06/2026 | Discussed the architecture diagram and estimated AWS service costs. | Reviewed the architecture diagram with the team and clarified the roles of services such as S3, Lambda, API Gateway, DynamoDB, Cognito, CloudFront, and CloudWatch. Started estimating cost categories including transcript/audio storage on S3, Lambda invocations, API Gateway requests, DynamoDB reads/writes, CloudFront data transfer, and CloudWatch logs/monitoring. | [AWS Pricing Calculator](https://calculator.aws/#/) <br> [AWS Architecture Center](https://aws.amazon.com/architecture/) | This step helped avoid choosing an architecture that would be too costly for the MVP scope. |
| 09/06/2026 | Continued improving the project and researching additional technologies and algorithms. | Explored improvement directions such as transcript processing optimization, splitting the AI processing pipeline into clearer steps, improving task extraction from meeting content, and standardizing output data. Also evaluated techniques that could make the system more stable, including retry logic, queue-based processing, result caching, and validation before writing to the database. | None | Focused on solutions that fit the project instead of adding unnecessary complexity. |
| 10/06/2026 | Discussed with the team and researched AWS blog content about Kiro to prepare a blog post. | Read and summarized information about Kiro with the team, focusing on how Kiro supports software development workflows, requirement clarification, spec creation, and structured implementation. Started selecting key ideas for the blog post to be shared in the group. | [AWS Blog](https://aws.amazon.com/blogs/) | Focused on understanding Kiro and turning the content into a readable blog post. |
| 11/06/2026 | Continued discussion and completed the outline for the Kiro blog post. | Agreed on the blog outline: introduction to Kiro, the problems Kiro solves, how Kiro supports developers, differences compared with using a regular AI assistant, and how Kiro could be applied to the team project. Prepared the content with a concise and practical writing style. | [AWS Blog](https://aws.amazon.com/blogs/) | Combined document reading with team discussion so the blog would include practical perspective, not only a summary. |
| 12/06/2026 | Continued working on the project. | Continued developing the AI Meeting Workforce Platform based on the feedback received during the week. Prioritized completing missing parts, checking the main processing flow, and preparing for the next integration or improvement steps. | None | Focused on project progress and keeping the structure aligned with the team. |

---

## Architecture Discussion & AWS Cost Estimation

This week, the team continued reviewing the overall architecture of the **AI Meeting Workforce Platform** to ensure the selected AWS services fit the MVP scope:

| Component | Planned AWS Service | Cost Factors |
|---|---|---|
| Transcript/audio storage | Amazon S3 | Storage size, upload/download requests, lifecycle policy |
| Backend/AI processing | AWS Lambda | Invocation count, execution duration, memory allocation |
| API | Amazon API Gateway | Frontend request volume |
| Database | Amazon DynamoDB | Read/write capacity, query patterns, secondary indexes |
| Authentication | Amazon Cognito | Monthly active users, user pool usage |
| CDN | Amazon CloudFront | Data transfer, request count |
| Monitoring | Amazon CloudWatch | Log volume, metrics, alarms |

**Observation:** For the MVP phase, a serverless approach is still suitable because costs can scale with actual usage. However, the team needs to control logs, API/Lambda invocation counts, file sizes, and DynamoDB read/write patterns to avoid unnecessary cost growth.

---

## Technologies and Algorithms Considered

* **Transcript preprocessing**: Clean meeting transcripts before passing them into AI summarization/task extraction.
* **Task extraction pipeline**: Split processing into steps such as detecting action items, assignees, priorities, and deadlines.
* **Retry logic**: Retry failed API calls or Lambda processing tasks.
* **Queue-based processing**: Consider queues for long transcript processing to avoid timeout issues.
* **Caching**: Cache dashboard data or common query results to reduce database reads.
* **Validation layer**: Standardize data before writing to DynamoDB to reduce data errors during development.

---

## Kiro Research and Blog Preparation

The team researched AWS content related to **Kiro** to prepare a blog post for the group. The planned content includes:

* What Kiro is and how it supports developers.
* Why spec-driven development helps reduce ambiguity in projects.
* How Kiro can help write requirements, split tasks, create plans, and generate code.
* Differences between Kiro and using a regular AI assistant for isolated questions.
* How Kiro could be applied to the AI Meeting Workforce Platform project.

---

## Knowledge & Skills Gained

* Better understanding of how to review an architecture diagram from a practical implementation perspective.
* Learned to evaluate AWS architecture from both technical and operational cost perspectives.
* Gained more experience estimating major cost categories in a serverless system.
* Explored techniques for system stability such as retry, queueing, caching, and validation.
* Practiced reading technical blogs, summarizing key points, and turning them into shareable content.
* Improved teamwork skills through feedback collection and project direction alignment.

---

## Challenges & Solutions

* **AWS cost estimation had many variables**: Cost depends on requests, file size, Lambda runtime, and database read/write patterns. Solution: estimate each service separately, then combine the results with AWS Pricing Calculator.
* **The architecture diagram needed to balance completeness and readability**: Adding too many services could make it hard to understand. Solution: keep only MVP-required components in the main diagram and note future services separately.
* **Choosing suitable technologies for the project**: Many technologies and algorithms could be applied, but not all are necessary. Solution: prioritize simple approaches that directly solve project problems.
* **Writing a Kiro blog post that is easy for the group to understand**: Technical materials include many new concepts. Solution: write concisely with practical examples and connect the content to the current project.

---

## Lessons Learned

* When designing AWS architecture, technical flow and operational cost should be considered together.
* Serverless is suitable for MVPs, but logs, API calls, and data storage still need to be controlled.
* Team feedback helps reveal unclear parts of the architecture and processing flow early.
* Researching new technologies should start from real project problems instead of trends.
* Writing a technical blog is a useful way to verify understanding and share knowledge with others.
