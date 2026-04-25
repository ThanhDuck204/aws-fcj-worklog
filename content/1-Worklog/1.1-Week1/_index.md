---
title: "Week 1 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

### Week 1 Objectives:

* Get acquainted with the internship environment and the members of First Cloud Journey.
* Understand the basic concepts of Cloud Computing and AWS.
* Learn how to use the AWS Console and CLI, and become familiar with major AWS services.
* Grasp the principles of security and cost management when using AWS.
* Understand how AWS guides system design through the Well-Architected Framework.

---

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 | - Get acquainted with FCJ members and find a study group for discussion <br> - Read the rules and regulations of the internship unit <br> - Learn about Cloud Computing and AWS Global Infrastructure <br>&emsp; + Cloud Computing (on-demand, pay-as-you-go) <br>&emsp; + Benefits: cost optimization, flexibility, easy scalability <br>&emsp; + AWS consists of Regions, AZs, and Edge Locations <br> - Learn the overview of the Well-Architected Framework (6 pillars) <br> - Create an AWS Free Tier account and add a Visa card | 20/04/2026 | 20/04/2026 | https://cloudjourney.awsstudygroup.com/ <br> https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html |
| 3 | - Learn about the AWS Management Console <br>&emsp; + Do not use the Root User for daily tasks <br>&emsp; + Sign in with an IAM User <br> - Learn about AWS CLI and SDK <br>&emsp; + Configure Access Key and Secret Key <br>&emsp; + Understand how the CLI works <br> - Learn about AWS Support plans and how to create a support case | 21/04/2026 | 21/04/2026 | https://cloudjourney.awsstudygroup.com/ <br> https://www.youtube.com/watch?v=95quNuhvMT0 |
| 4 | - Set up AWS account security <br>&emsp; + Enable MFA for the Root User <br>&emsp; + Create an Admin Group and an Admin User <br>&emsp; + Assign the AdministratorAccess permission <br>&emsp; + Verify IAM sign-in <br> - Learn how to handle account authentication errors and contact support when needed | 22/04/2026 | 22/04/2026 | https://www.youtube.com/watch?v=1dG5xutGbr4 <br> https://www.youtube.com/watch?v=b9pK1oG534Q <br> https://www.youtube.com/watch?v=69iKhwI7k2Y |
| 5 | - Read documentation and practice comprehensive labs <br>&emsp; + VPC, Subnet, Route Table <br>&emsp; + Security Group <br>&emsp; + EC2 and IAM <br>&emsp; + RDS and AWS Budgets <br> - Practice the corresponding labs <br> - Perform full resource cleanup after completion | 23/04/2026 | 23/04/2026 | https://cloudjourney.awsstudygroup.com/ <br> https://000007.awsstudygroup.com/vi/3-usage-budget/ |
| 6 | - Learn how an application connects to a database in the cloud <br> - Practice the Database lab <br>&emsp; + Connect to the database <br>&emsp; + Insert data <br>&emsp; + Query data <br> - Install and explore Kiro <br> - **Study the theory of Module 02 - Networking & Security (VPC, Subnet, SG, NACL)** | 24/04/2026 | 24/04/2026 | https://cloudjourney.awsstudygroup.com/ <br> https://www.youtube.com/watch?v=uAQCm4sm_1c |

---

### Week 1 Achievements:

---

* **Built a solid foundation in Cloud Computing and AWS:**
  * Clearly understood the difference between the **On-Premise** model and **Cloud Computing**, especially the cloud's advantages in scalability and cost optimization.
  * Grasped the nature of the **on-demand** and **pay-as-you-go** model, and recognized that uncontrolled resource usage can lead to unexpected costs.
  * Understood AWS global infrastructure:
    * **Region**: the main deployment area
    * **Availability Zone (AZ)**: ensures high availability
    * **Edge Location**: helps reduce latency for content delivery
  * Took the first steps in choosing a suitable AWS Region for users in Vietnam, with Singapore as the preferred option for balancing latency and cost.

---

* **Understood system design thinking through the AWS Well-Architected Framework:**
  * Grasped the 6 core pillars and the role of each one in building systems:
    * Operational Excellence
    * Security
    * Reliability
    * Performance Efficiency
    * Cost Optimization
    * Sustainability
  * Understood that system design is not only about making things run, but also about ensuring:
    * Scalability
    * Fault tolerance
    * Cost-aware design
  * Recognized the importance of:
    * **Decoupling systems** instead of designing them as monoliths
    * Prioritizing **Managed Services** to reduce operational effort
    * Avoiding over-provisioning resources and using Auto Scaling when appropriate

---

* **Developed an AWS cost management mindset:**
  * Clearly recognized the risks of the pay-as-you-go model when resources are not properly controlled.
  * Identified common causes of unnecessary costs:
    * Forgetting to stop EC2 instances
    * Not deleting RDS instances or snapshots
    * Using resources outside the Free Tier limits
  * Practiced using **AWS Budgets** to:
    * Set cost alert thresholds
    * Monitor usage over time
  * Formed the habit of:
    * **Always cleaning up resources after completing a lab**
    * Reviewing active resources before ending a working session
  * Started using **Kiro** to support:
    * Creating a resource review checklist
    * Partially automating the cost-control review process

---

* **Grasped the basic security principles in AWS:**
  * Clearly understood the risk of using the **Root User** and why it should not be used for daily work.
  * Completed the following:
    * Enabled **MFA** for the Root User
    * Created an **IAM User** and an **IAM Group**
    * Assigned permissions through the Group instead of assigning them directly to the User
  * Understood and applied the **Principle of Least Privilege** when granting access.
  * Recognized that security in the cloud is based on the **Shared Responsibility Model** between AWS and the user.

---

* **Understood how AWS Support works and how to handle basic incidents:**
  * Learned the available AWS Support plans and the scope of each one.
  * Learned how to create a **Support Case** when needed.
  * Gained the ability to handle some basic issues related to authentication and access permissions.

---

* **Became familiar with AWS Console, CLI, and SDK:**
  * Used the AWS Management Console to create and manage resources.
  * Configured AWS CLI and understood how it interacts with AWS through APIs.
  * Ran several basic commands to work with resources.
  * Understood the role of the **AWS SDK** in integrating AWS services into real applications.

---

* **Completed the labs and understood the relationships between AWS services:**
  * Deployed a basic architecture including:
    * **VPC**: set up the network
    * **Subnet**: split public and private areas
    * **EC2**: deploy compute resources
    * **RDS**: manage the database
  * Understood the relationships between these components:
    * EC2 runs inside a Subnet that belongs to a VPC
    * Security Groups control access to instances
    * RDS connects to the application through the network layer
  * Practiced:
    * Connecting to the database
    * Inserting and querying data
  * After finishing the labs, performed full cleanup of all resources to avoid unnecessary charges.

---

* **Built a strong understanding of Module 02 - Networking & Security (highlight of the week):**
  * Understood how to build network architecture in AWS through VPC.
  * Clearly distinguished:
    * **Public Subnet**: can access the Internet
    * **Private Subnet**: cannot access the Internet directly
  * Grasped the role of key components:
    * **Internet Gateway (IGW)**: connects the VPC to the Internet
    * **NAT Gateway**: allows outbound Internet access from a Private Subnet
    * **Route Table**: controls traffic routing
    * **VPC Endpoint**: provides private connectivity to AWS services
  * Clearly understood the security mechanisms:
    * **Security Group (Stateful)**: controls traffic at the instance level
    * **NACL (Stateless)**: controls traffic at the subnet level
  * Analyzed traffic flow:
    * Public EC2 <-> Internet
    * Private EC2 -> NAT -> Internet
  * Became familiar with scaling and multi-network models:
    * **VPC Peering**
    * **Transit Gateway**
  * Recognized that network design is a critical foundation for ensuring:
    * System security
    * Scalability
    * Application stability

---

### Practice Images:

![Setup](/images/Worklog-weak1/setup-virtual-mfa-device.png)

![Create](/images/Worklog-weak1/create-admin-group-and-admin-user.png)

![Done Budget](/images/Worklog-weak1/done-all-lab-budget.png)

![Done All](/images/Worklog-weak1/done-all-5-labs-get-100-credit-aws.png)
