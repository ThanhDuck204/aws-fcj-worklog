---
title: "Week 7 Worklog"
date: 2026-06-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

## Week 7 Objectives

* Finalize the scope of the AI Meeting Workforce Platform team project.
* Design the overall architecture and initial project skeleton.
* Build mock data, mock services, and role-based layouts so the team can develop in parallel.
* Check dependencies and define the AWS services planned for the MVP.
* Continue Module 06 to evaluate database options.

---

## Work Completed

| Date | Task | Result | Resources | Notes |
|---|---|---|---|---|
| 01/06/2026 | Team meeting to finalize the project idea and initial architecture. | Agreed on the AI Meeting Workforce Platform scope: transcript upload, AI meeting summary, task extraction, and dashboards for Admin/Manager/Employee. Sketched an architecture using Next.js, Cognito, S3, Lambda, DynamoDB, API Gateway, and CloudFront. | [Next.js Documentation](https://nextjs.org/docs) <br> [AWS Architecture Center](https://aws.amazon.com/architecture/) | Finalized the main project direction. |
| 02/06/2026 | Created mock data, mock AI service, mock auth, and checked packages. | Created departments, users, meetings, tasks, and notifications data. Added mock AI service for meeting summary/task extraction and reviewed dependencies to avoid risky versions. | None | Prepared a frontend foundation before the backend is ready. |
| 03/06/2026 | Built layout, role-based navigation, and main routing. | Created AppShell, Sidebar, TopBar, stat cards, panels, status pills, and main pages for Admin/Manager/Employee. Navigation was separated by role for easier extension later. | None | Focused on UI structure and access flow. |
| 04/06/2026 | Continued Module 06 about RDS, Aurora, DynamoDB, and DMS. | Compared database services to see which ones fit the project. DynamoDB remained a reasonable MVP choice because meeting/task data can be modeled in a NoSQL style. | [Cloud Journey](https://cloudjourney.awsstudygroup.com/) | Connected database knowledge to the team project. |
| 05/06/2026 | Collected team feedback and adjusted the project skeleton. | Reviewed folder structure, mock data, service layer, and AWS integration preparation. Some points were noted for Week 8, especially the meeting data processing flow. | None | Synchronized early to avoid inconsistent implementation styles. |

---

## Weekly Notes

This was the week where the work shifted clearly from individual labs to a team project. The hardest part was not writing code immediately, but agreeing on a scope small enough for the MVP.

The team chose to build mock data and mock services first so the frontend could run early. This makes the product flow visible sooner, then real APIs and AWS integrations can replace the mock layer later.

---

## Challenges Encountered

* While finalizing scope, there were many ideas to add, but the MVP needed to stay small enough for the team to complete.
* Mock data had to be easy for the frontend to use while still staying close to the future schema.
* Role-based routing can create repeated page/navigation code if configuration is not separated clearly.
* The team needed to agree on folder structure and service layer style to avoid inconsistent implementations.

---

## Lessons Learned

* Team projects need early scope alignment, otherwise features can grow too quickly.
* Mock data should be designed close to the future schema to reduce rework.
* Role-based navigation should be centralized in configuration for easier maintenance.
* Database selection should be based on application read/write patterns, not habit.
