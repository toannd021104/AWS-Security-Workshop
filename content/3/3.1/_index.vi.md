---
title : "Tập trung các phát hiện từ các dịch vụ bảo mật AWS"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 3.1. </b> "
---

AWS Security Hub tự động thu thập và hợp nhất các phát hiện bảo mật từ những dịch vụ AWS đã được kích hoạt trong môi trường của bạn, bao gồm phát hiện xâm nhập từ Amazon GuardDuty, kết quả quét lỗ hổng từ Amazon Inspector, các phát hiện liên quan đến chính sách bucket Amazon S3 từ Amazon Macie, tài nguyên công khai hoặc chia sẻ chéo tài khoản từ IAM Access Analyzer, cũng như các tài nguyên chưa được bảo vệ bởi AWS Firewall Manager.

Cơ chế tập trung này mang lại một góc nhìn thống nhất về tình trạng bảo mật và mức độ tuân thủ trong toàn bộ môi trường AWS. AWS Security Hub tổng hợp phát hiện từ hàng chục dịch vụ bảo mật AWS và các sản phẩm thuộc AWS Partner Network (APN) tại một nơi duy nhất, sử dụng định dạng chuẩn là **AWS Security Finding Format (ASFF)**. Lưu ý rằng Security Hub không tiếp nhận các phát hiện được tạo ra trước thời điểm bạn kích hoạt dịch vụ. Mỗi phát hiện sẽ được lưu trữ trong vòng 90 ngày kể từ lần cập nhật gần nhất.

Trang **Integrations** trong AWS Management Console cho phép bạn truy cập và quản lý tất cả các tích hợp với dịch vụ AWS và giải pháp bên thứ ba. Ngoài ra, AWS Security Hub API cũng cung cấp các thao tác để tự động hóa việc quản lý tích hợp. Đối với các dịch vụ AWS, các tích hợp này được bật sẵn theo mặc định và bạn có thể chủ động vô hiệu hóa nếu cần.

---

#### Tập trung các phát hiện từ các dịch vụ bảo mật AWS

1. Truy cập AWS Security Hub và mở trang **Summary**.  
Trang [Security Hub Summary page](https://us-east-1.console.aws.amazon.com/securityhub/home?region=us-east-1#/summary) cung cấp cái nhìn tổng quan về trạng thái bảo mật và tuân thủ của tài khoản AWS.

2. Dành một vài phút để quan sát các thông tin tổng hợp hiển thị trên trang Summary. Bạn có nhận ra những loại mối đe dọa phổ biến nhất trong môi trường của mình không? Các phát hiện này đang được Security Hub tổng hợp từ Amazon GuardDuty.

Security Hub widgets  
![VPC](/images/3/3.1/s2.png)

3. Mở trang **Integrations** trong Security Hub và cuộn để xem danh sách các tích hợp hiện có.
![VPC](/images/3/3.1/s3a.png)
![VPC](/images/3/3.1/s3b.png)

Có thể thấy rằng nhiều tích hợp, chẳng hạn như **Amazon: GuardDuty** và **Amazon: Inspector**, đã được tự động bật. Tuy nhiên, để có phát hiện bảo mật, bản thân từng dịch vụ tương ứng vẫn cần được kích hoạt riêng.

4. Security Hub cho phép bạn chủ động bật hoặc tắt từng tích hợp AWS. Dù không được khuyến nghị trong thực tế, hãy thử vô hiệu hóa tích hợp **AWS: Firewall Manager** bằng cách chọn **Stop accepting findings**.
![VPC](/images/3/3.1/s5a.png?featherlight=false&width=10pc)

5. Một hộp thoại cảnh báo sẽ xuất hiện với nội dung:  
“Not accepting findings from this integration means that the product can still try to send findings to Security Hub, but Security Hub will not ingest them.”  
Chọn **Cancel** để giữ nguyên tích hợp này.
![VPC](/images/3/3.1/s5b.png)

6. Để xem các phát hiện từ một dịch vụ cụ thể, tìm tích hợp **Amazon: GuardDuty** và chọn **See findings**. Thao tác này sẽ mở trang Findings và tự động áp dụng bộ lọc chỉ hiển thị các phát hiện từ GuardDuty. Giữ nguyên trang Findings.

7. Bạn có thể tùy chỉnh, xóa hoặc thay đổi các bộ lọc để điều chỉnh danh sách phát hiện đang hiển thị.

---

#### Tìm kiếm và xem xét các phát hiện bảo mật

8. Để xem toàn bộ phát hiện trong Security Hub, hãy xóa tất cả các bộ lọc (và **Group by** nếu có) bằng cách chọn dấu **X** bên cạnh từng bộ lọc.

9. Danh sách này có thể rất dài. Thử thu hẹp phạm vi bằng cách lọc các phát hiện có mức độ nghiêm trọng cao từ GuardDuty. Chọn **Add filters** trong thanh tìm kiếm.

10. Trong danh sách thả xuống, chọn **Severity label**, nhập **HIGH** (phân biệt chữ hoa), sau đó chọn **Apply**.
![VPC](/images/3/3.1/s10a.png)

Kết quả:
![VPC](/images/3/3.1/s10b.png)

Chọn một phát hiện để xem chi tiết:
![VPC](/images/3/3.1/s10c.png)

11. Tiếp tục chọn **Add filters**, lần này chọn **Product name**, nhập **GuardDuty**, rồi chọn **Apply**.

12. Nhấp vào tiêu đề của một phát hiện bất kỳ để mở bảng chi tiết. Mở rộng các mục và dành thời gian xem mô tả, hướng dẫn khắc phục, thông tin tài nguyên và các dữ liệu liên quan.

13. Trong bảng chi tiết, chọn **Finding ID** ở phía trên để hiển thị toàn bộ nội dung JSON của phát hiện. Security Hub sử dụng định dạng chuẩn ASFF, giúp giảm thiểu công sức chuyển đổi dữ liệu. Bạn có thể tải JSON này về để phục vụ điều tra chuyên sâu.
![VPC](/images/3/3.1/s13.png)

14. Đóng cửa sổ JSON bằng cách chọn **X** ở góc trên bên phải.

15. Chuyển sang tab **History** để xem lịch sử thay đổi của phát hiện theo dòng thời gian. Thông tin này giúp bạn hiểu rõ diễn biến sự cố và chủ động đánh giá rủi ro.

16. Đóng bảng chi tiết phát hiện nhưng vẫn ở lại trang **Findings**.

17. Để xác định tài nguyên nào tạo ra nhiều phát hiện nhất, xóa toàn bộ bộ lọc hiện có. Thêm bộ lọc mới với **Resource type** và nhập **AwsAccount**, sau đó chọn **Apply**.
![VPC](/images/3/3.1/s17a.png)

Kết quả:
![VPC](/images/3/3.1/s17b.png)

18. Thêm bộ lọc tiếp theo: chọn **Record state**, nhập **ACTIVE**, rồi chọn **Apply**.
![VPC](/images/3/3.1/s18.png)

19. Tiếp tục chọn **Add filters**, lần này chọn **Group by** và đặt giá trị là **ResourceId**. Danh sách hiển thị số lượng phát hiện trên từng tài nguyên, giúp bạn ưu tiên xử lý các tài nguyên có mức độ rủi ro cao.
![VPC](/images/3/3.1/s19.png)

Kết quả:
![VPC](/images/3/3.1/s19b.png)

---

#### Tạo insight từ các phát hiện đã tổng hợp

20. Nếu thấy danh sách này hữu ích, bạn có thể lưu lại dưới dạng một **Insight** tùy chỉnh. Chọn **Create insight** ở góc trên bên phải.

21. Đặt tên insight là **“0. Resources by counts of findings”**, sau đó chọn **Create insight**.
![VPC](/images/3/3.1/s20.png)

22. Trong thanh điều hướng bên trái, chọn **Insights**.  
Insight là tập hợp các phát hiện liên quan được xác định thông qua quy tắc tổng hợp và bộ lọc. Security Hub cung cấp sẵn các insight mặc định (không thể chỉnh sửa hoặc xóa), đồng thời cho phép bạn tạo insight tùy chỉnh theo nhu cầu riêng.

23. Chọn insight vừa tạo để xem chi tiết. Ngoài danh sách phát hiện, bạn còn có thêm các biểu đồ trực quan hỗ trợ phân tích.
![VPC](/images/3/3.1/s23.png)

24. Quay lại trang **Insights** bằng thanh điều hướng bên trái.

25. Dành thời gian xem qua các insight mặc định do AWS cung cấp và thử lọc theo mức độ nghiêm trọng.

26. Chọn insight **24. Severity by counts of findings**.

27. Chọn một nhãn mức độ nghiêm trọng (ví dụ: **Critical**) để xem các phát hiện tương ứng.
![VPC](/images/3/3.1/s26.png)

Kết quả:
![VPC](/images/3/3.1/s26b.png)
