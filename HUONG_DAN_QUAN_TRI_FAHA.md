# Hướng dẫn quản trị sản phẩm Yến Sào FaHa

Website vẫn là website tĩnh, tải nhanh và không cần máy chủ riêng. Decap CMS cung cấp trang quản trị; GitHub lưu lịch sử nội dung; Netlify tự cập nhật website sau mỗi lần xuất bản.

## 1. Thiết lập một lần

### Bước 1: Đưa website lên GitHub

1. Đăng nhập GitHub và tạo repository mới, ví dụ `faha-website`.
2. Chọn repository riêng tư nếu bạn không muốn người khác xem mã nguồn.
3. Tải toàn bộ nội dung trong thư mục deploy này lên nhánh `main`. `index.html` phải nằm ngay ở thư mục gốc của repository.
4. Không tải nguyên file ZIP vào repository. Cần giải nén ZIP và tải các file, thư mục bên trong.

### Bước 2: Kết nối project Netlify hiện tại với GitHub

1. Mở project đang phục vụ tên miền `yensaofaha.com` trên Netlify.
2. Vào **Project configuration > Build & deploy > Continuous deployment > Repository**.
3. Chọn liên kết repository GitHub vừa tạo.
4. Chọn nhánh `main`.
5. Để trống **Build command** và đặt **Publish directory** là `.`.
6. Chạy deploy và kiểm tra `https://yensaofaha.com` vẫn hoạt động bình thường.

Kết nối đúng project Netlify hiện tại sẽ giữ nguyên tên miền, HTTPS và cấu hình Search Console.

### Bước 3: Bật Netlify Identity và Git Gateway

1. Vào **Project configuration > Identity** và chọn **Enable Identity**.
2. Đặt **Registration preferences** thành **Invite only**.
3. Trong phần **Services**, bật **Git Gateway**.
4. Vào danh sách người dùng Identity và mời đúng email dùng để quản trị website.
5. Mở email mời, tạo mật khẩu, sau đó truy cập `https://yensaofaha.com/admin/`.

Git Gateway đang được Netlify đánh dấu là tính năng cũ. Nếu tài khoản Netlify không còn nút bật Git Gateway, cần chuyển cấu hình đăng nhập sang GitHub trực tiếp; dữ liệu sản phẩm và giao diện quản trị hiện tại vẫn được giữ nguyên.

## 2. Thêm sản phẩm mới

1. Truy cập `https://yensaofaha.com/admin/` và đăng nhập.
2. Chọn **Sản phẩm FaHa**.
3. Chọn **Danh sách sản phẩm**.
4. Mở đúng nhóm: **Yến chưng nóng**, **Signature FaHa**, **Set quà yến tinh chế** hoặc **Cháo yến**.
5. Chọn **Thêm sản phẩm** trong nhóm đó.
6. Nhập tên, giá hiển thị, mô tả, ảnh, nhãn và các thông tin ngắn.
7. Chọn **Xuất bản**.

Netlify sẽ tự deploy. Không cần tạo ZIP hoặc kéo thả website lại. Thông thường chỉ cần chờ trạng thái deploy chuyển sang **Published**, sau đó tải lại website.

## 3. Sửa giá hoặc thay ảnh

1. Mở sản phẩm trong đúng nhóm.
2. Sửa trường **Giá hiển thị** hoặc chọn ảnh mới.
3. Giữ cách ghi giá thống nhất, ví dụ `55.000đ / hũ`, `585.000đ` hoặc `Liên hệ`.
4. Chọn **Xuất bản**.

Ảnh mới được lưu trong `images/uploads/` và chỉ tải khi khách mở đến khu vực chứa sản phẩm đó.

## 4. Lưu ý an toàn

- Chỉ mời email quản trị đáng tin cậy.
- Không để chế độ đăng ký Identity ở trạng thái công khai.
- Không đổi tên các nhóm dữ liệu trong `data/products.json`.
- Nên dùng ảnh JPG, PNG hoặc WebP dưới 5 MB, chiều ngang khoảng 1.200 đến 1.600 px.
- Mọi thay đổi đều có lịch sử trên GitHub và danh sách deploy trên Netlify, nên có thể khôi phục phiên bản trước nếu nhập nhầm.

## 5. Các đường dẫn quan trọng

- Website: `https://yensaofaha.com`
- Quản trị: `https://yensaofaha.com/admin/`
- Dữ liệu sản phẩm: `data/products.json`
- Ảnh quản trị tải lên: `images/uploads/`
