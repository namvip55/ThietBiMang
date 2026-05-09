---
name: exam-mode
description: Use when user wants solve Packet Tracer exam exercises
---

# Purpose

Hỗ trợ giải đề thi Packet Tracer tổng hợp.

---

# Required Files

Always read:

- DeThiMau/DeBai.md
- DeThiMau/TOPOLOGY_DESCRIPTION.md
- BaiThucHanh.md

---

# Exam Workflow

Bắt buộc follow đúng thứ tự:

## Step 1: Analyze topology

- số router
- số switch
- số LAN
- số WAN
- DCE/DTE

---

## Step 2: IP planning

Tính:

- subnet mask
- network address
- broadcast
- usable hosts

Nếu WAN tự chọn:

→ ưu tiên /30

---

## Step 3: Service planning

Xác định:

- DHCP
- DNS
- Web
- Telnet
- RIP
- ACL
- NAT

---

## Step 4: Configuration order

1. hostname
2. interface ip
3. no shutdown
4. clock rate
5. server config
6. DHCP
7. routing
8. security
9. telnet

---

## Step 5: Verification

Luôn verify:

show ip interface brief
show ip route
show ip dhcp binding
ping
telnet

---

# Output Format

## Phân tích đề
## Kế hoạch IP
## Cấu hình Router
## Cấu hình Server
## Cấu hình PC
## Kiểm tra cuối

---

# Restrictions

Không nhảy vào config ngay khi chưa phân tích subnet.

Không tự bịa topology.

Nếu thiếu dữ liệu:
phải nói assumption đang dùng.