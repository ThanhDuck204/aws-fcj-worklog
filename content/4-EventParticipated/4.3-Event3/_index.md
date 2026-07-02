---
title: "Event 3"
date: 2026-06-20
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---
# Event Report: AWS Certification Quiz Competition

### Event Information

| Information | Details |
|---|---|
| **Event name** | AWS Certification Quiz Competition |
| **Date & Time** | 20/06/2026 |
| **Format** | Team competition (8 teams) |
| **Role** | Participant / Observer |
| **Hosted by** | AWS Study Group Community |

---

### Event Overview

The AWS Certification Quiz Competition was an exciting knowledge contest where 8 teams competed against each other to answer questions about AWS cloud services and cloud computing concepts in general. The event was led by anh Thinh, who provided valuable insights and additional knowledge about AWS concepts throughout the competition.

Unlike the usual workshops or sharing sessions, this was a real competition with a competitive edge, more intense but also a lot of fun.

---

### Competition Format

The competition took place over several rounds:

**Qualifying Round**
All 8 teams competed together. The questions in this round covered basic AWS knowledge. Teams showed very different levels of AWS knowledge -- some answered very quickly, while others needed more time to think.

**Semi-Finals**
The top-scoring teams advanced to the semi-finals. The questions were harder, more complex, and went deeper into specific AWS services. The difficulty level increased with each question.

**Finals (Postponed)**
Due to time constraints, the final round was postponed to the following week. This gave teams more time to prepare and study, while also building anticipation for the championship round.

One interesting observation was that teams often relied on intuition and educated guesses rather than pure technical knowledge. Everyone in the group jokingly called it "playing by spiritual vibes." This made the competition more fun and unpredictable.

---

### Main Topics Covered

**1. General AWS Knowledge**
Core AWS services and use cases, basic cloud computing knowledge, AWS best practices, and service integration.

**2. Real-world AWS Scenarios**
Questions included many practical scenarios testing problem-solving skills, understanding of AWS service capabilities, cost optimization strategies, and security best practices.

**3. Resource-based vs Identity-based Policies**
One of the most interesting and practical questions focused on prioritizing resource-based policies over identity-based policies.

Why use Resource-Based Policies:
- Cross-Account Access: Easily grant resource access from different AWS accounts
- Centralized Management: Permissions defined directly on the resource
- Simplified Management: No need to modify user/role policies
- Clear Control: Easy to see who can access the resource
- No Assume Role Needed: Direct access without assuming a role

Common use cases: S3 Bucket Policies, SQS Queue Policies, SNS Topic Policies, Lambda Function Policies, KMS Key Policies.

Example: When you want to allow multiple accounts or services to access an S3 bucket, it is more efficient to add a bucket policy (resource-based) allowing those accounts rather than modifying IAM policies (identity-based) in each account.

**Identity-Based vs Resource-Based Policies:**
- Identity-Based Policies: Attached to IAM user, group, or role. Controls what the identity can do. Must be managed in each account.
- Resource-Based Policies: Attached directly to the resource (S3, SQS, SNS...). Controls who can access the resource. Centrally managed on the resource.

Best Practice: Use resource-based policies when you need to grant cross-account access or want centralized permission management.

---

### Knowledge from anh Thinh

Throughout the competition, anh Thinh provided valuable additional information and context for each question:

- Technical knowledge: How concepts apply in production environments
- Common mistakes: Pitfalls to avoid when deploying AWS services
- Best practices: Industry-standard approaches for AWS architecture
- Cost considerations: How different solutions impact AWS costs
- Security aspects: Security implications of AWS configurations

The learning approach anh Thinh shared was very practical: understand instead of memorize, focus on concepts rather than rote learning, and always ask why instead of just remembering what to do.

---

### Key Takeaways

**1. AWS Permission Management**
Deep understanding of resource-based vs identity-based policies, knowing when to use each type, understanding cross-account access models, and security best practices for permissions.

**2. Real-world AWS Knowledge**
Real scenarios are more valuable than pure theory. Understanding service interactions is crucial, and cost along with security must be considered in every decision.

**3. Team Competition Skills**
Quick thinking under pressure, collaborative problem solving, strategic guessing when uncertain, and learning from other teams' approaches.

**4. Continuous Learning**
AWS is vast and constantly evolving. Community events provide valuable learning opportunities. Real questions reveal knowledge gaps that need improvement.

---

### Personal Reflections

**Technical Development**
This competition highlighted areas where I need to improve: permission architecture needs deeper understanding of IAM and resource policies, need to understand how different AWS services work together, and need to better translate theoretical knowledge into real situations.

**Competition Experience**
Competing under time pressure revealed my true understanding. Some questions I thought I knew but could not answer immediately when asked. The competition also exposed areas where I need to study more. Observing how other teams solved problems was also an effective way to learn.

**Community Value**
Anh Thinh's additional explanations were invaluable. Learning from other teams' answers and reasoning was also very useful. The event helped connect with other AWS enthusiasts and created more motivation to study AWS more deeply.

**About the "spiritual vibes"**
Teams often relied on educated guesses and intuition rather than pure knowledge. Sounds funny but actually proved several things: solid foundational understanding enables good intuition, AWS experience builds pattern recognition, and confidence in educated guesses is a valuable skill. On top of that, teamwork can compensate for individual knowledge gaps.

---

### Action Plan

**Immediate learning**
- Deep dive into IAM Policies, especially resource-based vs identity-based
- Learn cross-account access models and best practices
- Understand how different AWS services interact
- Practice with real AWS architecture problems

**Long-term development**
- Consider preparing for AWS certification
- Build projects using different AWS services
- Continue attending AWS Study Group events
- Share learned knowledge with team members

**Final preparation**
- Review difficult topics for next week's final round
- Focus on challenging subjects
- Practice with AWS certification questions
- Discuss strategies with the team

---

### Event Rating

(5/5)

The competition format made learning fun and engaging. Anh Thinh's knowledge provided great value beyond the quiz questions. The scenario-based questions were very relevant to real AWS usage. The "intuition-based" approach of the teams brought humor and reduced tension.

### Event Photos

![AWS Certification Quiz - Competition moment 1](/images/Event/event3_1.jpg)

![AWS Certification Quiz - Competition moment 2](/images/Event/event3_2.jpg)

![AWS Certification Quiz - Event overview](/images/Event/event3_3.jpg)
