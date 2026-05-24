---
title: "Worklog Tuần 4"
date: 2026-05-11
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

# Worklog Tuần 4

## Mục tiêu tuần 4

- Tiếp tục nghiên cứu Module 04 – Lưu trữ trên AWS
- Tìm hiểu Snow Family, Storage Gateway, Disaster Recovery và AWS Backup
- Nghiên cứu AWS Cost Explorer API, Billing API và IAM API để chuẩn bị cho định hướng AWS Management Dashboard

## Công việc đã hoàn thành

| Ngày | Công việc | Kết quả | Tài liệu | Ghi chú |
|---|---|---|---|---|
| 2 | - Học Module 04-04: Snow Family, AWS Storage Gateway, Disaster Recovery, AWS Backup | Hoàn thành nghiên cứu về hybrid storage, data transfer, backup và disaster recovery strategies | [Module 04-04 - Snow Family and Storage Gateway](https://www.youtube.com/watch?v=YXn8Q_Hpsu4&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=106) | Hoàn thành đúng lịch |
| 3 | - Nghiên cứu AWS Cost Explorer API, Billing API, kiến trúc dashboard quản lý AWS | Hiểu được cách lấy dữ liệu chi phí qua GetCostAndUsage, phân biệt Cost Explorer API và Billing API | [AWS Cost Management API](https://docs.aws.amazon.com/aws-cost-management/latest/APIReference/Welcome.html) | Hoàn thành nghiên cứu API |
| 4 | - Nghiên cứu IAM Management API, mô hình phân quyền, khả năng theo dõi tài nguyên AWS | Học cách liệt kê users, groups, policies qua IAM API, xây dựng kế hoạch cho module quản lý người dùng | [IAM API Reference](https://docs.aws.amazon.com/IAM/latest/APIReference/Welcome.html) | Hoàn thành nghiên cứu IAM |
| 5 | - Xem lại và nghiên cứu các công nghệ mà các anh chị đã chia sẻ trong Event 1: Proptimizer Extension, BMAD methodology, và xem cách tối ưu chi phí dịch vụ AWS | Nắm sâu về Proptimizer, BMAD, và các kỹ thuật tối ưu chi phí từ kiến thức được chia sẻ trong sự kiện | [Bài Thu Hoạch Event 1](/4-eventparticipated/4.1-event1/) | Xem lại nội dung sự kiện |
| 6 | - Xử lý ghi chú sự kiện, viết bài thu hoạch Event 1 về Prompt Engineering và BMAD | Hoàn thành bài thu hoạch event 1, áp dụng metodology vào workflow | [Bài Thu Hoạch Event 1](/4-eventparticipated/4.1-event1/) | Viết bài thu hoạch sau sự kiện |

## Kiến thức đã học

- **Snow Family**: Snowball, Snowball Edge, Snowmobile hỗ trợ di chuyển dữ liệu lớn khi băng thông Internet không đủ
- **AWS Storage Gateway**: Phân biệt File Gateway (NFS/SMB), Volume Gateway (iSCSI Block), Tape Gateway (iSCSI VTL) theo giao thức và workload phù hợp
- **Disaster Recovery**: Nắm được ý nghĩa RTO/RPO, so sánh các chiến lược: Backup & Restore, Pilot Light, Low Capacity Active-Active, Full Capacity Active-Active
- **AWS Backup**: Hiểu cách dùng Backup Plan, retention policy, backup vault quản lý sao lưu tập trung cho EC2, EBS, RDS, DynamoDB, EFS, Storage Gateway
- **AWS APIs**: Nghiên cứu Cost Explorer API (GetCostAndUsage), Billing API, IAM API để xây dựng dashboard
- **Kiến trúc dashboard**: Lập kế hoạch backend layer kết nối với AWS SDK/API, UI hiển thị chi phí, trạng thái tài nguyên, thông tin IAM
- **Prompt Engineering & BMAD**: Học cách tối ưu workflow phát triển qua Proptimizer Extension và phương pháp BMAD
- **Tối ưu chi phí AWS**: Áp dụng Free Tier, cấu hình AWS Budgets, chọn tài nguyên dựa trên nhu cầu thực tế

## Thành tựu

- Hoàn thành nghiên cứu toàn diện về Storage services, Backup và Disaster recovery trên AWS
- Xây dựng được kiến trúcต้น bản cho AWS Management Dashboard kết hợp nhiều API
- Áp dụng được kiến thức từ sự kiện cộng đồng để cải thiện quy trình development
- Hoàn thành tất cả công việc được lên kế hoạch cho tuần 4
- Viết bài thu hoạch chi tiết cho sự kiện cộng đồng tham gia

## Khó khăn & Giải pháp

- **Khó khãn**: Dễ nhầm lẫn giữa các chiến lược Disaster Recovery
  **Giải pháp**: Dùng RTO/RPO là tiêu chí chính để phân biệt từng mô hình

- **Khó khãn**: Chọn loại Storage Gateway phù hợp với workload cụ thể
  **Giải pháp**: Ghi nhớ theo giao thức: NFS/SMB cho File Gateway, iSCSI Block cho Volume Gateway, iSCSI VTL cho Tape Gateway

- **Khó khãn**: Xác định mức độ truy cập tối thiểu cần thiết cho dashboard
  **Giải pháp**: Đối chiếu IAM Actions với tài liệu AWS, ưu tiên quyền read-only tối thiểu

## Tài liệu tham khảo

- AWS Documentation: Snow Family and Storage Gateway
- AWS Cost Explorer API Reference
- AWS IAM API Reference
- Bài Thu Hoạch Event 1 về Prompt Engineering và BMAD
- Tài liệu tối ưu chi phí AWS từ cộng đồng
