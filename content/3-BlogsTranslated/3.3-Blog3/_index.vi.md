---
title: "Blog 3 - AWS Pricing Calculator"
date: 2026-07-09
weight: 1
chapter: false
pre: " <b> 3.3. </b> "
---


# AWS Pricing Calculator — Công cụ ước tính chi phí trước khi triển khai

Chào anh em AWS Study Group VN!

Trong quá trình học và thực hành AWS, mình nhận ra một câu hỏi xuất hiện rất thường xuyên: *"Triển khai một dịch vụ sẽ tốn bao nhiêu tiền mỗi tháng?"*

Thay vì tạo tài nguyên thật rồi chờ hóa đơn cuối tháng, AWS cung cấp một công cụ miễn phí giúp chúng ta ước tính chi phí trước khi triển khai, đó là **AWS Pricing Calculator**.

Trong bài viết này, mình sẽ chia sẻ cách sử dụng AWS Pricing Calculator để tính chi phí cho một EC2 cơ bản.

---

## AWS Pricing Calculator là gì?

AWS Pricing Calculator là công cụ cho phép bạn tạo các kịch bản (estimate) cho khối lượng công việc mới hoặc thay đổi khối lượng công việc hiện có để ước tính chi phí.

> *Hình 1. Giao diện AWS Pricing Calculator*

{{< figure src="/images/blog/blog3.1.jpg" title="Hình 1. Giao diện chính của AWS Pricing Calculator" >}}

---

## Vì sao nên sử dụng AWS Pricing Calculator?

Theo mình, công cụ này hữu ích trong các trường hợp:

- **Ước tính được chi phí** trước khi triển khai hệ thống.
- **Lập kế hoạch ngân sách** cho dự án.
- **Chia sẻ estimate** với khách hàng hoặc thành viên trong nhóm.

---

## Quy trình sử dụng AWS Pricing Calculator

Quy trình sử dụng có thể tóm tắt như sau:

1. **Tạo Estimate** — Bắt đầu một bản ước tính mới.
2. **Chọn dịch vụ** cần tính chi phí (EC2, S3, RDS,...).

> *Hình 2. Chọn dịch vụ cần ước tính*

{{< figure src="/images/blog/blog3.2.jpg" title="Hình 2. Lựa chọn dịch vụ AWS để ước tính chi phí" >}}

3. **Nhập các thông số** cấu hình — loại instance, dung lượng lưu trữ, region,...
4. **Estimate** sẽ được hiển thị tại trang **My Estimate** với chi phí ước tính theo tháng.

> *Hình 3. Kết quả ước tính chi phí*

{{< figure src="/images/blog/blog3.3.jpg" title="Hình 3. Chi tiết estimate hiển thị tại My Estimate" >}}

---

## Một số lưu ý

AWS Pricing Calculator **chỉ cung cấp chi phí ước tính** dựa trên các thông số được nhập.

Chi phí thực tế có thể thay đổi tùy thuộc vào:
- Mức sử dụng thực tế.
- Lưu lượng mạng phát sinh.
- Các dịch vụ bổ sung.
- Thay đổi về giá dịch vụ theo Region.

Do đó, kết quả từ Pricing Calculator nên được xem như **một công cụ hỗ trợ lập kế hoạch chi phí** hơn là con số tuyệt đối.

---

## Tổng kết

Theo mình, AWS Pricing Calculator là một công cụ hữu ích đối với bất kỳ ai đang học hoặc làm việc với AWS.

Thay vì triển khai tài nguyên rồi mới kiểm tra chi phí, chúng ta có thể chủ động ước tính trước ngân sách, so sánh các lựa chọn và đưa ra quyết định phù hợp ngay từ giai đoạn thiết kế hệ thống.

Nếu anh em đã từng sử dụng AWS Pricing Calculator hoặc có kinh nghiệm về tối ưu chi phí trên AWS thì có thể chia sẻ thêm ở phần bình luận nhé.

---

## Tài liệu tham khảo

- [Bài viết trên Facebook Group](https://www.facebook.com/share/p/18MB3hwy2g/)
- [AWS Pricing Calculator](https://aws.amazon.com/vi/aws-cost-management/aws-pricing-calculator/)
