# Báo cáo nhóm

Báo cáo ngắn, tối đa 2 trang. Số liệu chi tiết nằm trong các file hồ sơ; ở đây chỉ dẫn lại con số chính. Mọi con số tính từ cột `_simulated` đều có nhãn `[simulated]`.

## 1. Thông tin nhóm

- **Tên nhóm:** GREEN
- **Lớp:** L3B
- **Repo nhóm:** `K5-L3B-DAY13-GREEN-LaunchEconomics`
- **Thành viên:** xem chi tiết tại [TEAM.md](../../TEAM.md)
  1. Võ Thị Phương Nhung (`2A202603918`, TV1 — nhánh `nhungvo`)
  2. Nguyễn Tiến Đạt (`2A202603922`, TV2 — nhánh `dat`)
  3. Nguyễn Minh Phúc (`2A202603894`, TV3 — nhánh `phuc`)
  4. Nguyễn Đức Hải (`2A202603899`, TV4 — nhánh `haind`)

## 2. Mục tiêu và cách tiếp cận

Mục tiêu của bài lab là dựng bộ **hồ sơ launch v0** (Gate 2a) cho trợ lý hoàn phí của LogiX-VN từ mẫu dữ liệu giả lập 1.200 yêu cầu (1.624 lần chạy) nhằm trả lời bốn câu hỏi: có đáng chạy không, nhân viên có dùng không, khi hỏng xử lý thế nào, và thiết kế pilot ra sao để ra được quyết định.

Nhóm làm việc song song qua 5 checkpoint (CP1–CP5) trên 4 nhánh Git riêng, tuân thủ nguyên tắc mỗi file đầu ra chỉ có một người giữ chính; các thành viên khác chạy script tính độc lập (`src/lab13.py`, `src/tv2_cp5_tinh_so.py`, `src/tv3_tinh_so.py`, `src/tv4_tinh_so.py`), tạo file bàn giao và đối chiếu chéo số liệu trước khi gộp PR vào `main`.

## 3. Giải pháp

- **Nhiệm vụ A (Mô hình chi phí):** Cài đặt 3 hàm A1 (đạt `1,20 · 1,25 · 1,25`) và `mo_hinh(...)` trong [src/lab13.py](../../src/lab13.py), tính đủ token và tool trên mọi lần chạy kể cả lần lỗi, cộng chi phí xem lại/làm lại từ cột `_simulated`, tách theo 4 loại yêu cầu (A3) và cộng chi phí cố định 40 triệu đ/tháng (A4). Kết quả tại [bang_chi_phi.md](bang_chi_phi.md).
- **Nhiệm vụ B (Bảng độ nhạy):** Gọi lại `mo_hinh(...)` cho 9 kịch bản đơn (B1), 1 kịch bản cặp (B2), chi phí cả hệ thống theo giới hạn 1–3 lần chạy (B3) và kịch bản xem lại 100% trong phạm vi (B4). Kết quả tại [bang_chi_phi.md](bang_chi_phi.md).
- **Nhiệm vụ C (Bảng lỗi và khắc phục):** TV1 và TV2 gắn nhãn độc lập 20 ca lỗi theo 5 loại Google PAIR; TV3 dùng `src/tv3_cp3_dong_thuan.py` so khớp, sau đó ghép bảng khắc phục đo được 5 ca của TV4 vào [bang_loi.md](bang_loi.md).
- **Nhiệm vụ D (Kế hoạch pilot):** Tính đủ cỡ mẫu D1(a–e) với `ICC = 0,02`, trả lời 5 câu kiểm tra tách tác động D2, lấy tỉ lệ mở lại hiện tại làm căn cứ đặt 4 luật dừng đủ 4 vế NẾU – TRONG – THÌ – KHÔNG THÌ trong [pilot_plan.yaml](pilot_plan.yaml).
- **Nhiệm vụ E (Chỉ số, rủi ro và hồ sơ launch v0):** Tính thử 3 chỉ số E1, đề xuất thêm 1 chỉ số dùng (TV2) và 1 chỉ số an toàn (TV3), thiết kế 12 event có `trace_id` gốc và lập bảng 3 rủi ro kinh tế trong [chi_so.md](chi_so.md); tổng hợp hồ sơ một trang bảy mục tại [ho_so_launch_v0.md](ho_so_launch_v0.md).

## 4. Kết quả

- **Kinh tế (A, B):** Chi phí mỗi việc thành công toàn mẫu là **4.472 đ** `[simulated]`, gấp **16,3 lần** hoá đơn token + tool (274,7 đ/yêu cầu); giờ nhân viên chiếm 92,5% (làm lại 51,8%, xem lại 40,7% `[simulated]`). Trong phạm vi `noi_dia + hang_nang` (982/1.200 yêu cầu), chi phí là **3.414 đ** và khi cộng cố định 40 triệu đ/tháng thành **4.599 đ = 0,38×** mức 12.000 đ ở 45.000 yêu cầu/tháng (5.784 đ = 0,48× ở nửa khối lượng; hoà vốn ~6.212 yêu cầu/tháng `[simulated]`). Ba yếu tố nhạy nhất: làm lại ×2 (**+51,8%**), xem lại ×2 (**+40,7%**), lương +25% (**+23,1%**) `[simulated]`. Giới hạn **2 lần chạy** rẻ nhất cho cả hệ thống (**6.901.220 đ** `[simulated]`). Xem lại 100% lên **11.743 đ = 0,98×** (hoặc **12.415 đ = 1,03×** nếu làm lại 15,3 phút `[simulated]`).
- **Lỗi (C):** Đồng thuận gắn nhãn độc lập **20/20 = 100%** (kappa 1,00; phân bố 4 · 5 · 4 · 4 · 3); đủ 5 ca khắc phục (1, 20, 18, 4, 17) với event, ngưỡng và vai trò phụ trách rõ.
- **Pilot và chỉ số (D, E):** Chia theo nhân viên **20 + 20**, phân tầng theo 12 depot, chấp nhận **MDE 6 điểm** (`n = 859/nhóm`, DE 6,96, `m ≥ 299`; power còn **0,64** ở mức 5 điểm), ngày quyết định `2027-01-18`. Trong đợt chạy thử (không có đối chứng): chỉ số chính **82,83%** (92,26% phạm vi), bỏ qua gợi ý **27,12%** (21,09% phạm vi), mở lại 7 ngày **4,25%** (3,97% phạm vi; riêng `hang_nang` 8,23%), trung bình xem lại **5,03 phút/lượt** `[simulated]`.
- **Đề xuất cuối trong [ho_so_launch_v0.md](ho_so_launch_v0.md):** **Go có điều kiện** cho pilot `noi_dia + hang_nang` (bắt đầu `2026-12-07`), gắn 5 điều kiện kiểm tra trước và trong pilot (sửa khoá chống trùng ca 20/7, ký chấp nhận MDE 6 điểm, bật đủ 12 event thay cột `_simulated`, giảm xem lại theo bậc 100% → 50% → 25%, và theo dõi riêng `hang_nang`).
- **Duyệt chéo Gate 2a:** Bản tự chấm mô phỏng hội đồng tại [phieu_cham.md](phieu_cham.md) đạt **30/30** (Go có điều kiện); nhóm tiếp tục cập nhật nếu có thêm phản hồi từ nhóm hội đồng khác.

## 5. Khó khăn và cách xử lý

- **Rủi ro xung đột file khi 4 người làm song song:** Xử lý bằng quy ước mỗi file đầu ra có đúng một người giữ chính; các thành viên khác nộp file bàn giao (`tv2_cp3/4/5_ban_giao.md`, `tv3_ban_giao.md`, `tv4_ban_giao.md`) rồi merge từng checkpoint.
- **Cỡ mẫu chia cụm không đủ cho mức chênh 5 điểm:** 20 nhân viên/nhánh có trần `c / ICC = 1.000 < 1.251`, 6 depot/nhánh có trần 300. Nhóm tính rõ giới hạn D1(b–d), chuyển sang MDE 6 điểm (D1e) và nêu minh bạch con số bất lợi power 0,64 để Giám đốc vận hành ký chấp nhận.
- **Khác biệt cấu trúc `trace_id` và thiếu event cho ca 7:** Khi rà soát CP5, TV2 phát hiện `logix_runs.csv` tạo 1.624 `trace_id` riêng cho 1.200 yêu cầu và 11 event ban đầu chưa bắt trực tiếp tin nhắn `"đã hoàn"` (ca 7). Nhóm thống nhất quy ước 1 `trace_id` gốc/yêu cầu kèm `request_id` và bổ sung event thứ 12 `refund_notification_sent`.
- **Đảm bảo tính độc lập ở CP3:** Hai bộ nhãn độc lập được chốt từ đề gốc; nhóm lưu riêng commit từng bộ nhãn (`45ce63c`, `fc2dd2f`) và đối chiếu tự động bằng `src/tv3_cp3_dong_thuan.py`.

## 6. Tổng hợp đóng góp

Chi tiết đóng góp và mã commit của từng thành viên nằm trong [TEAM.md](../../TEAM.md) và 4 báo cáo cá nhân:

| Thành viên | Vai trò chính | File giữ / bàn giao chính |
| --- | --- | --- |
| Võ Thị Phương Nhung (`2A202603918`, TV1) | Viết code `src/lab13.py` (A1–A2, B1–B4), gắn nhãn độc lập 1, D1(a), chỉ số chính | `src/lab13.py`, `tv1_cp3_nhan_da_dien.md`, [2A202603918_VoThiPhuongNhung.md](2A202603918_VoThiPhuongNhung.md) |
| Nguyễn Tiến Đạt (`2A202603922`, TV2) | Kiểm số & giữ `bang_chi_phi.md` (A1–A4, B1–B4), gắn nhãn độc lập 2, D1(b–d), E1 dùng + event `trace_id` + rà soát CP5 | `bang_chi_phi.md`, `tv2_cp3/4/5_ban_giao.md`, `src/tv2_cp5_tinh_so.py`, [2A202603922_NguyenTienDat.md](2A202603922_NguyenTienDat.md) |
| Nguyễn Minh Phúc (`2A202603894`, TV3) | A3, B3, giữ `bang_loi.md` & tính đồng thuận CP3, D1(e) & D2, chỉ số an toàn & rủi ro kinh tế E2 | `bang_loi.md`, `tv3_ban_giao.md`, `src/tv3_tinh_so.py`, `src/tv3_cp3_dong_thuan.py`, [2A202603894_NguyenMinhPhuc.md](2A202603894_NguyenMinhPhuc.md) |
| Nguyễn Đức Hải (`2A202603899`, TV4) | A4, B2, B4, bảng khắc phục 5 ca, giữ `pilot_plan.yaml`, `chi_so.md`, `ho_so_launch_v0.md` và tổng hợp hồ sơ | `pilot_plan.yaml`, `chi_so.md`, `ho_so_launch_v0.md`, `tv4_ban_giao.md`, `src/tv4_tinh_so.py`, [2A202603899_NguyenDucHai.md](2A202603899_NguyenDucHai.md) |

## 7. Hạn chế và hướng cải thiện

- **Dữ liệu giả lập và chưa có đối chứng:** Hai cột phút xem lại/làm lại mang đuôi `_simulated` và đợt chạy thử 2 tuần không có nhóm đối chứng. Hướng cải thiện: bật đủ 12 event ngay tuần 1 pilot để thay bằng số đo thật và chỉ đánh giá tác động nhân quả sau bước 0.50 (`2027-01-18`).
- **Độ nhạy lực thống kê và rủi ro `hang_nang`:** Thiết kế 20 + 20 chỉ đạt power 0,64 nếu hiệu ứng thật là 5 điểm, còn `hang_nang` đang có tỉ lệ mở lại 8,23%. Hướng cải thiện: nếu `hang_nang` kém đối chứng ≥ 2 điểm ở bước 0.25 thì thu hẹp ngay về `noi_dia`.
- **Đóng gói code một lệnh:** Hiện bảng A3 và D1 chạy qua `src/tv3_tinh_so.py` và `src/tv4_tinh_so.py` trong khi `src/lab13.py` vẫn còn 2 dòng `# TODO`; cần gộp nốt vào `src/lab13.py` để một lệnh `python lab13.py` in đủ A, B và D1.

## 8. Tài liệu tham khảo

- Erol và cộng sự, *Cost-of-Pass: An Economic Framework for Evaluating Language Models*, https://arxiv.org/abs/2504.13359
- Google PAIR, *People + AI Guidebook*, chương "Errors + Graceful Failure", https://pair.withgoogle.com
- Tài liệu `statsmodels`, lớp `NormalIndPower` (mục `stats.power`)
- Tài liệu Lab 13: [docs/du_lieu_va_cong_thuc.md](../../docs/du_lieu_va_cong_thuc.md) và [docs/Lab13_Huong_dan_chi_tiet_buoi_chieu.md](../../docs/Lab13_Huong_dan_chi_tiet_buoi_chieu.md)
