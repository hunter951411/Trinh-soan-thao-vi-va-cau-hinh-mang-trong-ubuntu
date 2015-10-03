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

Sử dụng lệnh route để thiết lập đường đi
• Xem đường đi hiện tại
– route -n
• Đặt cửa khẩu mặc định (default gateway)
– route add default gw ip-getway {interface-name}
– route add default gw 192.168.1.1 eth0
Thực hành
• Cấu hình tạm thời cho máy tính X
– IP 172.16.19.100+X
– Netmask: 255.255.255.0
• Kiểm tra nối kết với máy tính kế bên Y
– ping 172.16.19.100+Y
• Kiểm tra nối kết với gateway 172.16.19.1
– ping 172.16.19.1
• Kiểm tra nối kết với Proxy 172.16.2.100
– ping 172.16.2.100
Thực hành
• Thêm cửa khẩu mặc định 172.16.19.1
– sudo route add default gw 172.16.19.1
• Kiểm tra lại nối kết với DNS Server 172.16.1.2
– Ping 172.16.1.2
• Kiểm tra lại nối kết với Proxy 172.16.1.100
– ping 172.16.1.100

Cấu hình IP tĩnh
• Thông tin về cấu hình IP lưu trong file /etc/network/interfaces:
# Cấu hình IP tĩnh cho giao diện eth0
auto eth0
iface eth0 inet static
address 192.168.1.2
netmask 255.255.255.1.0
gateway 192.168.1.1
• Khởi động lại dịch vụ mạng để lấy cấu hình mới
– sudo /etc/init.d/networking restart
Thực hành
• Dùng phần mềm nano để biên soạn file
/etc/network/interfaces
– sudo nano /etc/network/interfaces
• Bổ sung các thông tin sau:
auto eth0
iface eth0 inet static
Address 172.16.19.100+X
Netmask 255.255.255.0
Gateway 172.16.19.1

Cấu hình IP động
• Thông tin về cấu hình IP lưu trong file /etc/network/interfaces:
# Cấu hình IP động cho giao diện eth0
# Chỉ thay từ khóa static bằng dhcp
auto eth0
iface eth0 inet dhcp

Tắt/mở giao diện mạng
• Tắt giao diện eth0
– sudo ifconfig eth0 down
• Mở giao diện eth0
– sudo Ifconfig eth0 up
– Sẽ lấy lại cấu hình lưu trong /etc/network/interfaces

Xác định DNS server
• Server phân giải tên miền (DNS server) cấu hình trong tập tin /etc/resolv.conf
search domain1
domain2
nameserver dns-server-ip1
nameserver dns-server-ip1
• Nếu chỉ đưa tên máy tính sẽ lần lượt tự động gán thêm phần mở rộng domain1, donaim2 thành tên
đầy đủ trước khi phân giải thành địa chỉ IP

Thực hành (1)
• Ping đến proxy với tên proxy.cit.ctu.edu.vn
– ping proxy.cit.ctu.edu.vn
• Ping đến DNS Server có địa chỉ 172.16.99.2
• Cấu hình DNS server là 172.16.99.2
– Mở file /etc/resolv.conf
• sudo nano /etc/resolv.conf
– Sửa đổi tập tin resolv.conf để chỉ chứa một dòng
• nameserver 172.16.99.2
• Ping đến proxy với tên proxy.cit.ctu.edu.vn

Thực hành (2)
• Ping đến Proxy với tên không có domain
– ping proxy
• Thêm vào đầu file /etc/resolv.conf dòng sau
– search cit.ctu.edu.vn
• Ping đến Proxy với tên không có domain
– ping proxy



Cấu hình Proxy
• Đặc tả trong tập tin /etc/apt/apt.conf
• Có chứng thực người dùng
– Acquire::http::Proxy "http://user:pass@proxy-host:port/";
– Acquire::ftp::Proxy "http://user:pass@proxy-host:port/";
• Không chứng thực người dùng
– Acquire::http::Proxy "http://proxy-host:port/";
– Acquire::ftp::Proxy "http://proxy-host:port/";
