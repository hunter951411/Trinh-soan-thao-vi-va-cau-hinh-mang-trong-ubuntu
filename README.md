# Trinh-soan-thao-vi-va-cau-hinh-mang-trong-ubuntu


#1. Trình soạn thảo vi trong linux.

##1.1 Giới thiệu

- Vi (video interractif) là trình soạn thảo theo trang màn hình mặc định trong linux. Màn hình được xem như một cửa sổ mở trên tập tin. Có khả năng di chuyển con trỏ đến bất kì vị trí nào trên màn hình. Cửa sổ có thể di chuyển tự do trên tập tin. Phần lớn các phím dùng độc lập hoặc kết hợp với phím Shift và Ctrl để tạo ra các lệnh của vi. Khi lệnh bị gõ sai, vi báo hiệu bằng cách nháy màm hình, kêu còi hay thông báo......(Được xây dụng từ chương trình soạn thảo dòng ex). Các ệnh của ex có thể được gọi khi có dấu "." ở cuối màn hình. Vi khồng đồi hỏi nhiều tài nguyên thêm vào đó các chức năng soạn thảo cơ bản. Vi có thể tìm kiếm, thay thế, và kết nối các file và nó có ngôn ngữ macro của chính nó, cũng như một số các đặc điểm bổ sung.

- Trình soạn thảo vi có hai chế độ:
<ul>
<li>Input mode: Văn bản được đưa vào trong tài liệu, có thể chèn hoặc bổ sung văn bản</li>
<li>Command mode: Dịch chuyển tài liệu, trộn các dòng, tìm kiếm.... Thực hiện được mọi chức năng của Command mode trư việc nhập văn bản. Văn bản chỉ có thể được đưa vào trong Input mode</li>
</ul>

##1.2 Khởi động vi

-  Ta dùng lệnh:

| $vi tên_tập_tin |
|-----------------|

Cửa sổ soạn thảo sẽ được mở tại đầu tập tin. Nếu tập tin chưa tồn tại, nó sẽ được tạo ra tự động bằng lệnh ghi. Dòng cuối cùng trên màn hình được dùng vào những công việc sau:
- Vào các lệnh.
- Thống kê.
- Báo lỗi.

Nếu chỉ muốn xem nội dung của tập tin mà không sửa, xóa, hay thêm thông tin, ta dùng lệnh:

| $view tên_tập_tin |
|-------------------|

Để thoát quá trình xem nhấn phím ESC trên góc trái phía trên bàn phím, và gõ :q! rồi ấn Enter.


##1.3 Thoát khỏi vi

- Vi cung cấp 2 option cho phép bạn thoát khỏi vi
<ul>
<li>Thoát ra và lưu lại những thay đổi, nhấn ESC và dùng lệnh :ZZ hoặc :wq</li>
<li>Thoát ra và không lưu lại những thay đổi, nhấn ESC và dùng lệnh :q!</li>
</ul>

- Ngoài ra còn có thể chạy một lệnh SHELL

| :! Lệnh |
|---------|

- Hay gọi SHELL, sau đó chạy lệnh của người dùng, khi kết thúc bấm Ctrl+D để trở lại vi:

|:! sh |
|-------|
| $ Lệnh |
| $ Ctrl+D |

##1.4 Soạn thảo vi.

###1.4.1 Chèn kí tự

- Chèn kí tự trên một dòng:

| a kí_tự ESC |
|-------------|

- Chèn kí tự vào sau vị trí con trỏ

| i kí_tự ESC |
|-------------|


###1.4.3 Xóa văn bản.

- Xóa 1 từ 

| dw |
|----|
         
- Xóa 3 từ 

| 3dw |
|-----|
         
- Xóa dòng hiện hành 

| dd |
|----|

- Xóa 5 dòng 

| 5dd |
|-----|
             
- Xóa 1 kí tự 
  
| x |
|---|
  


