---
title: "Inspector - Bảng điều khiển"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2.3.2 </b> "
---

#### Kiểm tra bảng điều khiển của Inspector

1. Truy cập **Dashboard** của Inspector tại liên kết sau:  
   https://us-east-1.console.aws.amazon.com/inspector/v2/home?region=us-east-1#/dashboard

2. Ở phần đầu trang, bạn sẽ thấy mục **Environment coverage**. Khu vực này thể hiện tỷ lệ phần trăm các instance hiện đang được bảo vệ. Lưu ý rằng không phải tất cả instance đều được quét. Bạn có thể nhấp vào tỷ lệ phần trăm này để xem chi tiết những instance nào đang nằm trong phạm vi quét.

![VPC](/images/2/2.3/2.3.2/s2.png)

3. Trên bảng điều khiển, quan sát mục **Risk Based Remediations** ở gần đầu trang. Phần này hiển thị năm gói phần mềm có lỗ hổng nghiêm trọng ảnh hưởng đến số lượng tài nguyên lớn nhất trong môi trường. Việc ưu tiên khắc phục các gói phần mềm này có thể giúp giảm đáng kể tổng mức rủi ro nghiêm trọng. Chọn tên một gói phần mềm để xem thông tin chi tiết về các lỗ hổng liên quan và danh sách tài nguyên bị ảnh hưởng.

![VPC](/images/2/2.3/2.3.2/s3.png)

4. Ngoài ra, trong bảng điều khiển bạn cũng có thể xem các thông tin tổng hợp sau:

- Các kho Amazon ECR có số lượng phát hiện nghiêm trọng nhiều nhất
- Các Amazon ECR container image có số lượng phát hiện nghiêm trọng nhiều nhất
- Các Amazon EC2 instance có số lượng phát hiện nghiêm trọng nhiều nhất
- Các Amazon Machine Image (AMI) có số lượng phát hiện nghiêm trọng nhiều nhất
- Các AWS Lambda function có số lượng phát hiện nghiêm trọng nhiều nhất
- Các trình phát hiện mã được sử dụng để quét mã Lambda

![VPC](/images/2/2.3/2.3.2/s4.png)

Hãy dành thời gian xem qua một vài phát hiện. Chọn một phát hiện bất kỳ để xem thông tin chi tiết.

![VPC](/images/2/2.3/2.3.2/e1.png)

Thông tin chi tiết bổ sung của phát hiện:

![VPC](/images/2/2.3/2.3.2/e2.png)

Bạn có thể chọn mục **techniques** để tìm hiểu thêm về các kỹ thuật và ngữ cảnh liên quan đến phát hiện này.

![VPC](/images/2/2.3/2.3.2/e3.png)
