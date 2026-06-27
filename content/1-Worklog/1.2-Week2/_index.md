---
title: "Week 2 Worklog"
date: 2026-04-27
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

## Week 2 Objectives

* Complete Module 02 about Networking & Security on AWS.
* Understand traffic flow through VPC, subnet, route table, Internet Gateway, Security Group, and Network ACL.
* Learn about VPN, Direct Connect, VPC Peering, and Transit Gateway.
* Practice networking labs to become more comfortable with multi-tier network design.

---

## Work Completed

| Date | Task | Result | Resources | Notes |
|---|---|---|---|---|
| 27/04/2026 | Studied Networking & Security theory: VPC, VPN, Direct Connect, and ELB. | Understood basic VPC traffic flow and the role of each networking component. Also compared ALB and NLB at a high level. | [VPC Workshop](https://000003.awsstudygroup.com/) | Networking basics are required before later labs. |
| 28/04/2026 | Practiced creating VPC, subnet, route table, Internet Gateway, and Network ACL. | Built a basic VPC with public/private subnets. Configuring route tables manually made it clearer why private subnet instances cannot access the Internet directly. | [VPC Workshop](https://000003.awsstudygroup.com/) | Completed the basic VPC lab. |
| 29/04/2026 | Studied Hybrid DNS with Route 53 Resolver and reviewed Security Group configuration. | Understood inbound/outbound resolver endpoints and how DNS can work between on-premise environments and AWS. Reviewed Security Group vs NACL again. | [Hybrid DNS Workshop](https://000010.awsstudygroup.com/) | DNS required slower reading to avoid mixing up the resolution flow. |
| 30/04/2026 | Practiced VPC Peering, Network ACL, CloudFormation, and EC2. | Created a VPC Peering connection and understood the limitation that it does not support transitive routing. Started using CloudFormation templates to deploy infrastructure. | [VPC Peering Workshop](https://000019.awsstudygroup.com/) | CloudFormation reduces repeated Console work. |
| 01/05/2026 | Studied Transit Gateway and completed Module 02. | Understood the hub-and-spoke model of Transit Gateway and when it is more suitable than VPC Peering. | [Transit Gateway Workshop](https://000020.awsstudygroup.com/) | Completed Module 02. |

---

## Weekly Notes

This week focused heavily on networking, so it was easy to get lost by only reading theory. I had to redraw traffic flow several times, especially for route tables, NACLs, and Transit Gateway.

One important takeaway is that network issues are rarely caused by only one setting. When ping or connection tests time out, the route out, route back, Security Group, NACL, and subnet placement all need to be checked.

---

## Challenges Encountered

* VPC traffic flow was difficult to follow when route table, Internet Gateway, NACL, and Security Group were all involved.
* NACL is stateless, so it was easy to forget outbound or ephemeral ports during connectivity tests.
* Transit Gateway and VPC Peering have different routing behavior, which was confusing at first.
* Route 53 Resolver and Hybrid DNS were less visual than EC2/VPC labs, so the resolution flow needed careful review.

---

## Lessons Learned

* Security Group is stateful, while NACL is stateless, so both inbound and outbound rules matter.
* VPC Peering works for simple connections but is not ideal for routing across many VPCs.
* Transit Gateway is easier to manage as the number of VPCs grows.
* Networking issues should be debugged by following the traffic path from source to destination.
