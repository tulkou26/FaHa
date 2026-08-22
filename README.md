# Yến Sào FaHa - bản quản trị sản phẩm

Đây là bản website tĩnh FaHa đã được bổ sung quản trị sản phẩm bằng Decap CMS, Netlify Identity và Git Gateway.

## Nội dung cập nhật

- Thêm **Sữa chua yến sào**, giá **55.000đ / hũ**, tại mục Signature FaHa.
- Cập nhật **Yến viên tự chưng Baby** thành **60.000đ / hũ**.
- Dữ liệu sản phẩm được quản lý tại `data/products.json`.
- Trang quản trị nằm tại `/admin/`.
- Giao diện, nội dung, ảnh và cấu hình SEO còn lại được giữ nguyên từ bản deploy nguồn.

## Chạy thử trên máy

Không mở bằng cách bấm trực tiếp vào `index.html` nếu muốn kiểm tra dữ liệu JSON. Hãy chạy một static server tại thư mục này, ví dụ:

```powershell
python -m http.server 8080
```

Sau đó mở `http://localhost:8080/`.

## Deploy

Website không có build command. Publish directory là `.`. Để Decap CMS tự cập nhật nội dung, project Netlify cần được kết nối với repository GitHub thay vì chỉ deploy bằng cách kéo thả ZIP.

Xem hướng dẫn chi tiết trong `HUONG_DAN_QUAN_TRI_FAHA.md`.
