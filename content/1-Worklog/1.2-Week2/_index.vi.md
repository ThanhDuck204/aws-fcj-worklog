---
title: "Worklog Tuần 2"
date: 2026-04-27
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

## Mục tiêu tuần 2

* Hoàn thành Module 02 về Networking & Security trên AWS.
* Hiểu rõ hơn cách traffic đi qua VPC, subnet, route table, Internet Gateway, Security Group và Network ACL.
* Tìm hiểu các mô hình kết nối như VPN, Direct Connect, VPC Peering và Transit Gateway.
* Thực hành các lab networking để quen với cách thiết kế mạng nhiều tầng.

---

## Công việc đã thực hiện

| Ngày | Công việc | Kết quả | Tài liệu | Ghi chú |
|---|---|---|---|---|
| 27/04/2026 | Học lý thuyết Networking & Security: VPC, VPN, Direct Connect và ELB. | Hiểu luồng traffic cơ bản trong VPC và vai trò của từng thành phần mạng. Phân biệt được ALB/NLB ở mức khái niệm và use case. | [VPC Workshop](https://000003.awsstudygroup.com/) | Cần nắm kỹ networking trước khi làm các lab sau. |
| 28/04/2026 | Thực hành tạo VPC, subnet, route table, Internet Gateway và Network ACL. | Triển khai được VPC cơ bản với public/private subnet. Khi tự cấu hình route table, mình hiểu rõ hơn vì sao instance trong private subnet không đi Internet trực tiếp. | [VPC Workshop](https://000003.awsstudygroup.com/) | Hoàn thành lab VPC cơ bản. |
| 29/04/2026 | Tìm hiểu Hybrid DNS với Route 53 Resolver và cấu hình Security Group. | Nắm được ý tưởng inbound/outbound endpoint và cách DNS có thể hoạt động giữa môi trường on-premise với AWS. Ôn lại khác biệt giữa Security Group và NACL. | [Hybrid DNS Workshop](https://000010.awsstudygroup.com/) | Phần DNS cần đọc chậm để không nhầm luồng phân giải. |
| 30/04/2026 | Thực hành VPC Peering, Network ACL, CloudFormation và EC2. | Tạo được kết nối VPC Peering và hiểu giới hạn không hỗ trợ transitive routing. Bắt đầu làm quen với CloudFormation để triển khai hạ tầng bằng template. | [VPC Peering Workshop](https://000019.awsstudygroup.com/) | CloudFormation giúp giảm thao tác lặp trên Console. |
| 01/05/2026 | Tìm hiểu Transit Gateway và hoàn thành Module 02. | Hiểu mô hình hub-and-spoke của Transit Gateway, phù hợp khi cần kết nối nhiều VPC. So sánh được khi nào dùng VPC Peering và khi nào nên dùng Transit Gateway. | [Transit Gateway Workshop](https://000020.awsstudygroup.com/) | Hoàn thành Module 02. |

---

## Ghi chú trong tuần

Tuần này tập trung nhiều vào networking nên khá dễ bị rối nếu chỉ đọc lý thuyết. Mình phải vẽ lại luồng traffic vài lần, đặc biệt ở các phần route table, NACL và Transit Gateway.

Điểm đáng chú ý là các lỗi mạng thường không nằm ở một chỗ duy nhất. Khi ping hoặc connect timeout, cần kiểm tra cả route đi, route về, Security Group, NACL và subnet đang đặt tài nguyên.

---

## Khó khăn gặp phải

* Luồng traffic trong VPC khó theo dõi khi có nhiều thành phần như route table, Internet Gateway, NACL và Security Group.
* NACL là stateless nên dễ quên mở chiều outbound hoặc ephemeral ports khi kiểm thử kết nối.
* Transit Gateway và VPC Peering có cách hoạt động khác nhau, ban đầu dễ nhầm phần routing giữa các VPC.
* Route 53 Resolver và Hybrid DNS cần đọc chậm vì luồng phân giải DNS không trực quan như các lab EC2/VPC cơ bản.

---

## Kiến thức rút ra

* Security Group là stateful, còn NACL là stateless nên cần chú ý cả inbound và outbound rule.
* VPC Peering phù hợp với kết nối đơn giản, nhưng không phù hợp nếu cần routing qua nhiều VPC.
* Transit Gateway dễ quản lý hơn khi số lượng VPC tăng lên.
* Khi debug networking, nên kiểm tra theo luồng từ nguồn đến đích thay vì chỉnh rule ngẫu nhiên.
