---
title: "Worklog Tuần 3"
date: 2026-05-04
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

# Worklog Tuần 3

## Mục tiêu tuần 3

- Bắt đầu học Module 03 – Compute trên AWS
- Nắm được các khái niệm cốt lõi của Amazon EC2: Instance Type, AMI, Key Pair và mô hình định giá
- Tìm hiểu EC2 Scaling, lưu trữ mạng (EFS, FSx) và khởi đầu Module 04 – Storage

## Công việc đã hoàn thành

| Ngày | Công việc | Kết quả | Tài liệu | Ghi chú |
|---|---|---|---|---|
| 2 | - Tìm hiểu lý thuyết Module 03 – Compute: Amazon EC2, Instance Type, AMI, Key Pair | Nắm vững kiến trúc EC2, hiểu cách chọn Instance Type và AMI phù hợp |  | Hoàn thành mục tiêu lý thuyết EC2 cơ bản |
| 3 | - Tìm hiểu về EC2 User Data, EC2 Meta Data và EC2 Auto Scaling | Học cách tự động hóa cấu hình server và tự động scaling |  | Hoàn thành phần công cụ hỗ trợ EC2 |
| 4 | - Hoàn thành Lab 13: Triển khai hạ tầng AWS Backup, thiết lập SNS, kiểm thử sao lưu/khôi phục | Đã triển khai thành công AWS Backup infrastructure<br>Cấu hình SNS alerts và kiểm thử restore qua Lambda | [AWS Backup Lab](https://000013.awsstudygroup.com/) | Hoàn thành lab AWS Backup |
| 5 | - Tìm hiểu workshop AWS Storage Gateway<br>- Nghiên cứu S3 Static Website & CloudFront<br>- Hoàn thành Module 03 | Hiểu kiến trúc Storage Gateway (SMB, cache volume)<br>Host website tĩnh trên S3 với Versioning và OAC<br>Hoàn thành Module 03Compute | [Storage Gateway Workshop](https://000024.awsstudygroup.com/vi/3-cleanup/)<br>[S3 Static Website Workshop](https://000057.awsstudygroup.com/) | Hoành thành workshop lưu trữ vàModule 03 |
| 6 | - Bắt đầu học lý thuyết Module 04 – Lưu trữ trên AWS (Storage) | Bắt đầu với tổng quan dịch vụ lưu trữ và kiến thức nền tảng về S3 trước khi học sâu hơn ở tuần 4 | [Module 04-01 - Storage on AWS](https://www.youtube.com/watch?v=hsCfP0IxoaM&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=103)<br>[Module 04-02 - Amazon S3](https://www.youtube.com/watch?v=_yunukwcAwc&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=104) | Chuẩn bị cho tuần 4 |

## Kiến thức đã học

- **Amazon EC2**: Hiểu kiến trúc qua Instance Type (CPU, RAM, Network) và AMI (OS, permissions, block device mapping)
- **Bảo mật truy cập**: Quản lý Key Pair cho SSH (Linux) và RDP password decryption (Windows)
- **Mô hình định giá**: So sánh On-demand, Reserved, Savings Plans, Spot để chọn chiến lược phù hợp workload
- **Lưu trữ EC2**: Phân biệt Instance Store (ephemeral, NVMe) và EBS storage (persistent)
- **Tự động hóa**: Sử dụng EC2 User Data (launch scripts) và EC2 Meta Data để auto-bootstrap
- **Auto Scaling**: Hiểu politiques tự động scale-out/in để duy trì High Availability
- **File System Network**: So sánh Amazon EFS (Linux-only) và Amazon FSx (Windows/Linux) cho mount multi-EC2
- **AWS MGN**: Hiểu vai trò trong việc replication on-premise servers lên AWS cho Disaster Recovery
- **Amazon S3**: Nắm được WORM model, 5TB/object limit, multipart upload, S3 Access Points
- **S3 Storage Classes**: Tối ưu chi phí qua Standard, IA, Intelligent Tiering, Glacier/Deep Archive
- **Object Lifecycle Management**: Tự động chuyển tier giữa các lớp storage
- **Cross-Region Replication (CRR)**: Tăng dự phòng qua sao chép cross-region

## Thành tựu

- Hoàn thành Module 03 – Compute trên AWS
- Triển khai thành công lab 13 (AWS Backup infrastructure với SNS và Lambda restore)
- Hoàn thành workshop Storage Gateway & S3 (static website, CloudFront OAC)
- Đạt được kiến thức vững về EC2, scaling, storage và Disaster Recovery
- Chuẩn bị tốt để bắt đầu Module 04 – Storage vào tuần tới

## Khó khăn & Giải pháp

- **Khó khăn**: Không thể khởi tạo Storage Gateway thực tế do vượt hạn mức Free Tier
  **Giải pháp**: Tập trung phân tích lý thuyết và đọc tài liệu workshop chính thức của AWS

- **Khó khăn**: Bối rối giữa `Block public access` (tài khoản/bucket) và `Bucket Policy` chi tiết cho S3 static website
  **Giải pháp**: Nghiên cứu documentation và cấu hình thành công `s3:GetObject` cho `Principal: "*"` kết hợp tắt public access blocks

- **Khó khăn**: Lambda restore trong AWS Backup yêu cầu IAM Role chi tiết, hay gặp lỗi "Access Denied"
  **Giải pháp**: Rà soát CloudFormation template và theo dõi CloudWatch Logs để hiểu cách IAM Role được gán quyền tự động

## Tài liệu tham khảo

- AWS Study Group Module 03 learning materials
- AWS Documentation về EC2, Auto Scaling, EBS, EFS, FSx
- AWS Well-Architected Framework: performance efficiency và reliability pillars
- AWS Backup workshop materials
- AWS Storage Gateway official documentation
- Amazon S3 User Guide: storage classes, lifecycle management, replication
- AWS MGN (Migration Hub) documentation
