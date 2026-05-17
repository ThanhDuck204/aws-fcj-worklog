---
title: "Worklog Tuần 1"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

## Mục tiêu tuần 1

* Làm quen với môi trường thực tập và các thành viên trong First Cloud Journey.
* Hiểu được các khái niệm cơ bản về Cloud Computing và AWS.
* Thực hành IAM, bảo mật tài khoản, quản lý chi phí và thiết lập mạng/database cơ bản.

---

## Công việc đã thực hiện

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | Tìm hiểu Cloud Computing, AWS Global Infrastructure và Well-Architected Framework. | 20/04/2026 | 20/04/2026 | https://cloudjourney.awsstudygroup.com/ <br> https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html |
| 3 | Tìm hiểu AWS Management Console, CLI, SDK và cách tạo AWS Support case. | 21/04/2026 | 21/04/2026 | https://cloudjourney.awsstudygroup.com/ <br> https://www.youtube.com/watch?v=95quNuhvMT0 |
| 4 | Thiết lập bảo mật tài khoản AWS (MFA, IAM User/Group) và xử lý lỗi xác thực. | 22/04/2026 | 22/04/2026 | https://www.youtube.com/watch?v=1dG5xutGbr4 <br> https://www.youtube.com/watch?v=b9pK1oG534Q <br> https://www.youtube.com/watch?v=69iKhwI7k2Y |
| 5 | Thực hành lab tổng hợp (VPC, SG, EC2, RDS) và sử dụng AWS Budgets. | 23/04/2026 | 23/04/2026 | https://cloudjourney.awsstudygroup.com/ <br> https://000007.awsstudygroup.com/vi/3-usage-budget/ |
| 6 | Thực hành Database (kết nối, truy vấn dữ liệu), dùng công cụ Kiro và học lý thuyết Module 02. | 24/04/2026 | 24/04/2026 | https://cloudjourney.awsstudygroup.com/ <br> https://www.youtube.com/watch?v=uAQCm4sm_1c |

---

## Kiến thức & kỹ năng đạt được

### 1. Nền tảng Cloud Computing & AWS

* **Nắm vững khái niệm**: Hiểu lợi thế của Cloud (on-demand, pay-as-you-go) so với On-Premise, và cấu trúc hạ tầng toàn cầu AWS (Region, AZ, Edge Location).
* **Đã nghiên cứu Well-Architected Framework**: Làm quen với 6 trụ cột thiết kế hệ thống đảm bảo tính mở rộng, chịu lỗi và tiết kiệm chi phí.

### 2. Bảo mật tài khoản & IAM

* **Đã thực hành cấu hình IAM**: Bật MFA cho Root account, tạo IAM User/Group và phân quyền tối thiểu (Least Privilege) để không dùng Root cho công việc hằng ngày.
* **Đã thiết lập kiểm soát chi phí**: Cấu hình cảnh báo chi tiêu với **AWS Budgets** và nắm được quy trình mở Support Case khi gặp sự cố xác thực.

### 3. Tổng quan Networking & Database

* **Đã nghiên cứu kiến trúc VPC cơ bản**: Nắm bắt Public/Private Subnet, Internet Gateway, NAT Gateway và Route Table.
* **Nắm được cơ chế bảo mật mạng**: Phân biệt Security Group (Stateful, cấp instance) và Network ACL (Stateless, cấp subnet).
* **Đã tìm hiểu dịch vụ RDS**: Nắm cách cấp phát database trên cloud và kết nối từ EC2 vào RDS an toàn.

---

## Kết quả thực hành & Lab

* **Lab Bảo mật**: Thiết lập cấu trúc IAM User/Group, bật Virtual MFA cho Root account và cấu hình cảnh báo AWS Budgets.
* **Lab Mạng & Database**: Triển khai VPC với Public/Private Subnet, cấp phát EC2 và RDS, hoàn thành toàn bộ 5 lab đầu tiên và dùng Kiro để cleanup tài nguyên.

---

## Khó khăn gặp phải & Cách khắc phục

* **Làm quen với AWS Console**: Giao diện rộng với quá nhiều dịch vụ khiến tìm kiếm menu mất thời gian ban đầu.
  * *Cách khắc phục*: Sử dụng thanh Global Search và ghim (pin) các dịch vụ thường dùng lên header.
* **Kiểm soát chi phí phát sinh**: Lo ngại bị tính phí ngoài ý muốn do quên tắt EC2/RDS sau khi thực hành.
  * *Cách khắc phục*: Cấu hình AWS Budgets từ ngày đầu và dùng Kiro để quét tài nguyên "mồ côi" trước mỗi lần log out.

---

## Bài học rút ra

* Không bao giờ dùng Root account cho công việc hằng ngày — MFA và IAM User với quyền hạn phù hợp là nguyên tắc bắt buộc khi làm việc với AWS.
* AWS tính phí theo mức sử dụng thực tế; phải kết hợp AWS Budgets và quy trình dọn dẹp tài nguyên để tránh phát sinh chi phí bất ngờ.
* VPC là nền tảng của mọi dịch vụ AWS — hiểu rõ Subnet, Security Group và Route Table là điều kiện tiên quyết trước khi triển khai bất kỳ dịch vụ nào khác.

---

## Hình ảnh thực hành

![Setup](/images/Worklog-weak1/setup-virtual-mfa-device.png)

![Create](/images/Worklog-weak1/create-admin-group-and-admin-user.png)

![Done Budget](/images/Worklog-weak1/done-all-lab-budget.png)

![Done All](/images/Worklog-weak1/done-all-5-labs-get-100-credit-aws.png)
