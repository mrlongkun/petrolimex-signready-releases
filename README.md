# Petrolimex SignReady ✒️

[![Version](https://img.shields.io/badge/Version-v2.0.1-EA6022?style=for-the-badge&logo=git)](https://github.com/mrlongkun/petrolimex-signready-releases/releases/latest)
[![Platform](https://img.shields.io/badge/Platform-Windows%20x64-0072CE?style=for-the-badge&logo=windows)](https://github.com/mrlongkun/petrolimex-signready-releases)
[![Framework](https://img.shields.io/badge/.NET-10.0%20WPF-512BD4?style=for-the-badge&logo=dotnet)](https://dotnet.microsoft.com/)
[![Tests](https://img.shields.io/badge/Tests-278%20Passed-10B981?style=for-the-badge)](https://github.com/mrlongkun/petrolimex-signready-releases)

**Petrolimex SignReady** là ứng dụng desktop chuyên dụng dành cho cán bộ công nhân viên Petrolimex, hỗ trợ tự động kiểm tra, rà soát thể thức văn bản Word (`.docx` / `.doc`) và chèn thẻ định vị (Key) mỏ neo phục vụ ký số điện tử trên hệ thống **eOffice**.

---

## 📥 Liên kết tải về (Phiên bản mới nhất)

| Bộ cài đặt | Dung lượng | Trường hợp sử dụng | Tải trực tiếp |
|---|---|---|---|
| 🌐 **Online Setup** | ~13.6 MB | Dành cho máy tính có kết nối Internet (tự tải .NET 10 nếu máy thiếu). | [**Tải về (.exe)**](https://github.com/mrlongkun/petrolimex-signready-releases/releases/latest/download/Petrolimex-SignReady-Online-Setup.exe) |
| 💾 **Offline Full Setup** | ~263 MB | Dành cho máy mạng nội bộ không có Internet (đã gồm sẵn .NET 10 & WebView2). | [**Tải về (.exe)**](https://github.com/mrlongkun/petrolimex-signready-releases/releases/latest/download/Petrolimex-SignReady-Offline-Full-Setup.exe) |

> 📌 **Xem toàn bộ các phiên bản:** [Danh sách Releases trên GitHub](https://github.com/mrlongkun/petrolimex-signready-releases/releases)

---

## 🚀 Điểm mới nổi bật trong Bản v2.0.1

- 🌙 **Giao diện Tối (Dark Mode):** Chuyển đổi giao diện Sáng / Tối mượt mà, tự nhớ cấu hình.
- ⚡ **Tự động cập nhật trực tuyến:** Nâng cấp ngầm qua gói vá vi sai Delta chỉ **1.57 MB**.
- 🗄️ **CSDL SQLite bền vững:** Lưu tập trung tại `C:\SignReady\Data\petrolimex_signready.db` dùng chung cho mọi tài khoản máy tính, tự động sao lưu an toàn.
- 💻 **Bộ cài đặt WiX Wizard mới:** Thêm tùy chọn tạo shortcut Desktop / Start Menu và tự khởi chạy sau khi hoàn tất.
- 📖 **Ngăn kéo Hướng dẫn sử dụng:** Thiết kế lại Drawer 3 thẻ trực quan kèm tìm kiếm tức thì.

---

## ✨ Chức năng cốt lõi

1. **Kiểm tra OpenXML độc lập:** Tự phân tích nhị phân OpenXML, **không cần cài Microsoft Word** đối với `.docx`, tốc độ quét < 800ms.
2. **Chống phân mảnh thẻ ký (Run Normalization):** Tự động hàn gắn các thẻ Key bị Word chia cắt nhiều Run XML, đảm bảo eOffice nhận diện 100%.
3. **Wizard Chuẩn hóa 5 bước:** Dẫn dắt sửa lỗi trực quan, lưu bản nháp `_BanNhap.docx` hoặc xuất `_SignReady.docx` (**không bao giờ ghi đè tệp gốc**).
4. **Quản trị danh mục & Nhập Excel:** Quản lý Người ký, Đơn vị; nhập Excel mẫu với cơ chế Transaction an toàn.
5. **Nhật ký thao tác (Audit Trail):** Ghi vết lịch sử từng phiên kèm mã băm **SHA-256**, hỗ trợ lọc và xuất CSV.

---

## 🏷️ Bảng danh mục Thẻ ký số (Key SignReady)

| Thẻ mỏ neo | Mục đích sử dụng | Ví dụ hợp lệ |
|---|---|---|
| `[So]` | Vị trí số phát hành văn bản (Bắt buộc với văn bản Có số) | `Số: [So]/PLX-TCKT` |
| `[Ngay] [Thang] [Nam]` | Ngày tháng năm ban hành văn bản | `ngày [Ngay] tháng [Thang] năm [Nam]` |
| `[KySo<username>]` | Vị trí ký số chính của lãnh đạo | `[KySotranvan.a]` |
| `[Nhay<username>]` | Vị trí ký số nháy của chuyên viên (đặt trước Nơi nhận) | `[Nhaynguyen.b]` |

---

## 📖 Quy trình sử dụng nhanh (4 Bước)

1. **Tiếp nhận:** Kéo thả tệp Word vào ứng dụng ➔ Bấm **Kiểm tra điều kiện**.
2. **Đánh giá:** Đọc kết quả Đạt SignReady (Xanh), Cần xem lại (Vàng) hoặc Bị chặn (Đỏ).
3. **Chuẩn hóa:** Bấm **Bắt đầu Chuẩn hóa** ➔ Thực hiện tuần tự qua Wizard 5 bước.
4. **Xuất tệp:** Bấm **Xuất tệp SignReady** ➔ Mở tệp kết quả bằng Word kiểm tra trực quan lần cuối trước khi trình ký trên eOffice.

---

## 🔒 Cam kết An toàn thông tin

- Nguyên tắc **Offline-First**: 100% quá trình xử lý diễn ra trong RAM máy trạm, **tuyệt đối không gửi tài liệu lên Internet**.
- Ứng dụng chỉ chuẩn hóa cấu trúc tệp Word; **không lưu trữ mã PIN, khóa bí mật PKI hay chứng thư số**.

---

## 📞 Hỗ trợ kỹ thuật

* **Đơn vị phát triển:** Bộ phận Kỹ thuật & Chuyển đổi số — Petrolimex Đồng Nai.
* **Cổng thông tin:** [hotrochxdplxdn.netlify.app](https://hotrochxdplxdn.netlify.app/)
* **Báo cáo lỗi:** Tạo [Issue trên GitHub](https://github.com/mrlongkun/petrolimex-signready-releases/issues).

---
*Bản quyền © 2026 Tập đoàn Xăng dầu Việt Nam (Petrolimex).*
