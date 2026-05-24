---
title: "Worklog Tuần 2"
date: 2026-04-27
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

# Worklog Tuần 2

## Mục tiêu tuần 2

- Hoàn thành Module 02 – Networking & Security trên AWS
- Nắm được các phương thức kết nối mạng lai (VPN, Direct Connect) và cân bằng tải (ELB)
- Thiết kế và triển khai kiến trúc mạng đa vùng với VPC Peering và Transit Gateway

## Công việc đã hoàn thành

| Ngày | Công việc | Kết quả | Tài liệu | Ghi chú |
|---|---|---|---|---|
| 2 | - Học lý thuyết Networking & Security: VPN, Direct Connect, ELB, kiến trúc VPC | Nắm vững luồng traffic VPC và các mô hình kết nối lai | [VPC Workshop](https://000003.awsstudygroup.com/) | Hoàn thành phần lý thuyết |
| 3 | - Thực hành VPC: Subnet, Route Table, Internet Gateway, Network ACL | Đã triển khai được VPC cơ bản với public/private subnet | [VPC Workshop](https://000003.awsstudygroup.com/) | Hoàn thành lab VPC cơ bản |
| 4 | - Thiết lập Hybrid DNS với Route 53<br>- Cấu hình Security Group<br>- Kết nối RDGW | Hoàn thành cấu hình DNS hybrid<br>Cải thiện bảo mật với SG | [Hybrid DNS Workshop](https://000010.awsstudygroup.com/) | Hoàn thành lab DNS & bảo mật |
| 5 | - Thực hành VPC Peering, Network ACL, CloudFormation, EC2 | Đã triển khai VPC peering<br>Triển khai infra qua CloudFormation | [VPC Peering Workshop](https://000019.awsstudygroup.com/) | Hoàn thành lab mở rộng mạng |
| 6 | - Tìm hiểu & triển khai Transit Gateway<br>- Hoàn thành Module 02 | Đã cấu hình Transit Gateway (Hub & Spoke)<br>Hoàn thành Module 02 | [Transit Gateway Workshop](https://000020.awsstudygroup.com/) | Hoàn thành lab và module 02 |

## Kiến thức đã học

- **Kiến trúc VPC & Bảo mật**: Luồng traffic qua Route Table, IGW, NAT; kết hợp SG (Stateful) và NACL (Stateless)
- **Kết nối doanh nghiệp**: Phân biệt VPN Site-to-Site (chi phí thấp) và Direct Connect (ổn định, bandwidth cao)
- **ELB**: Hiểu ALB (Layer 7) và NLB (Layer 4), Health Check, Sticky Session
- **Route 53 Resolver**: Inbound/Outbound Endpoint đồng bộ DNS giữa datacenter và AWS
- **Mở rộng mạng**: VPC Peering (giới hạn: không hỗ trợ transitive routing)
- **Transit Gateway**: Cloud Router trung tâm (Hub & Spoke), đơn giản quản lý nhiều VPC
- **CloudFormation**: Sử dụng template để triển khai nhanh VPC, Subnet, Route Table

## Thành tựu

- Hoàn thành Module 02 – Networking & Security trên AWS
- Triển khai thành công lab VPC đa tầng, Hybrid DNS & Transit Gateway
- Thiết kế kiến trúc mạng đa régions với VPC Peering và Transit Gateway
- Nắm được các mô hình kết nối lai và cân bằng tải trên AWS

## Khó khăn & Giải pháp

- **Khó khăn**: Quên khai báo route trả về trong lab Transit Gateway gây timeout ping
  **Giải pháp**: Rà soát lại luồng traffic, bổ sung route trỏ về VPC đích qua TGW Attachment

- **Khó khăn**: Custom NACL chặn traffic vì chỉ mở port Inbound, quên Outbound ephemeral ports
  **Giải pháp**: Hiểu tính Stateless của NACL, mở dải port 1024–65535 cho Outbound phản hồi

- **Khó khăn**: Forwarding Rule và Endpoint trong Route 53 Resolver khó hiểu khi mới tiếp cận
  **Giải pháp**: Nghiên cứu luồng phân giải DNS từ video lý thuyết trước khi cấu hình Console

## Tài liệu tham khảo

- AWS Study Group Module 02 learning materials
- AWS Documentation về VPC, Transit Gateway, Direct Connect
- AWS Well-Architected Framework đặc điểm reliability và performance efficiency
- AWS Blog về best practice kết nối lai
