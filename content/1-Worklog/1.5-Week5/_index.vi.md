---
title: "Worklog Tuần 5"
date: 2026-05-18
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

## Mục tiêu tuần 5

* Bắt đầu nghiên cứu Module 05 – Các dịch vụ bảo mật của AWS.
* Nắm được Shared Responsibility Model, IAM, Cognito, AWS Organizations, Identity Center và KMS.
* Nghiên cứu Lab 18 ở mức tài liệu do tài khoản Free Tier bị giới hạn, thực hành Lab 22 về tối ưu chi phí EC2 bằng Lambda và hoàn thành Lab 27 về quản lý tài nguyên bằng Tag.

---

## Công việc đã thực hiện

| Ngày | Công việc | Kết quả | Tài liệu | Ghi chú |
|---|---|---|---|---|
| 18/05/2026 | Tìm hiểu Module 05: Shared Responsibility Model, IAM và Cognito. | Hiểu ranh giới trách nhiệm bảo mật giữa AWS và khách hàng, cách quản lý truy cập bằng IAM và use case xác thực người dùng bằng Cognito. | [Module 05-01 - Shared Responsibility Model](https://www.youtube.com/watch?v=tsobAlSg19g&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=151) <br> [Module 05-02 - IAM](https://www.youtube.com/watch?v=N_vlJGAqZxo&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=152) <br> [Module 05-03 - Amazon Cognito](https://www.youtube.com/watch?v=pZ2fgEFK3Vs&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=153) | Hoàn thành nhóm lý thuyết đầu của Module 05. |
| 19/05/2026 | Tìm hiểu AWS Organizations, AWS Identity Center, AWS KMS, Security Hub và phần hands-on/additional research. | Nắm cách quản lý nhiều account, phân quyền tập trung, quản lý khóa mã hóa, khái niệm Security Hub và định hướng thực hành của Module 05. | [Module 05-04 - AWS Organizations](https://www.youtube.com/watch?v=5oQY8Rogz9Y&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=154) <br> [Module 05-05 - AWS Identity Center](https://www.youtube.com/watch?v=NW1xrMkNMjU&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=155) <br> [Module 05-06 - AWS KMS](https://www.youtube.com/watch?v=GMihNQojhZc&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=156) <br> [Module 05-07 - AWS Security Hub](https://www.youtube.com/watch?v=clj2E0rNBEs&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=157) <br> [Module 05-08 - Hands-on and Additional Research](https://www.youtube.com/watch?v=0SdpD2GPYz4&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=158) | Hoàn thành nhóm lý thuyết thứ hai của Module 05. |
| 20/05/2026 | Nghiên cứu Lab 18 ở mức tài liệu do giới hạn Free Tier. | Hiểu luồng Security Hub, cách tổng hợp finding và kiểm tra trạng thái bảo mật trong AWS Account. | [Lab 18 - AWS Security Hub](https://000018.awsstudygroup.com/) | Lab 18 chỉ đọc tài liệu. |
| 21/05/2026 | Tiếp tục thực hành Lab 22: tối ưu chi phí EC2 bằng Lambda, EventBridge và Slack notification. | Xây dựng và kiểm thử automation start/stop EC2 theo lịch, có thông báo Slack. | [Lab 22 - EC2 Cost Optimization](https://000022.awsstudygroup.com/vi/2-prerequiste/) | Hoàn thành phần thực hành automation EC2. |
| 22/05/2026 | Nghỉ vì lý do cá nhân. | Không thực hiện công việc kỹ thuật. |  | Nghỉ cá nhân. |
| 23/05/2026 | Hoàn thành Lab 27: quản lý tài nguyên bằng Tag. | Thực hành tổ chức tài nguyên AWS bằng tag, Resource Groups và AWS CLI. | [Lab 27 - Resource Tagging](https://000027.awsstudygroup.com/vi/) | Lab 27 đã hoàn thành. |

---

## Kiến thức & kỹ năng đạt được

### 1. Module 05 – AWS Security Services

* **Shared Responsibility Model**: Hiểu ranh giới trách nhiệm giữa AWS và khách hàng; AWS bảo vệ hạ tầng cloud, còn khách hàng chịu trách nhiệm cấu hình bảo mật tài nguyên, dữ liệu, IAM và ứng dụng.
* **IAM**: Nắm vai trò của IAM User, Group, Policy và Role; hiểu nguyên tắc Least Privilege, Explicit Deny và cách service role giúp dịch vụ AWS truy cập tài nguyên mà không cần hardcode credential.
* **Cognito & Organizations**: Tìm hiểu Cognito cho xác thực người dùng ứng dụng và AWS Organizations để quản lý nhiều account, OU, consolidated billing và Service Control Policies.
* **Identity Center & KMS**: Hiểu cách quản lý truy cập tập trung bằng Permission Set và cách KMS quản lý key để mã hóa dữ liệu at rest.

### 2. Lab 18 – AWS Security Hub

* Nghiên cứu luồng hoạt động của Lab 18 trong Module 05; chưa triển khai trực tiếp do giới hạn của tài khoản Free Tier nên chỉ dừng ở mức đọc hiểu và ghi nhận quy trình.
* Nắm cách Security Hub tổng hợp finding, theo dõi security score và hỗ trợ kiểm tra trạng thái tuân thủ trong AWS Account.

### 3. Lab 22 – Optimize EC2 Cost with Lambda

* Chuẩn bị hạ tầng gồm VPC, Security Group, EC2 instance test và workspace Slack nhận thông báo.
* Gắn tag `environment_auto=true` cho EC2 để Lambda lọc đúng instance cần tự động start/stop.
* Tạo IAM Role `dc-common-lambda-role` cho Lambda với quyền thao tác EC2 và ghi log CloudWatch.
* Kiểm thử Lambda auto stop thành công với `statusCode: 200` và nhận thông báo qua Slack.
* Tạo EventBridge rules `dc-common-lambda-auto-start` và `dc-common-lambda-auto-stop` để chạy tự động theo lịch.

### 4. Lab 27 – Quản lý tài nguyên bằng Tag

* Hoàn thành Lab 27 trong Module 05, tập trung vào cách dùng tag để tổ chức, nhận diện và quản lý tài nguyên AWS.
* Tạo 2 EC2 instance có gắn tag phục vụ kiểm thử, gồm các thông tin như `Name`, `Service`, `Owner`, `Environment` và `Operating System`.
* Thực hành thêm, chỉnh sửa và xóa tag bằng chức năng **Manage tags** trên EC2 Console.
* Lọc EC2 instance theo tag, ví dụ `Owner=NTDuc`, để kiểm tra khả năng tìm kiếm tài nguyên theo metadata.
* Sử dụng AWS CLI để tạo EBS volume kèm tag, giúp hiểu cách áp dụng tagging ngoài giao diện Console.
* Tạo Resource Group `MarketingBU` dựa trên tag `BusinessUnit=Marketing` để gom nhóm các tài nguyên liên quan.

---

## Khó khăn gặp phải & Cách khắc phục

* **Phân biệt trách nhiệm bảo mật giữa AWS và khách hàng**: Đối chiếu lại Shared Responsibility Model theo từng loại dịch vụ để tránh nhầm lẫn.
* **Giới hạn Free Tier khi tìm hiểu Lab 18**: Tập trung đọc hiểu tài liệu, ghi nhận luồng cấu hình và các bước kiểm tra thay vì bật Security Hub trực tiếp.
* **Kiểm soát tài nguyên trong Lab 22**: Dùng tag để giới hạn phạm vi automation và kiểm tra kết quả qua Lambda test event, EC2 state và Slack notification.
* **Quản lý nhiều tài nguyên trong Lab 27**: Chuẩn hóa key/value của tag để dễ lọc tài nguyên, tránh nhập sai tên tag khi tạo EC2, EBS volume và Resource Group.

---

## Bài học rút ra

* IAM là nền tảng quan trọng khi thiết kế bảo mật trên AWS; cần ưu tiên Least Privilege và hạn chế dùng root account.
* Lambda kết hợp EventBridge phù hợp cho các tác vụ vận hành định kỳ như tự động start/stop EC2 để tiết kiệm chi phí.
* Tagging giúp automation chạy đúng tài nguyên và giảm rủi ro ảnh hưởng nhầm instance khác.
* Tagging và Resource Groups giúp quản lý tài nguyên AWS có tổ chức hơn, đặc biệt khi cần lọc theo owner, môi trường, dự án hoặc business unit.

---

## Hình ảnh thực hành

> Lab 18 không có hình ảnh thực hành vì tài khoản Free Tier bị giới hạn, nên phần này chỉ ghi nhận hình ảnh của Lab 22 và Lab 27.

### Lab 22 – Optimize EC2 Cost with Lambda

![Lab22 Create IAM Role](/images/Worklog-week5/Lab22-%20Create%20IAM%20role%20for%20Lambda%20function.png)

![Lab22 Add Tag EC2](/images/Worklog-week5/Lab22-Add%20tag%20EC2%20instances.png)

![Lab22 Slack Notification Result](/images/Worklog-week5/Lab22-Check%20Lambda%20result%20auto%20and%20stop%202.0.png)

![Lab22 Auto Stop Result](/images/Worklog-week5/Lab22-Check%20Lambda%20result%20auto%20and%20stop.png)

![Lab22 Create EC2 Instance](/images/Worklog-week5/Lab22-Create%20Ec2%20instances%20for%20lambda.png)

![Lab22 EventBridge Auto Start Rule](/images/Worklog-week5/Lab22-Create%20rule%20auto%20start%20lamdba%20auto%20start%20.png)

![Lab22 EventBridge Auto Stop Rule](/images/Worklog-week5/Lab22-Create%20rule%20auto%20stop%20lamdba%20function.png)

![Lab22 Create Security Group](/images/Worklog-week5/Lab22-Create%20security%20groups%20for%20lambda.png)

![Lab22 Create VPC](/images/Worklog-week5/Lab22-Create%20Vpc%20lambda.png)

![Lab22 Create Slack Workspace](/images/Worklog-week5/Lab22-Create%20workspace%20Slack.png)

### Lab 27 – Quản lý tài nguyên bằng Tag

![Lab27 Create 2 EC2 with tag](/images/Worklog-week5/Lab27-Create%202%20EC2%20with%20tag.png)

![Lab27 Add or Delete tag with Manage tags](/images/Worklog-week5/Lab27-Add%20or%20Delete%20tag%20with%20Manage%20tags.png)

![Lab27 Filter resources by tag](/images/Worklog-week5/Lab27-Filter%20resouces%20by%20tag.png)

![Lab27 Using tag CLI](/images/Worklog-week5/Lab27-Using%20tag%20CLI.png)

![Lab27 Create Resource Group](/images/Worklog-week5/Lab27-Create%20Resource%20Group.png)
