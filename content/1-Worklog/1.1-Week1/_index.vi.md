---
title: "Worklog Tuần 1"
date: 2026-04-20
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

## Mục tiêu tuần 1

* Làm quen với môi trường thực tập, cách học và cách ghi chép trong First Cloud Journey.
* Nắm các khái niệm nền tảng về Cloud Computing, AWS Global Infrastructure và Well-Architected Framework.
* Thực hành các phần cơ bản của AWS như IAM, MFA, VPC, EC2, RDS và AWS Budgets.
* Tạo thói quen dọn dẹp tài nguyên sau khi lab để tránh phát sinh chi phí.

---

## Công việc đã thực hiện

| Ngày | Công việc | Kết quả | Tài liệu | Ghi chú |
|---|---|---|---|---|
| 20/04/2026 | Làm quen chương trình, đọc tổng quan về Cloud Computing và AWS. | Hiểu sự khác nhau giữa Cloud và On-Premise, cách AWS tổ chức Region, Availability Zone và Edge Location. Bắt đầu ghi chú theo từng module để dễ xem lại. | [Cloud Journey](https://cloudjourney.awsstudygroup.com/) | Ngày đầu chủ yếu để bắt nhịp. |
| 21/04/2026 | Học Well-Architected Framework và các công cụ AWS cơ bản. | Nắm 6 trụ cột của Well-Architected Framework. Làm quen với AWS Management Console, CLI, SDK và cách mở support case khi cần hỗ trợ. | [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html) <br> [AWS Support Case Tutorial](https://www.youtube.com/watch?v=95quNuhvMT0) | Bắt đầu hiểu cách AWS nhìn một hệ thống tốt. |
| 22/04/2026 | Thiết lập bảo mật tài khoản AWS với MFA, IAM User và IAM Group. | Bật MFA cho tài khoản, tạo IAM user/group và thử xử lý một số lỗi xác thực cơ bản. Phần này giúp mình hiểu rõ hơn vì sao không nên dùng root account cho công việc hằng ngày. | [AWS Account Security Tutorial](https://www.youtube.com/watch?v=1dG5xutGbr4) <br> [IAM User and Group Tutorial](https://www.youtube.com/watch?v=b9pK1oG534Q) <br> [MFA Setup Tutorial](https://www.youtube.com/watch?v=69iKhwI7k2Y) | Hoàn thành phần bảo mật tài khoản. |
| 23/04/2026 | Thực hành lab tổng hợp với VPC, Security Group, EC2, RDS và AWS Budgets. | Tạo được hạ tầng cơ bản gồm mạng, máy chủ và database. Thiết lập cảnh báo chi tiêu bằng AWS Budgets để theo dõi chi phí trong quá trình học. | [AWS Budgets Lab](https://000007.awsstudygroup.com/vi/3-usage-budget/) | Phần lab giúp nối lý thuyết với thao tác thực tế. |
| 24/04/2026 | Thực hành kết nối database, dùng Kiro để hỗ trợ dọn tài nguyên và bắt đầu Module 02. | Kết nối và truy vấn database thành công. Sau lab, kiểm tra lại tài nguyên đã tạo để hạn chế bỏ sót EC2/RDS đang chạy. | [Cloud Journey](https://cloudjourney.awsstudygroup.com/) <br> [Module 02 Theory](https://www.youtube.com/watch?v=uAQCm4sm_1c) | Chuyển dần sang phần Networking. |

---

## Ghi chú trong tuần

Tuần đầu tiên là giai đoạn làm quen nên mình tập trung vào nền tảng nhiều hơn là đi sâu một dịch vụ cụ thể. Phần quan trọng nhất là hiểu cách AWS tổ chức tài nguyên và vì sao IAM/MFA phải được làm ngay từ đầu.

Các bài lab về VPC, EC2 và RDS giúp mình thấy rõ hơn luồng triển khai một ứng dụng đơn giản trên cloud. Trước đó các khái niệm như subnet, route table hay security group còn khá rời rạc; sau khi tự cấu hình thì dễ hình dung hơn nhiều.

---

## Khó khăn gặp phải

* AWS Console có nhiều dịch vụ và menu nên lúc đầu mất thời gian tìm đúng chỗ cần cấu hình.
* Một số khái niệm mạng như subnet, route table và security group dễ nhầm khi chỉ học lý thuyết.
* Khi làm lab có cảm giác lo bị phát sinh chi phí nếu quên tắt EC2, RDS hoặc các tài nguyên liên quan.
* Cần tự tạo thói quen ghi chú và cleanup sau mỗi buổi học, vì nếu để dồn lại sẽ khó nhớ tài nguyên nào đã tạo.

---

## Kiến thức rút ra

* AWS Console có rất nhiều dịch vụ, nên cần biết dùng search và ghi lại các dịch vụ hay dùng.
* IAM và MFA là phần nền tảng, không nên để đến cuối mới cấu hình.
* AWS Budgets nên được tạo sớm để tránh quên tài nguyên đang chạy.
* Khi làm lab, bước cleanup quan trọng ngang với bước tạo tài nguyên.
