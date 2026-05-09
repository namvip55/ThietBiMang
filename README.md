# Cisco Packet Tracer Learning System

Hệ thống tài liệu hỗ trợ học tập, thực hành mạng Cisco Packet Tracer và luyện đề thi thực hành.

## 🚀 Mục tiêu
- Nắm vững kiến thức từ cơ bản đến nâng cao (Lab 1 - Lab 16).
- Hiểu rõ bản chất câu lệnh và logic vận hành mạng.
- Tự giải quyết các bài toán thực tế và đề thi tổng hợp.

## 💻 Cài đặt & Chuẩn bị

### 1. Cài đặt Cisco Packet Tracer
Để thực hành các bài lab này, bạn cần cài đặt phần mềm mô phỏng mạng của Cisco:
- **Tải xuống:** Truy cập [Skills For All](https://skillsforall.com/) hoặc [Cisco Networking Academy](https://www.netacad.com/) để tải bản mới nhất (Yêu cầu tài khoản miễn phí).
- **Yêu cầu:** Phiên bản 8.0 trở lên để đảm bảo tính tương thích với các lệnh và tính năng mới.

### 2. Sử dụng Repository
- **Clone repo:** 
  ```bash
  git clone https://github.com/[your-username]/ThietBiMang.git
  ```
- **Mở tài liệu:** Bạn có thể đọc các file `.md` trực tiếp trên GitHub hoặc dùng VS Code để theo dõi hướng dẫn trong khi làm lab.

## 📁 Cấu trúc Repository

### 1. [BaiThucHanh.md](BaiThucHanh.md)
Tài liệu chính chứa 16 bài lab thực hành:
- **Lab 1–3:** Router basic & IP configuration.
- **Lab 4–5:** Security & Telnet.
- **Lab 6:** CDP (Cisco Discovery Protocol).
- **Lab 7:** Static Routing.
- **Lab 8:** DHCP.
- **Lab 9–11:** Routing Protocols (RIP, EIGRP, OSPF).
- **Lab 12–13:** ACL & NAT.
- **Lab 14–16:** Switching (VLAN, VTP, STP).

### 2. [DeThiMau/](DeThiMau/)
Khu vực luyện đề thi mẫu:
- **[DeBai.md](DeThiMau/DeBai.md):** Các yêu cầu kỹ thuật (VLAN, Routing, NAT, Services...).
- **[TOPOLOGY_DESCRIPTION.md](DeThiMau/TOPOLOGY_DESCRIPTION.md):** Mô tả sơ đồ kết nối mạng (Topology) và phân bổ Interface.

## 🛠️ Quy trình thực hành (Recommended)

1. **Học (Learning):** Đi theo thứ tự từ Lab 1 đến Lab 16. Đừng nhảy cóc nếu chưa nắm vững nền tảng.
2. **Hiểu (Understanding):** Tập trung vào việc giải thích *tại sao* dùng lệnh đó thay vì chỉ copy-paste.
3. **Luyện đề (Exam):**
    - Phân tích Topology.
    - Chia Subnet & Quy hoạch IP.
    - Cấu hình Interface (Lưu ý `no shutdown` và `clock rate` cho DCE).
    - Cấu hình Services (DHCP, DNS, Telnet...).
    - Cấu hình Routing & Security.
    - Kiểm tra (Verify) bằng các lệnh `ping`, `show ip route`, `show ip interface brief`.

## 📝 Lưu ý quan trọng
- Luôn ưu tiên Subnet `/30` cho các kết nối WAN links nếu đề bài không chỉ định IP.
- Kiểm tra bảng định tuyến (`show ip route`) thường xuyên để đảm bảo thông suốt mạng.
- Thực hiện `copy running-config startup-config` để lưu cấu hình.

---
*Chúc bạn học tốt và làm chủ kỹ năng networking!*
