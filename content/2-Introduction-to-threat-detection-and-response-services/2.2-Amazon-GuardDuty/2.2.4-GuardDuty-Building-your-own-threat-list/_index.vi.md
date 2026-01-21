---
title: "GuardDuty - Xây dựng danh sách mối đe dọa của riêng bạn"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 2.2.4 </b> "
---

#### Triển khai danh sách mối đe dọa với địa chỉ giả

1. Truy cập dịch vụ **Amazon S3** trong AWS Console.

2. Tìm S3 bucket có tên chứa chuỗi **"-threatlistbucket-"** và chọn bucket đó.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.4-GuardDuty-Building-your-own-threat-list/s2.png)

Đây là bucket đã được thiết lập sẵn trong tài khoản AWS Workshop.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.4-GuardDuty-Building-your-own-threat-list/s2b.png)

3. Tải lên S3 bucket danh sách mối đe dọa mà bạn đã chuẩn bị trước đó.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.4-GuardDuty-Building-your-own-threat-list/s3.png)

1. Ghi lại **S3 URI** của tệp vừa tải lên. Để lấy URI, mở bucket, chọn tệp tương ứng và sao chép giá trị **S3 URI**.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.4-GuardDuty-Building-your-own-threat-list/s4.png)

1. Tiếp theo, tiến hành thêm danh sách đã tải lên vào GuardDuty. Quay lại bảng điều khiển **Amazon GuardDuty**.

2. Trong menu điều hướng bên trái của GuardDuty, chọn **Lists**.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.4-GuardDuty-Building-your-own-threat-list/s6.png)

7. Chọn nút **Add a threat IP list**.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.4-GuardDuty-Building-your-own-threat-list/s7.png)

1. Trong trường **List name**, nhập tên cho danh sách, ví dụ: **"Test Threat List"**.

2. Tại mục vị trí (Location), dán **S3 URI** của tệp danh sách mà bạn đã ghi lại ở bước trước.

3. Chọn định dạng **Plaintext**.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.4-GuardDuty-Building-your-own-threat-list/s10.png)

11. Đánh dấu **I Agree**, sau đó chọn **Add list** để tạo danh sách.

12. Sau khi danh sách được tạo, bạn cần kích hoạt để GuardDuty bắt đầu sử dụng. Chọn danh sách vừa thêm, mở menu **Actions**, rồi chọn **Activate**.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.4-GuardDuty-Building-your-own-threat-list/s12.png)

13. Khi danh sách được kích hoạt thành công, một thông báo trạng thái màu xanh lá sẽ xuất hiện với nội dung **"Successfully updated the list..."**.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.4-GuardDuty-Building-your-own-threat-list/s13.png)
