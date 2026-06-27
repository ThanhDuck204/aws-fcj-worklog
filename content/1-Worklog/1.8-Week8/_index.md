---
title: "Week 8 Worklog"
date: 2026-06-08
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

## Week 8 Objectives

* Work with the team to review the progress of the AI Meeting Workforce Platform.
* Adjust the architecture based on feedback, especially transcript, task, and user data flows.
* Estimate AWS costs for the MVP phase.
* Explore optimization ideas for AI processing, data validation, and caching.
* Prepare a short Kiro blog outline for sharing in the group.

---

## Work Completed

| Date | Task | Result | Resources | Notes |
|---|---|---|---|---|
| 08/06/2026 | Worked with the team at the company, reviewed project progress, and collected feedback. | Reviewed what was built last week, including layout, mock data, role-based routing, and meeting processing flow. Noted items to improve: module organization, AI output data, and AWS integration preparation. | None | Finalized improvement items for the week. |
| 09/06/2026 | Reviewed the architecture diagram and estimated AWS costs. | Clarified the roles of S3, Lambda, API Gateway, DynamoDB, Cognito, CloudFront, and CloudWatch. Recorded cost factors such as transcript/audio storage, Lambda/API Gateway calls, CloudWatch logs, and DynamoDB requests. | [AWS Pricing Calculator](https://calculator.aws/#/) <br> [AWS Architecture Center](https://aws.amazon.com/architecture/) | Prioritized an MVP-sized architecture. |
| 10/06/2026 | Explored project optimization ideas. | Reviewed possible improvements such as transcript preprocessing, splitting the AI pipeline into clearer steps, standardizing output data, adding retry logic, and considering dashboard caching. | None | Started with simple solutions before making the system too complex. |
| 11/06/2026 | Researched Kiro and prepared a blog outline. | Agreed on the main points: what Kiro is, how spec-driven development reduces ambiguity, and how it could apply to the team project. The outline was written to be short and readable. | [AWS Blog](https://aws.amazon.com/blogs/) | The blog should focus on practical experience, not only documentation summary. |
| 12/06/2026 | Continued project development based on the week's feedback. | Rechecked the main flow of the AI Meeting Workforce Platform, adjusted missing parts, and prepared for the next integration/improvement step. Also recorded a few architecture decisions for team reference. | None | Focused on keeping the project structure clear. |

---

## Weekly Notes

This week the team reviewed the project more carefully instead of only adding new code. The architecture was reviewed from two angles: how the system runs and where AWS costs may appear.

The important point for me was not to add too many AWS services to the MVP just because they are interesting. At the current scale, the architecture needs to be clear enough for future development while staying simple enough for the team to implement and debug.

---

## Challenges Encountered

* AWS cost estimation was still not exact because it depends on request volume, file size, and how users actually use the system.
* The architecture diagram needed enough detail for implementation but should not include too many components that make it hard to follow.
* Transcript processing and task extraction need clear steps; putting everything into one flow would make debugging harder.
* The Kiro blog needed to be short and easy to understand instead of only summarizing technical documentation.

---

## Lessons Learned

* AWS architecture design should consider both technical flow and operational cost.
* Serverless fits the MVP, but logs, requests, and stored data still need to be controlled.
* Team feedback helps reveal unclear architecture parts early.
* Recording design decisions helps reduce confusion during later development.
