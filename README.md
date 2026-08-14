# MNT Taxi Rạch Giá

Trang landing page giới thiệu dịch vụ **MNT Taxi Rạch Giá** — Taxi Rạch Giá ⚡ *An toàn – Êm ái – Thân thiện môi trường 🌿*.

Toàn bộ website là một trang tĩnh duy nhất: **`index.html`** (HTML + CSS + JS được viết gộp trong cùng một file, không dùng framework hay build tool).

## Cấu trúc file `index.html`

```
index.html
├── <head>                         Khai báo meta, title, font, icon
│   ├── meta charset/viewport/theme-color
│   ├── <title>                    "MNT Taxi Rạch Giá | 0924 000 979"
│   ├── Google Fonts               Be Vietnam Pro (100% chuẩn tiếng Việt)
│   ├── Font Awesome 6.5.0 (CDN)   Bộ icon
│   ├── <script> kaspersky-labs    Script bên thứ 3 (chèn kèm, không do site tạo)
│   └── <style>                    CSS nội bộ cho toàn bộ trang (biến màu, header,
│                                   hero, booking form, services, vehicle, footer...)
│
└── <body>
    ├── <header class="header">                Thanh điều hướng cố định (sticky)
    │   ├── .logo                                Logo "Taxi"
    │   ├── nav#nav                              Menu: Trang chủ / Giới thiệu / Dịch vụ /
    │   │                                         Bảng giá / Xe của chúng tôi / Tin tức / Liên hệ
    │   ├── .head-btn.call                        Nút gọi nhanh 0924 000 979
    │   ├── .head-btn.zalo                        Nút chat Zalo
    │   └── button#menu (☰)                      Nút mở menu trên mobile
    │
    ├── <section id="home" class="hero">        Khu vực đầu trang (banner)
    │   ├── .hero-main
    │   │   ├── Tiêu đề "Taxi RẠCH GIÁ ⚡"
    │   │   ├── Tagline "AN TOÀN – ÊM ÁI – THÂN THIỆN MÔI TRƯỜNG 🌿"
    │   │   ├── .benefits (4 mục)                 Xe điện hiện đại / An toàn tuyệt đối /
    │   │   │                                     Thân thiện môi trường / Phục vụ 24/7
    │   │   └── .cars-photo                       Ảnh đội xe (ảnh nhúng base64)
    │   └── #dat-xe .booking                      Form đặt xe
    │       └── form#form
    │           ├── input#name, #phone           Họ tên, số điện thoại
    │           ├── select#vehicle                Loại xe (điện / xăng)
    │           ├── input#time                     Thời gian đón
    │           ├── input#pickup, #dropoff        Điểm đón, điểm đến
    │           ├── textarea#note                 Ghi chú
    │           └── button "ĐẶT XE NGAY"          Submit → gửi qua Zalo (xem phần Script)
    │
    ├── <section id="dich-vu" class="services"> Danh sách dịch vụ
    │   ├── Đưa đón sân bay
    │   ├── Đi tỉnh 2 chiều
    │   ├── Du lịch tham quan
    │   ├── Hợp đồng doanh nghiệp
    │   ├── Sự kiện – cưới hỏi
    │   └── .green-banner                        "Đi taxi xăng – tiết kiệm – giá hợp lý"
    │
    ├── <section id="xe" class="vehicle-section"> Danh sách xe
    │   ├── Nhóm "⚡ Xe điện 4–7 chỗ"
    │   │   └── VinFast VF6 / VF7 / VF8 / Limo Green
    │   └── Nhóm "⛽ Xe xăng 4–7 chỗ"
    │       └── Toyota Vios / Hyundai Accent / Toyota Innova / Kia Carnival
    │       (mỗi xe: ảnh, danh sách đặc điểm, nút "Đặt xe" → cuộn về #dat-xe)
    │
    ├── <footer id="lien-he" class="footer">    Thông tin liên hệ
    │   ├── Khu vực hoạt động                     Rạch Giá – Kiên Giang
    │   ├── Tại sao chọn MNT?                      Xe mới, tài xế thân thiện, giá minh bạch, 24/7
    │   ├── Liên hệ ngay                           0924 000 979
    │   ├── Thanh toán linh hoạt                    Tiền mặt / chuyển khoản / ví điện tử / công nợ
    │   └── Kết nối                                Facebook • Zalo • TikTok • Google Maps
    │
    ├── .float                                   Nút nổi (gọi ngay / Zalo) luôn hiện khi cuộn
    ├── a.topbtn                                  Nút cuộn lên đầu trang
    │
    └── <script> (2 khối JS cuối trang)
        ├── Toggle menu mobile (mở/đóng nav)
        ├── Xử lý submit form đặt xe → tạo nội dung tin nhắn rồi
        │   mở Zalo (zalo.me) kèm nội dung đã điền
        └── Ẩn ảnh (img) nếu tải lỗi (onerror → display:none)
```

## Công nghệ sử dụng

- HTML5 + CSS3 thuần (viết trong `<style>` nội tuyến, dùng CSS variables cho màu chủ đạo)
- JavaScript thuần (vanilla JS), không dùng thư viện/framework
- Ảnh xe được nhúng trực tiếp dạng `base64` trong file (không cần thư mục ảnh riêng)
- Font chữ: Google Fonts "Be Vietnam Pro"
- Icon: Font Awesome (qua CDN)
- Đặt xe: chuyển hướng sang Zalo kèm nội dung đặt xe đã điền (không có backend riêng)

## Chạy thử / triển khai

Vì đây là trang tĩnh 100%, chỉ cần mở trực tiếp `index.html` bằng trình duyệt hoặc deploy thư mục gốc lên Netlify — không cần bước build.
