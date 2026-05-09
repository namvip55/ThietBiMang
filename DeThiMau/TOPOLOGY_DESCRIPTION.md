# TOPOLOGY DESCRIPTION

## Tổng quan thiết bị
- 4 Routers:
  - Router0
  - Router1
  - Router2
  - Router3

- 2 Switches:
  - Switch0 (LAN bên trái)
  - Switch1 (LAN bên phải)

- 3 PCs:
  - PC0
  - PC1
  - PC2

- 2 Servers:
  - Server0
  - Server1

---

# Kết nối LAN bên trái

## PC0 → Switch0
- PC0 Fa0
→ Switch0 Fa0/13

## PC1 → Switch0
- PC1 Fa0
→ Switch0 Fa0/15

## Switch0 → Router0
- Switch0 Gig0/2
→ Router0 Gig0/0

---

# Kết nối WAN giữa các Router (Serial)

## Router0 ↔ Router1
- Router0 Se0/3/0
→ Router1 Se0/2/0

Trạng thái:
- Router0 là DCE (biểu tượng đồng hồ)
- Cần cấu hình clock rate tại Router0

---

## Router1 ↔ Router3
- Router1 Se0/1/0
→ Router3 Se0/1/0

Trạng thái:
- Router3 là DCE
- Cần cấu hình clock rate tại Router3

---

## Router1 ↔ Router2
- Router1 Se0/1/1
→ Router2 Se0/0/0

Trạng thái:
- Router1 là DCE
- Cần cấu hình clock rate tại Router1

---

## Router3 ↔ Router2
- Router3 Se0/3/0
→ Router2 Se0/0/1

Trạng thái:
- Router3 là DCE
- Cần cấu hình clock rate tại Router3

---

# Kết nối LAN bên phải

## Router1 → Switch1
- Router1 Gig0/0
→ Switch1 Gig0/1

---

## Switch1 → PC2
- Switch1 Fa0/13
→ PC2 Fa0

---

## Switch1 → Server0
- Switch1 Fa0/12
→ Server0 Fa0

---

## Switch1 → Server1
- Switch1 Fa0/14
→ Server1 Fa0

---

# IP Constraints từ đề bài

## LAN Router0
Router0 Gig0/0:
- IP cố định: 172.20.100.200/19

Thiết bị cùng LAN:
- PC0 → DHCP
- PC1 → DHCP

---

## LAN Router1
Router1 Gig0/0:
- IP cố định: 192.168.1.200/28

Thiết bị cùng LAN:
- PC2 → DHCP
- Server0 → Static IP
- Server1 → Static IP

---

# Server Requirements

## Server0
- Static IP: usable IP đầu tiên
- Enable HTTP/Web Server

## Server1
- Static IP: usable IP thứ hai
- Enable DNS Server
- Create DNS record:

tenmien.net
→ trỏ về IP của Server0

---

# Routing Requirements
- Tất cả routers chạy RIP
- Các mạng LAN + WAN phải quảng bá đầy đủ
- Sau khi cấu hình:
  - PC0 ping PC2 thành công
  - PC1 ping Server0 thành công
  - DNS hoạt động

---

# Security Requirements

## Router0
- Hostname: Router0
- Console password: CNTT
- Enable password: DHDL
- Mã hóa toàn bộ password

---

# Telnet Requirement

Từ PC2:
- Telnet vào Router0
- Truy cập qua IP LAN của Router0:
172.20.100.200