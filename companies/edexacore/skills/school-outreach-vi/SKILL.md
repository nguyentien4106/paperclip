---
name: school-outreach-vi
description: Cách soạn email, tin nhắn Zalo và kịch bản gọi điện tiếng Việt để giới thiệu EdexaCore tới Ban giám hiệu trường phổ thông, kèm định dạng gói gửi cho người gửi thủ công, nhịp follow-up và quy tắc chống spam. Dùng khi soạn tin tiếp cận, follow-up hoặc trả lời phản hồi của trường.
---

# Tiếp cận trường học bằng tiếng Việt

## 1. Giọng văn

- Trang trọng, ấm áp, tôn trọng: "Kính gửi Thầy/Cô ...", "Trân trọng".
- Gọi theo chức vụ khi biết: "Kính gửi Thầy Nguyễn Văn A — Hiệu trưởng Trường THCS ...".
  Không biết tên → "Kính gửi Ban Giám hiệu Trường ...". Không biết giới tính → dùng "Thầy/Cô".
- Ngắn: email ≤ 150 từ, Zalo ≤ 60 từ. Một lời kêu gọi hành động duy nhất.
- Nói về **lợi ích cho giáo viên và học sinh**, không liệt kê tính năng.

## 2. Cấu trúc email lần 1

1. **Tiêu đề** (≤ 60 ký tự), cụ thể, không giật tít, không viết hoa toàn bộ.
   Vd: `Trợ lý AI miễn phí cho giáo viên Trường THCS <tên>`
2. **Mở đầu cá nhân hoá** bằng `tin_hieu` có nguồn (1 câu). Không có thì dùng cấp học/địa phương.
3. **Giá trị** (1–2 câu) theo cấp học:
   - Tiểu học: giảm thời gian nhận xét học sinh, kết nối phụ huynh.
   - THCS: soạn bài, ra đề và chấm nhanh hơn với Teacher CorePilot.
   - THPT: ôn tập cá nhân hoá cho học sinh, quản lý điểm tập trung.
4. **Miễn phí** (1 câu): "Hiện EdexaCore cho các trường sử dụng miễn phí."
5. **Lời kêu gọi:** hẹn demo online 20 phút **hoặc** link đăng ký — chọn một.
6. **Ký tên** đầy đủ: họ tên, chức danh, EdexaCore, SĐT/email, website.
7. **Dòng từ chối:** "Nếu Thầy/Cô không muốn nhận thêm thông tin từ chúng tôi, xin vui lòng phản hồi 'Từ chối' — chúng tôi sẽ không liên hệ lại."

## 3. Nhịp liên hệ (tối đa 3 lần chạm trong ~14 ngày)

| Lần | Ngày | Kênh | Nội dung |
| --- | --- | --- | --- |
| 1 | D0 | Email (hoặc Zalo/fanpage nếu không có email) | Giới thiệu như trên |
| 2 | D+4 làm việc | Email trả lời trên cùng luồng | 2–3 câu, thêm một lợi ích/ví dụ cụ thể, nhắc lời mời |
| 3 | D+10 làm việc | Gọi điện tới SĐT trường (board thực hiện) hoặc email ngắn | Hỏi có nên liên hệ người khác phù hợp hơn không |

Hết 3 lần không phản hồi → `no_response`. Không gửi vào cuối tuần, ngày lễ, Tết; tránh tuần
kiểm tra cuối kỳ. Khung giờ đề xuất: 7:30–10:30 hoặc 14:00–16:00 ngày làm việc.

## 4. Kịch bản gọi điện (board dùng)

1. Chào, giới thiệu tên và EdexaCore (1 câu). Hỏi xin gặp Thầy/Cô phụ trách chuyên môn hoặc CNTT.
2. Lý do gọi (1 câu) + "nhà trường dùng miễn phí".
3. Hỏi một câu khám phá: "Hiện các thầy cô đang soạn đề, nhận xét học sinh trên công cụ nào ạ?"
4. Đề xuất: gửi tài liệu qua email/Zalo hoặc hẹn demo 20 phút.
5. Bị từ chối → cảm ơn, ghi `do_not_contact`.

## 5. Gói gửi (định dạng bàn giao cho board)

`send-pack-<tỉnh>-<cấp>-<n>.csv`, UTF-8, cột:
`lead_id, kenh, to, subject, body, zalo_text, ghi_chu_cho_nguoi_gui`

`send-pack-<tỉnh>-<cấp>-<n>.md`: bản xem nhanh từng tin nhắn, sắp xếp theo `diem_uu_tien` giảm dần,
đánh dấu ⚠️ những tin cần board kiểm tra thêm (vd: thông tin người liên hệ có thể đã cũ).

Kiểm tra trước khi bàn giao:
- Không có lead `do_not_contact` hoặc trùng email/SĐT với lô trước.
- Mọi chi tiết cá nhân hoá khớp với `tin_hieu` + `nguon_url` trong CSV gốc.
- Không có placeholder chưa thay (`<...>`, `[CẦN BỔ SUNG]`).
- Có dòng từ chối và chữ ký đầy đủ.

## 6. Xử lý phản hồi

| Loại | Hành động |
| --- | --- |
| Quan tâm / muốn demo | Soạn thư xác nhận + 2–3 khung giờ; tạo issue cho `customer-success` |
| Hỏi thêm | Trả lời ngắn từ FAQ; câu nào chưa có trong `edexacore-product` thì hỏi board |
| Chưa phải lúc | Cảm ơn, hỏi thời điểm phù hợp, đặt `not_now` + ngày liên hệ lại |
| Chuyển người khác | Cảm ơn, cập nhật người liên hệ mới, bắt đầu lại từ lần chạm 1 |
| Từ chối / không muốn nhận tin | Thư cảm ơn một dòng (tuỳ chọn), `do_not_contact` ngay |

## 7. Quy tắc chống spam (Nghị định 91/2020/NĐ-CP)

- Danh tính người gửi rõ ràng, nội dung trung thực, luôn có cách từ chối nhận tin.
- Gửi theo lô nhỏ, cá nhân hoá — không gửi hàng loạt cùng một nội dung.
- Không nhắn Zalo/SMS tới số cá nhân không được công bố cho mục đích liên hệ công việc.
- Tôn trọng yêu cầu từ chối ngay lập tức và vĩnh viễn.
