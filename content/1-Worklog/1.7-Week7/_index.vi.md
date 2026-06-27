---
title: "Worklog Tuần 7"
date: 2026-06-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

## Mục tiêu tuần 7

* Chốt phạm vi dự án nhóm AI Meeting Workforce Platform.
* Thiết kế kiến trúc tổng thể và khung xương ban đầu cho project.
* Xây dựng dữ liệu mock, mock service và layout theo vai trò để nhóm có thể phát triển song song.
* Kiểm tra dependencies và định hướng các dịch vụ AWS sẽ dùng cho MVP.
* Tiếp tục học Module 06 để đánh giá thêm các lựa chọn database.

---

## Công việc đã thực hiện

| Ngày | Công việc | Kết quả | Tài liệu | Ghi chú |
|---|---|---|---|---|
| 01/06/2026 | Họp nhóm chốt ý tưởng dự án và thiết kế kiến trúc ban đầu. | Thống nhất phạm vi AI Meeting Workforce Platform: upload transcript, AI tóm tắt cuộc họp, trích xuất task và dashboard theo vai trò Admin/Manager/Employee. Phác thảo kiến trúc dùng Next.js, Cognito, S3, Lambda, DynamoDB, API Gateway và CloudFront. | [Next.js Documentation](https://nextjs.org/docs) <br> [AWS Architecture Center](https://aws.amazon.com/architecture/) | Chốt hướng đi chính cho project. |
| 02/06/2026 | Tạo dữ liệu mock, mock AI service, auth mock và kiểm tra package. | Tạo dữ liệu departments, users, meetings, tasks và notifications. Bổ sung mock AI service để mô phỏng tóm tắt cuộc họp/trích xuất task, đồng thời kiểm tra dependencies để tránh dùng phiên bản có rủi ro bảo mật. | Không có | Chuẩn bị nền để frontend chạy độc lập trước khi backend sẵn sàng. |
| 03/06/2026 | Xây dựng layout, navigation theo role và routing chính. | Tạo AppShell, Sidebar, TopBar, stat cards, panels, status pills và các page chính cho Admin/Manager/Employee. Navigation được tách theo role để dễ mở rộng sau này. | Không có | Tập trung vào cấu trúc UI và luồng truy cập. |
| 04/06/2026 | Học tiếp Module 06 về RDS, Aurora, DynamoDB và DMS. | So sánh nhanh các dịch vụ database để xem dịch vụ nào phù hợp với dự án. DynamoDB vẫn là lựa chọn hợp lý cho MVP vì dữ liệu task/meeting có thể thiết kế theo hướng NoSQL. | [Cloud Journey](https://cloudjourney.awsstudygroup.com/) | Liên hệ kiến thức database với project nhóm. |
| 05/06/2026 | Nhận góp ý từ nhóm và chỉnh lại khung xương dự án. | Rà soát cách chia thư mục, mock data, service layer và các phần chuẩn bị tích hợp AWS. Một số điểm được ghi lại để chỉnh tiếp ở tuần sau, nhất là luồng xử lý dữ liệu cuộc họp. | Không có | Dành thời gian đồng bộ để tránh mỗi người làm một kiểu. |

---

## Ghi chú trong tuần

Đây là tuần chuyển từ học/lab cá nhân sang làm dự án nhóm rõ ràng hơn. Việc khó nhất không phải là viết code ngay, mà là thống nhất phạm vi đủ nhỏ để làm được trong giai đoạn MVP.

Nhóm chọn cách dựng mock data và mock service trước để frontend có thể chạy được sớm. Cách này giúp mọi người nhìn thấy luồng sản phẩm nhanh hơn, sau đó mới thay dần bằng API thật và tích hợp AWS.

---

## Khó khăn gặp phải

* Lúc chốt scope dự án, có nhiều ý tưởng muốn thêm nhưng cần giữ MVP đủ nhỏ để nhóm làm kịp.
* Thiết kế mock data phải vừa dễ dùng cho frontend, vừa không quá khác với schema dự kiến sau này.
* Routing theo nhiều role khiến cấu trúc page và navigation dễ bị lặp nếu không tách cấu hình rõ ràng.
* Nhóm cần thống nhất cách chia thư mục và service layer để tránh mỗi người triển khai theo một style khác nhau.

---

## Kiến thức rút ra

* Project nhóm cần thống nhất scope sớm, nếu không rất dễ thêm quá nhiều tính năng.
* Mock data nên được thiết kế gần với schema tương lai để tránh phải sửa nhiều.
* Navigation theo role nên được gom vào cấu hình chung để dễ bảo trì.
* Khi chọn database, cần nhìn vào pattern đọc/ghi của ứng dụng thay vì chọn theo thói quen.
