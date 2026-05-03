---
title: "Worklog Tuần 2"
date: 2026-04-27
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

## Mục tiêu tuần 2

* Tiếp tục học Module 02 – Networking & Security trên AWS  
* Nắm được các phương thức kết nối mạng (VPN, Direct Connect)  
* Hiểu cơ chế hoạt động của Elastic Load Balancing (ELB)  
* Làm quen với kiến trúc mạng cơ bản trong AWS VPC  

---

## Công việc đã thực hiện

| Thứ | Công việc | Ngày |
|-----|----------|------|
| 2 | Học Networking & Security, tìm hiểu VPN, Direct Connect, ELB, kiến trúc VPC | 27/04 |
| 3 | Thực hành VPC: Subnet, Route Table, Internet Gateway, Network ACL | 28/04 |
| 4 | Thiết lập Hybrid DNS với Route 53, cấu hình Security Group, kết nối RDGW | 29/04 |
| 5 | Thực hành VPC Peering, Network ACL, CloudFormation, EC2 | 30/04 |
| 6 | Tìm hiểu & triển khai Transit Gateway, hoàn thành Module 02 | 02/05 |

---

## Kiến thức & kỹ năng đạt được

### 1. Kết nối mạng trong AWS

* Hiểu cách kết nối giữa On-Premise và AWS  
* Nắm được:
  * VPN Site-to-Site (kết nối hệ thống nội bộ với VPC)
  * VPN Client-to-Site (người dùng truy cập từ xa)
* Phân biệt:
  * VPN: chi phí thấp, linh hoạt  
  * Direct Connect: ổn định, độ trễ thấp  

---

### 2. Elastic Load Balancing (ELB)

* Hiểu vai trò phân phối traffic, tăng tính sẵn sàng  
* Biết cơ chế Health Check và Sticky Session  
* Phân biệt các loại:
  * ALB (HTTP/HTTPS – Layer 7)  
  * NLB (TCP/TLS – hiệu năng cao)  
  * CLB (cũ)  
  * GWLB (bảo mật)  

---

### 3. Kiến trúc mạng AWS VPC

* Hiểu các thành phần chính:
  * Subnet (Public / Private)
  * Route Table
  * Internet Gateway (IGW)
  * NAT Gateway
  * Security Group (Stateful)  

* Triển khai mô hình VPC:
  * 2 Public Subnet  
  * 2 Private Subnet  
  * Hoạt động trên nhiều Availability Zone  

---

### 4. Network ACL (NACL)

* Hiểu cơ chế Stateless  
* Phải cấu hình cả Inbound & Outbound  
* Phân biệt:
  * Default NACL (Allow all)
  * Custom NACL (Deny all)

---

### 5. Hybrid DNS (Route 53 Resolver)

* Hiểu mô hình DNS kết hợp AWS và On-Premise  
* Thực hành:
  * Outbound Endpoint (AWS → On-prem)
  * Inbound Endpoint (On-prem → AWS)
  * Resolver Rules  

* Kiểm tra thành công bằng:
  * nslookup  
  * Resolve-DnsName  

---

### 6. Security & Monitoring

* Cấu hình Security Group:
  * Public / Private / VPC Endpoint  
* Hiểu mô hình bảo mật nhiều lớp:
  * Security Group + NACL  

* Sử dụng VPC Flow Logs:
  * Theo dõi traffic (ACCEPT / REJECT)
  * Phục vụ debug và bảo mật  

---

### 7. VPC Peering

* Kết nối 2 VPC qua private network  
* Không đi qua Internet  
* Hiểu hạn chế:
  * Không hỗ trợ transitive peering  

---

### 8. AWS Transit Gateway

* Hiểu vai trò cloud router trung tâm (hub)  
* So sánh:
  * VPC Peering → phức tạp khi nhiều VPC  
  * Transit Gateway → đơn giản, dễ mở rộng  

* Thực hành:
  * Kết nối 4 VPC qua Transit Gateway  
  * Cấu hình Route Table  
  * Kiểm tra kết nối thành công giữa các VPC  

---

### 9. CloudFormation

* Sử dụng template để tạo hạ tầng tự động  
* Triển khai nhanh:
  * VPC
  * Subnet
  * EC2
  * Transit Gateway  

---

## Kết quả thực hành

* Tạo hoàn chỉnh hệ thống VPC nhiều lớp  
* Thiết lập Hybrid DNS hoạt động thành công  
* Kết nối VPC bằng Peering và Transit Gateway  
* Kiểm tra:
  * Ping giữa các VPC thành công  
  * Kết nối Internet từ private subnet thành công  
* Hoàn thành hơn 10 bài lab thực tế  

---

## Khó khăn gặp phải

* Khó hiểu luồng hoạt động của Route 53 Resolver ban đầu  
* Nhầm lẫn giữa Security Group (Stateful) và NACL (Stateless)  
* Cấu hình Route Table sai dẫn đến không ping được giữa các VPC  
* NAT Gateway có thể phát sinh chi phí nếu không kiểm soát  

---

## Bài học rút ra

* Luôn vẽ sơ đồ mạng trước khi cấu hình  
* Hiểu flow traffic quan trọng hơn thuộc lòng lý thuyết  
* Kiểm tra kỹ Route Table khi có lỗi kết nối  
* Theo dõi chi phí khi sử dụng dịch vụ AWS  

---

## Hình ảnh thực hành

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