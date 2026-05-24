---
title: "Worklog Tuần 1"
date: 2026-04-20
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

# Worklog Tuần 1

## Mục tiêu tuần 1

- Làm quen với môi trường thực tập và các thành viên trong First Cloud Journey
- Hiểu được các khái niệm cơ bản về Cloud Computing và AWS
- Thực hành IAM, bảo mật tài khoản, quản lý chi phí và thiết lập mạng/database cơ bản

## Công việc đã hoàn thành

| Ngày | Công việc | Kết quả | Tài liệu | Ghi chú |
|---|---|---|---|---|
| 2 | - Tìm hiểu Cloud Computing, AWS Global Infrastructure<br>- Học Well-Architected Framework | Nắm vững khái niệm Cloud vs On-Premise<br>Hiểu 6 trụ cột Well-Architected Framework | [Cloud Journey](https://cloudjourney.awsstudygroup.com/)<br>[AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html) | Hoàn thành mục tiêu khai báo |
| 3 | - Khám phá AWS Management Console, CLI, SDK<br>- Học cách tạo AWS Support case | Thao tác thành công với các công cụ AWS cơ bản<br>D biết quy trình mở trường hợp hỗ trợ | [Cloud Journey](https://cloudjourney.awsstudygroup.com/)<br>[AWS Support Case Tutorial](https://www.youtube.com/watch?v=95quNuhvMT0) | Hoàn thành làm quen với công cụ AWS |
| 4 | - Thiết lập bảo mật tài khoản AWS (MFA, IAM User/Group)<br>- Xử lý lỗi xác thực | Hoàn thành cấu trúc IAM cơ bản<br>Có thể tự xử lý vấn đề xác thực thường gặp | [AWS Account Security Tutorial](https://www.youtube.com/watch?v=1dG5xutGbr4)<br>[IAM User and Group Tutorial](https://www.youtube.com/watch?v=b9pK1oG534Q)<br>[MFA Setup Tutorial](https://www.youtube.com/watch?v=69iKhwI7k2Y) | Hoàn thành lab bảo mật tài khoản |
| 5 | - Thực hành lab tổng hợp (VPC, SG, EC2, RDS)<br>- Sử dụng AWS Budgets | Hoàn thành 5 lab encontrados<br>Thiết lập cảnh báo chi tiêu thành công | [Cloud Journey](https://cloudjourney.awsstudygroup.com/)<br>[AWS Budgets Lab](https://000007.awsstudygroup.com/vi/3-usage-budget/) | Hoàn thành lab tích hợp mạng & database |
| 6 | - Thực hành Database (kết nối, truy vấn)<br>- Dùng công cụ Kiro<br>- Học lý thuyết Module 02 | Kết nối và truy vấn database thành công<br>Tự động dọn dẹp tài nguyên<br>Bắt đầu học Module 02 | [Cloud Journey](https://cloudjourney.awsstudygroup.com/)<br>[Module 02 Theory](https://www.youtube.com/watch?v=uAQCm4sm_1c) | Chuyển sang học lý thuyếtModule 02 |

## Kiến thức đã học

- **Cloud Computing & AWS**: Lợi thế on-demand, pay-as-you-go; cấu trúc Regions, AZs, Edge Locations
- **Well-Architected Framework**: 6 trụ cột: Operational Excellence, Security, Reliability, Performance Efficiency, Cost Optimization, Sustainability
- **IAM & Bảo mật**: MFA cho Root account, tạo IAM User/Group, áp dụng Least Privilege
- **Quản lý chi phí**: AWS Budgets để thiết lập cảnh báo chi tiêu
- **Networking**: VPC, Public/Private Subnets, Internet Gateway, NAT Gateway, Route Table
- **Network Security**: Security Groups (Stateful, instance-level) vs Network ACLs (Stateless, subnet-level)
- **Database**: RDS provisioning và kết nối từ EC2 an toàn
- **Công cụ**: Kiro để tự động dọn dẹp tài nguyên AWS

## Thành tựu

- Hoàn thành tất cả lab tiêu chuẩn tuần 1 (VPC, SG, EC2, RDS, IAM, Budgets)
- Thiết lập thành công môi trường thực tập AWS cơ bản
- Đạt được hiểu biết vững về nền tảng Cloud Computing và AWS
- Chuẩn bị tốt để chuyển sang Module 02

## Khó khăn & Giải pháp

- **Khó khăn**: Giao diện AWS Console quá banyak dịch vụ, tìm menu mất thời gian
  **Giải pháp**: Sử dụng thanh Global Search và ghim các dịch vụ thường dùng

- **Khó khăn**: Lo ngại bị tính phí ngoài ý tưởng vì quên tắt tài nguyên
  **Giải pháp**: Cấu hình AWS Budgets từ ngày đầu + dùng Kiro quét tài nguyên "mồ côi" trước logout

## Tài liệu tham khảo

- AWS Well-Architected Framework documentation
- AWS Study Group learning materials
- YouTube tutorials về IAM, VPC, EC2, RDS
- AWS Budgets documentation
- AWS CLI & SDK getting started guides
