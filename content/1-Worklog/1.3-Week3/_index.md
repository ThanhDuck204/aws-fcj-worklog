---
title: "Week 3 Worklog"
date: 2026-05-04
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

## Week 3 Objectives

* Start Module 03 about Compute on AWS.
* Understand EC2 concepts such as instance type, AMI, key pair, user data, metadata, and Auto Scaling.
* Practice AWS Backup, Storage Gateway, and S3 static website hosting.
* Prepare the foundation for Module 04 about Storage.

---

## Work Completed

| Date | Task | Result | Resources | Notes |
|---|---|---|---|---|
| 04/05/2026 | Studied EC2 theory: instance type, AMI, key pair, and pricing model. | Understood how to choose an instance based on CPU/RAM/network, how AMI affects the OS and initial configuration, and compared On-Demand, Reserved, Savings Plans, and Spot. | [Cloud Journey](https://cloudjourney.awsstudygroup.com/) | Core foundation for Compute. |
| 05/05/2026 | Studied EC2 User Data, EC2 Metadata, and EC2 Auto Scaling. | Learned how user data can bootstrap a server at launch. Understood metadata endpoint and the idea of scaling out/in based on demand. | [Cloud Journey](https://cloudjourney.awsstudygroup.com/) | These concepts are useful for automation. |
| 06/05/2026 | Completed Lab 13 about AWS Backup, SNS, and restore testing. | Deployed AWS Backup infrastructure, configured SNS notifications, and tested restore flow through Lambda. | [AWS Backup Lab](https://000013.awsstudygroup.com/) | Backup only matters when restore is tested. |
| 07/05/2026 | Studied Storage Gateway, S3 Static Website, and CloudFront. | Understood how Storage Gateway supports hybrid storage. Practiced hosting a static website on S3 with versioning and CloudFront/OAC for safer access. | [Storage Gateway Workshop](https://000024.awsstudygroup.com/vi/3-cleanup/) <br> [S3 Static Website Workshop](https://000057.awsstudygroup.com/) | Completed Module 03. |
| 08/05/2026 | Started Module 04 about Storage. | Watched the AWS storage overview and reviewed key Amazon S3 concepts before studying deeper storage topics next week. | [Module 04-01 - Storage on AWS](https://www.youtube.com/watch?v=hsCfP0IxoaM&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=103) <br> [Module 04-02 - Amazon S3](https://www.youtube.com/watch?v=_yunukwcAwc&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=104) | Prepared for Week 4. |

---

## Weekly Notes

This week made the difference between compute and storage on AWS clearer. EC2 was easy to approach because it feels similar to a traditional server, but user data, metadata, and Auto Scaling show how cloud operations differ from manual server management.

AWS Backup was also practical. I realized that backup is only useful when the restore process is clear and tested, not just when a backup plan is enabled.

---

## Challenges Encountered

* EC2 has many instance types and pricing models, so the choice needs to be based on workload rather than price alone.
* User Data and Metadata were a bit abstract at first because they relate to automation during instance launch.
* The AWS Backup lab required several IAM permissions and resources, so each step needed careful reading before running.
* Storage Gateway could not be fully practiced in the learning account, so I focused on documentation and architecture notes.

---

## Lessons Learned

* Instance type selection should follow workload needs, not only the lowest cost.
* User Data is useful for automatically configuring servers at launch.
* AWS Backup should include restore testing to ensure data can actually be recovered.
* S3 static website and CloudFront show how storage can directly participate in application architecture.
