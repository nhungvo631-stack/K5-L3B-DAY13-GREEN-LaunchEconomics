# Team

## Thông tin nhóm

- Tên nhóm: GREEN
- Lớp: L3B
- Repo nhóm: `K5-L3B-DAY13-GREEN-LaunchEconomics` (xem [SUBMISSION.md](SUBMISSION.md))
- URL repo, nhánh nộp, commit chốt: https://github.com/nhungvo631-stack/K5-L3B-DAY13-GREEN-LaunchEconomics · nhánh `main` · cập nhật mã commit chốt cuối trên `main` sau khi gộp PR đóng gói (mốc trước đóng gói: `bdf3ee6`)

## Thành viên

| STT | Họ tên | MSSV | Email | GitHub | Vai trò |
| --: | ------ | ---- | ----- | ------ | ------- |
|   1 | Võ Thị Phương Nhung | 2A202603918 | nhungvo631@gmail.com | `@nhungvo631-stack` | Người viết code (`src/lab13.py`) kiêm Người gắn nhãn 1 (TV1) |
|   2 | Nguyễn Tiến Đạt | 2A202603922 | ntdkhongdeptrailam5924@gmail.com | `@duhocsinh4to10` | Người kiểm số kiêm Người gắn nhãn 2 (TV2, giữ `bang_chi_phi.md`) |
|   3 | Nguyễn Minh Phúc | 2A202603894 | nminhphuc.nmp@gmail.com | `MinPhuc` | Người kiểm số (TV3, giữ `bang_loi.md`) |
|   4 | Nguyễn Đức Hải | 2A202603899 | 26ai.haind4@vinuni.edu.vn | `@hainguyen312` | Người giữ hồ sơ (TV4, giữ `pilot_plan.yaml`, `chi_so.md`, `ho_so_launch_v0.md`) |

Bốn vai của lab:

- **Người viết code:** viết và chạy `src/lab13.py`.
- **Người kiểm số:** tính tay một con số để đối chiếu, điền bảng.
- **Người gắn nhãn 1:** đọc đề, theo dõi điều kiện "Xong khi"; gắn nhãn 20 ca độc lập ở CP3.
- **Người gắn nhãn 2, kiêm giữ hồ sơ:** điền `report/team/ho_so_launch_v0.md` từ đầu buổi; gắn nhãn 20 ca độc lập ở CP3.

Đổi người viết code sau giờ giải lao, để ít nhất hai người trong nhóm tự tay tính được chi phí (cả 4 thành viên đều có script tự tính/đối chiếu độc lập trong `src/`).

## Cá nhân

Báo cáo cá nhân của 4 thành viên nằm trong `report/team/` (giữ nguyên file mẫu `report/team/MSSV_HoTen.md`):

- [2A202603918_VoThiPhuongNhung.md](report/team/2A202603918_VoThiPhuongNhung.md)
- [2A202603922_NguyenTienDat.md](report/team/2A202603922_NguyenTienDat.md)
- [2A202603894_NguyenMinhPhuc.md](report/team/2A202603894_NguyenMinhPhuc.md)
- [2A202603899_NguyenDucHai.md](report/team/2A202603899_NguyenDucHai.md)

## VoThiPhuongNhung-2A202603918

### Phần việc phụ trách

- CP1 (A1, A2): cài đặt ba hàm kinh tế chạy lại và `mo_hinh(...)` trong `src/lab13.py`.
- CP2 (B1–B4): bổ sung hàm gọi lại mô hình `in_kich_ban_b(...)` cho 9 kịch bản đơn, kịch bản cặp, giới hạn chạy 1–3 lần và xem lại 100%.
- CP3: gắn nhãn độc lập 20 ca lỗi theo 5 loại Google PAIR (Bộ nhãn độc lập số 1).
- CP4 (D1a): tính cỡ mẫu theo yêu cầu cho baseline 0,70 và mục tiêu +5 điểm.
- CP5: tính thử chỉ số chính và kiểm tra diễn đạt quan sát (không khẳng định nhân quả).

### Đóng góp cụ thể

- Hoàn thiện A1 đạt đủ 3 phép thử (`1,20 · 1,25 · 1,25`) và A2 cho chi phí mỗi việc thành công **4.472 đ** trên 978 việc thành công (`[simulated]`).
- Hoàn thiện B1–B4 trong `src/lab13.py`: B1 đủ 9 kịch bản, B2 **6.543 đ (+46,3%)**, B3 rẻ nhất 2 lần chạy (**6.901.220 đ**), B4 xem lại 100% **11.743 đ** hoặc **12.415 đ** `[simulated]`.
- Chốt Bộ nhãn độc lập số 1 cho 20/20 ca tại `report/team/tv1_cp3_nhan_da_dien.md`.
- Tính D1(a) = **1.251 yêu cầu mỗi nhóm** và chỉ số chính đợt chạy thử **82,83%** (994/1.200), nhấn mạnh chưa có đối chứng.

### Bằng chứng

- Nhánh `nhungvo`: commits `d601b14`, `bddce53`, `5d0f643` (PR #14), `45ce63c` (PR #15), `2bc0a84` (PR #23).
- File: `src/lab13.py`, `report/team/tv1_cp3_nhan_da_dien.md`, `report/team/2A202603918_VoThiPhuongNhung.md`.

## NguyenTienDat-2A202603922

### Phần việc phụ trách

- CP1–CP2: đối chiếu độc lập A1–A2; giữ và tổng hợp `report/team/bang_chi_phi.md` (A1–A4, B1 đủ 9 kịch bản, xếp hạng độ nhạy và ghép B2–B4).
- CP3: gắn nhãn độc lập 20/20 ca lỗi theo Google PAIR (Bộ nhãn độc lập số 2).
- CP4 (D1b–d): tính cỡ mẫu chia cụm theo nhân viên và theo depot, hệ số thiết kế `DE` và giới hạn cỡ mẫu hiệu dụng `c / ICC`.
- CP5: tính thử chỉ số sử dụng, đề xuất chỉ số sử dụng, thiết kế & nối event có `trace_id`, rà soát tính nhất quán toàn bộ 5 file hồ sơ; hỗ trợ hoàn thiện bản nháp `phieu_cham.md`, `group_report.md`, `TEAM.md`.

### Đóng góp cụ thể

- Hoàn thiện `report/team/bang_chi_phi.md` đủ A1–A4 và B1–B4, đủ nhãn `simulated`, khớp 100% với code.
- Chốt 20/20 nhãn lỗi độc lập trong `report/team/tv2_cp3_ban_giao.md`, đạt đồng thuận **20/20 = 100%** cùng TV1 trong `report/team/bang_loi.md`.
- Chứng minh chia 20 nhân viên/nhánh (trần **1.000**) và 6 depot/nhánh (trần **300**) đều nhỏ hơn 1.251 nên không đủ mẫu cho mức chênh 5 điểm, làm căn cứ chuyển sang MDE 6 điểm trong `pilot_plan.yaml`.
- Viết `src/tv2_cp5_tinh_so.py` tính độc lập tỉ lệ bỏ qua gợi ý (**27,12%** toàn mẫu; **21,09%** trong phạm vi; phút xem lại TB **5,03 phút** `[simulated]`), đề xuất chỉ số sử dụng đo kèm tràn tác động, đề xuất chuẩn hoá 1 `trace_id` gốc/yêu cầu và event thứ 12 `refund_notification_sent` cho ca 7 (được TV4 tích hợp vào `chi_so.md` và `ho_so_launch_v0.md`).

### Bằng chứng

- Nhánh `dat`: commits `edf5976` (PR #4), `716345c` (PR #7), `a9e3133` (PR #11), `fc2dd2f` (PR #16), `5e7f94e` (PR #19), `0dd1727` (PR #22), `7b72103` (PR #24).
- File: `report/team/bang_chi_phi.md`, `report/team/tv2_cp3_ban_giao.md`, `report/team/tv2_cp4_ban_giao.md`, `report/team/tv2_cp5_ban_giao.md`, `src/tv2_cp5_tinh_so.py`, `report/team/2A202603922_NguyenTienDat.md`.

## NguyenMinhPhuc-2A202603894

### Phần việc phụ trách

- CP1 (A3): tách chi phí theo 4 loại yêu cầu và tỉ lệ `ok` theo lần thử, đề xuất thu hẹp phạm vi pilot.
- CP2 (B3): phân tích giới hạn 1, 2, 3 lần chạy và tính tổng chi phí cả hệ thống.
- CP3: giữ `report/team/bang_loi.md`, tính đồng thuận hai bộ nhãn độc lập và ghép bảng khắc phục 5 ca của TV4.
- CP4 (D1e, D2): tính cỡ mẫu mức chênh 6 điểm (`m ≥ 299`, power ở 5 điểm) và trả lời 5 câu tách tác động.
- CP5: tính chỉ số an toàn, đề xuất thêm chỉ số an toàn và soạn bảng rủi ro kinh tế E2; dựng UI trình chiếu hỗ trợ duyệt Gate 2a.

### Đóng góp cụ thể

- A3 `[simulated]`: `noi_dia` 2.696 đ (0,22×), `hang_nang` 8.221 đ (0,69×), `quoc_te` 22.515 đ (1,88×; `ok` giảm 30,0% → 11,4% → 2,2%), `doi_tac` 10.215 đ (0,85×); chốt phạm vi `noi_dia + hang_nang`.
- B3 `[simulated]`: giới hạn 2 lần rẻ nhất cho công ty (**6.901.220 đ**), tránh tối ưu riêng CPS ở 1 lần chạy (4.111 đ) vì đẩy thêm 85 ca sang nhân viên.
- CP3: viết `src/tv3_cp3_dong_thuan.py`, tính đồng thuận **20/20 = 100%** (kappa 1,00) và hoàn thiện `report/team/bang_loi.md`.
- D1(e) & D2: **859/nhóm**, DE **6,96**, `m ≥ 299`, nêu rõ con số bất lợi **power ≈ 0,64** nếu tác động thật 5 điểm.
- CP5: mở lại 7 ngày **4,25%** toàn mẫu, **3,97%** phạm vi (`hang_nang` **8,23%**); đề xuất chỉ số mở lại ở ca không xem lại (**4,99%** vs **0,00%** ở ca xem lại và giữ nguyên); soạn 3 dòng rủi ro kinh tế E2 `[simulated]`.

### Bằng chứng

- Nhánh `phuc` / `phuc-*`: commits `b06edcb` (PR #3), `0fea896` (PR #6), `fad2ba0` (PR #9), `d2d7638` (PR #17), `9e56d65` (PR #18), `3b893d6` (PR #21).
- File: `src/tv3_tinh_so.py`, `src/tv3_cp3_dong_thuan.py`, `report/team/tv3_ban_giao.md`, `report/team/bang_loi.md`, `report/team/tv3_bao_cao_ui.html`, `report/team/2A202603894_NguyenMinhPhuc.md`.

## NguyenDucHai-2A202603899

### Phần việc phụ trách

- CP1 (A4): tính chi phí cố định 40 triệu đ/tháng cho phạm vi `noi_dia + hang_nang` ở 45.000 yêu cầu/tháng và nửa khối lượng.
- CP2 (B2, B4): đổi cặp token ×2 + xem lại ×2; kịch bản xem lại 100% và số chuyển tiếp rủi ro kinh tế sang CP5.
- CP3: soạn bảng khắc phục đo được cho 5 loại lỗi kèm 5 ca dự phòng và ngưỡng nền từ dữ liệu.
- CP4: giữ và hoàn thiện `report/team/pilot_plan.yaml` (đủ D1–D2, 4 luật dừng đủ 4 vế, rollback, lịch và ngày quyết định).
- CP5: giữ và tổng hợp `report/team/chi_so.md` và `report/team/ho_so_launch_v0.md` (7 mục, đề xuất Go có điều kiện kèm 5 điều kiện).

### Đóng góp cụ thể

- A4 `[simulated]`: chi phí trong phạm vi + cố định là **4.599 đ = 0,38×** (45.000 yêu cầu/tháng), **5.784 đ = 0,48×** (nửa khối lượng), hoà vốn ~**6.212 yêu cầu/tháng**, cả hệ thống cộng 82 ca nhân viên làm thay là **0,43×**.
- B2 & B4 `[simulated]`: B2 **6.543 đ (+46,3%)**; B4 xem lại 100% là **11.743 đ = 0,98×** (hoặc **12.415 đ = 1,03×** với 15,3 phút làm lại), hoà vốn xem lại ≤ 5,1 phút (4,8 phút).
- CP3: soạn đủ 5 ca khắc phục chính (1, 20, 18, 4, 17) và 5 ca dự phòng; khớp 100% nhãn thống nhất của nhóm.
- CP4–CP5: hoàn thiện `pilot_plan.yaml` đọc sạch bằng `yaml.safe_load`, tổng hợp `chi_so.md` (đủ 12 event `trace_id`, đối chiếu chạy lại cả 3 script của nhóm) và `ho_so_launch_v0.md` với đề xuất **Go có điều kiện** (5 điều kiện có vai trò và hạn kiểm tra).

### Bằng chứng

- Nhánh `haind`: commits `b1bef74` (PR #2), `16b5e4e` (PR #8), `290f265` (PR #12), `66f8577` và `1b30ea5` (PR #20), `5206abe` (PR #25).
- File: `src/tv4_tinh_so.py`, `report/team/tv4_ban_giao.md`, `report/team/pilot_plan.yaml`, `report/team/chi_so.md`, `report/team/ho_so_launch_v0.md`, `report/team/2A202603899_NguyenDucHai.md`.
