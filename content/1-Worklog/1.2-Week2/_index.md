---
title: "Week 2 Worklog"
date: 2026-04-27
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

## Week 2 Objectives

* Complete Module 02 – Networking & Security on AWS.
* Understand hybrid network connectivity methods (VPN, Direct Connect).
* Deeply grasp the mechanics of Elastic Load Balancing (ELB) and Route 53 Resolver.
* Design and deploy multi-region network architectures (VPC Peering, Transit Gateway).

---

## Tasks Carried Out

| Day | Task | Start Date | Completion Date | Reference Materials |
| --- | ---- | ---------- | --------------- | ------------------- |
| 2 | Studied Networking & Security, learned about VPN, Direct Connect, ELB, and VPC architecture. | 27/04/2026 | 27/04/2026 | https://000003.awsstudygroup.com/ |
| 3 | Practiced VPC: Subnet, Route Table, Internet Gateway, Network ACL. | 28/04/2026 | 28/04/2026 | https://000003.awsstudygroup.com/ |
| 4 | Set up Hybrid DNS with Route 53, configured Security Groups, connected to RDGW. | 29/04/2026 | 29/04/2026 | https://000010.awsstudygroup.com/ |
| 5 | Practiced VPC Peering, Network ACL, CloudFormation, EC2. | 30/04/2026 | 30/04/2026 | https://000019.awsstudygroup.com/ |
| 6 | Studied & deployed Transit Gateway, completed Module 02. | 02/05/2026 | 02/05/2026 | https://000020.awsstudygroup.com/ |

---

## Knowledge & Skills Gained

### 1. In-depth VPC Architecture & Security

* **Mastered VPC Network Architecture**: Thoroughly understood real-world traffic flows routing through Route Tables, Internet Gateways (for Public Subnets), and NAT Gateways (for Private Subnets).
* **Studied Multi-layered Security**: Coordinated Security Groups (instance-level control) with Network ACLs (subnet-level control), clearly distinguishing between Default NACLs (allow all) and Custom NACLs.
* **Researched Network Monitoring**: Learned to utilize VPC Flow Logs to monitor access logs (ACCEPT/REJECT), supporting robust debugging and security auditing.

### 2. Enterprise Network Connectivity Services

* **Analyzed Hybrid Connectivity Models**: Differentiated the practical applications of Site-to-Site VPN (cost-effective) and Direct Connect (stable, high-bandwidth) when integrating On-Premise environments with AWS.
* **Studied Load Distribution (ELB)**: Understood the traffic sharing mechanisms of ALB (Layer 7), NLB (Layer 4 high performance), and features such as Health Checks and Sticky Sessions.
* **Researched Hybrid DNS Systems**: Grasped the mechanics of AWS Route 53 Resolver (Inbound/Outbound Endpoints) to synchronize DNS resolution between physical Data Centers and the Cloud environment.

### 3. Scaling Wide Area Networks

* **Understood Basic VPC Connectivity**: Learned to configure VPC Peering to link two VPCs across the internal AWS network, acknowledging its limitation of lacking transitive routing support.
* **Analyzed AWS Transit Gateway**: Identified the Transit Gateway as a central Cloud Router (Hub & Spoke), simplifying management when connecting dozens of VPCs compared to complex Peering meshes.
* **Explored Infrastructure as Code (IaC)**: Familiarized with CloudFormation to rapidly deploy bulk resources (VPCs, Subnets, Route Tables) via pre-defined templates.

---

## Lab & Practical Experience

### 1. Multi-tier VPC Architecture Lab

* **Practiced**: Successfully deployed a comprehensive VPC environment encompassing 2 Public Subnets and 2 Private Subnets spanning multiple Availability Zones.
* **Configured**: Established precise Route Tables ensuring EC2 instances in Private Subnets can securely access the Internet via NAT Gateways while blocking unauthorized inbound access.
* **Achieved**: Validated configurations via successful ping tests, solidifying a robust network foundation suitable for real-world applications.

### 2. Hybrid DNS & Transit Gateway Lab

* **Practiced**: Configured Outbound/Inbound Endpoints for Route 53 Resolver and established DNS query routing rules bridging On-Premise and AWS environments.
* **Configured**: Leveraged CloudFormation to rapidly spin up 4 VPCs, subsequently configuring a Transit Gateway and associated Route Tables to interconnect the entire network system.
* **Achieved**: Successfully executed cross-network `nslookup` commands and ensured seamless ping connectivity between EC2 instances across disparate VPCs via the Transit Gateway.

---

## Difficulties Encountered & Solutions

* **Connectivity Failures due to Route Table Misconfigurations**: During the Transit Gateway lab, omitting the return route declarations in the subnet Route Tables resulted in continuous ping timeouts.
  * *Solution*: Reassessed the traffic flow and explicitly added routes pointing the destination VPC CIDRs back to the Transit Gateway Attachments.
* **Stateful vs. Stateless Confusion**: Initial Custom NACL configurations failed because only the Inbound ports were opened, neglecting the Outbound return path (Ephemeral ports), which blocked traffic.
  * *Solution*: Deepened understanding of the Stateless nature of NACLs and adjusted rules to open the ephemeral port range (1024-65535) for outbound responses.
* **Complexity of Route 53 Resolver Flows**: The abstract concepts of Forwarding Rules and Endpoints were initially challenging to grasp when simulating a Hybrid environment.
  * *Solution*: Carefully studied the DNS resolution process provided in the theory video to clearly visualize the query logs and pathways before configuring them directly in the AWS Console.

---

## Lessons Learned

* **Understanding the Architecture is Mandatory Before Deployment**: For Networking services, carefully studying the overall network structure provided in the tutorials is non-negotiable. Without understanding the architecture, it is extremely easy to make critical errors in CIDR and Route Table configurations.
* **Master Flows over Memorizing Theory**: In AWS networking, understanding the exact path of a packet (Packet Flow) from Instance -> SG -> NACL -> Route Table -> IGW/TGW is far more valuable than memorizing service definitions.
* **Controlling NAT Gateway Cost Risks**: NAT Gateways incur costs based on processing volume and uptime. It is imperative to enforce strict cleanup routines immediately after completing labs involving this service.

---

## Lab Screenshots

![Create VPC](/images/Worklog-week2/create%20vpc.png)
![Create Subnet](/images/Worklog-week2/create%20subnet.png)
![Create Internet Gateway](/images/Worklog-week2/create%20Internet%20Gateway.png)
![Create Route Tables](/images/Worklog-week2/create%20route%20tables.png)
![Create Security Groups](/images/Worklog-week2/create%20security%20groups.png)
![Create SG Lab 19](/images/Worklog-week2/create%20SG%20lab19.png)
![Update Network ACL](/images/Worklog-week2/update%20Network%20ACL.png)
![VPC Peering](/images/Worklog-week2/create%20conecting%20Peering.png)
![Active Cross-Peer DNS](/images/Worklog-week2/active%20cross-peer%20dns.png)
![Generate Key Pair](/images/Worklog-week2/Generate%20Key%20Pair.png)
![Create Key Pair Lab 20](/images/Worklog-week2/create%20keypair%20lab%2020.png)
![Create CloudFormation Template](/images/Worklog-week2/create%20CloudFormation%20Template.png)
![Create EC2 Instance](/images/Worklog-week2/create%20EC2%20instance.png)
![Transit Gateway](/images/Worklog-week2/create%20Transit%20gatewyas.png)
