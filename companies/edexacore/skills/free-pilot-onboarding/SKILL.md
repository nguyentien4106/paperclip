---
name: free-pilot-onboarding
description: Quy trình đưa một trường từ "đồng ý dùng thử" đến "kích hoạt" trên EdexaCore miễn phí — demo, thiết lập, đào tạo giáo viên, đồng ý của phụ huynh và theo dõi chỉ số kích hoạt. Dùng khi chuẩn bị demo, onboarding hoặc theo dõi sức khoẻ trường đang dùng.
---

# Onboarding trường dùng miễn phí

## Định nghĩa "kích hoạt" (CEO có thể điều chỉnh)

Một trường được coi là **active** khi trong 14 ngày liên tiếp:
- ≥ 5 giáo viên đăng nhập và dùng Teacher CorePilot ít nhất 1 lần/tuần, **và**
- ≥ 1 lớp có dữ liệu thật (bài giao, điểm hoặc chuyên cần).

Mốc trung gian: `account_created` → `first_teacher_value` (giáo viên đầu tiên tạo được sản phẩm
dùng thật với Teacher CorePilot) → `5_teachers_weekly` → `active`.

## Quy trình

### Bước 1 — Chuẩn bị demo (trước buổi demo)
- Đọc lại toàn bộ lịch sử trao đổi và CSV lead.
- Agenda 20–30 phút: 3' bối cảnh trường → 10' Teacher CorePilot với ví dụ đúng cấp học và môn
  học phổ biến → 5' SIS/LMS → 5' dữ liệu & quyền riêng tư → 5' bước tiếp theo.
- Chuẩn bị 3 câu hỏi khám phá: công cụ đang dùng, nỗi đau lớn nhất của giáo viên, ai quyết định.
- Board thực hiện demo; bạn gửi agenda + ghi chú cho board qua interaction.

### Bước 2 — Thiết lập (tuần 1)
- Checklist: người phụ trách phía trường, danh sách lớp, tài khoản giáo viên nhóm thí điểm
  (khuyến nghị bắt đầu 5–10 giáo viên nhiệt tình), dữ liệu mẫu.
- **Trước khi đưa dữ liệu học sinh hoặc bật AI cho học sinh/phụ huynh:** cung cấp cho trường
  mẫu thông báo và mẫu xin đồng ý của cha mẹ/người giám hộ; ghi nhận trường xác nhận đã có
  đồng ý. Chưa có → chỉ dùng tính năng dành cho giáo viên với dữ liệu không định danh.

### Bước 3 — Đào tạo (tuần 1–2)
- Buổi 30 phút cho nhóm giáo viên thí điểm: mỗi người tự làm 1 sản phẩm thật (một đề kiểm tra,
  một giáo án, một bộ nhận xét) ngay trong buổi.
- Gửi hướng dẫn nhanh 1 trang (lấy từ `content-marketer`).

### Bước 4 — Theo dõi (hằng tuần)
- Ghi vào document của trường: số giáo viên hoạt động, số sản phẩm AI tạo ra, lớp có dữ liệu, vướng mắc.
- Trường **đứng im** (không có hoạt động 7 ngày) → soạn tin hỏi thăm cho board + đề xuất buổi hỗ trợ ngắn.
- Đạt `active` → xin phép trường lấy trích dẫn/số liệu cho case study; tạo issue cho `content-marketer`.

### Bước 5 — Mở rộng
- Từ nhóm thí điểm → toàn tổ chuyên môn → toàn trường.
- Hỏi giới thiệu trường khác (cùng xã/phường, cùng cụm chuyên môn) → tạo lead mới với
  `tin_hieu = "được giới thiệu bởi <trường>"` và gửi CEO.

## Phản hồi sản phẩm

Ghi mọi lỗi, yêu cầu tính năng, lời khen kèm tên trường và ngày vào document `product-feedback`
trên project "Kích hoạt & thành công khách hàng"; CEO tổng hợp gửi board hằng tuần.
