---
title: "Worklog Tuần 2"
date: 2026-04-27
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

## Mục tiêu tuần 2

* Hoàn thành Module 02 – Networking & Security trên AWS.
* Nắm được các phương thức kết nối mạng lai (VPN, Direct Connect) và cân bằng tải (ELB).
* Thiết kế và triển khai kiến trúc mạng đa vùng với VPC Peering và Transit Gateway.

---

## Công việc đã thực hiện

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | Học lý thuyết Networking & Security – VPN, Direct Connect, ELB, kiến trúc VPC | 27/04/2026 | 27/04/2026 | https://000003.awsstudygroup.com/ |
| 3 | Thực hành VPC: Subnet, Route Table, Internet Gateway, Network ACL | 28/04/2026 | 28/04/2026 | https://000003.awsstudygroup.com/ |
| 4 | Thiết lập Hybrid DNS với Route 53, cấu hình Security Group, kết nối RDGW | 29/04/2026 | 29/04/2026 | https://000010.awsstudygroup.com/ |
| 5 | Thực hành VPC Peering, Network ACL, CloudFormation, EC2 | 30/04/2026 | 30/04/2026 | https://000019.awsstudygroup.com/ |
| 6 | Tìm hiểu & triển khai Transit Gateway, hoàn thành Module 02 | 02/05/2026 | 02/05/2026 | https://000020.awsstudygroup.com/ |

---

## Kiến thức & kỹ năng đạt được

### 1. Kiến trúc VPC chuyên sâu & Security

* **Nắm vững luồng traffic VPC**: Hiểu rõ cách traffic đi qua Route Table, Internet Gateway (Public Subnet) và NAT Gateway (Private Subnet) trong môi trường thực tế.
* **Đã nghiên cứu bảo mật nhiều lớp**: Phối hợp Security Group (Stateful, cấp instance) với Network ACL (Stateless, cấp subnet), phân biệt Default NACL (cho phép tất cả) và Custom NACL.
* **Đã tìm hiểu VPC Flow Logs**: Nắm cách giám sát log truy cập (ACCEPT/REJECT) để hỗ trợ debug và rà soát bảo mật.

### 2. Kết nối doanh nghiệp & DNS lai

* **Đã phân tích mô hình kết nối lai**: Phân biệt VPN Site-to-Site (chi phí thấp) và Direct Connect (ổn định, băng thông lớn) khi kết nối On-Premise với AWS.
* **Đã tìm hiểu ELB**: Hiểu cơ chế phân phối traffic của ALB (Layer 7) và NLB (Layer 4), cùng các tính năng Health Check và Sticky Session.
* **Đã nghiên cứu Route 53 Resolver**: Nắm cách Inbound/Outbound Endpoint đồng bộ phân giải DNS giữa Data Center vật lý và AWS Cloud.

### 3. Mở rộng mạng diện rộng

* **Nắm được VPC Peering**: Cấu hình kết nối 2 VPC qua mạng nội bộ AWS; nhận ra giới hạn không hỗ trợ transitive routing.
* **Đã phân tích Transit Gateway**: Xác định Transit Gateway như Cloud Router trung tâm (Hub & Spoke), đơn giản hóa quản lý khi kết nối nhiều VPC so với Peering mesh.
* **Đã tìm hiểu CloudFormation (IaC)**: Sử dụng template để triển khai hàng loạt VPC, Subnet, Route Table một cách nhanh chóng.

---

## Kết quả thực hành & Lab

* **Lab VPC đa tầng**: Triển khai VPC gồm 2 Public và 2 Private Subnet trên nhiều AZ; cấu hình Route Table và NAT Gateway; kiểm chứng ping thành công.
* **Lab Hybrid DNS & Transit Gateway**: Cấu hình Route 53 Resolver Endpoint và Forwarding Rule; dùng CloudFormation tạo 4 VPC; kết nối qua Transit Gateway và kiểm tra `nslookup` liên mạng thành công.

---

## Khó khăn gặp phải & Cách khắc phục

* **Lỗi Route Table trong lab Transit Gateway**: Quên khai báo route trả về khiến ping bị time-out liên tục.
  * *Cách khắc phục*: Rà soát lại luồng traffic và bổ sung route trỏ CIDR VPC đích về Transit Gateway Attachment.
* **Nhầm lẫn Stateless NACL**: Custom NACL block traffic vì chỉ mở port Inbound mà quên Outbound ephemeral ports.
  * *Cách khắc phục*: Hiểu rõ tính Stateless của NACL và mở dải port (1024–65535) cho chiều phản hồi Outbound.
* **Khái niệm Route 53 Resolver trừu tượng**: Forwarding Rule và Endpoint khó hình dung khi mới tiếp cận môi trường Hybrid.
  * *Cách khắc phục*: Nghiên cứu kỹ luồng phân giải DNS trong video lý thuyết trước khi cấu hình trực tiếp trên Console.

---

## Bài học rút ra

* Luôn đọc hiểu sơ đồ kiến trúc mạng trước khi triển khai — thiếu một route hay CIDR có thể âm thầm làm đứt kết nối toàn hệ thống.
* Trong mạng AWS, hiểu đường đi của gói tin (Instance → SG → NACL → Route Table → IGW/TGW) quan trọng hơn thuộc lòng định nghĩa dịch vụ.
* NAT Gateway tính phí theo dung lượng xử lý và thời gian chạy — cần dọn dẹp ngay sau khi hoàn thành lab.

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