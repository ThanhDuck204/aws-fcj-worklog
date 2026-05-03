---
title: "Week 2 Worklog"
date: 2026-04-27
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

## Week 2 Objectives

* Continue studying Module 02 – Networking & Security on AWS  
* Understand network connectivity methods (VPN, Direct Connect)  
* Understand the mechanism of Elastic Load Balancing (ELB)  
* Get familiar with the basic network architecture in AWS VPC  

---

## Tasks Carried Out

| Day | Task | Date |
|-----|------|------|
| 2 | Studied Networking & Security, learned about VPN, Direct Connect, ELB, and VPC architecture | 27/04 |
| 3 | Practiced VPC: Subnet, Route Table, Internet Gateway, Network ACL | 28/04 |
| 4 | Set up Hybrid DNS with Route 53, configured Security Groups, connected to RDGW | 29/04 |
| 5 | Practiced VPC Peering, Network ACL, CloudFormation, EC2 | 30/04 |
| 6 | Studied & deployed Transit Gateway, completed Module 02 | 02/05 |

---

## Knowledge & Skills Gained

### 1. Network Connectivity in AWS

* Understood how to connect On-Premise environments to AWS  
* Learned about:
  * VPN Site-to-Site (connect on-premise systems to VPC)
  * VPN Client-to-Site (remote user access)
* Distinguished between:
  * VPN: low cost, flexible  
  * Direct Connect: stable, low latency  

---

### 2. Elastic Load Balancing (ELB)

* Understood its role in distributing traffic to increase system availability  
* Learned about Health Check mechanism and Sticky Session  
* Distinguished the types:
  * ALB (HTTP/HTTPS – Layer 7)  
  * NLB (TCP/TLS – high performance)  
  * CLB (legacy)  
  * GWLB (security appliances)  

---

### 3. AWS VPC Network Architecture

* Understood the main components:
  * Subnet (Public / Private)
  * Route Table
  * Internet Gateway (IGW)
  * NAT Gateway
  * Security Group (Stateful)  

* Deployed a VPC model with:
  * 2 Public Subnets  
  * 2 Private Subnets  
  * Distributed across multiple Availability Zones  

---

### 4. Network ACL (NACL)

* Understood Stateless mechanism  
* Must configure both Inbound & Outbound rules  
* Distinguished:
  * Default NACL (Allow all)
  * Custom NACL (Deny all)

---

### 5. Hybrid DNS (Route 53 Resolver)

* Understood the hybrid DNS model combining AWS and On-Premise  
* Practiced:
  * Outbound Endpoint (AWS → On-prem)
  * Inbound Endpoint (On-prem → AWS)
  * Resolver Rules  

* Verified successfully using:
  * nslookup  
  * Resolve-DnsName  

---

### 6. Security & Monitoring

* Configured Security Groups:
  * Public / Private / VPC Endpoint  
* Understood multi-layer security model:
  * Security Group + NACL  

* Used VPC Flow Logs:
  * Monitor traffic (ACCEPT / REJECT)
  * Useful for debugging and security auditing  

---

### 7. VPC Peering

* Connected 2 VPCs over the private AWS network  
* No traffic goes through the Internet  
* Understood limitations:
  * Does not support transitive peering  

---

### 8. AWS Transit Gateway

* Understood its role as a central cloud router (hub)  
* Compared:
  * VPC Peering → complex when managing many VPCs  
  * Transit Gateway → simple, easy to scale  

* Practiced:
  * Connected 4 VPCs through a single Transit Gateway  
  * Configured Route Tables  
  * Verified connectivity between all VPCs successfully  

---

### 9. CloudFormation

* Used templates to automatically provision infrastructure  
* Quickly deployed:
  * VPC
  * Subnet
  * EC2
  * Transit Gateway  

---

## Lab Results

* Successfully built a complete multi-tier VPC system  
* Set up Hybrid DNS and verified it working  
* Connected VPCs using both Peering and Transit Gateway  
* Verified:
  * Ping between VPCs succeeded  
  * Internet access from private subnets succeeded  
* Completed more than 10 hands-on labs  

---

## Challenges Encountered

* Difficult to understand the Route 53 Resolver traffic flow at first  
* Confused between Security Group (Stateful) and NACL (Stateless)  
* Misconfigured Route Table caused VPC-to-VPC ping to fail  
* NAT Gateway can incur costs if not monitored carefully  

---

## Lessons Learned

* Always draw a network diagram before configuring  
* Understanding traffic flow matters more than memorizing theory  
* Always check Route Table first when there is a connectivity issue  
* Monitor AWS costs when using managed services  

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
