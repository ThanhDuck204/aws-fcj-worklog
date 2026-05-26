---
title: "Week 6 Worklog"
date: 2026-05-25
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

## Week 6 Objectives

* Continue practicing AWS labs related to IAM, EC2, and conditional access control.
* Understand how IAM Policies, IAM Roles, and Resource Tags can limit EC2 permissions.
* Practice Lab 28: managing EC2 access with Resource Tags through IAM Services.
* Study Lab 30: limiting IAM user permissions with IAM Permission Boundary.
* Practice Lab 33: encrypting S3 data with AWS KMS and tracking activity with CloudTrail and Athena.

---

## Completed Work

| Date | Task | Result | Resources | Notes |
|---|---|---|---|---|
| 26/05/2026 | Practiced Lab 28 and studied Lab 30. | Lab 28 was about half completed; Lab 30 was completed up to Create Policy and the remaining flow was reviewed. | [Lab 28 - EC2 Service Access Management with Resource Tags through IAM Services](https://000028.awsstudygroup.com/) <br> [Lab 30 - IAM Permission Boundary](https://000030.awsstudygroup.com/vi/1-introduce/) | Lab 28 had an update role policy error; Lab 30 had some Console items missing/different from the guide. |
| 26/05/2026 | Practiced Lab 33: Encrypt at rest with AWS KMS. | Created IAM resources, KMS key, KMS-encrypted S3 bucket, CloudTrail, Athena, and tested encrypted data sharing. | [Lab 33 - Encrypt at rest with AWS KMS](https://000033.awsstudygroup.com/1-introduce/) | Completed the main steps. |

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

## Knowledge & Skills Acquired

* Understood how IAM policy conditions can limit permissions by Region and Resource Tags.
* Learned how to split EC2 permissions into smaller policies by action group: read, tag creation, instance creation, and instance management.
* Recognized that Resource Tags can be used not only for organization, but also as access-control conditions.
* Understood the role of IAM Role and trust relationship in allowing an IAM user to assume limited EC2 administration permissions.
* Learned how IAM Permission Boundary limits the maximum permissions of a user, even when the user has a broader identity-based policy.
* Understood the flow of encrypting S3 data with KMS, recording activity with CloudTrail, and querying logs with Athena.

---

## Challenges & Solutions

* **Error while updating role policy**: The role policy/trust relationship update did not complete successfully, stopping the lab before switch role and policy verification.
* **Full IAM condition testing not completed**: Because the role policy was not updated correctly, test cases such as blocked Regions, invalid tags, and EC2 actions with `Team=Alpha` could not be verified.
* **AWS Console differs from the Lab 30 guide**: While practicing, some AWS Console items were missing or different from the lab screenshots, so I only completed the Create Policy section and reviewed the remaining flow conceptually.
* **Next step**: Recheck the JSON policy, IAM user ARN, MFA condition in the trust policy, and the list of policies attached to the role before continuing the policy verification section.

---

## Lessons Learned

* With IAM conditions, a wrong key or invalid JSON policy format can prevent the role from working correctly.
* Splitting permissions into smaller policies makes EC2 access control easier to read and debug.
* Trust relationships should be checked carefully before switching roles, especially when MFA is required.
* Permission Boundary does not grant permissions by itself; it only sets the maximum permission boundary, while effective permissions still depend on both the identity-based policy and the boundary.
* When S3 data is encrypted with KMS, file access depends on both S3 permissions and KMS key permissions.

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
