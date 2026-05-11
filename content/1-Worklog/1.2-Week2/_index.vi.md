---
title: "Worklog Tuần 2"
date: 2026-04-27
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

## Mục tiêu tuần 2

* Hoàn thành Module 02 – Networking & Security trên AWS.
* Nắm được các phương thức kết nối mạng lai (VPN, Direct Connect).
* Hiểu sâu cơ chế hoạt động của Elastic Load Balancing (ELB) và Route 53 Resolver.
* Tự thiết kế và triển khai kiến trúc mạng đa vùng (VPC Peering, Transit Gateway).

---

## Công việc đã thực hiện

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | Học Networking & Security, tìm hiểu VPN, Direct Connect, ELB, kiến trúc VPC | 27/04/2026 | 27/04/2026 | https://000003.awsstudygroup.com/ |
| 3 | Thực hành VPC: Subnet, Route Table, Internet Gateway, Network ACL | 28/04/2026 | 28/04/2026 | https://000003.awsstudygroup.com/ |
| 4 | Thiết lập Hybrid DNS với Route 53, cấu hình Security Group, kết nối RDGW | 29/04/2026 | 29/04/2026 | https://000010.awsstudygroup.com/ |
| 5 | Thực hành VPC Peering, Network ACL, CloudFormation, EC2 | 30/04/2026 | 30/04/2026 | https://000019.awsstudygroup.com/ |
| 6 | Tìm hiểu & triển khai Transit Gateway, hoàn thành Module 02 | 02/05/2026 | 02/05/2026 | https://000020.awsstudygroup.com/ |

---

## Kiến thức & kỹ năng đạt được

### 1. Kiến trúc VPC chuyên sâu & Security

* **Nắm vững kiến trúc mạng VPC**: Hiểu rõ luồng traffic thực tế đi qua Route Table, Internet Gateway (cho Public Subnet) và NAT Gateway (cho Private Subnet).
* **Đã nghiên cứu bảo mật nhiều lớp**: Phối hợp giữa Security Group (kiểm soát tại instance) và Network ACL (kiểm soát tại subnet), phân biệt rõ Default NACL (cho phép tất cả) và Custom NACL.
* **Đã tìm hiểu giám sát mạng**: Nắm được cách sử dụng VPC Flow Logs để theo dõi log truy cập (ACCEPT/REJECT), phục vụ cho quá trình debug và rà soát bảo mật.

### 2. Các dịch vụ kết nối mạng doanh nghiệp

* **Đã phân tích mô hình kết nối lai**: Phân biệt tính ứng dụng của VPN Site-to-Site (chi phí thấp) và Direct Connect (ổn định, băng thông lớn) khi kết nối môi trường On-Premise với AWS.
* **Đã tìm hiểu phân phối tải (ELB)**: Hiểu cơ chế chia sẻ traffic của ALB (Layer 7), NLB (Layer 4 hiệu năng cao) và các tính năng như Health Check, Sticky Session.
* **Đã nghiên cứu hệ thống phân giải tên miền lai**: Nắm bắt cơ chế của AWS Route 53 Resolver (Inbound/Outbound Endpoint) để đồng bộ phân giải DNS giữa Data Center vật lý và môi trường Cloud.

### 3. Mở rộng hệ thống mạng diện rộng

* **Nắm được cơ chế kết nối VPC cơ bản**: Hiểu cách cấu hình VPC Peering để kết nối 2 VPC qua mạng nội bộ của AWS, và nhận thức được giới hạn không hỗ trợ kết nối bắc cầu (transitive peering).
* **Đã phân tích AWS Transit Gateway**: Nhận diện Transit Gateway như một Cloud Router trung tâm (Hub & Spoke), giúp đơn giản hóa quản lý khi cần kết nối hàng chục VPC thay vì tạo lưới Peering phức tạp.
* **Đã tìm hiểu tự động hóa hạ tầng (IaC)**: Làm quen với CloudFormation để triển khai hàng loạt tài nguyên (VPC, Subnet, Route Table) thông qua template định nghĩa sẵn.

---

## Kết quả thực hành & Lab

### 1. Lab Xây dựng kiến trúc VPC đa tầng

* **Đã thực hành**: Triển khai hoàn chỉnh môi trường VPC bao gồm 2 Public Subnet, 2 Private Subnet trải dài trên nhiều Availability Zone.
* **Đã cấu hình**: Thiết lập Route Table chính xác để EC2 trong Private Subnet có thể ra Internet thông qua NAT Gateway mà vẫn đảm bảo an toàn truy cập từ bên ngoài.
* **Kết quả đạt được**: Kiểm chứng ping thành công, hoàn thiện kiến trúc mạng nền tảng vững chắc cho các ứng dụng thực tế.

### 2. Lab Hybrid DNS & Transit Gateway

* **Đã thực hành**: Cấu hình Outbound/Inbound Endpoint cho Route 53 Resolver và tạo các Rule định tuyến truy vấn DNS giữa On-Premise và AWS.
* **Đã cấu hình**: Sử dụng CloudFormation để tạo nhanh 4 VPC, sau đó cấu hình Transit Gateway và Route Table để liên kết toàn bộ hệ thống mạng.
* **Kết quả đạt được**: Thực hiện thành công các lệnh `nslookup` liên mạng và đảm bảo các EC2 từ các VPC khác nhau có thể ping thông suốt qua Transit Gateway.

---

## Khó khăn gặp phải & Cách khắc phục

* **Lỗi cấu hình Route Table gây rớt kết nối**: Trong bài thực hành Transit Gateway, việc quên khai báo định tuyến (route) trả về trong Route Table của các subnet khiến ping bị time-out liên tục.
  * *Cách khắc phục*: Đã rà soát lại luồng dữ liệu (traffic flow) và bổ sung đầy đủ route trỏ CIDR của các VPC đích về Transit Gateway Attachment.
* **Nhầm lẫn cơ chế Stateful và Stateless**: Việc cấu hình Custom NACL ban đầu gặp lỗi do chỉ mở port chiều Inbound mà quên mở chiều Outbound (Ephemeral ports), khiến traffic bị chặn.
  * *Cách khắc phục*: Nhận thức sâu sắc tính chất Stateless của NACL và điều chỉnh mở dải port (1024-65535) cho chiều phản hồi (Outbound).
* **Bối rối với luồng hoạt động của Route 53 Resolver**: Khái niệm Forwarding Rule và Endpoint khá trừu tượng khi mô phỏng môi trường Hybrid.
  * *Cách khắc phục*: Đã nghiên cứu kỹ cách thức phân giải DNS trong video lý thuyết để hình dung rõ luồng truy vấn (Query log) trước khi cấu hình trực tiếp trên Console.

---

## Bài học rút ra

* **Hiểu rõ kiến trúc trước khi triển khai**: Đối với các dịch vụ Networking, việc thấu hiểu toàn cảnh cấu trúc mạng từ tài liệu hướng dẫn là bắt buộc. Nếu bỏ qua bước này, cực kỳ dễ sai sót trong cấu hình CIDR và Route Table.
* **Nắm bắt luồng thay vì thuộc lòng lý thuyết**: Trong mạng AWS, hiểu rõ đường đi của một gói tin (Packet flow) từ Instance -> SG -> NACL -> Route Table -> IGW/TGW quan trọng hơn việc thuộc lòng định nghĩa dịch vụ.
* **Kiểm soát rủi ro chi phí NAT Gateway**: NAT Gateway là dịch vụ tính phí theo dung lượng xử lý và thời gian chạy. Cần cực kỳ lưu ý việc dọn dẹp (cleanup) dịch vụ này ngay sau khi hoàn thành lab.

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