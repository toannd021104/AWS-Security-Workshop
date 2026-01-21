---
title: "Tổng hợp tìm kiếm qua các Region"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 3.4. </b> "
---

Với tính năng tổng hợp qua nhiều Region, bạn có thể hợp nhất các phát hiện, cập nhật phát hiện, insight, trạng thái tuân thủ của các kiểm soát và điểm số bảo mật từ nhiều Region về một **Region tổng hợp** duy nhất. Từ Region này, bạn có thể quản lý và theo dõi toàn bộ dữ liệu bảo mật đã được hợp nhất.

Ví dụ, giả sử bạn cấu hình **US East (N. Virginia)** làm Region tổng hợp, và liên kết thêm **US West (Oregon)** cùng **US West (N. California)**. Khi truy cập trang **Findings** tại US East (N. Virginia), bạn sẽ thấy các phát hiện đến từ cả ba Region. Mọi cập nhật đối với các phát hiện này cũng sẽ được đồng bộ giữa các Region.  
Lưu ý rằng trạng thái bật/tắt của một kiểm soát vẫn cần được cấu hình riêng tại từng Region. Trong trường hợp một kiểm soát được bật ở Region liên kết nhưng bị tắt ở Region tổng hợp, bạn vẫn có thể xem trạng thái tuân thủ của kiểm soát đó từ Region tổng hợp, nhưng không thể thay đổi trạng thái bật/tắt trực tiếp từ đây.

#### Thiết lập tổng hợp tìm kiếm qua các Region

1. Bạn có thể đã thấy thông báo **Configure finding aggregation** trong Security Hub. Chọn bất kỳ thông báo nào để bắt đầu cấu hình. Nếu chưa thấy, hãy mở trang **Regions** dưới mục **Settings** từ thanh điều hướng bên trái.

2. Chọn **Configure finding aggregation**.
   ![VPC](/images/3/3.4/s2.png)

3. Chọn **US East (N. Virginia) - us-east-1** làm **Region tổng hợp**.

4. Chọn tất cả các Region khả dụng.

5. Chọn **Save** ở cuối trang. Thao tác này sẽ kích hoạt việc tổng hợp phát hiện giữa các Region, nhưng chưa bật Security Hub tại các Region còn lại.
   ![VPC](/images/3/3.4/s6.png)

**Lưu ý**: Khi bạn chọn **Save** để bật tổng hợp qua các Region, các điểm số bảo mật và dữ liệu kiểm soát đã được tổng hợp trước đó trong Security Hub sẽ bị xóa. Các phát hiện hiện có vẫn được giữ nguyên và tiếp tục được tạo, tuy nhiên các điểm số (ví dụ trên trang Summary) sẽ tạm thời không hiển thị cho đến khi các điểm số mới được tính toán dựa trên dữ liệu từ nhiều Region. Bạn nên hoàn thành phần workshop **Security Posture Management** trước khi thực hiện mô-đun này.

#### Bật các dịch vụ bảo mật AWS trong Region liên kết

Mặc dù nhiều dịch vụ bảo mật AWS đã được bật tại **us-east-1 (N. Virginia)** và bạn đã cấu hình tổng hợp phát hiện trong Security Hub, điều này không đồng nghĩa với việc các dịch vụ đó cũng đã được bật tại các Region khác.  
Để nhanh chóng bật cùng bộ dịch vụ bảo mật tại **us-east-2 (Ohio)**, bạn sẽ sử dụng CloudFormation để triển khai cấu hình tương tự tại Region thứ hai. Ngay sau khi các dịch vụ được bật tại Region này, các phát hiện phát sinh sẽ tự động được tổng hợp về Region tổng hợp nhờ cấu hình đã thiết lập trước đó.

7. Mở trang sau trong bảng điều khiển CloudFormation:  
   https://us-east-1.console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/?filteringText=cfn&filteringStatus=active&viewNested=false  
   ![VPC](/images/3/3.4/s7.png)

8. Chọn stack có tên **cfn**.
   ![VPC](/images/3/3.4/s8.png)

9. Mở tab **Outputs**.
   ![VPC](/images/3/3.4/s9.png)

10. Chọn liên kết **SecurityServicesCloudFormationLink** để khởi chạy mẫu CloudFormation đã được cấu hình sẵn tại **us-east-2 (Ohio)**. Trang **Quick create stack** sẽ được mở và tự động điền thông tin stack. Đảm bảo rằng góc trên bên phải hiển thị Region **Ohio**.

11. Giữ nguyên các giá trị cho **Stack name**, **MyAssetsBucketName** và **MyAssetsBucketPrefix**. Nếu các trường này trống, hãy liên hệ với người hướng dẫn.
    ![VPC](/images/3/3.4/s11.png)

12. Ở cuối trang, đánh dấu vào ô xác nhận:  
    **I acknowledge that AWS CloudFormation might create IAM resources with custom names and I acknowledge that AWS CloudFormation might require the following capability: CAPABILITY_AUTO_EXPAND**.

13. Chọn **Create stack**. Thao tác này sẽ bật AWS Config, Security Hub, Inspector, Detective, Macie và GuardDuty tại **us-east-2 (Ohio)**. Do bạn đã cấu hình tổng hợp phát hiện, các phát hiện mới từ Region này sẽ tự động xuất hiện tại Region tổng hợp. Quá trình này có thể mất vài phút, bạn có thể tiếp tục workshop mà không cần chờ.
    ![VPC](/images/3/3.4/s13.png)

14. Quay lại Security Hub. Nếu chưa chuyển về Region workshop ban đầu, bạn sẽ thấy thông báo **Go to aggregation region**. Chọn thông báo này và đảm bảo rằng bạn đang ở **us-east-1 (N. Virginia)** (hiển thị ở góc trên bên phải).

15. Khi đã trở lại Region tổng hợp, bạn sẽ thấy trang **Findings** hiển thị các phát hiện từ nhiều Region, đồng thời các biểu đồ trên trang **Summary** cũng phản ánh dữ liệu đa Region. Các nội dung này sẽ được phân tích chi tiết hơn ở các phần sau của workshop.

(Sau khoảng 5 phút)
![VPC](/images/3/3.4/s15.png)
