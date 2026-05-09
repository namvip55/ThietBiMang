--------------------------------------------------------------------------------
BÀI THỰC HÀNH SỐ 1: CẤU HÌNH CƠ BẢN CHO ROUTER
Mục tiêu: Giúp người học làm quen với giao diện dòng lệnh (CLI) và các chế độ làm việc của router
.
Các bước thực hiện chi tiết:
Khởi động thiết bị: Bật công tắc nguồn để khởi động router
.
Bỏ qua chế độ thiết lập tự động: Khi màn hình hiển thị câu hỏi vào "Setup mode", nhấn tổ hợp phím Ctrl + C để bỏ qua
.
Truy cập chế độ người dùng (User mode): Nhấn phím Enter. Lúc này, dấu nhắc lệnh sẽ hiển thị là Router>
.
Truy cập chế độ đặc quyền (Privilege mode):
Từ User mode, gõ lệnh enable
.
Dấu nhắc lệnh sẽ chuyển từ > sang # (Router#)
.
Mẹo nhỏ: Bạn có thể gõ en? để xem các lệnh bắt đầu bằng "en" hoặc gõ ena rồi nhấn phím Tab để tự động hoàn thiện lệnh
.
Truy cập chế độ cấu hình toàn cục (Global config mode):
Từ Privilege mode, gõ lệnh configure terminal
.
Dấu nhắc lệnh chuyển sang Router(config)#
.
Mẹo nhỏ: Có thể gõ nhanh conf + Tab và t + Tab để nhập lệnh
.
Thoát về chế độ đặc quyền: Từ Global config mode, gõ lệnh exit để trở về dấu nhắc #
.
Thoát về chế độ người dùng: Từ Privilege mode, gõ lệnh disable để trở về dấu nhắc >
.
Lưu ý quan trọng: Quá trình truy cập phải thực hiện theo đúng thứ tự tuần tự: User mode => Privilege mode => Global config mode. Bạn không thể đi tắt trực tiếp từ User mode lên Global config mode
.

--------------------------------------------------------------------------------
BÀI THỰC HÀNH SỐ 2: CẤU HÌNH CÁC THÔNG SỐ CƠ BẢN CHO ROUTER
Yêu cầu: Đổi tên router và thiết lập thông điệp chào mừng
.
Các bước thực hiện chi tiết:
Đặt tên cho Router (Hostname):
Truy cập vào chế độ Global config mode.
Sử dụng lệnh: hostname [tên_muốn_đặt]
.
Ví dụ: Router(config)# hostname R1
.
Cấu hình thông điệp biểu ngữ (Banner motd):
Cũng tại chế độ Global config mode, sử dụng câu lệnh: banner motd # [thông điệp] #
.
Ví dụ: R1(config)# banner motd # chao mung ban den voi router cua toi #
.
Lưu ý: Thông điệp phải được bắt đầu và kết thúc bằng cùng một ký tự đặc biệt (ví dụ dấu # hoặc *)
.

--------------------------------------------------------------------------------
BÀI THỰC HÀNH SỐ 3: CẤU HÌNH GÁN IP CHO CÁC CỔNG TRÊN ROUTER VÀ PC
Yêu cầu: Cấu hình địa chỉ IP cho cổng Gigabit Ethernet của Router và các máy tính (PC) trong mạng
.
Các bước thực hiện chi tiết:
1. Cấu hình trên Router:
Bước 1: Vào chế độ cấu hình cổng giao tiếp bằng lệnh: interface GigabitEthernet 0/0 (trong Global config mode)
.
Bước 2: Thêm mô tả cho cổng (tùy chọn): description [nội dung mô tả]
.
Ví dụ: R(config-if)# description Day la cong GigaEthernet
.
Bước 3: Gán địa chỉ IP và Subnet mask: ip address [địa_chỉ_IP] [subnet_mask]
.
Ví dụ: R(config-if)# ip address 192.168.1.1 255.255.255.0
.
Bước 4: Kích hoạt cổng: Sử dụng lệnh no shutdown
. Khi cổng được bật thành công, các chấm trạng thái trên sơ đồ sẽ chuyển sang màu xanh
.
2. Cấu hình trên PC (ví dụ PC0):
Bước 5: Click chuột trái vào biểu tượng PC0 để mở cửa sổ cấu hình
.
Bước 6: Chọn thẻ Desktop trên thanh thực đơn
.
Bước 7: Chọn mục IP Configuration và nhập các thông số sau ở chế độ Static (Tĩnh)
:
IP Address: 192.168.1.2 (hoặc theo sơ đồ)
.
Subnet Mask: 255.255.255.0
.
Default Gateway: 192.168.1.1 (Địa chỉ IP cổng Router)
.
Bước 8: Lặp lại các bước từ 5 đến 7 cho các máy tính còn lại (PC1, PC4...) với địa chỉ IP tương ứng
.
Kết quả cần đạt: Các cổng mạng trên Router hoạt động (màu xanh), Router và các PC có thể liên lạc được với nhau thông qua địa chỉ IP đã gán
.
--------------------------------------------------------------------------------
BÀI THỰC HÀNH SỐ 4: THỰC HÀNH BẢO MẬT CHO ROUTER (ĐẶT MẬT KHẨU VÀ BẺ KHÓA)
4.1. Đặt mật khẩu cho router
Yêu cầu: Đặt mật khẩu cho cổng Console, mật khẩu Privilege và mã hóa mật khẩu. Các bước thực hiện:
Đặt mật khẩu Console: Giúp bảo vệ quyền truy cập trực tiếp qua cáp console.
Đặt mật khẩu cho chế độ đặc quyền (Enable password):
Mã hóa tất cả mật khẩu trên router: Sử dụng chuẩn MD7 để che giấu mật khẩu trong file cấu hình.
4.2. Bẻ khóa cho router (Password Recovery)
Kịch bản: Người quản trị quên mật khẩu và cần truy cập lại vào router mà không làm mất cấu hình cũ
. Các bước thực hiện:
Khởi động và ngắt quãng: Tắt/Bật nguồn router. Khi router đang tải hệ điều hành (hiện dãy dấu #), nhấn tổ hợp phím Ctrl + Break để vào chế độ Rom monitor (rommon 1 >)
.
Thay đổi thanh ghi: Bỏ qua việc load cấu hình cũ lúc khởi động.
Khôi phục cấu hình: Sau khi router khởi động lại (không hỏi mật khẩu), vào Privilege mode và copy cấu hình từ NVRAM vào RAM.
Đặt mật khẩu mới: Tiến hành đặt lại mật khẩu Console và Enable như mục 4.1
.
Trở về chế độ khởi động mặc định: Trả thanh ghi về giá trị ban đầu để router load cấu hình khi khởi động sau này.
Lưu cấu hình: R1# copy running-config startup-config
.

--------------------------------------------------------------------------------
BÀI THỰC HÀNH SỐ 5: CẤU HÌNH DỊCH VỤ ĐIỀU KHIỂN TỪ XA TELNET CHO ROUTER
Mục tiêu: Điều khiển router từ xa qua mạng mà không cần dùng kết nối console trực tiếp
.
Các bước thực hiện:
Cấu hình cơ bản: Thiết lập IP cho cổng Router (ví dụ Fa0/0) và IP cho PC kết nối cùng mạng (tham khảo Lab 3)
.
Thiết lập mật khẩu Enable: Bắt buộc phải có mật khẩu này để đăng nhập từ xa (tham khảo Lab 4)
.
Cấu hình mật khẩu Telnet (VTY):
Cấu hình dịch vụ Telnet nâng cao (tùy chọn):
Khai báo domain: R1(config)# ip domain-name cisco
.
Tạo tài khoản: R1(config)# username toanday password duytoan
.
Cho phép đăng nhập bằng tài khoản cục bộ:
Truy cập từ PC: Vào PC > Desktop > Command Prompt, gõ lệnh: PC> telnet [Địa_chỉ_IP_Router] (ví dụ: telnet 192.168.2.2)
.

--------------------------------------------------------------------------------
BÀI THỰC HÀNH SỐ 6: GIAO THỨC CDP (CISCO DISCOVERY PROTOCOL)
Mục tiêu: Tìm hiểu các thiết bị lân cận của Cisco và cách quản lý thông tin kết nối
.
Các bước thực hiện:
Bật/Tắt CDP ở chế độ toàn cục (Global):
Bật: R1(config)# cdp run
.
Tắt: R1(config)# no cdp
.
Bật/Tắt CDP trên từng cổng (Interface):
Truy cập cổng (ví dụ Se0/0/0): R1(config)# interface se0/0/0.
Bật: R1(config-if)# cdp enable
.
Tắt (thường dùng cho cổng nối với PC/Thiết bị không phải Cisco): R1(config-if)# no cdp enable
.
Các lệnh kiểm tra:
Xem thông tin CDP chung: R1# show cdp (mặc định gửi gói tin mỗi 60s, thời gian tồn tại 180s)
.
Xem danh sách lân cận: R1# show cdp neighbors
.
Xem chi tiết thông tin láng giềng: R1# show cdp neighbors detail
.

--------------------------------------------------------------------------------
BÀI THỰC HÀNH SỐ 7: ĐỊNH TUYẾN TĨNH (STATIC ROUTE)
Kịch bản: Mô hình mạng gồm 3 router (RA, RB, RC) kết nối nối tiếp. Cần thiết lập đường đi để các PC ở các mạng khác nhau có thể thấy nhau
.
Các bước thực hiện định tuyến chi tiết:
Cấu hình trên Router RA: Thiết lập đường đi tới các mạng của RB và RC.
Tới mạng RB (192.168.1.0/24) qua cổng kế tiếp là RB (172.16.2.2): RA(config)# ip route 192.168.1.0 255.255.255.0 172.16.2.2
.
Tới mạng RC (173.16.0.0/16) qua RB (172.16.2.2): RA(config)# ip route 173.16.0.0 255.255.0.0 172.16.2.2
.
Cấu hình trên Router RB:
Tới mạng RA (10.0.0.0/8) qua RA (172.16.1.1): RB(config)# ip route 10.0.0.0 255.0.0.0 172.16.1.1
.
Tới mạng RC (173.16.0.0/16) qua RC (11.2.2.2): RB(config)# ip route 173.16.0.0 255.255.0.0 11.2.2.2
.
Cấu hình trên Router RC:
Tới mạng RB (192.168.1.0/24) qua RB (11.1.1.1): RC(config)# ip route 192.168.1.0 255.255.255.0 11.1.1.1
.
Tới mạng RA (10.0.0.0/8) qua RB (11.1.1.1): RC(config)# ip route 10.0.0.0 255.0.0.0 11.1.1.1
.
Kiểm tra và xác nhận:
Sử dụng lệnh show ip route để xem bảng định tuyến (đường tĩnh có ký hiệu chữ S)
.
Sử dụng lệnh ping từ các PC để kiểm tra thông suốt giữa các mạng
.
Lưu ý: Thay vì dùng địa chỉ IP của trạm kế tiếp (Next hop), bạn cũng có thể dùng tên cổng cục bộ của chính router đó để gửi gói tin ra (ví dụ: Serial 0/0/0)
.
--------------------------------------------------------------------------------
BÀI THỰC HÀNH SỐ 8: GIAO THỨC DHCP (DYNAMIC HOST CONFIGURATION PROTOCOL)
Mục tiêu: Cấu hình router tự động cấp phát địa chỉ IP cho các máy tính (PC) trong mạng
.
Các bước thực hiện chi tiết:
Cấu hình IP cho Router: Gán địa chỉ IP cho cổng kết nối với mạng LAN (ví dụ cổng fa0/0 hoặc fa0/1) và kích hoạt cổng bằng lệnh no shutdown
.
Cấu hình DNS Server (trên Server-PT):
Chọn DNS SERVER > thẻ Services > mục DNS
.
Chuyển DNS Service sang On
.
Nhập tên miền (ví dụ: cisco.com) vào ô Name, địa chỉ IP (ví dụ: 1.1.1.1) vào ô Address, chọn loại A Record và nhấn Add
.
Cấu hình DHCP Server trên Router:
Tạo bể cấp phát IP (DHCP Pool):
Loại trừ IP tĩnh (tùy chọn): Ngăn router cấp các địa chỉ IP đã dùng cho thiết bị cố định (ví dụ từ .1 đến .10): Router(config)# ip dhcp excluded-address 192.168.1.1 192.168.1.10
.
Cấu hình nhận IP tự động trên PC:
Vào từng PC > Desktop > IP Configuration.
Tích chọn DHCP. Nếu thành công, các ô IP Address, Subnet Mask và Gateway sẽ tự động được điền
.
Kiểm tra trên Router: Sử dụng lệnh show ip dhcp binding để xem danh sách các địa chỉ IP đã được cấp phát cho các thiết bị
.

--------------------------------------------------------------------------------
BÀI THỰC HÀNH SỐ 9: GIAO THỨC RIP (ROUTING INFORMATION PROTOCOL)
Mục tiêu: Giúp các mạng khác nhau có thể liên lạc được với nhau thông qua giao thức định tuyến RIPv1 hoặc RIPv2
.
Các bước thực hiện chi tiết:
Cấu hình IP cơ bản: Đặt IP cho tất cả các cổng LAN, WAN trên các Router và IP tĩnh cho các PC theo sơ đồ
.
Cấu hình RIP trên Router (ví dụ Router R1):
Kích hoạt giao thức RIP: R1(config)# router rip
.
Khai báo các mạng kết nối trực tiếp:
Nâng cấp lên RIPv2 (tùy chọn): Để sử dụng các tính năng ưu việt hơn, gõ thêm lệnh version 2 trong chế độ cấu hình RIP
.
Tối ưu hóa định tuyến: Nên tắt cơ chế tự động tổng hợp đường mạng để tránh thiếu chính xác: R1(config-router)# no auto-summary
.
Kiểm tra:
Sử dụng lệnh show ip route để xem bảng định tuyến (các đường học được qua RIP có ký hiệu chữ R)
.
Sử dụng chế độ Simulation để theo dõi đường đi của gói tin giữa các PC
.

--------------------------------------------------------------------------------
BÀI THỰC HÀNH SỐ 10: GIAO THỨC EIGRP (INTER-GATEWAY ROUTING PROTOCOL)
Mục tiêu: Sử dụng EIGRP (thay thế cho IGRP cũ) để thiết lập định tuyến cho mô hình mạng lớn
.
Các bước thực hiện chi tiết:
Cấu hình cơ bản: Thiết lập IP cho các cổng Router và PC. Chú ý các kết nối Serial cần cấu hình clock rate nếu cần thiết
.
Cấu hình EIGRP trên các Router:
Bật giao thức với chỉ số AS (phải giống nhau trên các router): R1(config)# router eigrp 100
.
Khai báo mạng kèm theo Wildcard mask: R1(config-router)# network 192.168.1.0 0.0.0.255
.
Tắt tính năng tự động tổng hợp: no auto-summary
.
Điều chỉnh băng thông (Bandwidth): Để thay đổi cách tính toán đường đi tốt nhất, truy cập vào cổng interface và gán giá trị bandwidth: R1(config-if)# bandwidth 64 (đơn vị Kbps)
.
Quảng bá Interface Loopback: Tạo interface ảo để giả lập các mạng khác và đưa vào EIGRP:
Kiểm tra:
Xem quan hệ láng giềng: show ip eigrp neighbors
.
Xem bảng cấu trúc mạng: show ip eigrp topology
.

--------------------------------------------------------------------------------
BÀI THỰC HÀNH SỐ 11: GIAO THỨC OSPF (OPEN SHORTEST PATH FIRST)
Mục tiêu: Cấu hình định tuyến OSPF và điều chỉnh các thông số để lựa chọn đường đi tối ưu
.
Các bước thực hiện chi tiết:
Thiết lập IP: Cấu hình địa chỉ IP cho tất cả thiết bị theo mô hình
.
Cấu hình OSPF trên Router:
Khởi tạo OSPF với Process ID: R1(config)# router ospf 1
.
Khai báo mạng, Wildcard mask và phân vùng (Area): R1(config-router)# network 192.168.10.0 0.0.0.3 area 0
.
Bầu chọn Designated Router (DR): Đặt độ ưu tiên cho cổng để quyết định router nào làm DR: R1(config-if)# ip ospf priority 50
.
Điều chỉnh thông số Cost: OSPF chọn đường dựa trên Cost thấp nhất. Có thể thay đổi trực tiếp: R1(config-if)# ip ospf cost 200
.
Quảng bá định tuyến (Redistribution):
Quảng bá đường mặc định: default-information originate
.
Quảng bá các route từ giao thức khác (như RIP) vào OSPF: R1(config-router)# redistribute rip subnets
.
Kiểm tra cấu hình:
Xem bảng định tuyến OSPF: show ip route ospf
.
Kiểm tra thông số trên interface: show ip ospf interface [tên_cổng]
.
--------------------------------------------------------------------------------
BÀI THỰC HÀNH SỐ 12: CẤU HÌNH ACL (ACCESS-LIST)
Mục tiêu: Kiểm soát lưu lượng mạng bằng cách cho phép hoặc từ chối các gói tin dựa trên địa chỉ IP và giao thức
.
12.1. Cấu hình ACL trên Router R1 (Chặn truy cập Web)
Yêu cầu: Cấm mạng 192.168.1.0/24 truy cập Web Server 192.168.20.254 qua cổng 80 (www)
.
Truy cập vào cổng kết nối với mạng LAN:
Áp dụng ACL vào cổng (chiều đi vào router):
Định nghĩa quy tắc chặn (Extended ACL):
(Lưu ý: Luôn cần lệnh permit ip any any ở cuối vì ACL có quy tắc ngầm định là deny all)
.
12.2. Cấu hình ACL trên Router R2 (Chặn truy cập mạng)
Yêu cầu: Cấm mạng 192.168.1.0/24 truy cập đến toàn bộ mạng 192.168.20.0/24
.
Định nghĩa ACL chuẩn (Standard ACL) bằng tên:
Áp dụng vào các interface (chiều đi ra khỏi cổng):

--------------------------------------------------------------------------------
BÀI THỰC HÀNH SỐ 13: CẤU HÌNH GIAO THỨC NAT (STATIC NAT)
Mục tiêu: Ánh xạ 1-1 giữa IP nội bộ và IP công cộng để ẩn địa chỉ gốc
.
Các bước thực hiện chi tiết:
Cấu hình interface nội bộ (Inside):
Cấu hình interface bên ngoài (Outside):
Thiết lập ánh xạ NAT tĩnh: Ánh xạ IP LAN 172.16.16.1 sang IP Public 64.100.50.1.
Kiểm tra bảng NAT:

--------------------------------------------------------------------------------
BÀI THỰC HÀNH SỐ 14: CẤU HÌNH VLAN (INTER-VLAN)
Mục tiêu: Chia switch vật lý thành các phân đoạn mạng ảo độc lập
.
Các bước thực hiện chi tiết:
Tạo VLAN và đặt tên:
Gán cổng vào VLAN:
Cấu hình địa chỉ IP quản lý cho VLAN (SVI):

--------------------------------------------------------------------------------
BÀI THỰC HÀNH SỐ 15: CẤU HÌNH VTP VÀ TRUNKING
Mục tiêu: Quản lý VLAN tập trung và cho phép dữ liệu nhiều VLAN đi qua một kết nối duy nhất
.
15.1. Cấu hình VTP (VLAN Trunking Protocol)
Trên VTP Server:
Trên VTP Client:
15.2. Cấu hình đường Trunk
Trên Switch: Thiết lập các cổng nối giữa Switch-Switch hoặc Switch-Router thành cổng Trunk.
Trên Router (Inter-VLAN Routing - Sub-interfaces):

--------------------------------------------------------------------------------
BÀI THỰC HÀNH SỐ 16: CẤU HÌNH SPANNING-TREE (STP)
Mục tiêu: Ngăn chặn vòng lặp trong sơ đồ mạng có kết nối dự phòng
.
Các bước thực hiện chi tiết:
Kích hoạt chế độ Spanning Tree:
Thiết lập Root Bridge cho VLAN: Sử dụng giá trị priority thấp nhất để ép switch làm Root (mặc định là 32768).
Kiểm tra trạng thái các cổng:
Các trạng thái cổng quan trọng cần quan sát: FWD (Forwarding - Chuyển tiếp) và BLK (Blocking - Bị khóa)
.