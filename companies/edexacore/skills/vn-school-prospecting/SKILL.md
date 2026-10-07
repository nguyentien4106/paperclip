---
name: vn-school-prospecting
description: Quy trình tìm trường tiểu học, THCS, THPT theo tỉnh/thành Việt Nam và xác định đầu mối liên hệ công khai, hợp pháp. Dùng khi nghiên cứu, xác minh hoặc làm giàu dữ liệu lead trường học.
---

# Tìm khách hàng là trường phổ thông tại Việt Nam

## 1. Hiểu cấu trúc quản lý (xác minh lại trước mỗi tỉnh)

- Từ 01/07/2025 Việt Nam vận hành chính quyền địa phương hai cấp (tỉnh và xã), số tỉnh/thành
  được sắp xếp lại. Luôn dùng **tên đơn vị hành chính hiện hành** và kiểm tra lại trên cổng
  thông tin của tỉnh, vì tên xã/phường và cơ quan quản lý có thể đã thay đổi.
- THPT thường do **Sở GD&ĐT** quản lý trực tiếp. Tiểu học và THCS công lập thường thuộc quản lý
  của **UBND cấp xã/phường** (sau khi bỏ cấp huyện). Trường tư thục/liên cấp tự chủ hơn.
- Ghi nhận cơ quan quản lý vào `ghi_chu` — Outreach và CEO cần biết ai có thể ra quyết định.

## 2. Nguồn dữ liệu được phép (theo thứ tự ưu tiên)

1. **Website chính thức của trường** (thường là tên miền `.edu.vn`): trang "Giới thiệu", "Liên hệ", "Ban giám hiệu".
2. **Cổng thông tin Sở GD&ĐT** của tỉnh/thành: danh bạ đơn vị trực thuộc, danh sách trường.
3. **Cổng thông tin UBND tỉnh/xã**: danh bạ cơ quan, đơn vị.
4. **Fanpage chính thức** của trường (có dấu hiệu là trang chính thức: liên kết từ website, tên đầy đủ, hoạt động thường xuyên).
5. Bản đồ/danh bạ doanh nghiệp công khai — chỉ để lấy địa chỉ/SĐT tổng đài của trường, phải đối chiếu với nguồn 1–3.

## 3. Nguồn và hành vi bị cấm

- Danh sách mua bán, dữ liệu rò rỉ, nhóm kín, hồ sơ mạng xã hội cá nhân.
- Đoán email (ghép tên + tên miền) hoặc SĐT cá nhân không được nhà trường công bố cho mục đích liên hệ công việc.
- Thu thập thông tin học sinh, phụ huynh, hoặc ảnh cá nhân.
- Vượt qua đăng nhập, CAPTCHA, hoặc điều khoản sử dụng của website.
- Gửi bất kỳ tin nhắn nào (bạn chỉ nghiên cứu).

**Lý do:** Nghị định 13/2023/NĐ-CP và Luật Bảo vệ dữ liệu cá nhân yêu cầu xử lý dữ liệu cá nhân
có mục đích và căn cứ hợp pháp. Ưu tiên **kênh liên hệ của tổ chức** (email/SĐT của trường) hơn
kênh của cá nhân; tên và chức vụ Ban giám hiệu được trường công bố công khai thì được ghi lại
kèm nguồn để cá nhân hoá lời chào.

## 4. Quy trình cho một lô

1. Xác nhận phạm vi từ issue: tỉnh/thành, cấp học, loại hình, số lượng mục tiêu.
2. Lấy danh sách trường từ nguồn 2–3; nếu không có, tìm theo từ khoá như
   `"trường THCS" <tên xã/phường> <tỉnh>`, `site:edu.vn <tỉnh> tiểu học`.
3. Với mỗi trường, mở website/fanpage chính thức, điền schema trong skill `lead-pipeline`.
4. Ghi `tin_hieu` khi có thông tin cụ thể, có nguồn: đạt chuẩn quốc gia, giải thưởng, tin về
   ứng dụng CNTT/chuyển đổi số, sự kiện sắp tới. Không ghi suy diễn.
5. Khử trùng lặp với các lô trước và danh sách `do_not_contact`.
6. Chấm `diem_uu_tien`, đặt `trang_thai = researched` (hoặc `new` nếu thiếu kênh liên hệ).
7. Kiểm tra chất lượng trước khi bàn giao:
   - 100% bản ghi có `nguon_url` và `ngay_xac_minh`.
   - Không có email/SĐT nào thiếu nguồn.
   - Tối thiểu 70% bản ghi có ít nhất một kênh liên hệ của trường.
8. Upload CSV làm artifact, viết tóm tắt, tạo issue con cho `outreach-rep`.

## 5. Mẹo thực tế

- Nhiều website trường dùng chung một nền tảng cổng thông tin do Sở triển khai — nắm được cấu trúc
  URL của một trường thì áp dụng được cho cả tỉnh.
- Trang "Ban giám hiệu" thường cập nhật chậm: nếu thấy tin bổ nhiệm mới hơn, dùng thông tin mới và ghi cả hai nguồn.
- Khi không tìm được email, SĐT trường + fanpage chính thức vẫn là lead hợp lệ (`kenh_lien_he = phone` hoặc `fanpage`).
