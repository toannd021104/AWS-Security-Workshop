---
title: "Security Hub - Phát hiện bảo mật"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 2.1.3 </b> "
---

#### Phát hiện bảo mật trong Security Hub

1. Trong Security Hub, chọn **Findings** từ bảng điều hướng bên trái.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.3-Security-Hub-Findings/s1.png)

2. Bạn có thể áp dụng bộ lọc để giới hạn danh sách các phát hiện được hiển thị. Chọn **Add filter**.

3. Chọn **Product name**, sau đó nhập **GuardDuty** (phân biệt chữ hoa/chữ thường), rồi chọn **Apply**.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.3-Security-Hub-Findings/s3.png)

4. Danh sách lúc này sẽ hiển thị toàn bộ các phát hiện bảo mật mà Security Hub thu thập từ dịch vụ phát hiện mối đe dọa GuardDuty. Số lượng phát hiện có thể khá lớn.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.3-Security-Hub-Findings/s4.png)

Tiếp tục tinh chỉnh để chỉ còn các phát hiện có mức độ nghiêm trọng cao. Chọn **Add filters** một lần nữa.

5. Từ danh sách thả xuống, chọn **Severity label**, nhập **HIGH** (chú ý viết hoa), sau đó chọn **Apply**.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.3-Security-Hub-Findings/s5a.png)

Kết quả:

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.3-Security-Hub-Findings/s5b.png)

6. Chọn một phát hiện bất kỳ và nhấp vào tiêu đề để mở bảng chi tiết. Mở rộng tất cả các phần và dành thời gian xem xét nội dung, bao gồm mô tả, liên kết hướng dẫn khắc phục, thông tin tài nguyên và các dữ liệu liên quan khác.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.3-Security-Hub-Findings/s6.png)

7. Trong bảng chi tiết, chọn **Finding ID** ở phía trên để hiển thị toàn bộ nội dung JSON của phát hiện. Tệp JSON này có thể được tải về để phục vụ việc phân tích hoặc điều tra chuyên sâu.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.3-Security-Hub-Findings/s7.png)

8. Đóng cửa sổ JSON bằng cách chọn **X** ở góc trên bên phải.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.3-Security-Hub-Findings/s8.png)

9. Ở phần đầu của bảng chi tiết phát hiện, mở tab **History** để xem danh sách các thay đổi theo trình tự thời gian đã được áp dụng cho phát hiện này. Việc theo dõi lịch sử giúp bạn nhanh chóng nhận diện các rủi ro tiềm ẩn và chủ động đưa ra biện pháp xử lý.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.3-Security-Hub-Findings/s9.png)

10. Đóng bảng chi tiết bằng cách chọn **X** ở góc trên bên phải, nhưng vẫn giữ nguyên tại trang **Findings**.

11. Để xác định những tài nguyên nào trong môi trường đang tạo ra nhiều phát hiện nhất, hãy xoá toàn bộ bộ lọc hiện tại. Sau đó, thêm bộ lọc mới với **Resource type**, chọn **not**, và nhập **AwsAccount**, rồi chọn **Apply**.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.3-Security-Hub-Findings/s11.png)

12. Thêm một bộ lọc khác bằng cách chọn **Record state**, nhập **ACTIVE**, và chọn **Apply**.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.3-Security-Hub-Findings/s12.png)

13. Chọn **Add filters** thêm một lần nữa. Lần này, chọn **Group by** và đặt giá trị là **ResourceId**, sau đó chọn **Apply**. Danh sách kết quả sẽ hiển thị số lượng phát hiện bảo mật tương ứng với từng tài nguyên.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.3-Security-Hub-Findings/s13.png)

14. Xem thông tin chi tiết hơn bằng cách chọn **Insight details**.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.3-Security-Hub-Findings/s14.png)
![VPC](/images/2/2.1-AWS-Security-Hub/2.1.3-Security-Hub-Findings/s15.png)

15. Quan sát các phát hiện bảo mật khác được lọc theo loại bên cung cấp **TTPs/Discovery/Recon:IAMUser-MaliciousIPCallerCustom**, do **GuardDuty** tạo ra.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.3-Security-Hub-Findings/o1.png)

16. Chọn một phát hiện để xem chi tiết. Phát hiện này cho biết API **ListBuckets** đã được gọi bởi các tác nhân không được ủy quyền, xuất phát từ một địa chỉ IP nằm trong danh sách mối đe dọa tuỳ chỉnh của bucket.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.3-Security-Hub-Findings/o2.png)

17. Tiếp tục xem các phát hiện bảo mật khác được tạo bởi **Inspector**.

![VPC](/images/2/2.1-AWS-Security-Hub/2.1.3-Security-Hub-Findings/o3.png)

Các phát hiện này được sinh ra khi **Inspector** quét các EC2 instance và phát hiện những lỗ hổng bảo mật tồn tại trên hệ thống.
