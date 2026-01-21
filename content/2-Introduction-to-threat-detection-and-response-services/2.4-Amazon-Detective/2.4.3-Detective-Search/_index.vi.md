---
title: "Detective - Tìm kiếm"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 2.4.3 </b> "
---

#### Detective - Tìm kiếm

1. Truy cập trang **Search** trong Amazon Detective theo liên kết sau:  
   https://us-east-1.console.aws.amazon.com/detective/home?region=us-east-1#search

2. Thử thực hiện một ví dụ tìm kiếm với IAM role mà bạn đang sử dụng.
   - Tại mục **Select type**, chọn **AWS Role**.
   - Nhập tên role **WSParticipantRole** và nhấn **Search**.  
     ![VPC](/images/2/2.4/2.4.3/s2.png)

3. Chọn **Principal ID** để xem chi tiết cách role **WSParticipantRole** đã được sử dụng trong khoảng thời gian được ghi nhận.  
   Dành thời gian quan sát các biểu đồ và các tab thông tin trên trang này. Đặc biệt, lưu ý **phạm vi thời gian** ở góc trên bên phải và so sánh với các hoạt động bạn đã thực hiện trước đó trong workshop. Các dữ liệu hiển thị nên phản ánh đúng những thao tác đã diễn ra.

![VPC](/images/2/2.4/2.4.3/s2b.png)
