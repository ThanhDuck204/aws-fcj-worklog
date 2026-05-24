---
title: "Week 2 Worklog"
date: 2026-04-27
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

## Week 2 Objectives

* Complete Module 02 â€“ Networking & Security on AWS.
* Understand hybrid connectivity methods (VPN, Direct Connect) and load balancing (ELB).
* Design and deploy multi-region network architectures using VPC Peering and Transit Gateway.

---

## Tasks Carried Out

| Date | Task | Result | Resources | Notes |
|---|---|---|---|---|
| 27/04/2026 | Studied Networking & Security theory: VPN, Direct Connect, ELB, and VPC architecture. | Understood VPC traffic flow and hybrid connectivity models. | [VPC Workshop](https://000003.awsstudygroup.com/) | Completed networking theory. |
| 28/04/2026 | Practiced VPC: Subnet, Route Table, Internet Gateway, and Network ACL. | Deployed a basic VPC with public/private subnet structure. | [VPC Workshop](https://000003.awsstudygroup.com/) | Completed basic VPC lab. |
| 29/04/2026 | Set up Hybrid DNS with Route 53, configured Security Groups, and connected to RDGW. | Completed hybrid DNS configuration and improved security setup with Security Groups. | [Hybrid DNS Workshop](https://000010.awsstudygroup.com/) | Completed DNS and security lab. |
| 30/04/2026 | Practiced VPC Peering, Network ACL, CloudFormation, and EC2. | Deployed VPC peering and provisioned infrastructure through CloudFormation. | [VPC Peering Workshop](https://000019.awsstudygroup.com/) | Completed network expansion lab. |
| 02/05/2026 | Studied and deployed Transit Gateway, then completed Module 02. | Configured Transit Gateway with a hub-and-spoke model and completed Module 02. | [Transit Gateway Workshop](https://000020.awsstudygroup.com/) | Completed lab and module. |

---

## Knowledge & Skills Gained

### 1. VPC Architecture & Security

* **Mastered VPC Traffic Flow**: Understood how traffic routes through Route Tables, Internet Gateways (Public Subnets), and NAT Gateways (Private Subnets) in real-world deployments.
* **Studied Multi-layer Security**: Coordinated Security Groups (Stateful, instance-level) with Network ACLs (Stateless, subnet-level), distinguishing Default vs. Custom NACL behavior.
* **Researched VPC Flow Logs**: Learned to monitor ACCEPT/REJECT traffic logs for debugging and security auditing.

### 2. Enterprise Connectivity & DNS

* **Analyzed Hybrid Connectivity**: Differentiated Site-to-Site VPN (cost-effective) from Direct Connect (stable, high-bandwidth) for On-Premise-to-AWS integration.
* **Studied ELB**: Understood traffic distribution across ALB (Layer 7) and NLB (Layer 4), including Health Checks and Sticky Sessions.
* **Researched Route 53 Resolver**: Learned how Inbound/Outbound Endpoints synchronize DNS resolution between On-Premise Data Centers and AWS.

### 3. Wide-Area Network Scaling

* **Understood VPC Peering**: Configured peer connections between two VPCs over AWS's internal network; recognized the transitive routing limitation.
* **Analyzed Transit Gateway**: Identified it as a central Cloud Router (Hub & Spoke) that simplifies managing many VPC connections compared to a Peering mesh.
* **Explored CloudFormation (IaC)**: Used templates to rapidly provision VPCs, Subnets, and Route Tables in bulk.

---

## Lab & Practical Experience

* **Multi-tier VPC Lab**: Deployed a VPC with 2 Public and 2 Private Subnets across multiple AZs; configured Route Tables and NAT Gateways; validated with successful ping tests.
* **Hybrid DNS & Transit Gateway Lab**: Configured Route 53 Resolver Endpoints and Forwarding Rules; used CloudFormation to spin up 4 VPCs; connected them via Transit Gateway and verified cross-VPC `nslookup` and ping connectivity.

---

## Difficulties Encountered & Solutions

* **Route Table Misconfiguration in Transit Gateway Lab**: Omitting return routes in subnet Route Tables caused continuous ping timeouts.
  * *Solution*: Re-traced the traffic flow and added routes pointing destination VPC CIDRs back to the Transit Gateway Attachments.
* **Stateless NACL Confusion**: Custom NACL blocked traffic because only Inbound ports were opened, ignoring Outbound ephemeral ports.
  * *Solution*: Understood the Stateless nature of NACLs and opened the ephemeral port range (1024â€“65535) for outbound responses.
* **Route 53 Resolver Concepts**: Forwarding Rules and Endpoints were abstract when simulating a Hybrid environment.
  * *Solution*: Studied the DNS query flow from the theory video before configuring directly in the Console.

---

## Lessons Learned

* Always study the full network architecture diagram before starting â€“ missing a single CIDR or route entry can silently break connectivity.
* In AWS networking, understanding the exact packet path (Instance â†’ SG â†’ NACL â†’ Route Table â†’ IGW/TGW) is more valuable than memorizing service definitions.
* NAT Gateway incurs charges by data volume and uptime â€“ enforce strict cleanup routines immediately after finishing any lab that uses it.

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
