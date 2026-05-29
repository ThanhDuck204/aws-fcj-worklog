---
title: "Week 6 Worklog"
date: 2026-05-25
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

## Week 6 Objectives

* Continue completing the remaining Module 05 labs related to IAM, EC2, and conditional access control.
* Understand how IAM Policies, IAM Roles, and Resource Tags can limit EC2 permissions.
* Practice Lab 28: managing EC2 access with Resource Tags through IAM Services.
* Study Lab 30: limiting IAM user permissions with IAM Permission Boundary.
* Practice Lab 33: encrypting S3 data with AWS KMS and tracking activity with CloudTrail and Athena.
* Study Lab 44: IAM Role & Condition, focusing on assume role and access conditions by IP/time.
* Study Lab 48: granting applications access to AWS services with IAM Role instead of direct access keys.
* After finishing the remaining Module 05 labs on Wednesday, begin Module 06-01 on database fundamentals.
* Continue studying Module 06 theory, focusing on Amazon Redshift and Amazon ElastiCache to understand data analytics services and application performance optimization.

---

## Completed Work

| Date | Task | Result | Resources | Notes |
|---|---|---|---|---|
| 26/05/2026 | Practiced Lab 28 and studied Lab 30. | Lab 28 was about half completed; Lab 30 was completed up to Create Policy and the remaining flow was reviewed. | [Lab 28 - EC2 Service Access Management with Resource Tags through IAM Services](https://000028.awsstudygroup.com/) <br> [Lab 30 - IAM Permission Boundary](https://000030.awsstudygroup.com/vi/1-introduce/) | Lab 28 had an update role policy error; Lab 30 had some Console items missing/different from the guide. |
| 26/05/2026 | Practiced Lab 33: Encrypt at rest with AWS KMS. | Created IAM resources, KMS key, KMS-encrypted S3 bucket, CloudTrail, Athena, and tested encrypted data sharing. | [Lab 33 - Encrypt at rest with AWS KMS](https://000033.awsstudygroup.com/1-introduce/) | Completed the main steps. |
| 27/05/2026 | Finished the remaining Module 05 lab research and started Module 06-01. | Researched Lab 44 and Lab 48 to close out the Module 05 lab set; then studied the Database Concepts review video to build foundations before moving into AWS database services. | [Lab 44 - IAM Role & Condition](https://000044.awsstudygroup.com/vi/1-iam-intro/) <br> [Lab 48 - Grant application access with IAM Role](https://000048.awsstudygroup.com/vi/1-prepare/) <br> [Module 06-01 - Database Concepts review](https://www.youtube.com/watch?v=OOD2RwWuLRw&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=217) | Lab 44/48 were research only because they require several IAM resources, EC2/S3, and may create permission or cost risks. |
| 29/05/2026 | Continued studying Module 06 theory through Module 06-03: Redshift - ElastiCache. | Understood Amazon Redshift for data warehouse/OLAP workloads, MPP architecture, columnar storage, and Redshift Spectrum; also learned how Amazon ElastiCache uses Redis/Memcached caching to reduce database load and improve application performance. | [Module 06-03 - Redshift - ElastiCache](https://www.youtube.com/watch?v=UvdiRW34aNI&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=219&t=145s) | Focused on theory, architecture notes, and use cases; no hands-on lab was deployed to avoid creating resources. |
| 30/05/2026 | Off for personal reasons. | No learning activities. |  | Personal leave. |

---

## Lab 28 Content

Lab 28 focuses on controlling EC2 access with Resource Tags through IAM. The lab applies Least Privilege and IAM policy conditions so users can interact with EC2 only when the required Region and tag conditions are satisfied.

### 1. Introduction

* Reviewed the purpose of the lab: managing EC2 access by tag instead of granting broad permissions across all resources.
* Learned how Resource Tags support delegated administration, especially when separating permissions by team or operator group.
* The main lab condition is the `Team=Alpha` tag and allowed AWS Regions such as `us-east-1` and `us-west-1`.

### 2. Preparation

* Prepared an AWS Account for testing.
* Created an IAM user with MFA so the user can perform assume role actions.
* Noted that the account should support more than one Region to test Region-based access conditions.

### 3. Create IAM Policy

* Created 5 IAM policies for EC2 access control:
  * `ec2-list-read`: allows read/list permissions for EC2 in selected Regions.
  * `ec2-create-tags`: allows tag creation during EC2 instance creation.
  * `ec2-create-tags-existing`: allows tagging existing EC2 resources when tag conditions are satisfied.
  * `ec2-run-instances`: allows EC2 instance creation when Region and `Team=Alpha` tag conditions are met.
  * `ec2-manage-instances`: allows start, stop, reboot, and terminate actions for EC2 instances with matching tags.
* This section helped reinforce condition keys such as `aws:RequestedRegion`, `aws:RequestTag`, `aws:TagKeys`, and `ec2:ResourceTag`.

### 4. Create IAM Role

* Created an IAM Role for the EC2 Administrator group, for example `ec2-admin-team-alpha`.
* Attached the 5 policies created earlier so the role has only the required permissions.
* Configured the trust relationship so the IAM user can assume the role, with MFA required as a best practice.
* Current practice status: reached the create/update role policy stage, but an error occurred while updating the policy, so this step is not fully complete.

### 5. Check Policy

* The planned verification step uses switch role to confirm that the policies work as expected.
* Test cases include:
  * Accessing a disallowed Region.
  * Accessing an allowed Region.
  * Creating EC2 without required tags or with invalid tags.
  * Editing tags on an EC2 instance.
  * Managing EC2 instances through start, stop, reboot, and terminate actions when the tag is valid.
* Because of the update role policy error, the policy verification section has not been completed.

### 6. Clean up resources

* After completing the lab, the IAM user, IAM role, policies, and related EC2 resources should be removed to avoid security risk and unnecessary cost.
* Cleanup has not been performed because the lab is not fully complete yet.

---

## Lab 30 Content

Lab 30 focuses on **IAM Permission Boundary**, a mechanism for limiting the maximum permissions an IAM user can have. The lab demonstrates a user with `AmazonEC2FullAccess` that is still limited to managing EC2 only in a selected Region through a permission boundary.

### 1. Introduction

* Learned what IAM Permission Boundary is and how it limits the maximum permissions for an IAM user or group.
* Understood effective permissions: the user's actual permissions are the intersection of the identity-based policy and the permission boundary.
* Reviewed why Permission Boundary helps reduce privilege escalation risk when many users and policies change over time.

### 2. Preparation

* Prepared an AWS Account that can use IAM.
* Noted that the lab mainly uses IAM Management Console and verifies EC2 access by Region.

### 3. Create Limited Policy

* Created the `ec2-admin-restrict-region` policy to limit the user's maximum permissions.
* The policy allows `ec2:*` actions only when the request is made in `ap-southeast-1`.
* Current practice status: completed the Create Policy section and understood how `aws:RequestedRegion` is used to restrict the permission scope.

### 4. Create Limited IAM User

* The lab guides creating the `ec2-admin` IAM user, attaching `AmazonEC2FullAccess`, and applying the `ec2-admin-restrict-region` permission boundary.
* This section was reviewed only because some AWS Console items were missing or different from the screenshots/instructions in the lab guide, so I could not continue following the steps exactly.

### 5. Check Limited IAM User

* The planned verification step signs in as `ec2-admin`, opens EC2 in Singapore `ap-southeast-1`, and confirms the user can access EC2 normally.
* Then the test switches to Sydney `ap-southeast-2` to confirm EC2 access is blocked by the permission boundary.
* This section was not completed directly, but I reviewed it to understand that the permission boundary still limits permissions even when the user has a broader identity-based policy.

### 6. Clean up resources

* After the lab, the `ec2-admin` IAM user and `ec2-admin-restrict-region` policy should be deleted.
* Cleanup was not performed because the user creation and verification steps were not implemented directly.

---

## Lab 33 Content

Lab 33 focuses on **encrypting data at rest with AWS KMS**, storing data in **Amazon S3**, recording activity with **AWS CloudTrail**, and querying logs with **Amazon Athena**.

* **1. Introduction**: Reviewed how KMS, S3, CloudTrail, and Athena work together for data security and auditing.
* **2. Preparation steps**: Created policy/role, group, and user for the lab permissions.
* **3. Create Key Management Service**: Created a KMS key for data encryption.
* **4. Create Amazon S3**: Created an S3 bucket, enabled KMS encryption, and uploaded test data.
* **5. Create AWS CloudTrail and Amazon Athena**: Created a trail for activity logs and used Athena to query log data in S3.
* **6. Test and share encrypted data on S3**: Tested access to encrypted files and observed how KMS permissions affect data access.
* **7. Resource cleanup**: Clean up S3 bucket, KMS key, CloudTrail, Athena output, and IAM resources after the lab.

---

## Lab 44 Content

Lab 44 focuses on **IAM Role & Condition**, showing how an IAM user can assume a role and how trust policy conditions can restrict access by IP address or time window.

* **1. IAM introduction**: Reviewed IAM, requests to AWS services, request authentication, and the assume role process.
* **2. Create IAM Group**: Create `ec2-rds-admin-group` with EC2/RDS administration permissions.
* **3. Create IAM User**: Create users such as `EC2-admin-user`, `RDS-admin-user`, `Group-user`, and `No-permission-user`, then verify each user's access.
* **4. Configure Role Condition**: Create `lab44-RoleFullAccess`, configure switch role, and add conditions to restrict access by IP/time.
* **5. Resource cleanup**: Delete the role, IAM users, and user group after finishing the lab.

**Reason for research only**: The lab requires multiple IAM users, EC2/RDS admin permissions, and an `AdministratorAccess` role; the verification section may also create EC2/RDS resources. I studied the flow instead of implementing it directly to avoid overly broad permissions, IAM misconfiguration risk, and unnecessary resources.

---

## Lab 48 Content

Lab 48 focuses on **granting applications access to AWS services with IAM Role**, comparing direct access key usage with attaching an IAM Role to EC2 so an application can upload files to S3 more safely.

* **1. Preparation**: Create an EC2 instance and S3 bucket for the upload application.
* **2. Use access key**: Create an IAM user, access key/secret access key, and use them in a Python application to upload a file to S3.
* **3. IAM Role on EC2**: Create an IAM Role, attach it to EC2, and let the application access S3 through temporary credentials instead of hardcoded keys.
* **4. Resource cleanup**: Delete the S3 bucket, EC2 instance, IAM user, and IAM role after completing the lab.

**Reason for research only**: The lab requires EC2, S3 bucket, IAM user, access key, and IAM Role. I studied it instead of implementing it directly to avoid unnecessary resources, avoid managing access keys, and reduce credential exposure risk during testing.

---

## Module 06-01 Content

The **Database Concepts review** video belongs to AWS First Cloud Journey and reviews database fundamentals before learning Amazon RDS, Aurora, ElastiCache, and Redshift.

* **Database, Primary Key, Foreign Key**: Reviewed structured/semi-structured data storage, unique row identification, and table relationships.
* **Index and Partitioning**: Learned how indexes speed up reads with write/storage tradeoffs, and how partitioning improves queries on large tables.
* **Log and Buffer**: Understood how logs support recovery/synchronization and how buffers improve access speed through memory.
* **RDBMS and NoSQL**: Compared SQL table-based systems with flexible-schema NoSQL models such as key-value, document, wide-column, and graph.
* **OLTP and OLAP**: Distinguished transaction-oriented systems from analytical/data warehouse workloads.

---

## Module 06-03 Content

The **Redshift - ElastiCache** video introduces two important AWS managed services in Module 06: **Amazon Redshift** for large-scale data analytics and **Amazon ElastiCache** for caching to optimize application performance.

### 1. Amazon Redshift

* **Overview**: Amazon Redshift is an AWS managed data warehouse service for Big Data and complex OLAP queries. It is based on PostgreSQL concepts, but is optimized for analytical workloads rather than OLTP transactions.
* **MPP architecture**: Redshift uses Massively Parallel Processing. The Leader Node receives queries, coordinates execution plans, and aggregates results, while Compute Nodes process and store distributed data in parallel.
* **Columnar storage**: Data is stored by column instead of by row. This is efficient for analytical queries because the system can read only the required columns, reducing scan volume and speeding up aggregations.
* **SQL and connectivity**: Redshift supports SQL and common JDBC/ODBC drivers, making it compatible with SQL clients and BI tools.
* **Cost and performance optimization**: Transient/cloned clusters can be used to increase processing capacity during high-demand periods. Redshift Spectrum also allows querying data directly from Amazon S3 without loading all data into the cluster, reducing storage cost and expanding analytics scope.

### 2. Amazon ElastiCache

* **Overview**: Amazon ElastiCache is an AWS managed caching service that supports Redis and Memcached engines for low-latency, in-memory data access.
* **Application architecture role**: ElastiCache is usually placed between the application layer and the database layer. Applications read frequently accessed data from cache first and query the database only on cache misses, reducing database load.
* **Performance**: Because data is stored in memory, cache helps speed up common read/write operations, especially for repeated data such as sessions, profiles, configuration, query results, or dashboard data.
* **Node management**: ElastiCache helps detect and replace failed nodes, reducing the infrastructure operations required compared with self-managed cache clusters.
* **Caching logic**: The service provides the cache infrastructure, but developers still decide what to cache, TTL values, when to invalidate cache entries, and how to handle cache misses. This is critical to avoid stale data or ineffective caching.

### 3. Next Study Direction

* Review SQL fundamentals to better understand querying in RDS, Redshift, and data warehouse systems.
* Learn more about Amazon RDS, Database Migration Service (DMS), and Schema Conversion Tool (SCT) to understand database operations and migration on AWS.
* Use books such as **Database Internals** and **The Data Warehouse Toolkit** as deeper references for storage engines, query processing, and data warehouse design.

---

## Knowledge & Skills Acquired

* Understood how IAM policy conditions can limit permissions by Region and Resource Tags.
* Learned how to split EC2 permissions into smaller policies by action group: read, tag creation, instance creation, and instance management.
* Recognized that Resource Tags can be used not only for organization, but also as access-control conditions.
* Understood the role of IAM Role and trust relationship in allowing an IAM user to assume limited EC2 administration permissions.
* Learned how IAM Permission Boundary limits the maximum permissions of a user, even when the user has a broader identity-based policy.
* Understood the flow of encrypting S3 data with KMS, recording activity with CloudTrail, and querying logs with Athena.
* Learned how trust policy conditions can restrict assume role by IP address and time.
* Understood why EC2 IAM Role is safer than hardcoding access keys in an application.
* Strengthened database foundations before studying AWS Database services such as RDS, Aurora, ElastiCache, and Redshift.
* Understood Amazon Redshift's role in data warehouse, OLAP, and large-scale analytics workloads.
* Learned Redshift's MPP architecture with Leader Node, Compute Nodes, and parallel data processing.
* Compared row-based storage and columnar storage, and understood why columnar storage fits analytical queries.
* Understood how Redshift Spectrum supports querying data on Amazon S3 without loading all data into the cluster.
* Understood Amazon ElastiCache's role in Redis/Memcached caching to reduce database load and improve application latency.
* Recognized that caching logic is the developer's responsibility, including cache selection, TTL, and cache invalidation.

---

## Challenges & Solutions

* **Error while updating role policy**: The role policy/trust relationship update did not complete successfully, stopping the lab before switch role and policy verification.
* **Full IAM condition testing not completed**: Because the role policy was not updated correctly, test cases such as blocked Regions, invalid tags, and EC2 actions with `Team=Alpha` could not be verified.
* **AWS Console differs from the Lab 30 guide**: While practicing, some AWS Console items were missing or different from the lab screenshots, so I only completed the Create Policy section and reviewed the remaining flow conceptually.
* **Lab 44 not practiced directly**: The lab uses multiple IAM users, admin permissions, and may create EC2/RDS during verification, so I researched it to avoid permission and cost risks.
* **Lab 48 not practiced directly**: The lab requires EC2/S3 and access keys, so I researched it to avoid cost and credential risks.
* **Module 06-03 is mainly architecture theory**: Redshift and ElastiCache include new concepts such as MPP, columnar storage, cache invalidation, and cache misses, so I documented them by use case to avoid confusing data warehouses, transactional databases, and caches.
* **Next step**: Recheck the JSON policy, IAM user ARN, MFA condition in the trust policy, and the list of policies attached to the role before continuing the policy verification section.

---

## Lessons Learned

* With IAM conditions, a wrong key or invalid JSON policy format can prevent the role from working correctly.
* Splitting permissions into smaller policies makes EC2 access control easier to read and debug.
* Trust relationships should be checked carefully before switching roles, especially when MFA is required.
* Permission Boundary does not grant permissions by itself; it only sets the maximum permission boundary, while effective permissions still depend on both the identity-based policy and the boundary.
* When S3 data is encrypted with KMS, file access depends on both S3 permissions and KMS key permissions.
* When configuring assume role, trust relationship is as important as permission policy because it controls who can use a role and under which conditions.
* For applications running on EC2, IAM Role should be preferred for temporary credentials instead of storing long-term access keys in code or on the server.
* Before choosing an AWS database service, it is important to understand whether the workload is OLTP or OLAP and whether the data model fits RDBMS or NoSQL.
* Redshift is suitable for analytics and OLAP queries, and should not be treated as a transactional database replacement for RDS.
* Columnar storage makes analytical queries more efficient because only the required columns are read, especially for aggregation and filtering.
* ElastiCache can speed up systems, but it does not solve all performance problems automatically; its effectiveness depends heavily on the application's caching strategy.
* When using cache, it is important to think about the data lifecycle: what data is cached, how long it stays cached, when it is refreshed, and how cache misses are handled.

---

## Practice Screenshots

> Lab 28 is only partially completed and is currently blocked by the update role policy error, so this section only records the completed steps.

### Lab 28 – Managing EC2 access with Resource Tags through IAM

![Lab28 Create Admin group and add IAM users](/images/Worklog-week6/Lab28-Create%20Admin%20group%20and%20add%20IAM%20users.png)

![Lab28 Create policies](/images/Worklog-week6/Lab28-Create%20policies.png)

![Lab28 Create IAM Role with policies](/images/Worklog-week6/Lab28-Create%20an%20IAM%20Role%20with%20the%20policies%20that%20were%20just%20created..png)

### Lab 30 – IAM Permission Boundary

![Lab30 Create policy limited](/images/Worklog-week6/Lab30-Create%20policty%20limited.png)

### Lab 33 – Encrypt at rest with AWS KMS

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
