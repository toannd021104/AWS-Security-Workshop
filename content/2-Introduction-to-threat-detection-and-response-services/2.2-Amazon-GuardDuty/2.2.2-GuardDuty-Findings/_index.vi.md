---
title: "GuardDuty - Phát hiện bảo mật"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2.2.2 </b> "
---

Một phát hiện của GuardDuty phản ánh một vấn đề bảo mật tiềm ẩn được nhận diện trong môi trường AWS của bạn. GuardDuty tạo phát hiện khi phát hiện các hành vi bất thường có khả năng gây hại. Bạn có thể xem và quản lý các phát hiện này trực tiếp trên trang **Findings** của bảng điều khiển GuardDuty, hoặc thông qua các lệnh CLI và API của GuardDuty.

#### Xem xét một phát hiện trong GuardDuty

1. Điều hướng đến **Findings** trong Amazon GuardDuty bằng cách chọn **Findings** từ bảng điều hướng bên trái.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.2-GuardDuty-Findings/s1.png)

Dưới đây là danh sách các phát hiện trong tài khoản AWS Workshop:

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.2-GuardDuty-Findings/s1b.png)

2. Chọn một phát hiện bất kỳ bằng cách nhấp vào hàng tương ứng. Bảng tóm tắt phát hiện sẽ được hiển thị ở phía bên phải màn hình. Nội dung chi tiết sẽ thay đổi tuỳ theo loại phát hiện.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.2-GuardDuty-Findings/s2.png)

Xem thêm một phát hiện khác trong workshop:

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.2-GuardDuty-Findings/s2b.png)

3. Dành thời gian xem xét nội dung của phát hiện mà bạn đã mở.

#### Hiểu mức độ nghiêm trọng của phát hiện trong GuardDuty

4. Xác định trường **Severity** của phát hiện đã chọn để biết mức độ nghiêm trọng.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.2-GuardDuty-Findings/s4.png)

5. Nếu bạn cần xem hoặc tải phát hiện dưới dạng JSON, hãy chọn **Finding ID** ở đầu phần tóm tắt phát hiện.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.2-GuardDuty-Findings/s5a.png)
![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.2-GuardDuty-Findings/s5b.png)

6. Đóng phần tóm tắt phát hiện bằng cách chọn **X** ở góc trên bên phải.

#### Tìm kiếm và lọc các phát hiện bảo mật của GuardDuty

7. Chọn thanh tìm kiếm với nhãn **Add filter criteria**.

8. Nhập **Severity** vào thanh tìm kiếm và chọn **Severity**. Một menu phụ sẽ xuất hiện với các mức **Low**, **Medium** và **High**.

9. Đánh dấu chọn **High** và nhấp **Apply**. Danh sách phát hiện sẽ được cập nhật để chỉ hiển thị các phát hiện có mức độ nghiêm trọng cao.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.2-GuardDuty-Findings/s9a.png)
![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.2-GuardDuty-Findings/s9b.png)

#### Quản lý các phát hiện bảo mật của GuardDuty

10. Khi đã chọn một phát hiện, mở menu **Actions** ở góc trên bên phải của trang và chọn **Archive** để lưu trữ phát hiện.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.2-GuardDuty-Findings/s10.png)

11. Phát hiện sau khi được lưu trữ sẽ không còn hiển thị trong danh sách hiện tại. Để xem lại, mở menu **Current** và chuyển sang **Archived** để hiển thị các phát hiện đã được lưu trữ.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.2-GuardDuty-Findings/s11a.png)

Kết quả:

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.2-GuardDuty-Findings/s11b.png)

12. Để khôi phục một phát hiện đã lưu trữ, chọn phát hiện đó, mở menu **Actions** và nhấp **Unarchive** để huỷ lưu trữ.

![VPC](/images/2/2.2-Amazon-GuardDuty/2.2.2-GuardDuty-Findings/s2.png)
