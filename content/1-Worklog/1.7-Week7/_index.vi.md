---
title: "Worklog Tuần 7"
date: 2026-06-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

## Mục tiêu tuần 7

* Họp nhóm để chốt phạm vi dự án và thiết kế kiến trúc tổng thể cho AI Meeting Workforce Platform.
* Thiết kế khung xương dự án với các dịch vụ AWS mà dự án sẽ sử dụng (IAM, S3, Lambda, DynamoDB, API Gateway, Cognito, CloudFront).
* Triển khai khung xương dự án với dữ liệu mock làm nền tảng cho phát triển theo phân quyền.
* Kiểm tra và cập nhật các thư viện lên phiên bản mới nhất để tránh lỗ hổng bảo mật.
* Tiếp tục hoàn thiện khung xương dự án dựa trên feedback của nhóm cho đến khi mọi người thấy cấu trúc phù hợp.
* Học nội dung còn lại của Module 06 (RDS, Aurora, DMS, DynamoDB) để xác định thêm dịch vụ AWS có thể tích hợp vào dự án.

---

## Công việc đã thực hiện

| Ngày | Công việc | Kết quả | Tài liệu | Ghi chú |
|---|---|---|---|---|
| 01/06/2026 | Họp nhóm chốt dự án và thiết kế khung xương với các dịch vụ AWS. | Thống nhất phạm vi AI Meeting Workforce Platform: upload transcript cuộc họp, AI tóm tắt, trích xuất task, dashboard theo vai trò (Admin/Manager/Employee). Thiết kế kiến trúc dùng Next.js frontend, với các dịch vụ AWS dự kiến: Cognito cho auth, S3 lưu transcript/file, Lambda xử lý AI, DynamoDB lưu dữ liệu, API Gateway cho REST endpoints, CloudFront cho CDN. Tạo cấu trúc Next.js project ban đầu với Pages Router. | [Next.js Documentation](https://nextjs.org/docs) <br> [AWS Architecture Center](https://aws.amazon.com/architecture/) | Hoàn thành khởi động dự án và thiết lập khung xương. |
| 02/06/2026 | Triển khai khung xương với dữ liệu mock; kiểm tra và cập nhật phiên bản thư viện. | Tạo tầng dữ liệu mock (`src/lib/mockData.js`) với departments, users, meetings, tasks và notifications. Xây dựng mock AI service (`src/lib/mockAI.js`) mô phỏng tóm tắt cuộc họp và trích xuất task. Thiết lập auth service mock (`src/lib/auth.js`) với localStorage-based session management. Chạy `npm audit` và cập nhật packages: nâng cấp `next` từ 13.5.11, `react`/`react-dom` giữ ở 18.2.0 với bản vá bảo mật, cập nhật `framer-motion` và `lucide-react`, đảm bảo `eslint-config-next` khớp với phiên bản Next.js. | Không có | Chủ yếu làm project nhóm, tập trung vào phần code và thống nhất cấu trúc nên không ghi link tài liệu riêng. |
| 03/06/2026 | Tiếp tục xây dựng khung xương: components layout, điều hướng theo vai trò, và routing. | Xây dựng `AppShell.jsx` làm layout chính với dark narrow sidebar, top bar và điều hướng theo role ADMIN/MANAGER/EMPLOYEE. Triển khai `Sidebar.jsx` và `TopBar.jsx`. Tạo stat cards, panels, status pills, empty states và loading states là các UI components có thể tái sử dụng. Thiết lập cấu trúc Pages Router: `/pages/login.jsx`, `/pages/admin/*` (dashboard, departments, users, tasks, analytics, logs, settings), `/pages/manager/*` (dashboard, meetings, tasks, employees, analytics), `/pages/employee/*` (dashboard, meetings, tasks, notifications, profile). Tùy chỉnh navigation items theo từng role với dashboard riêng biệt. | Không có | Chủ yếu làm project nhóm, hoàn thiện layout và routing nên không ghi link tài liệu riêng. |
| 04/06/2026 | Tiếp tục học Module 06 để tìm hiểu thêm các dịch vụ AWS có thể áp dụng vào dự án. | Tập trung học tiếp các nội dung của Module 06 về RDS, Aurora, DynamoDB và DMS để hiểu rõ hơn cách từng dịch vụ hoạt động, ưu điểm, hạn chế và trường hợp sử dụng phù hợp. Từ đó đánh giá xem ngoài các dịch vụ đã chọn ban đầu, dự án AI Meeting Workforce Platform có thể áp dụng thêm dịch vụ AWS nào cho phần lưu trữ dữ liệu, xử lý backend, migration hoặc tối ưu hiệu năng trong giai đoạn MVP và sau MVP. | Không có | Chủ yếu học tiếp nội dung module và liên hệ với project nhóm, không ghi link tài liệu riêng cho ngày này. |
| 05/06/2026 | Tiếp tục góp ý, nhận ý kiến từ các thành viên nhóm và phát triển thêm khung xương dự án. | Trao đổi với các thành viên trong nhóm về cấu trúc hiện tại của project, ghi nhận các góp ý liên quan đến phân chia thư mục, luồng điều hướng, dữ liệu mock và các phần cần chuẩn bị cho việc tích hợp AWS sau này. Dựa trên feedback của nhóm, tiếp tục điều chỉnh và phát triển thêm khung xương dự án để các phần frontend, service layer và AWS integrations có hướng triển khai rõ ràng hơn. | Không có | Chủ yếu phát triển project nhóm và xử lý feedback nội bộ nên không có tài liệu tham khảo riêng. |

---

## Thiết kế kiến trúc dự án & AWS Services

### 1. Tổng quan dự án

**AI Meeting Workforce Platform** là công cụ nội bộ được thiết kế để:
- Cho phép employee và manager upload transcript cuộc họp.
- Sử dụng AI để tự động tóm tắt cuộc họp và trích xuất các task hành động.
- Cung cấp dashboard theo vai trò (Admin, Manager, Employee) để theo dõi tiến độ.
- Theo dõi thông báo, phân công task và analytics theo phòng ban.

### 2. Tech Stack (Kế hoạch)

| Tầng | Công nghệ | Mục đích |
|---|---|---|
| **Frontend** | Next.js (React) + Tailwind CSS | SSR/SPA hybrid, Pages Router |
| **Auth** | Amazon Cognito | User pools, social sign-in, JWT tokens |
| **Storage** | Amazon S3 + CloudFront | Lưu transcript, audio files, CDN |
| **Compute** | AWS Lambda | Xử lý AI (tóm tắt, trích xuất task) |
| **Database** | Amazon DynamoDB | Lưu meetings, tasks, notifications, user sessions |
| **API** | Amazon API Gateway | REST endpoints cho frontend-backend |
| **Cache** | Amazon ElastiCache (Redis) | Session caching, caching dashboard queries |
| **Monitoring** | AWS CloudTrail + CloudWatch | Audit logging, monitoring, alerting |

---

## Kiểm tra bảo mật thư viện (02/06/2026)

| Package | Trước | Sau | Lý do |
|---|---|---|---|
| `next` | 13.5.11 | 13.5.11 (giữ nguyên) | Bản 13.x ổn định nhất; nâng cấp lên 14.x sau MVP |
| `react` / `react-dom` | 18.2.0 | 18.2.0 (xác nhận) | Bản 18.x mới nhất, không có lỗ hổng bảo mật |
| `framer-motion` | ^12.40.0 | ^12.40.0 | Đã cập nhật lên bản patch mới nhất |
| `lucide-react` | ^1.17.0 | ^1.17.0 | Đã cập nhật |
| `eslint-config-next` | ^13.5.11 | ^13.5.11 | Đồng bộ với phiên bản Next.js |
| `autoprefixer` | 10.4.19 | 10.4.19 | Đã cập nhật |
| `tailwindcss` | 3.4.4 | 3.4.4 | Đã cập nhật |

**Kết luận**: Tất cả dependencies trực tiếp đều ở phiên bản an toàn, được duy trì. Không phát hiện lỗ hổng nghiêm trọng. Việc nâng cấp Next.js 13 → 14 được hoãn lại sau MVP để tránh breaking changes trong giai đoạn đang phát triển tích cực.

---

## Cấu trúc dữ liệu Mock

Dữ liệu mock được thiết kế để phản ánh DynamoDB schema tương lai:

- **Departments**: 4 team (Frontend, Backend, AI, DevOps), mỗi team có manager và thành viên.
- **Users**: 12 nhân viên với 3 role (ADMIN, MANAGER, EMPLOYEE), có tên, email, avatar và trạng thái thực tế.
- **Meetings**: 5 bản ghi cuộc họp với theo dõi trạng thái (COMPLETED, PROCESSING), transcript, summary và liên kết phòng ban.
- **Tasks**: 10 task được trích xuất từ meetings với người được giao, mức độ ưu tiên (HIGH, MEDIUM), theo dõi tiến độ và hạn chót.
- **Notifications**: Thông báo dạng tin nhắn với theo dõi trạng thái đã đọc/chưa đọc.

Tất cả dữ liệu mock được tập trung trong `src/lib/mockData.js` và có thể thay thế bằng API calls thật khi backend sẵn sàng.

---

## Học Module 06 – Đánh giá AWS Services cho dự án

### Các dịch vụ đã xem xét (04/06/2026)

| Service | Use Case | Phù hợp cho dự án | Ưu tiên |
|---|---|---|---|
| **Amazon DynamoDB** | NoSQL storage cho meetings, tasks, notifications | ✅ Cao – hoàn hảo cho workload đọc/ghi cao | MVP |
| **Amazon RDS** | Dữ liệu quan hệ cho reports, truy vấn có cấu trúc | ⏸ Trung bình – dời lại sau MVP | Post-MVP |
| **Amazon Aurora** | RDS alternative hiệu năng cao | ❌ Overkill cho quy mô hiện tại | Future |
| **AWS DMS** | Migration database | ❌ Chưa cần thiết | Future |
| **Amazon ElastiCache** | Redis caching cho dashboards, sessions | ✅ Cao – giảm tải đọc DynamoDB | MVP |
| **Amazon S3** | Lưu trữ file (transcripts, audio) | ✅ Cao – yêu cầu cốt lõi | MVP |

### Quyết định

Cho **giai đoạn MVP**, dự án sẽ sử dụng:
1. **DynamoDB** làm kho dữ liệu chính (schema linh hoạt, serverless, pay-per-use).
2. **S3 + CloudFront** cho lưu trữ file và CDN.
3. **Lambda + API Gateway** cho backend serverless.
4. **ElastiCache (Redis)** cho caching để giảm chi phí đọc database và cải thiện thời gian phản hồi dashboard.
5. **Cognito** cho xác thực và phân quyền người dùng.

RDS/Aurora sẽ được đánh giá lại sau MVP nếu yêu cầu reporting đòi hỏi truy vấn quan hệ phức tạp.

---

## Kiến thức & kỹ năng đạt được

* Hiểu cách thiết kế kiến trúc full-stack application tích hợp nhiều AWS services.
* Học cách cấu trúc Next.js project với routing và layout theo phân quyền.
* Xây dựng dữ liệu mock và mock AI service mô phỏng hành vi AWS thực tế (DynamoDB, Lambda).
* Thực hiện quy trình kiểm tra bảo mật thư viện: xác định packages có lỗ hổng, kiểm tra cơ sở dữ liệu cảnh báo và áp dụng bản vá an toàn.
* Xây dựng hệ thống components có thể tái sử dụng (AppShell, StatCard, Panel, StatusPill, EmptyState, LoadingState) đảm bảo UI nhất quán giữa các role.
* Hiểu nguyên tắc thiết kế single-table của DynamoDB và cách ánh xạ vào các mẫu truy cập dữ liệu của dự án.
* So sánh DynamoDB (NoSQL) vs RDS/Aurora (relational) cho các loại workload khác nhau.
* Học cách ElastiCache Redis có thể vừa là session store vừa là query result cache để tối ưu chi phí và hiệu năng.
* Nhận ra Cognito user pools có thể tích hợp với API Gateway Lambda authorizers để kiểm soát truy cập chi tiết.

---

## Khó khăn gặp phải & Cách khắc phục

* **Phối hợp nhiều AWS services trong một kiến trúc**: Cần thời gian để mapping luồng dữ liệu giữa các services. Giải pháp: vẽ sơ đồ kiến trúc phân tầng và xác nhận trách nhiệm của từng service trước khi code.
* **Căn chỉnh dữ liệu mock với DynamoDB schema tương lai**: Dữ liệu mock cần phản ánh single-table design của DynamoDB. Giải pháp: thiết kế mock data với partition keys, sort keys và GSIs ngay từ đầu.
* **Cảnh báo bảo mật từ transitive dependencies**: Một số packages gián tiếp có cảnh báo mức thấp không thể fix bằng cách cập nhật direct dependencies. Giải pháp: ghi nhận findings và hẹn kiểm tra lại trước khi production deployment.
* **Thống nhất khung xương dự án trong nhóm**: Các thành viên có ý kiến khác nhau về cấu trúc thư mục và quy tắc đặt tên. Giải pháp: lặp qua 2-3 vòng feedback và đạt đồng thuận với cấu trúc hiện tại.
* **Đánh giá AWS services mà không phát sinh chi phí**: Không thể triển khai tài nguyên AWS thật trong quá trình đánh giá. Giải pháp: dựa vào tài liệu, pricing calculators và free-tier documentation để đánh giá.

---

## Bài học rút ra

* Bắt đầu với dữ liệu mock phản ánh production database schema giúp tiết kiệm đáng kể công sức làm lại sau này.
* Khung xương dự án được thiết kế tốt với phân tách rõ ràng (pages, components, lib, services, integrations) giúp phát triển song song trong nhóm dễ dàng hơn.
* Kiểm tra bảo mật thư viện nên được thực hiện sớm và thường xuyên — cập nhật package vào ngày thứ 2 rẻ hơn nhiều so với xử lý CVE vào ngày ra mắt.
* Routing theo phân quyền hoạt động tốt nhất khi navigation metadata được tập trung trong một configuration object (xem `roleMeta` trong `AppShell.jsx`), giúp dễ dàng thêm/xoá routes mà không cần chỉnh từng page.
* Khi thiết kế AWS architecture cho startup/MVP, serverless-first (DynamoDB + Lambda + API Gateway) thường là phương án chi phí thấp nhất vì có thể scale về 0 khi không sử dụng.
* ElastiCache Redis không chỉ là "nice to have" — nó trực tiếp giảm chi phí đọc DynamoDB, vốn có thể chiếm phần lớn hoá đơn trong ứng dụng read-heavy.
* Các dịch vụ database trong Module 06 có mối liên hệ chặt chẽ hơn so với tưởng tượng ban đầu: hiểu DynamoDB, RDS và ElastiCache cùng nhau giúp đưa ra quyết định tradeoff sáng suốt thay vì chọn database theo thói quen.
