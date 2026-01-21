---
title: "Inspector  - Phát hiện bảo mật"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 2.3.3 </b> "
---

#### Lọc các phát hiện bảo mật

1. Truy cập trang **Findings: All Findings** tại:  
   https://us-east-1.console.aws.amazon.com/inspector/v2/home?region=us-east-1#/findings/all

2. Ở phía trên cùng của trang, chọn ô nhập **Filter criteria** với nội dung gợi ý _Add filter_. Bộ lọc cho phép bạn chỉ hiển thị các phát hiện bảo mật đáp ứng tiêu chí đã chọn; những phát hiện không phù hợp sẽ bị loại khỏi danh sách. Dành một chút thời gian để xem qua các tuỳ chọn lọc hiện có.

3. Bạn có thể tạo bộ lọc riêng cho từng tab nhằm tập trung vào những loại phát hiện cụ thể. Thử lọc theo **resource tag**: chọn **Add filter**, sau đó chọn **Resource tag**. Lưu ý bộ lọc có phân biệt chữ hoa và chữ thường. Nhập **"Environment"** cho **Key** và **"Development"** cho **Value**, rồi chọn **Apply**. Kết quả sẽ hiển thị các phát hiện bảo mật của những tài nguyên có tag tương ứng.

![VPC](/images/2/2.3/2.3.3/s3.png)

4. Sau khi quan sát kết quả, xoá bộ lọc vừa tạo bằng cách chọn **Clear filters**.

<!--
5. Thêm một bộ lọc mới. Chọn trường **Add filter**, chọn **Resource tag**. Lưu ý các bộ lọc có phân biệt chữ hoa chữ thường. Nhập **"Name"** cho Key và **"EC2InstanceDev3"** cho **Value**. Thao tác này sẽ chỉ hiển thị các phát hiện bảo mật liên quan đến EC2 instance có tên "EC2InstanceDev3". Bạn có thể thử kết hợp nhiều bộ lọc để thu hẹp kết quả.

6. Xoá bộ lọc vừa thêm bằng cách chọn **Clear filters**.


#### Xem xét phát hiện bảo mật về khả năng truy cập mạng của EC2

7. Chọn **Add filter**, sau đó chọn **Type** và đặt giá trị là **Network Reachability**, rồi chọn **Apply**.

8. Chọn tiêu đề của một phát hiện trong danh sách đã lọc để mở báo cáo chi tiết. Báo cáo này cung cấp các thông tin như mức độ nghiêm trọng (Severity), dải cổng đang mở, Account ID, thông tin tài nguyên và các đường mạng đang mở.


#### Xem xét phát hiện bảo mật về lỗ hổng mã nguồn của Lambda

9. Xoá toàn bộ bộ lọc bằng **Clear filters**, sau đó chọn **Add filter**, chọn **Type** và đặt giá trị là **Code Vulnerability**, rồi chọn **Apply**.

10. Chọn phát hiện có tiêu đề **CWE-117,93 - Log injection** để xem báo cáo chi tiết.

11. Báo cáo nêu rõ rằng: *"User-provided inputs must be sanitized before they are logged..."*. Phần chi tiết bao gồm thông tin về tài nguyên bị ảnh hưởng và các gợi ý khắc phục. Hãy đọc kỹ hướng dẫn khắc phục. Nếu có thời gian, bạn có thể thử xử lý vấn đề mà không cần xoá Lambda function.

12. Đóng báo cáo phát hiện và xoá toàn bộ bộ lọc bằng cách chọn **Clear filters** một lần nữa. -->
