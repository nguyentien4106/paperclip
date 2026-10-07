---
name: lead-pipeline
description: Schema dữ liệu lead, các trạng thái pipeline, tiêu chí chấm điểm ưu tiên và quy tắc khử trùng lặp dùng chung cho mọi agent của EdexaCore. Dùng khi tạo, cập nhật, chuyển giao hoặc báo cáo về lead trường học.
---

# Lead pipeline của EdexaCore

## Schema CSV (UTF-8, có header, đúng thứ tự cột)

| Cột | Bắt buộc | Ghi chú |
| --- | --- | --- |
| `lead_id` | ✓ | `<mã-tỉnh>-<cấp>-<số thứ tự>`, vd `HN-THCS-0042`. Không đổi sau khi tạo |
| `ma_truong` |  | Mã trường chính thức nếu được công bố |
| `ten_truong` | ✓ | Tên đầy đủ, đúng như trên nguồn chính thức |
| `cap_hoc` | ✓ | `TH` / `THCS` / `THPT` / `LIEN_CAP` |
| `loai_hinh` | ✓ | `cong_lap` / `tu_thuc` / `quoc_te` / `khac` |
| `tinh_thanh` | ✓ | Tên tỉnh/thành theo đơn vị hành chính hiện hành |
| `xa_phuong` |  | Xã/phường/đặc khu |
| `dia_chi` |  |  |
| `website` |  | Website/fanpage **chính thức** |
| `email_truong` |  | Email công khai của trường |
| `sdt_truong` |  | Số điện thoại công khai của trường |
| `nguoi_lien_he` |  | Họ tên người được công bố công khai (vd Hiệu trưởng) |
| `chuc_vu` |  | Hiệu trưởng / Phó HT / Phụ trách CNTT / Giáo vụ ... |
| `kenh_lien_he` | ✓ | `email` / `phone` / `zalo` / `fanpage` — kênh công khai tốt nhất |
| `nguon_url` | ✓ | URL nơi tìm thấy thông tin liên hệ |
| `ngay_xac_minh` | ✓ | `YYYY-MM-DD` |
| `quy_mo` |  | Số lớp/học sinh nếu được công bố |
| `tin_hieu` |  | Tín hiệu cá nhân hoá có nguồn (thành tích, hoạt động chuyển đổi số...) |
| `diem_uu_tien` | ✓ | 0–100, theo bảng dưới |
| `trang_thai` | ✓ | Xem vòng đời bên dưới |
| `ghi_chu` |  | Ngày gửi, lần chạm, tóm tắt phản hồi |

## Vòng đời trạng thái

```
new → researched → drafted → contacted → replied → demo_scheduled → onboarding → active
                                   ↘ no_response (sau 3 lần chạm)
                    bất kỳ bước nào ↘ not_now (hẹn lại ngày cụ thể) | do_not_contact
```

- `do_not_contact` là **vĩnh viễn**: không bao giờ soạn tin mới cho lead này hoặc cho cùng email/SĐT.
- `not_now`: ghi ngày được phép liên hệ lại trong `ghi_chu`.

## Chấm điểm ưu tiên (gợi ý ban đầu — CEO điều chỉnh)

| Tiêu chí | Điểm |
| --- | --- |
| Có email hoặc SĐT công khai của trường | +25 |
| Có tên người liên hệ trong Ban giám hiệu được công bố | +15 |
| Tư thục / liên cấp / quốc tế (ra quyết định nhanh) | +20 |
| Có dấu hiệu chuyển đổi số (website cập nhật, tin bài về CNTT, giải thưởng) | +15 |
| Quy mô lớn (≥ 30 lớp) | +10 |
| Có tín hiệu cá nhân hoá cụ thể | +10 |
| Board có quan hệ / được giới thiệu | +5 |

## Khử trùng lặp

Khoá chính: `ma_truong` nếu có; nếu không thì `ten_truong` (chuẩn hoá: bỏ dấu, viết thường,
bỏ tiền tố "Trường") + `xa_phuong` + `tinh_thanh`. Đồng thời so trùng `email_truong` và
`sdt_truong` với tất cả lô trước, đặc biệt với danh sách `do_not_contact`.

## Lưu trữ

- Mỗi lô là một artifact CSV trên issue của lô đó.
- CEO duy trì document `lead-registry` trên project "Pipeline trường học": bảng tổng hợp theo tỉnh/cấp/trạng thái và danh sách `do_not_contact` (chỉ lưu email/SĐT/tên trường, không lưu thêm dữ liệu cá nhân).

## Chỉ số báo cáo hằng tuần

Đã nghiên cứu · Đã soạn · Đã gửi · Phản hồi (%) · Demo · Onboarding · Kích hoạt · Từ chối —
chia theo tỉnh, cấp học, loại hình.
