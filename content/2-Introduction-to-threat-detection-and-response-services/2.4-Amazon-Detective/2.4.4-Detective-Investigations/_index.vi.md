---
title: "Detective - Điều tra"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 2.4.4 </b> "
---

#### Xác định tài nguyên cần thực hiện điều tra

1. Truy cập **IAM Console** và mở trang **Roles** tại địa chỉ:  
   https://us-east-1.console.aws.amazon.com/iam/home?region=us-east-1#/roles

2. Trong danh sách role, tìm các role có tên bắt đầu bằng chuỗi  
   **`cfn-GuardDutyLabsInfrastructure-GeneralInstanceRole-`**.

3. Nhấp chọn role tương ứng.
   ![VPC](/images/2/2.4/2.4.4/s3.png)

4. Tại trang chi tiết role, sao chép **ARN** hiển thị ở phần đầu trang.  
   ARN này sẽ được sử dụng để khởi tạo quá trình điều tra ở bước tiếp theo.
   ![VPC](/images/2/2.4/2.4.4/s4.png)

---

#### Thực hiện điều tra bằng Amazon Detective

1. Mở trang **Investigations** trong Amazon Detective theo liên kết:  
   https://us-east-1.console.aws.amazon.com/detective/home?region=us-east-1#investigations

2. Trên giao diện Investigations, chọn **Run investigation** ở góc trên bên phải.
   ![VPC](/images/2/2.4/2.4.4/s6.png)

3. Tại bước **Select resource**, Detective cung cấp nhiều cách để khởi chạy điều tra:
   - Điều tra tài nguyên được Detective đề xuất,
   - Điều tra một tài nguyên cụ thể do người dùng chỉ định,
   - Hoặc khởi tạo điều tra từ trang **Detective Search**.

   Trong bài lab này, chọn **Specify an AWS role or user with an ARN**.

4. Ở mục **Select resource type**, chọn **AWS role**.

5. Tại trường **Resource ARN**, dán ARN của role đã sao chép ở phần trước.

6. Nhấn **Run investigation** để bắt đầu quá trình phân tích.
   ![VPC](/images/2/2.4/2.4.4/s11.png)

7. Chờ quá trình điều tra hoàn tất. Thông thường, trạng thái sẽ chuyển sang **Successful** sau khoảng 2–3 phút.
   ![VPC](/images/2/2.4/2.4.4/s12a.png)

8. Nhấp vào **Investigation ID** để xem chi tiết kết quả điều tra.  
   Tùy thuộc vào dữ liệu lịch sử của tài khoản, bạn có thể thấy thông báo như  
   _“We did not observe uncommon behavior…”_ nếu không phát hiện hành vi bất thường.

   Trong trường hợp Detective phát hiện dấu hiệu đáng ngờ, báo cáo sẽ bao gồm phần  
   **Indicators of Compromise (IoCs)** với các thông tin chi tiết liên quan.  
   Phần tóm tắt điều tra giúp làm nổi bật các chỉ báo bất thường trong khoảng thời gian đã chọn, từ đó hỗ trợ:
   - Xác định nhanh nguyên nhân gốc rễ của sự cố bảo mật tiềm ẩn,
   - Nhận diện các mẫu hành vi đáng chú ý,
   - Hiểu rõ những tài nguyên bị ảnh hưởng bởi chuỗi sự kiện bảo mật.

![VPC](/images/2/2.4/2.4.4/s12b.png)
![VPC](/images/2/2.4/2.4.4/s12c.png)

9. Khi mở rộng phân tích với thực thể thuộc loại **IP address**, Detective sẽ hiển thị nhiều **TTP (Tactics, Techniques, and Procedures)** khác nhau liên quan đến hành vi được quan sát.
   ![VPC](/images/2/2.4/2.4.4/s12d.png)

Các loại TTP này giúp cung cấp thêm ngữ cảnh để hiểu rõ bản chất và mức độ nghiêm trọng của các hoạt động được phát hiện trong quá trình điều tra.
![VPC](/images/2/2.4/2.4.4/s12e.png)
