---
title: "Blog 2 - Running Traditional Web Applications on AWS Nitro Enclaves"
date: 2026-07-02
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---


# Running Traditional Web Applications on AWS Nitro Enclaves Without Modifying Source Code

While researching AWS Nitro Enclaves, I came across an interesting AWS article about bringing traditional web applications into an Enclave environment with almost no source code changes.

Since the original article was published on AWS China, I read, translated, and summarized the key points during my research. If there are any inaccuracies or omissions, I welcome your feedback.

---

## What is Nitro Enclaves?

Nitro Enclaves is an isolated computing environment created from an EC2 Instance through the AWS Nitro Hypervisor.

The main purpose of this service is to process highly sensitive data such as:
- Encryption Keys
- Financial data
- Medical data
- Personally identifiable information (PII)
- Tasks requiring high security

What makes Nitro Enclaves special is its almost complete isolation:
- No IP address
- No Internet connectivity
- No direct SSH access
- No persistent storage

All communication with the Enclave must go through VSOCK and the Parent EC2 Instance.

This is what gives Nitro Enclaves its high level of security, but it also makes migrating existing applications into an Enclave more challenging.

{{< figure src="/images/blog/blog2.1.jpg" title="Figure 1. AWS Nitro Enclaves architecture overview" >}}

---

## Challenges When Migrating Web Applications

Most web applications today operate based on TCP/IP through HTTP or HTTPS.

However, Nitro Enclaves does not support traditional network communication — it only uses VSOCK.

If deployed directly, developers would need to modify significant portions of the source code to convert all communication from TCP/IP to VSOCK.

For systems that are already running stably or for legacy applications, this is both time-consuming and risky, as it can easily affect the application's existing logic.

---

## AWS Proposed Solution

What I found interesting is that AWS proposes using SOCAT as a proxy layer to translate between HTTP and VSOCK.

The model consists of two proxies:

- **Proxy on Parent EC2:** receives HTTP connections from outside, converts them to VSOCK, and forwards them into the Enclave.
- **Proxy inside the Enclave:** receives VSOCK, converts it back to HTTP for the application to process.

The reverse direction works the same way.

If an application inside the Enclave needs to connect to the outside, the proxy converts traffic from HTTP to VSOCK so the Parent EC2 can handle network access on behalf of the Enclave.

With this approach, the application can still operate almost as if it were running on a regular Linux server, with little to no modification to its processing logic.

{{< figure src="/images/blog/blog2.2.jpg" title="Figure 2. SOCAT proxy architecture for Nitro Enclaves communication" >}}

---

## Deployment Process

According to the AWS article, the deployment process can be summarized as follows:

1. Install Nitro Enclaves CLI and Developer Tools.
2. Build the application as a Docker Image.
3. Convert the Docker Image to EIF format (Enclave Image File).
4. Launch the Enclave using Nitro CLI.
5. Deploy two SOCAT proxies on the Parent EC2 and inside the Enclave.
6. Access the application through the Parent Instance; all traffic is forwarded into the Enclave via VSOCK.

---

## What I Found Interesting

What I appreciate most about this approach is that AWS does not require developers to rewrite their entire application just because of a different communication mechanism.

Instead, adding a proxy layer allows leveraging existing applications, significantly reducing the cost and time needed to move a system into a more secure environment.

This is also a great example of combining open-source tools like SOCAT with AWS services to solve compatibility challenges while maintaining the isolation and security of Nitro Enclaves.

Of course, there are some considerations with this model, such as proxy performance, traffic monitoring, and overall architecture design to fit each system. Therefore, before applying this to a production environment, it should be carefully evaluated based on the specific needs of each project.

---

## Summary

In my opinion, Nitro Enclaves is a very interesting AWS service for those researching security or building systems that process sensitive data.

This article also demonstrates a practical approach: instead of modifying the entire application to adapt to Enclaves, we can use a protocol conversion layer to significantly reduce migration effort while still maintaining the security level that Nitro Enclaves provides.

This is my first time researching and synthesizing content on this topic. If there are any shortcomings in my translation or research, I welcome your feedback to help me improve.

---

## Evidence Link

This article was posted on the AWS Study Group VN Facebook group as evidence of the blog writing and translation activities:
- [Facebook Post - Running Traditional Web Applications on AWS Nitro Enclaves](https://www.facebook.com/groups/awsstudygroupfcj/?multi_permalinks=2198943464203947&notif_id=1782875552662961&notif_t=feedback_reaction_generic&ref=notif)

## References

- Reference Material (AWS China Blog): [Running Traditional Web Application Migration Practices in AWS Nitro Enclaves](https://aws.amazon.com/cn/blogs/china/running-traditional-web-application-migration-practices-in-aws-nitro-enclaves/)
