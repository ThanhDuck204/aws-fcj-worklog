---
title: "Week 4 Worklog"
date: 2026-05-11
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

# Worklog Week 4

## Week 4 Objectives

- Continue studying Module 04 – Storage on AWS.
- Learn about Snow Family, Storage Gateway, Disaster Recovery, and AWS Backup.
- Research AWS Cost Explorer API, Billing API, and IAM API to prepare for AWS Management Dashboard direction.

## Completed Work

| Date | Task | Result | Resources | Notes |
|---|---|---|---|---|
| 12/05/2026 | Studied Module 04-04: Snow Family, AWS Storage Gateway, Disaster Recovery, and AWS Backup. | Completed research on hybrid storage, data transfer, backup, and disaster recovery strategies. | [Module 04-04 - Snow Family and Storage Gateway](https://www.youtube.com/watch?v=YXn8Q_Hpsu4&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=106) | Completed on schedule. |
| 13/05/2026 | Researched AWS Cost Explorer API, Billing API, and AWS management dashboard architecture. | Understood how to get cost data through GetCostAndUsage and distinguish Cost Explorer API from Billing API. | [AWS Cost Management API](https://docs.aws.amazon.com/aws-cost-management/latest/APIReference/Welcome.html) | Completed API research. |
| 14/05/2026 | Researched IAM Management API, permission models, and AWS resource monitoring. | Learned how to list users, groups, and policies through IAM API; built a plan for the user management module. | [IAM API Reference](https://docs.aws.amazon.com/IAM/latest/APIReference/Welcome.html) | Completed IAM research. |
| 15/05/2026 | Reviewed technologies shared by speakers in Event 1: Proptimizer Extension, BMAD methodology, and AWS cost optimization practices. | Gained deeper understanding of Proptimizer, BMAD, and cost optimization techniques from community sharing. | [Event 1 Report](/4-eventparticipated/4.1-event1/) | Reviewed event content. |
| 16/05/2026 | Processed event notes and wrote the Event 1 report on Prompt Engineering and BMAD. | Completed the Event 1 report and applied the methodology to my workflow. | [Event 1 Report](/4-eventparticipated/4.1-event1/) | Wrote report after event. |

## Knowledge Learned

- **Snow Family**: Snowball, Snowball Edge, Snowmobile support large-scale data migration when Internet bandwidth is insufficient
- **AWS Storage Gateway**: Differentiated File Gateway (NFS/SMB), Volume Gateway (iSCSI Block), Tape Gateway (iSCSI VTL) by protocol and suitable workload
- **Disaster Recovery**: Understood RTO/RPO, compared strategies: Backup & Restore, Pilot Light, Low Capacity Active-Active, Full Capacity Active-Active
- **AWS Backup**: Understood how to use Backup Plan, retention policy, backup vault to manage centralized backup for EC2, EBS, RDS, DynamoDB, EFS, Storage Gateway
- **AWS APIs**: Researched Cost Explorer API (GetCostAndUsage), Billing API, IAM API to build dashboard
- **Dashboard Architecture**: Planned backend layer connecting to AWS SDK/API, UI to display costs, resource status, and IAM information
- **Prompt Engineering & BMAD**: Learned to optimize development workflow via Proptimizer Extension and BMAD method
- **AWS Cost Optimization**: Applied Free Tier, configured AWS Budgets, selected resources based on actual needs

## Achievements

- Completed comprehensive research on Storage services, Backup, and Disaster Recovery on AWS
- Developed prototype architecture for AWS Management Dashboard combining multiple APIs
- Applied knowledge from community event to improve development process
- Completed all planned tasks for week 4

## Challenges & Solutions

- **Challenge**: Confusing between different Disaster Recovery strategies
  **Solution**: Used RTO/RPO as the main criterion to distinguish each model

- **Challenge**: Selecting appropriate Storage Gateway type for specific workload
  **Solution**: Remembered by protocol: NFS/SMB for File Gateway, iSCSI Block for Volume Gateway, iSCSI VTL for Tape Gateway

- **Challenge**: Determining minimum access level needed for dashboard
  **Solution**: Compared IAM Actions with AWS documentation, prioritized minimal read-only access

## References

- AWS Documentation: Snow Family and Storage Gateway
- AWS Cost Explorer API Reference
- AWS IAM API Reference
- Event 1 Report on Prompt Engineering and BMAD
- AWS Cost Optimization materials from community
