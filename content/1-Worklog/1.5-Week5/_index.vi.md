---
title: "Worklog Tuần 5"
date: 2026-05-18
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

## Mục tiêu tuần 5

* Bắt đầu Module 05 về các dịch vụ bảo mật trên AWS.
* Hiểu Shared Responsibility Model, IAM, Cognito, Organizations, Identity Center, KMS và Security Hub.
* Nghiên cứu Lab 18 ở mức tài liệu do giới hạn Free Tier.
* Thực hành Lab 22 về tự động bật/tắt EC2 để tối ưu chi phí.
* Hoàn thành Lab 27 về quản lý tài nguyên bằng tag.

---

## Công việc đã thực hiện

| Ngày | Công việc | Kết quả | Tài liệu | Ghi chú |
|---|---|---|---|---|
| 18/05/2026 | Học Shared Responsibility Model, IAM và Cognito. | Hiểu ranh giới trách nhiệm giữa AWS và người dùng. Ôn lại IAM User, Group, Policy, Role và xem Cognito như một hướng xác thực cho ứng dụng. | [Module 05-01](https://www.youtube.com/watch?v=tsobAlSg19g&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=151) <br> [Module 05-02](https://www.youtube.com/watch?v=N_vlJGAqZxo&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=152) <br> [Module 05-03](https://www.youtube.com/watch?v=pZ2fgEFK3Vs&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=153) | Hoàn thành phần đầu của Module 05. |
| 19/05/2026 | Học Organizations, Identity Center, KMS, Security Hub và phần hands-on overview. | Nắm cách quản lý nhiều account, phân quyền tập trung và mã hóa bằng KMS. Security Hub được ghi nhận ở mức tổng quan vì cần cân nhắc chi phí khi bật trực tiếp. | [Module 05-04](https://www.youtube.com/watch?v=5oQY8Rogz9Y&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=154) <br> [Module 05-05](https://www.youtube.com/watch?v=NW1xrMkNMjU&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=155) <br> [Module 05-06](https://www.youtube.com/watch?v=GMihNQojhZc&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=156) <br> [Module 05-07](https://www.youtube.com/watch?v=clj2E0rNBEs&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=157) | Ghi chú kỹ phần quyền và mã hóa. |
| 20/05/2026 | Nghiên cứu Lab 18 về AWS Security Hub. | Đọc luồng lab, hiểu cách Security Hub tổng hợp finding, theo dõi security score và hỗ trợ kiểm tra trạng thái bảo mật trong account. | [Lab 18 - AWS Security Hub](https://000018.awsstudygroup.com/) | Chỉ đọc tài liệu, không bật trực tiếp để tránh phát sinh chi phí. |
| 21/05/2026 | Thực hành Lab 22: tối ưu chi phí EC2 bằng Lambda, EventBridge và Slack. | Tạo EC2 test, gắn tag để Lambda lọc đúng instance, viết automation start/stop theo lịch và kiểm tra thông báo qua Slack. | [Lab 22 - EC2 Cost Optimization](https://000022.awsstudygroup.com/vi/2-prerequiste/) | Hoàn thành phần automation chính. |
| 22/05/2026 | Nghỉ cá nhân. | Không có hoạt động học tập trong ngày. |  | Nghỉ. |
| 23/05/2026 | Hoàn thành Lab 27 về quản lý tài nguyên bằng tag. | Thực hành gắn tag cho EC2/EBS, lọc tài nguyên theo metadata và tạo Resource Group dựa trên tag. | [Lab 27 - Resource Tagging](https://000027.awsstudygroup.com/vi/) | Tagging rất hữu ích cho quản lý và automation. |

---

## Ghi chú trong tuần

Tuần này xoay quanh bảo mật và vận hành tài nguyên. Mình nhận ra IAM không chỉ là tạo user hoặc gán quyền, mà là nền tảng để các dịch vụ AWS phối hợp với nhau an toàn hơn.

Lab 22 khá thực tế vì bài toán bật/tắt EC2 theo lịch có thể áp dụng ngay để giảm chi phí học tập. Lab 27 cũng giúp mình thấy tag không chỉ để đặt tên tài nguyên, mà còn dùng được cho lọc, quản lý, phân quyền và automation.

---

## Khó khăn gặp phải

* Shared Responsibility Model dễ nhầm ở các dịch vụ managed service, vì trách nhiệm của AWS và người dùng thay đổi theo từng loại dịch vụ.
* Lab 18 không thực hành trực tiếp được do giới hạn Free Tier, nên chỉ có thể đọc luồng và ghi chú lại.
* Lab 22 cần phối hợp nhiều phần như EC2 tag, IAM Role, Lambda, EventBridge và Slack nên phải kiểm tra từng bước khi debug.
* Khi làm Lab 27, nếu đặt tag không thống nhất thì lọc tài nguyên và tạo Resource Group rất dễ sai.

---

## Kiến thức rút ra

* Shared Responsibility Model giúp biết phần nào AWS quản lý và phần nào mình phải tự cấu hình.
* Lambda kết hợp EventBridge phù hợp cho các tác vụ vận hành định kỳ.
* Tagging nên được chuẩn hóa từ đầu để dễ quản lý tài nguyên về sau.
* Security Hub hữu ích, nhưng cần cân nhắc chi phí và phạm vi trước khi bật trong tài khoản học tập.

---

## Hình ảnh thực hành

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
