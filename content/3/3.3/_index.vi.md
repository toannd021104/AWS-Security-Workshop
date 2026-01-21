---
title: "Tập hợp các phát hiện từ các giải pháp của đối tác AWS"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

AWS Security Hub hỗ trợ tổng hợp dữ liệu phát hiện bảo mật không chỉ từ các dịch vụ bảo mật gốc của AWS mà còn từ các giải pháp bảo mật thuộc **AWS Partner Network (APN)**. Việc tích hợp này giúp cung cấp một cái nhìn toàn diện về trạng thái bảo mật và tuân thủ trên toàn bộ môi trường AWS của bạn.

Bên cạnh đó, Security Hub cũng cho phép tiếp nhận các phát hiện được tạo ra từ những công cụ hoặc giải pháp bảo mật tùy chỉnh do chính bạn xây dựng.

Đối với các tích hợp dịch vụ AWS và đối tác được hỗ trợ, Security Hub chỉ tiếp nhận và hợp nhất các phát hiện phát sinh **sau thời điểm Security Hub được kích hoạt** trong tài khoản AWS. Các phát hiện được tạo ra trước thời điểm bật Security Hub sẽ không được thu thập lại.

Một trong những giải pháp đối tác tiêu biểu có thể tích hợp với Security Hub là **Cloud Custodian**. Cloud Custodian cho phép bạn quản lý tài nguyên đám mây thông qua việc lọc, gán thẻ và áp dụng các hành động tương ứng. Công cụ này sử dụng DSL dựa trên YAML để định nghĩa các chính sách, giúp xây dựng hạ tầng đám mây được quản lý tốt, an toàn và tối ưu chi phí. Để biết thêm chi tiết, bạn có thể tham khảo tại: https://cloudcustodian.io/

#### Nhận phát hiện từ Cloud Custodian

1. Mở trang **Integrations** trong Security Hub và tìm kiếm **Cloud Custodian**.
   ![VPC](/images/3/3.3/s1.png)

2. Chọn **Accept findings** và xem xét các quyền cần thiết cho việc tích hợp.
   ![VPC](/images/3/3.3/s2.png)

3. Chọn **Accept findings** để xác nhận. Thao tác này sẽ thiết lập chính sách dịch vụ cho phép giải pháp đối tác gửi các phát hiện bảo mật vào tài khoản AWS của bạn.  
   Trong phạm vi workshop này, một phiên bản Cloud Custodian đã được cấu hình sẵn để tự động gửi phát hiện đến tích hợp vừa được bật. Đối với các giải pháp đối tác khác, bạn vẫn cần thực hiện thêm bước cấu hình phía đối tác để đảm bảo các phát hiện được gửi về Security Hub.

Sau khi hoàn tất, bạn có thể chọn **See findings** để xem các phát hiện mới từ Cloud Custodian. Lưu ý rằng có thể mất khoảng 5–10 phút để các phát hiện này xuất hiện trong Security Hub.
