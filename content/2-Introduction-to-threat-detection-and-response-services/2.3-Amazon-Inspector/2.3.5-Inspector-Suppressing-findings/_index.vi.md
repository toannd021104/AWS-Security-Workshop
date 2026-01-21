---
title: "Inspector - Ẩn phát hiện"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 2.3.5 </b> "
---

Quy tắc ẩn (suppression rules) cho phép bạn loại bỏ khỏi danh sách hiển thị những phát hiện đáp ứng các tiêu chí xác định. Ví dụ, bạn có thể cấu hình một quy tắc để ẩn toàn bộ các phát hiện có mức độ rủi ro thấp, từ đó tập trung nguồn lực vào các vấn đề bảo mật quan trọng hơn.

Các quy tắc ẩn chỉ ảnh hưởng đến cách hiển thị danh sách phát hiện và không tác động đến quá trình Inspector tạo phát hiện mới. Amazon Inspector vẫn tiếp tục quét và ghi nhận đầy đủ các phát hiện như bình thường.

Khi một phát hiện khớp với quy tắc ẩn, trạng thái của phát hiện đó sẽ được đặt là **Suppressed**. Theo mặc định, các phát hiện bị ẩn sẽ không xuất hiện trong danh sách. Tuy nhiên, bạn vẫn có thể xem lại chúng bất kỳ lúc nào trong bảng điều khiển.

#### Cấu hình rule để ẩn các phát hiện mức độ thấp trong môi trường dev

1. Trong bảng điều khiển Inspector, chọn **Suppression rules** từ menu điều hướng bên trái.

2. Chọn **Create Rule** để tạo quy tắc mới.

![VPC](/images/2/2.3/2.3.5/s2.png)

3. Trong trường **Name**, nhập **"Low Severity - Dev Environment"**.

4. Trong trường **Description**, nhập **"Suppress all findings with a low severity score for resources tagged with Development"**.

![VPC](/images/2/2.3/2.3.5/s4.png)

5. Tại mục **Suppression rule filters**, chọn **Severity** và đánh dấu vào mức **Low**, sau đó chọn **Apply**.

![VPC](/images/2/2.3/2.3.5/s5.png)

6. Thêm một bộ lọc khác bằng cách chọn **Resource tag** dưới nhóm EC2. Nhập **"Environment"** cho **key** và **"Development"** cho **value**, rồi chọn **Apply**.

7. Chọn **Save** để lưu quy tắc.

Kết quả:

![VPC](/images/2/2.3/2.3.5/s5b.png)

8. Để xem các phát hiện đã bị ẩn, mở trang [**All Findings**](https://us-east-1.console.aws.amazon.com/inspector/v2/home?region=us-east-1#/findings/all) và chuyển bộ lọc trạng thái từ **Active** sang **Suppressed** trong menu thả xuống.
