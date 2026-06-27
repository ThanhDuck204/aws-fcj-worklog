---
title: "Week 6 Worklog"
date: 2026-05-25
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

## Week 6 Objectives

* Continue remaining Module 05 labs about IAM, permission boundary, KMS, and role-based access.
* Practice Lab 28, Lab 30, and Lab 33 at a level suitable for the learning account.
* Study Lab 44 and Lab 48 to understand IAM Role, conditions, and granting AWS access to applications.
* Start Module 06 about databases, Redshift, and ElastiCache.

---

## Work Completed

| Date | Task | Result | Resources | Notes |
|---|---|---|---|---|
| 26/05/2026 | Practiced Lab 28 about EC2 access control with Resource Tags and studied Lab 30 about Permission Boundary. | Lab 28 reached the policy/role creation steps but stopped at an update role policy error. Lab 30 completed the policy creation part for restricting EC2 by Region and reviewed the remaining flow. | [Lab 28](https://000028.awsstudygroup.com/) <br> [Lab 30](https://000030.awsstudygroup.com/vi/1-introduce/) | Recorded the issue for later checking of JSON policy and trust relationship. |
| 26/05/2026 | Practiced Lab 33: encrypt data at rest with AWS KMS. | Created IAM resources, KMS key, S3 bucket with KMS encryption, CloudTrail, and Athena. Tested encrypted data access to understand the relationship between S3 permissions and KMS permissions. | [Lab 33 - Encrypt at rest with AWS KMS](https://000033.awsstudygroup.com/1-introduce/) | Completed the main steps. |
| 27/05/2026 | Studied Lab 44, Lab 48, and started Module 06-01. | Read about assume role flow, IP/time-based conditions, and attaching IAM Role to EC2 instead of hardcoding access keys. Then reviewed database concepts. | [Lab 44](https://000044.awsstudygroup.com/vi/1-iam-intro/) <br> [Lab 48](https://000048.awsstudygroup.com/vi/1-prepare/) <br> [Module 06-01](https://www.youtube.com/watch?v=OOD2RwWuLRw&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=217) | Lab 44/48 were documentation-only to avoid creating too many permissions and resources. |
| 29/05/2026 | Studied Module 06-03 about Redshift and ElastiCache. | Understood Redshift for OLAP/data warehouse, MPP architecture, and columnar storage. For ElastiCache, learned how Redis/Memcached can reduce database load and improve application latency. | [Module 06-03 - Redshift - ElastiCache](https://www.youtube.com/watch?v=UvdiRW34aNI&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=219&t=145s) | Focused on theory and use cases, without creating real clusters. |
| 30/05/2026 | Personal leave. | No learning activity. |  | Day off. |

---

## Weekly Notes

This week had a lot of advanced IAM content. The hardest part was policy conditions because a wrong key or missing trust relationship can make a role behave differently from expected.

Lab 33 was the clearest hands-on part of the week. When encrypting S3 files with KMS, I saw that access is not only controlled by bucket policy but also by permissions to use the KMS key.

Module 06 also started shifting the focus from security to database services. Redshift and ElastiCache serve very different purposes: one is for large-scale analytics, while the other caches frequently accessed data.

---

## Challenges Encountered

* Lab 28 stopped at the role policy update step, so JSON policy, ARN, and trust relationship need to be checked again.
* IAM Permission Boundary can be misunderstood as a permission-granting policy, while it actually only sets the maximum permission boundary.
* With KMS and S3, S3 access alone is not enough if decrypt permission on the KMS key is missing.
* Lab 44 and Lab 48 could create many IAM users, roles, access keys, and EC2/S3 resources, so I studied them instead of fully deploying them.
* Redshift and ElastiCache introduced new concepts such as MPP, columnar storage, cache miss, and cache invalidation, so notes had to be organized by use case.

---

## Lessons Learned

* IAM conditions are powerful but require careful checking of policy syntax, ARN, and trust relationship.
* Permission Boundary does not grant permissions; it only limits the maximum permissions of a user or role.
* When S3 uses KMS encryption, both object access and KMS key usage permission matter.
* IAM Role on EC2 is safer than long-term access keys in code.
* Redshift is suitable for OLAP/data warehouse workloads, not as a replacement for transactional RDS.
* ElastiCache is effective only when there is a clear caching strategy: what to cache, TTL, and invalidation rules.

---

## Practice Screenshots

### Lab 28 - EC2 Access Management with Resource Tags through IAM

![Lab28 Create Admin group and add IAM users](/images/Worklog-week6/Lab28-Create%20Admin%20group%20and%20add%20IAM%20users.png)

![Lab28 Create policies](/images/Worklog-week6/Lab28-Create%20policies.png)

![Lab28 Create IAM Role with policies](/images/Worklog-week6/Lab28-Create%20an%20IAM%20Role%20with%20the%20policies%20that%20were%20just%20created..png)

### Lab 30 - IAM Permission Boundary

![Lab30 Create policy limited](/images/Worklog-week6/Lab30-Create%20policty%20limited.png)

### Lab 33 - Encrypt at rest with AWS KMS

![Lab33 Create roles and policy](/images/Worklog-week6/Lab33-Create%20roles%20and%20policy.png)

![Lab33 Create Group and user with role S3](/images/Worklog-week6/Lab33-Create%20Group%20and%20user%20with%20role%20S3.png)

![Lab33 Create KMS Key](/images/Worklog-week6/Lab33-Create%20KMS%20Key.png)

![Lab33 Create S3 kms key](/images/Worklog-week6/Lab33-Create%20S3%20kms%20key.png)

![Lab33 Upload data to S3](/images/Worklog-week6/Lab33-Upload%20data%20to%20S3.png)

![Lab33 Create CloudTrail](/images/Worklog-week6/Lab33-Create%20Cloudtrail.png)

![Lab33 Logging to CloudTrail](/images/Worklog-week6/Lab33-Logging%20to%20CloudTrail.png)

![Lab33 Create Amazon Athena](/images/Worklog-week6/Lab33-Create%20Amazon%20Athena.png)

![Lab33 Retrieve data with Athena](/images/Worklog-week6/Lab33-Retrieve%20data%20with%20Athena.png)

![Lab33 Test and share encrypted data on S3](/images/Worklog-week6/Lab33-Test%20and%20share%20encrypted%20data%20on%20S3.png)
