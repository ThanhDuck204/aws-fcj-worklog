---
title: "Worklog Tuần 3"
date: 2026-05-05
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

## Mục tiêu tuần 3

* Bắt đầu học Module 03 – Compute trên AWS.
* Nắm được các khái niệm cơ bản về Amazon EC2.
* Hiểu cách lựa chọn Instance Type, AMI, và cơ chế bảo mật cho EC2.

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

* **Nắm được khái niệm tổng quan**: Hiểu rõ kiến trúc của EC2, khả năng cấp phát tài nguyên linh hoạt và tốc độ khởi tạo nhanh chóng, phù hợp cho nhiều dạng workload khác nhau.
* **Đã tìm hiểu phần cứng & ảo hóa**: Biết cách lựa chọn cấu hình qua **EC2 Instance Type** (đáp ứng yêu cầu CPU, RAM, Network) và kiến trúc ảo hóa bằng Hypervisor.
* **Đã nghiên cứu Amazon Machine Image (AMI)**: Hiểu cơ chế provision hàng loạt máy ảo sử dụng AMI (bao gồm hệ điều hành, quyền sử dụng, và block device mapping).
* **Đã thực hành bảo mật truy cập**: Nắm rõ cách quản lý **Key Pair** (Public/Private Key) để xác thực qua SSH (đối với Linux) và lấy mật khẩu RDP (đối với Windows).
* **Đã phân tích mô hình định giá**: Phân biệt và lựa chọn chiến lược **EC2 Pricing Options** (On-demand, Reserved, Savings Plans, Spot) phù hợp để tối ưu chi phí hạ tầng.

### 2. Các công cụ hỗ trợ EC2 & Scaling

* **Nắm được cơ chế lưu trữ cục bộ**: Phân biệt giữa **Instance Store** (lưu trữ NVMe tốc độ cao, mất dữ liệu khi stop) và các giải pháp lưu trữ bền vững (EBS).
* **Đã nghiên cứu tự động hóa cấu hình**: Vận dụng **EC2 User Data** (script chạy 1 lần lúc khởi tạo) và truy xuất thông tin từ **EC2 Meta Data** để tự động thiết lập môi trường server.
* **Đã tìm hiểu dịch vụ EC2 Auto Scaling**: Hiểu nguyên lý tự động mở rộng (scale out) và thu hẹp (scale in) số lượng EC2 dựa theo policy để đảm bảo tính sẵn sàng cao (High Availability).

### 3. Dịch vụ mở rộng & Lưu trữ mạng

* **Đã tìm hiểu Amazon Lightsail**: Nắm bắt giải pháp máy chủ ảo tích hợp sẵn băng thông, tối ưu cho ứng dụng nhẹ hoặc môi trường dev/test.
* **Đã nghiên cứu hệ thống File System**: So sánh **Amazon EFS** (chỉ hỗ trợ Linux) và **Amazon FSx** (hỗ trợ Windows/Linux), hiểu cách mount đồng thời lên nhiều EC2 và cơ chế tính phí linh hoạt.
* **Nắm được giải pháp di chuyển ứng dụng**: Hiểu vai trò của **AWS Application Migration Service (MGN)** trong việc triển khai Disaster Recovery Site bằng cách nhân bản máy chủ từ Data Center lên AWS.

### 4. Dịch vụ lưu trữ Amazon S3 (Storage)

* **Nắm được khái niệm Object Storage**: Hiểu kiến trúc lưu trữ đối tượng, mô hình ghi một lần đọc nhiều lần (WORM), giới hạn kích thước (tối đa 5TB/object) và tính năng multipart upload.
* **Đã tìm hiểu bảo mật bằng Access Point**: Nhận thức được lợi ích của việc tạo **S3 Access Point** giúp phân quyền chi tiết cho nhiều ứng dụng mà không cần thiết lập một bucket policy quá phức tạp.
* **Đã phân tích S3 Storage Class**: Hiểu cách phân loại dữ liệu để tối ưu hóa chi phí lưu trữ thông qua Standard, Infrequent Access (IA), Intelligent Tiering, và Glacier/Deep Archive.
* **Đã nghiên cứu tự động hóa luân chuyển dữ liệu**: Hiểu cơ chế thiết lập **Object Life Cycle Management** để tự động di chuyển object giữa các storage class và **Cross-Region Replication (CRR)** để tăng cường dự phòng.

---

## Kết quả thực hành & Lab

### 1. Lab 13: Triển khai hạ tầng AWS Backup

* **Đã thực hành**: Tạo S3 Bucket, điều chỉnh policy truy cập và sử dụng template CloudFormation để tự động khởi tạo toàn bộ hạ tầng AWS Backup.
* **Đã cấu hình**: Hệ thống cảnh báo tự động qua dịch vụ **Amazon SNS**, cho phép gửi email thông báo trạng thái ngay khi tác vụ sao lưu hoặc khôi phục hoàn tất.
* **Kết quả đạt được**: Vận hành thành công quy trình tạo bản sao lưu on-demand, khôi phục dữ liệu tự động qua AWS Lambda, và theo dõi log thực thi cụ thể trên CloudWatch.

### 2. Nghiên cứu Workshop Storage Gateway & S3 Static Website

* **Đã nghiên cứu**: Kiến trúc Storage Gateway (tạo cache volume, cấu hình file share SMB) để hiểu sâu về mô hình lưu trữ lai (hybrid storage) giữa môi trường On-premise và AWS Cloud.
* **Đã tìm hiểu**: Quy trình host tĩnh một website trực tiếp trên **S3 Bucket**, phương thức thiết lập quyền truy cập công khai an toàn và sử dụng tính năng Versioning để bảo vệ dữ liệu khỏi việc vô tình bị xóa.
* **Nắm được**: Mô hình tăng tốc độ phân phối nội dung website toàn cầu thông qua **Amazon CloudFront**, kết hợp thiết lập Origin Access Control (OAC) để đảm bảo bảo mật.

---

## Khó khăn gặp phải & Cách khắc phục

* **Hạn chế của tài khoản Free Tier**: Trong quá trình nghiên cứu AWS Storage Gateway, không thể thực hành trọn vẹn việc khởi tạo Gateway do vượt giới hạn tài nguyên của Free Tier.
  * *Cách khắc phục*: Chủ yếu tập trung phân tích lý thuyết, đọc hiểu quy trình thiết lập (cấu hình SMB, cache volume) thông qua tài liệu chính thức và các workshop mẫu của AWS.
* **Thiết lập quyền cho S3 Static Website**: Ban đầu gặp bối rối khi phân biệt giữa cấu hình chặn truy cập cấp độ tài khoản/bucket (`Block public access`) và cấp quyền chi tiết qua `Bucket Policy`.
  * *Cách khắc phục*: Đã chủ động nghiên cứu document và cấu hình thành công việc tắt chặn truy cập công khai kết hợp với viết policy `s3:GetObject` cho `Principal: "*"`.
* **Phức tạp trong cấu hình AWS Backup**: Quá trình thiết lập luồng phục hồi tự động qua AWS Lambda đòi hỏi cấu hình quyền IAM Role rất chi tiết, dễ xảy ra lỗi "Access Denied".
  * *Cách khắc phục*: Đã rà soát lại kỹ lưỡng kịch bản CloudFormation và theo dõi tiến trình thực thi qua CloudWatch Logs để phát hiện và nắm được cách IAM Role được gán quyền tự động.

---

## Bài học rút ra

* Việc hiểu rõ bản chất của **Pricing Options** và **Storage Classes** là yếu tố cốt lõi để đạt được mục tiêu Tối ưu hóa chi phí (Cost Optimization) trong quá trình thiết kế hệ thống trên cloud.
* Trong thực tế vận hành, việc ứng dụng **Object Life Cycle Management** và **Auto Scaling** là bắt buộc để hệ thống tự động thích ứng với nhu cầu tải và tuổi thọ dữ liệu, qua đó giảm thiểu đáng kể các can thiệp thủ công.
* Khi triển khai hạ tầng tự động qua **CloudFormation**, cần phải đọc hiểu chi tiết template và luồng tạo IAM Role để duy trì tính an toàn và bảo mật cho hệ thống.

---

## Hình ảnh thực hành

![Create Backup Plan](/images/Worklog-week3/create%20backup%20plan%20(%20lab13).png)

![Create S3 Bucket 01](/images/Worklog-week3/create%20s3%20bucket%2001%20(lab13).png)

![Create S3 Bucket 02](/images/Worklog-week3/create%20s3%20bucket%2002%20(lab13).png)
