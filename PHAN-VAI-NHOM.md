# PHÂN CÔNG CÔNG VIỆC · LAB 10 · Nhóm Simple (L3B)

**Repo:** `K5-L3B-DAY10-Simple-PoCtoPilotGate1`

| # | Họ và tên | MSSV | Vai | Trưởng nhóm |
|--:|---|---|---|---|
| 1 | Ngô Ngọc Hải | 2A202603939 | **Kỹ sư cổng** | ✓ |
| 2 | Trần Minh Đức | 2A202603977 | **Vận hành và pháp lý** | |
| 3 | Lê Thị Ly | 2A202603989 | **Sản phẩm và kinh doanh** | |

---

## Tóm tắt vai

| Vai | Người | File cầm chính |
|---|---|---|
| Kỹ sư cổng | **Hải** | `lab10/guards.py`, `lab10/monitors.py` |
| Vận hành & pháp lý | **Đức** | `operating_gates.json` mục `operations`+`legal`, `submission/`, `TEAM.md` |
| Sản phẩm & kinh doanh | **Ly** | `acceptance_criteria.json`, `operating_gates.json` mục `business`, Phiếu A, quyết định v1/v2 |

> Cả nhóm cùng đọc `problem-set.md`, cùng pre-mortem, cùng chốt v1/v2. Ai không viết code vẫn đọc trace để chỉ ticket còn hỏng.

---

## Việc theo từng mốc

### Phút 0–15 · Cài đặt
- **Hải** (trưởng nhóm): fork repo, đặt tên đúng dạng, clone, `git config user.name/email`, mời collaborator.
- **Cả nhóm**: `python3 -m unittest discover -s tests` → `Ran 13 tests ... OK`.
- **Đức**: điền bảng thành viên + thông tin nhóm trong `TEAM.md`.

### Phút 15–65 · Khối 1 — Ký tiêu chí (TRƯỚC khi đo)
| Người | Việc |
|---|---|
| **Ly** | Phiếu A câu **1.1, 1.6**; điền `config/acceptance_criteria.json` (5 ngưỡng `required`, `nice_to_have`, `business_ops`, `decision_rule`, `stop_condition`); chạy `python3 -m lab10.criteria sign` + commit/push tiêu chí |
| **Hải** | Phiếu A câu **1.3** (offline metric cho 1 bước) |
| **Đức** | Phiếu A câu **1.2, 1.4** (mục tiêu chị Oanh/chị Hạnh + telemetry production) |
| **Cả nhóm** | Câu **1.5** (chọn a/b/c/d — đáp án đúng là **(b)**) |

### Phút 65–115 · Khối 2A + 2B — Đo, rủi ro, cổng vòng 1, v1
| Người | Việc |
|---|---|
| **Hải** | Câu **2.1** (chạy `eval --suite base --stage base`, ghi mã run) · **2.2** (trace `T-002@55`) · **2.6** (code 2–3 cổng trong `guards.py`) · **2.7** · **2.8** (behavioral test `--adhoc`) |
| **Ly** | Câu **2.3** (bản đồ dữ liệu + ví dụ drift) · **2.9** (mục `business`: trần tiền, ngân sách, phạm vi, ROI) |
| **Đức** | Câu **2.4** (HAZOP ≥ 3 dòng + ≥ 2 dòng ngoài kỹ thuật; checklist 9 nhóm có PIC) · **2.10** (mục `operations`+`legal`, runbook 1–3, giờ cao điểm) |
| **Cả nhóm** | Câu **2.5** pre-mortem 4 lăng kính → chọn 2–3 cổng |
| **Hải + Ly** | Chốt: Hải chạy `python3 -m lab10.checkpoint`; Ly điền cột **v1** ở B8; cả nhóm push |

### Phút 125–200 · Khối 3 — Sự cố (thẻ Sx)
| Người | Việc |
|---|---|
| **Hải** | Nhận thẻ (3 lệnh git) · chạy `grade --incident Sx` **trước khi sửa** · câu **3.1** trace ≥ 2 ticket hỏng · sửa code trong `guards.py` · câu **3.6** thêm monitor mới trong `monitors.py` |
| **Ly** | Câu **3.2** (specification) · điền mục `business` nếu nguyên nhân là tiền/phạm vi · quyết định **v2** |
| **Đức** | Câu **3.3** (giả định môi trường) · phần riêng theo thẻ · runbook 4–5 · cập nhật checklist · điền `submission/submission.json` |
| **Cả nhóm** | Câu **3.1** (tác hại) · **3.4** fault tree trước · **3.5** bảng sửa · **3.7** fault tree sau + risk register |

### Phút 185–240 · V2, demo, nộp
- **Ly**: chốt cột **v2** (C12) + **ba dòng bắt buộc**.
- **Đức**: chạy `python3 -m lab10.check_submission --collect` tới khi in **`ĐỦ THÀNH PHẦN`**; push bài; nhắc mỗi người nộp link trên LMS.
- **Hải**: giữ code/config cuối chạy sạch ở cả 3 mốc (`base · prepared · after`); xử lý lỗi git nếu có.
- **Cả nhóm**: demo 3 mốc + phản biện; mỗi người viết mục cá nhân trong `TEAM.md`.

---

## Cam kết chung
- **Không sửa** file bị khoá hash, bản chụp vòng 1 (`guards_round1.py`, `operating_gates.round1.json`, `round1.lock`), và tiêu chí sau khi ký.
- Mọi ngưỡng/số phải **giải thích được** lúc demo; ký tiêu chí **trước** lần đo đầu tiên.
- `members` trong `submission.json` phải khớp `TEAM.md`: `["NgoNgocHai-2A202603939", "TranMinhDuc-2A202603977", "LeThiLy-2A202603989"]`.
