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

###1.4.1 Lệnh di chuyển con trỏ

| Lệnh di chuyển con trỏ |
|------------------------|
| h  – sang trái 1 space |
| e  – sang phải 1 space |
| w  – sang phải 1 từ |
| b  – sang trái 1 từ |
| k  – lên 1 dòng |
| j  – xuống 1 dòng |
| )  – cuối câu |
| (  – đầu câu |
| }  – đầu đoạn văn |
| {  – cuối đoạn văn |

###1.4.2 Lệnh xóa

| Lệnh xóa |
|----------|
| dw  – xóa 1 từ |
| d^  – xóa ký tự từ con trỏ đến đầu dòng |
| d$  – xóa ký tự từ con trỏ đến cuối dòng |
| 3dw  – xóa 3 từ |
| dd  – xóa dòng hiện hành |
| 5dd  – xóa 5 dòng |
| x  – xóa 1 ký tự |

###1.4.3 Lệnh thay thế

| Lệnh thay thế |
|---------------|
| cw  – thay thế 1 từ |
| 3cw  – thay thế 3 từ |
| cc  – dòng hiện hành |
| 5cc  – 5 dòng |

###1.4.4 Nhóm lệnh tìm kiếm

| Nhóm lệnh tìm kiếm |
|--------------------|
| ?  tìm  trở lên |
| /   tìm  trở xuống |
| */and   tìm từ kế tiếp của and |
| *?and   tìm từ kết thúc là and |
| */nThe   tìm dòng kế bắt đầu bằng The |
| n   tìm hướng xuống |
| N  tìm hướng lên |

###1.4.5 Nhóm lệnh tìm kiếm và thay thế

| Nhóm lệnh tìm kiếm và thay thế |
|--------------------------------|
| :s/text1/text2/g  – thay thế text1 bằng text2 |
| :1.$s/tập tin/thư mục  – thay tập tin bằng thư mục từ hàng 1 |
| :g/one/s/1/g  – thay thế one bằng 1 |

###1.4.6 Nhóm lệnh copy, paste, undo

| Nhóm lệnh copy, paste, undo |
|-----------------------------|
| Để copy ta dùng lệnh y và để paste ta dùng lệnh p |
| y$  – copy từ vị trí hiện tại của cursor đến cuối cùng |
| yy  – copy toàn bộ dòng tại vị trí cursor |
| 3yy  – copy 3 dòng liên tiếp |
| u  – Undo lại thao tác trước đó |

###1.4.7 Thao tác trên tập tin

| Thao tác trên tập tin |
|-----------------------|
|:w  – ghi vào tập tin |
| :x   – lưu và thoát khỏi chế độ soạn thảo |
| :wq  – lưu và thoát khỏi chế độ soạn thảo |
| :w  – lưu vào tập tin mới |
| :q  – thoát nếu ko có thay đổi |
| :q!  – thoát không lưu |
| :r  – mở tập tin đọc |



#2 Cấu hình mạng trong ubuntu

##2.1 Cấu hình ip tĩnh cho máy ubuntuserver

- Đầu tiên bạn dùng trình soạn thảo vi để mở tập tin /etc/network/interfaces

<img src="http://i.imgur.com/yEYQkYl.png">

- Ở đây mình đang để địa chỉ ip động, nhận DHCP, bạn chỉnh như hình dưới để có địa chỉ ip tĩnh:

<img src="http://i.imgur.com/OaPb2L2.png">

- ở đây cần phải thêm vào:
<ul>
<li>address: địa chỉ ip mà bạn muốn cấu hình tĩnh.</li>
<li>netmask: Chỉ số dải mạng con</li>
<li>gateway: Cổng mà tất cả các host đi ra ngoài mạng internet</li>
<li>network: Dải mạng</li>
<li>broadcast: Địa chỉ ip quảng báo của toàn mạng</li>
</ul>

- Sau đó bạn cần lưu thông tin vừa cấu hình lại, và restart card mạng với câu lệnh:

**/etc/init.d/networking restart**

Để kiểm tra bạn thử ping đến google:

<img src="http://i.imgur.com/kpaBf38.png">

##2.2 Cấu hình ip tĩnh tạm thời.

- Cấu hình địa chỉ ip bạn sử dụng lệnh:

**ifconfig eth0 192.168.221.221 netmask 255.255.255.0**

- Tiếp theo, cấu hình default gateway bạn sử dụng lệnh:

**route add default gw 192.168.221.2 eth0**

- Tuy nhiên, khi bạn restart máy đi thì cấu hình lại bị reset lại/
