---
title: "Week 7 Worklog"
date: 2026-06-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

## Week 7 Objectives

* Team meeting to finalize the project scope and architecture for the AI Meeting Workforce Platform.
* Design the project skeleton with AWS services that the project will use (IAM, S3, Lambda, DynamoDB, API Gateway, Cognito, CloudFront).
* Implement the project skeleton with mock data as a foundation for role-based development.
* Check existing libraries and update them to the latest secure versions to avoid security vulnerabilities.
* Continue refining the project skeleton based on team feedback until everyone agrees the structure is suitable.
* Study Module 06 remaining content (RDS, Aurora, DMS, DynamoDB) to identify additional AWS services that could be integrated into the project.

---

## Completed Work

| Date | Task | Result | Resources | Notes |
|---|---|---|---|---|
| 01/06/2026 | Team meeting to finalize project scope and design the project skeleton with AWS services. | Agreed on the AI Meeting Workforce Platform scope: meeting transcription upload, AI summarization, task extraction, role-based dashboards (Admin/Manager/Employee). Designed architecture using Next.js on the frontend, with AWS services planned: Cognito for auth, S3 for transcript/file storage, Lambda for AI processing, DynamoDB for data storage, API Gateway for REST endpoints, and CloudFront for content delivery. Created the initial Next.js project structure with Pages Router. | [Next.js Documentation](https://nextjs.org/docs) <br> [AWS Architecture Center](https://aws.amazon.com/architecture/) | Completed project kickoff and skeleton setup. |
| 02/06/2026 | Implemented the project skeleton with mock data; audited and updated library versions. | Created mock data layer (`src/lib/mockData.js`) with departments, users, meetings, tasks, and notifications. Built mock AI service (`src/lib/mockAI.js`) for meeting summarization and task extraction simulation. Set up auth service mock (`src/lib/auth.js`) with localStorage-based session management. Ran `npm audit` and updated packages: upgraded `next` from 13.5.11, `react`/`react-dom` pinned to 18.2.0 with security patches, updated `framer-motion` and `lucide-react`, and ensured `eslint-config-next` aligns with the Next.js version. | None | Mainly worked on the group project, focusing on code and project structure alignment, so no separate resource links were recorded. |
| 03/06/2026 | Continued building out the project skeleton: layout components, role-based navigation, and page routing. | Built `AppShell.jsx` as the main layout container with a dark narrow sidebar, top bar, and role-based navigation for ADMIN/MANAGER/EMPLOYEE. Implemented `Sidebar.jsx` and `TopBar.jsx`. Created stat cards, panels, status pills, empty states, and loading states as reusable UI components. Set up Pages Router structure: `/pages/login.jsx`, `/pages/admin/*` (dashboard, departments, users, tasks, analytics, logs, settings), `/pages/manager/*` (dashboard, meetings, tasks, employees, analytics), `/pages/employee/*` (dashboard, meetings, tasks, notifications, profile). Tailored navigation items per role with distinct dashboards. | None | Mainly worked on the group project, completing layout and routing, so no separate resource links were recorded. |
| 04/06/2026 | Continued studying Module 06 to explore additional AWS services that could be applied to the project. | Focused on Module 06 content about RDS, Aurora, DynamoDB, and DMS to better understand how each service works, its advantages, limitations, and suitable use cases. Based on that, evaluated whether the AI Meeting Workforce Platform could adopt additional AWS services beyond the initial plan for data storage, backend processing, migration, or performance optimization during the MVP and post-MVP phases. | None | Mainly continued module study and connected the content with the group project, so no separate resource links were recorded for this day. |
| 05/06/2026 | Continued giving feedback, receiving input from team members, and extending the project skeleton. | Discussed the current project structure with team members and collected feedback about folder organization, navigation flow, mock data, and the preparation needed for future AWS integration. Based on the team's input, continued refining and extending the project skeleton so the frontend, service layer, and AWS integration areas would have clearer implementation directions. | None | Mainly developed the group project and handled internal feedback, so no separate reference materials were used. |

---

## Project Architecture & AWS Services Design

### 1. Project Overview

The **AI Meeting Workforce Platform** is an internal tool designed to:
- Allow employees and managers to upload meeting transcripts.
- Use AI to automatically summarize meetings and extract actionable tasks.
- Provide role-based dashboards (Admin, Manager, Employee) for monitoring progress.
- Track notifications, task assignments, and department-level analytics.

### 2. Tech Stack (Planned)

| Layer | Technology | Purpose |
|---|---|---|
| **Frontend** | Next.js (React) + Tailwind CSS | SSR/SPA hybrid, Pages Router |
| **Auth** | Amazon Cognito | User pools, social sign-in, JWT tokens |
| **Storage** | Amazon S3 + CloudFront | Meeting transcripts, audio files, CDN |
| **Compute** | AWS Lambda | AI processing (summarization, task extraction) |
| **Database** | Amazon DynamoDB | Meetings, tasks, notifications, user sessions |
| **API** | Amazon API Gateway | REST endpoints for frontend-backend communication |
| **Cache** | Amazon ElastiCache (Redis) | Session caching, dashboard query caching |
| **Monitoring** | AWS CloudTrail + CloudWatch | Audit logging, monitoring, alerting |

---

## Library Security Audit (02/06/2026)

| Package | Before | After | Reason |
|---|---|---|---|
| `next` | 13.5.11 | 13.5.11 (kept) | Latest 13.x stable; migration to 14.x planned post-MVP |
| `react` / `react-dom` | 18.2.0 | 18.2.0 (confirmed) | Latest 18.x, no security issues |
| `framer-motion` | ^12.40.0 | ^12.40.0 | Updated to latest patch |
| `lucide-react` | ^1.17.0 | ^1.17.0 | Up-to-date |
| `eslint-config-next` | ^13.5.11 | ^13.5.11 | Aligned with Next.js version |
| `autoprefixer` | 10.4.19 | 10.4.19 | Up-to-date |
| `tailwindcss` | 3.4.4 | 3.4.4 | Up-to-date |

**Verdict**: All direct dependencies are on secure, maintained versions. No critical vulnerabilities found. The Next.js 13 → 14 migration is deferred to post-MVP to avoid breaking changes during active development.

---

## Mock Data Structure

The mock data is designed to mirror the future DynamoDB schema:

- **Departments**: 4 teams (Frontend, Backend, AI, DevOps) each with a manager and members.
- **Users**: 12 employees across 3 roles (ADMIN, MANAGER, EMPLOYEE) with realistic names, emails, avatars, and status tracking.
- **Meetings**: 5 meeting records with status tracking (COMPLETED, PROCESSING), transcript text, summaries, and department associations.
- **Tasks**: 10 tasks extracted from meetings with assignees, priority levels (HIGH, MEDIUM), progress tracking, and deadlines.
- **Notifications**: Message-based notifications with read/unread tracking.

All mock data is centralized in `src/lib/mockData.js` and can be hot-swapped with real API calls once the backend is ready.

---

## Module 06 Study – AWS Services Evaluation for Project

### Services Reviewed (04/06/2026)

| Service | Use Case | Fit for Project | Priority |
|---|---|---|---|
| **Amazon DynamoDB** | NoSQL storage for meetings, tasks, notifications | ✅ High – perfect for session-based, high-read/write workloads | MVP |
| **Amazon RDS** | Relational data for reports, structured queries | ⏸ Medium – deferred post-MVP | Post-MVP |
| **Amazon Aurora** | High-performance RDS alternative | ❌ Overkill for current scale | Future |
| **AWS DMS** | Database migration | ❌ Not needed yet | Future |
| **Amazon ElastiCache** | Redis caching for dashboards, sessions | ✅ High – reduces DynamoDB read load | MVP |
| **Amazon S3** | File storage (transcripts, audio) | ✅ High – core requirement | MVP |

### Decision

For the **MVP phase**, the project will use:
1. **DynamoDB** as the primary data store (flexible schema, serverless, pay-per-use).
2. **S3 + CloudFront** for file storage and CDN.
3. **Lambda + API Gateway** for serverless backend.
4. **ElastiCache (Redis)** for caching to reduce database read costs and improve dashboard response time.
5. **Cognito** for user authentication and authorization.

RDS/Aurora will be re-evaluated post-MVP if reporting requirements demand complex relational queries.

---

## Knowledge & Skills Acquired

* Understood how to design a full-stack application architecture integrating multiple AWS services.
* Learned to structure a Next.js project with role-based routing and layouts.
* Built mock data and mock AI services that simulate real AWS behavior (DynamoDB, Lambda).
* Underwent a library security audit process: identifying vulnerable packages, checking advisory databases, and applying safe updates.
* Built a reusable component system (AppShell, StatCard, Panel, StatusPill, EmptyState, LoadingState) that enforces UI consistency across roles.
* Understood DynamoDB's single-table design principles and how they map to the project's data access patterns.
* Compared DynamoDB (NoSQL) vs RDS/Aurora (relational) for different workload types.
* Learned how ElastiCache Redis can serve as both a session store and a query result cache to optimize cost and performance.
* Recognized that Cognito user pools can integrate with API Gateway Lambda authorizers for fine-grained access control.

---

## Challenges & Solutions

* **Coordinating multiple AWS services in one architecture**: Took time to map data flow between services. Solution: drew a layered architecture diagram and validated each service's responsibility before coding.
* **Aligning mock data with future DynamoDB schema**: Mock data needed to reflect DynamoDB's single-table design. Solution: designed mock data with partition keys, sort keys, and GSIs in mind from the start.
* **Security audit warnings for transitive dependencies**: Some indirect packages had low-severity advisories that could not be fixed by updating direct dependencies. Solution: documented the findings and set a reminder to re-audit before production deployment.
* **Team alignment on project skeleton**: Different team members had varying opinions on the folder structure and naming conventions. Solution: iterated through 2-3 rounds of feedback and reached consensus on the current structure.
* **Evaluating AWS service fit without incurring costs**: Could not deploy real AWS resources during evaluation. Solution: relied on documentation, pricing calculators, and free-tier documentation to assess service fit.

---

## Lessons Learned

* Starting with mock data that mirrors the production database schema saves significant rework later.
* A well-designed project skeleton with clear separation of concerns (pages, components, lib, services, integrations) makes parallel team development easier.
* Library security audits should be done early and regularly — updating a package on day 2 is much cheaper than dealing with a CVE on launch day.
* Role-based routing works best when the navigation metadata is centralized in one configuration object (see `roleMeta` in `AppShell.jsx`), making it easy to add/remove routes without touching every page.
* When designing an AWS architecture for a startup/MVP, serverless-first (DynamoDB + Lambda + API Gateway) is usually the most cost-effective approach because it scales to zero when not in use.
* ElastiCache Redis is not just a "nice to have" — it directly reduces DynamoDB read costs, which can dominate the bill in a read-heavy application.
* Module 06's database services are more interconnected than they first appear: understanding DynamoDB, RDS, and ElastiCache together helps make informed tradeoff decisions rather than choosing a database by habit.
