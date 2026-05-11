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
* Biết cách sử dụng AWS Console, CLI và làm quen với các dịch vụ chính.
* Nắm được các nguyên tắc bảo mật và quản lý chi phí khi sử dụng AWS.
* Hiểu định hướng thiết kế hệ thống thông qua Well-Architected Framework.

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

* **Nắm vững khái niệm**: Hiểu rõ lợi thế của mô hình Cloud Computing (on-demand, pay-as-you-go) so với On-Premise truyền thống về khả năng mở rộng và chi phí.
* **Đã tìm hiểu hạ tầng toàn cầu**: Nắm bắt cấu trúc Region, Availability Zone (AZ) và Edge Location để tối ưu hóa độ trễ và độ sẵn sàng cho người dùng.
* **Đã nghiên cứu tư duy thiết kế**: Nắm vững 6 trụ cột cốt lõi của AWS Well-Architected Framework để thiết kế hệ thống đảm bảo tính mở rộng, chịu lỗi và tiết kiệm chi phí.

### 2. Quản lý Tài khoản & Bảo mật (Security)

* **Nắm được nguyên tắc bảo mật cơ bản**: Hiểu và áp dụng mô hình Trách nhiệm chia sẻ (Shared Responsibility Model) và nguyên tắc Đặc quyền tối thiểu (Least Privilege).
* **Đã thực hành quản lý IAM**: Nắm rõ rủi ro của Root User, thực hiện bật MFA, tạo IAM User/Group và phân quyền quản trị an toàn thay vì dùng Root User cho công việc hằng ngày.

### 3. Tối ưu chi phí & Vận hành

* **Đã tìm hiểu quản lý chi phí**: Nhận diện các nguyên nhân phát sinh chi phí ngoài ý muốn và thực hành thiết lập cảnh báo với **AWS Budgets**.
* **Đã thực hành quy trình dọn dẹp**: Hình thành thói quen kiểm tra và cleanup toàn bộ tài nguyên không sử dụng sau các bài lab để tránh tính phí.
* **Nắm được quy trình Support**: Hiểu các gói AWS Support và biết cách mở Support Case khi gặp sự cố xác thực tài khoản.

### 4. Tổng quan Networking & Database

* **Đã nghiên cứu kiến trúc VPC cơ bản**: Bước đầu làm quen với các khái niệm Public/Private Subnet, Internet Gateway, NAT Gateway và Route Table.
* **Nắm được cơ chế bảo mật mạng**: Phân biệt cơ chế hoạt động của Security Group (Stateful) bảo vệ ở cấp độ instance và Network ACL (Stateless) bảo vệ ở cấp độ subnet.
* **Đã tìm hiểu dịch vụ RDS**: Nắm được cách cấp phát cơ sở dữ liệu trên cloud và phương thức để ứng dụng EC2 kết nối an toàn với RDS.

---

## Kết quả thực hành & Lab

### 1. Lab Cơ sở hạ tầng & Bảo mật cơ bản

* **Đã thực hành**: Thiết lập thành công tài khoản AWS, tạo cấu trúc IAM User/Group chuẩn, và cấu hình Virtual MFA cho Root User.
* **Đã cấu hình**: Thiết lập giới hạn chi tiêu và cảnh báo ngân sách thông qua tính năng AWS Budgets.
* **Kết quả đạt được**: Nắm vững luồng sử dụng AWS Console, sẵn sàng môi trường chuẩn bị cho các bài lab nâng cao hơn.

### 2. Lab Kiến trúc mạng & Database

* **Đã thực hành**: Triển khai một kiến trúc mạng thu nhỏ bao gồm VPC, chia Subnet, và thiết lập Security Group cho máy chủ web.
* **Đã cấu hình**: Cấp phát máy chủ EC2 cơ bản và một instance RDS, sau đó thực hiện kết nối ứng dụng với database thành công.
* **Kết quả đạt được**: Hoàn thành toàn bộ chuỗi 5 lab đầu tiên và sử dụng Kiro để kiểm tra, cleanup tự động hệ thống.

---

## Khó khăn gặp phải & Cách khắc phục

* **Làm quen với giao diện AWS Console**: Giao diện rộng với quá nhiều dịch vụ khiến việc tìm kiếm menu (như IAM hay Billing) mất nhiều thời gian ban đầu.
  * *Cách khắc phục*: Tập làm quen với thanh công cụ tìm kiếm toàn cục (Global Search) và ghim (pin) các dịch vụ thường dùng lên thanh điều hướng.
* **Kiểm soát chi phí phát sinh**: Khi thao tác tạo RDS và EC2, lo ngại việc bị trừ tiền thẻ Visa do quên tắt dịch vụ hoặc vượt mức Free Tier.
  * *Cách khắc phục*: Đã cấu hình AWS Budgets ngay từ ngày đầu và tập thói quen sử dụng công cụ Kiro để quét các tài nguyên "mồ côi" trước khi log out.

---

## Bài học rút ra

* **Bảo mật là ưu tiên số một**: Không bao giờ sử dụng Root User cho các tác vụ hằng ngày và luôn thiết lập MFA là nguyên tắc sống còn khi làm việc với AWS.
* **Kiểm soát chi phí tự động**: AWS tính tiền theo nguyên tắc pay-as-you-go, do đó việc dựa vào trí nhớ để tắt máy chủ là không an toàn; phải kết hợp AWS Budgets và quy trình dọn dẹp bài bản.
* **Nắm vững kiến trúc mạng**: Dù là dịch vụ EC2 hay RDS, mọi thứ đều phải chạy trên nền tảng VPC. Do đó, hiểu rõ luồng mạng (Subnet, Security Group) là tiền đề để làm việc với bất kỳ dịch vụ AWS nào khác.

---

## Hình ảnh thực hành

![Setup](/images/Worklog-weak1/setup-virtual-mfa-device.png)

![Create](/images/Worklog-weak1/create-admin-group-and-admin-user.png)

![Done Budget](/images/Worklog-weak1/done-all-lab-budget.png)

![Done All](/images/Worklog-weak1/done-all-5-labs-get-100-credit-aws.png)
