---
title: "Worklog Tuần 3"
date: 2026-05-05
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

## Mục tiêu tuần 3

* Bắt đầu học Module 03 – Compute trên AWS.
* Nắm được các khái niệm cốt lõi của Amazon EC2: Instance Type, AMI, Key Pair và mô hình định giá.
* Tìm hiểu EC2 Scaling, lưu trữ mạng (EFS, FSx) và khởi đầu Module 04 – Storage.

---

## Công việc đã thực hiện

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | Tìm hiểu lý thuyết Module 03 – Compute: Amazon EC2, Instance Type, AMI, Key Pair | 05/05/2026 | 05/05/2026 | |
| 3 | Tìm hiểu về EC2 User Data, EC2 Meta Data và EC2 Auto Scaling | 06/05/2026 | 06/05/2026 | |
| 4 | Hoàn thành Lab 13: Thực hành triển khai hạ tầng AWS Backup, thiết lập SNS và kiểm thử sao lưu/khôi phục | 07/05/2026 | 07/05/2026 | https://000013.awsstudygroup.com/ |
| 5 | Tìm hiểu workshop AWS Storage Gateway và nghiên cứu S3 Static Website & CloudFront. Hoàn thành Module 03. | 08/05/2026 | 08/05/2026 | https://000024.awsstudygroup.com/vi/3-cleanup/ <br> https://000057.awsstudygroup.com/ |
| 6 | Bắt đầu học lý thuyết của Module 04 – Lưu trữ trên AWS (Storage) | 09/05/2026 | 09/05/2026 | |

---

## Kiến thức & kỹ năng đạt được

### 1. Dịch vụ Amazon EC2 (Compute)

* **Nắm được kiến trúc EC2**: Hiểu cơ chế cấp phát tài nguyên linh hoạt qua **EC2 Instance Type** (CPU, RAM, Network) và **AMI** (hệ điều hành, quyền sử dụng, block device mapping).
* **Đã thực hành bảo mật truy cập**: Quản lý **Key Pair** để xác thực qua SSH (Linux) và lấy mật khẩu RDP (Windows).
* **Đã phân tích mô hình định giá**: So sánh **EC2 Pricing Options** (On-demand, Reserved, Savings Plans, Spot) để chọn chiến lược phù hợp với từng loại workload.

### 2. Công cụ hỗ trợ EC2 & Scaling

* **Nắm được các loại lưu trữ**: Phân biệt **Instance Store** (NVMe tốc độ cao, mất khi stop) với lưu trữ bền vững EBS.
* **Đã nghiên cứu tự động hóa cấu hình**: Dùng **EC2 User Data** (script khởi tạo) và **EC2 Meta Data** để tự động thiết lập môi trường server.
* **Đã tìm hiểu EC2 Auto Scaling**: Hiểu nguyên lý tự động scale out/in theo policy để đảm bảo High Availability.

### 3. Dịch vụ mở rộng & Lưu trữ mạng

* **Đã nghiên cứu File System**: So sánh **Amazon EFS** (chỉ Linux) và **Amazon FSx** (Windows/Linux), hiểu cách mount đồng thời lên nhiều EC2.
* **Nắm được giải pháp migration**: Hiểu vai trò của **AWS MGN** trong việc nhân bản máy chủ On-premise lên AWS cho Disaster Recovery.

### 4. Dịch vụ lưu trữ Amazon S3

* **Nắm được Object Storage**: Hiểu mô hình WORM, giới hạn 5TB/object, multipart upload và **S3 Access Point** để phân quyền chi tiết.
* **Đã phân tích S3 Storage Class**: Nắm cách tối ưu chi phí qua Standard, IA, Intelligent Tiering và Glacier/Deep Archive.
* **Đã nghiên cứu tự động hóa vòng đời**: Hiểu **Object Lifecycle Management** để tự động chuyển tier và **Cross-Region Replication (CRR)** để tăng dự phòng.

---

## Kết quả thực hành & Lab

* **Lab 13 – AWS Backup**: Tạo S3 Bucket, triển khai template CloudFormation, cấu hình cảnh báo **Amazon SNS**, thực hiện thành công backup on-demand và khôi phục tự động qua AWS Lambda; theo dõi log qua CloudWatch.
* **Workshop Storage Gateway & S3**: Nghiên cứu kiến trúc Storage Gateway (SMB file share, cache volume); host website tĩnh trên S3 với Bucket Policy và Versioning; tìm hiểu **Amazon CloudFront** kết hợp Origin Access Control (OAC).

---

## Khó khăn gặp phải & Cách khắc phục

* **Giới hạn Free Tier với Storage Gateway**: Không thể khởi tạo Gateway thực tế do vượt hạn mức tài nguyên Free Tier.
  * *Cách khắc phục*: Tập trung phân tích lý thuyết và đọc hiểu quy trình thiết lập qua tài liệu chính thức và workshop mẫu của AWS.
* **Phân biệt quyền truy cập S3 Static Website**: Ban đầu bối rối giữa `Block public access` cấp tài khoản/bucket và `Bucket Policy` chi tiết.
  * *Cách khắc phục*: Nghiên cứu document và cấu hình thành công `s3:GetObject` cho `Principal: "*"` kết hợp tắt chặn truy cập công khai.
* **Phức tạp IAM trong AWS Backup**: Luồng phục hồi tự động qua Lambda yêu cầu IAM Role rất chi tiết, dễ gặp lỗi "Access Denied".
  * *Cách khắc phục*: Rà soát kịch bản CloudFormation và theo dõi log thực thi trên CloudWatch để hiểu cách IAM Role được gán quyền tự động.

---

## Bài học rút ra

* Hiểu đúng **Pricing Options** và **Storage Classes** là nền tảng để đạt Cost Optimization khi thiết kế hệ thống cloud.
* **Object Lifecycle Management** và **Auto Scaling** là công cụ vận hành thiết yếu — chúng loại bỏ thao tác thủ công và giúp hệ thống tự thích ứng.
* Khi dùng **CloudFormation**, luôn đọc kỹ template và luồng tạo IAM Role để tránh lỗi quyền âm thầm trong quá trình tự động hóa.

---

## Hình ảnh thực hành

![Create Backup Plan](/images/Worklog-week3/create%20backup%20plan%20(%20lab13).png)

![Create S3 Bucket 01](/images/Worklog-week3/create%20s3%20bucket%2001%20(lab13).png)

![Create S3 Bucket 02](/images/Worklog-week3/create%20s3%20bucket%2002%20(lab13).png)
