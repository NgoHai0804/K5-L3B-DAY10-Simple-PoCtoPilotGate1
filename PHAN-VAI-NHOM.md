# PHÂN CÔNG CÔNG VIỆC · LAB 10 · Nhóm Simple (L3B)

**Repo:** `K5-L3B-DAY10-Simple-PoCtoPilotGate1`
**Thẻ sự cố đã bốc:** **S4** — *Đêm 11.11: ticket gấp ba, hàng chờ duyệt ngập* (đã copy `incidents/S4/` vào repo; `integrity ok ✅`).

| # | Họ và tên | MSSV | Vai | Trưởng nhóm |
|--:|---|---|---|---|
| 1 | Ngô Ngọc Hải | 2A202603939 | **Kỹ sư cổng** | ✓ |
| 2 | Trần Minh Đức | 2A202603977 | **Vận hành và pháp lý** | |
| 3 | Lê Thị Ly | 2A202603989 | **Sản phẩm và kinh doanh** | |

---

## Tóm tắt vai + file cầm chính

| Vai | Người | File cầm chính | Phiếu |
|---|---|---|---|
| Kỹ sư cổng | **Hải** | `lab10/guards.py`, `lab10/monitors.py`; chạy `eval`, `trace`, `gate`, `checkpoint` | Phiếu A (1.3) · Phiếu B (2.1, 2.2, 2.6–2.8, B7.1–B7.3) · Phiếu C (3.0, 3.1 trace, 3.6) |
| Vận hành & pháp lý | **Đức** | `config/operating_gates.json` (`operations`, `legal`), runbook, `submission/`, `TEAM.md` | Phiếu A (1.2, 1.4) · Phiếu B (2.4: HAZOP + checklist, 2.10, B7.5–B7.6) · Phiếu C (3.3, phần riêng S4, 3.7/C9–C11) |
| Sản phẩm & kinh doanh | **Ly** | `config/acceptance_criteria.json`, `config/operating_gates.json` (`business`), quyết định v1/v2 | Phiếu A (1.1, 1.6) · Phiếu B (2.3, 2.9, B8-v1) · Phiếu C (3.2, C12-v2) |

> Cả nhóm cùng đọc `problem-set.md`, cùng pre-mortem, cùng chốt v1/v2. Ai không viết code vẫn đọc trace để chỉ ticket còn hỏng.

---

## Timeline (mốc → việc chung)

| Mốc | Phút | Việc chung | Phiếu |
|---|---|---|---|
| CP1 | 0–15 | Fork/clone, danh tính Git, test xanh, `TEAM.md` | — |
| CP2 | 15–65 | Viết & **ký tiêu chí trước khi đo** | A |
| CP2A | 65–85 | Đo mốc base, dò rủi ro, pre-mortem | B |
| CP2B | 85–105 | Code 2–3 cổng, đặt cổng number | B |
| CP3 | 105–115 | **Chốt cổng vòng 1**, quyết định **v1** | B (B8) |
| Nghỉ | 115–125 | — | — |
| CP4 | 125–185 | Nhận thẻ S4, phân tích, sửa, **v2** | C |
| CP5 | 185–240 | V2, gom bài, demo, nộp | C (C12) |

---

## 1. CP1 · Phút 0–15 · Cài đặt

- **Hải (trưởng nhóm, phụ trách repo):**
  - Fork repo mẫu → đặt đúng tên `K5-L3B-DAY10-Simple-PoCtoPilotGate1`; giữ Public.
  - `git clone`; **đặt danh tính Git bằng MSSV** và email giả: `git config user.name "2A202603939"` · `git config user.email "2A202603939@example.com"` (không dùng email cá nhân).
  - **Settings → Collaborators**: mời Đức, Ly quyền **Write**.
  - Chạy `python3 -m unittest discover -s tests` → `Ran 13 tests ... OK`.
- **Đức:** điền bảng thành viên + thông tin nhóm trong `TEAM.md`; Hải soát lại.
- **Cả nhóm:** thống nhất 3 vai; mở sẵn `problem-set.md`.

**Xong khi:** repo đúng tên, Public; `origin` trỏ repo của bàn; test `OK`; bảng thành viên `TEAM.md` điền đủ.

---

## 2. CP2 · Phút 15–65 · Khối 1 — Ký tiêu chí (TRƯỚC khi đo)

> Luật vàng: chưa chạy trợ lý lần nào cho tới khi ký.

| Người | Việc |
|---|---|
| **Ly** | Phiếu A câu **1.1** (mục tiêu cấp hệ thống, dựa PRD v1.1 §3), **1.6** (câu tiêu chí "Nếu… thì…", 4 câu soát, 2 câu ranh giới đầu ra). Điền `config/acceptance_criteria.json`: `team` = tên repo, `signed_by`, `required` (pass_rate, pass_k, 3 chỉ số an toàn), `nice_to_have.escalation_rate_max`, `business_ops` (cost, roi, queue_stuck), `stop_condition`, 4 dòng `decision_rule`. Chạy **lệnh 1** `python3 -m lab10.criteria sign` + **commit/push ngay**. |
| **Hải** | Phiếu A câu **1.3** (mục A2 cột "Offline"): chọn **MỘT bước** + offline metric (Thước đo · Dữ liệu · Cách tính). Gợi ý: bước "chọn độ trễ", metric = tỉ lệ `model_override`. Ngồi canh **thứ tự**: ký + commit ký phải **trước** lần `eval` đầu tiên. |
| **Đức** | Phiếu A câu **1.2** (mục tiêu từ chị Oanh + chị Hạnh), **1.4** (telemetry production: khung thời gian + ngưỡng + điểm mù). |
| **Cả nhóm** | Câu **1.5** → đáp án **(b)**. Soát `acceptance_criteria.json` lần cuối trước khi ký. Điền A5 (giờ ký, mã commit ký 7 ký tự, đã push chưa). |

**Xong khi:** Phiếu A A1–A5 điền; `.json` + `.lock` đã push; commit `Sign acceptance criteria` có trên GitHub **trước** mọi `eval`.

---

## 3. CP2A · Phút 65–85 · Đo mốc base + dò rủi ro

| Người | Việc |
|---|---|
| **Hải** | Câu **2.1**: `python3 -m lab10.eval --suite base --stage base --note "baseline"` rồi `python3 -m lab10.gate --run runs/<mã>/report.json`. Ghi mã run vào B1 + B0 dòng 1; đọc khối "kinh doanh và vận hành" + "theo kho và hãng"; nêu lý lẽ **tự chặn / người duyệt / kết hợp**. Câu **2.2**: `python3 -m lab10.trace --suite base --ticket T-002 --seed 55` → điền bảng soát lỗi B2 (T-002@55 là **lỗi chìm**). |
| **Ly** | Câu **2.3**: bản đồ dữ liệu B3 + 1 ví dụ drift trong 3 tháng (REFUND-v3 → v4 ngày 2026-12-01). |
| **Đức** | Câu **2.4**: HAZOP vòng 1 B4 (≥3 dòng + ≥2 dòng ngoài kỹ thuật) + checklist 9 nhóm B5 (mỗi dòng có **PIC có tên**). |
| **Cả nhóm** | Câu **2.5**: pre-mortem **4 lăng kính** B6 (Kỹ thuật · Kinh doanh · Con người & vận hành · Pháp lý), chọn 2–3 lý do thành cổng. |

**Xong khi:** có mã run base; `T-002@55` xếp loại lỗi; pre-mortem đủ 4 lăng kính.

---

## 4. CP2B · Phút 85–105 · Cổng phòng ngừa

| Người | Việc |
|---|---|
| **Hải** | Câu **2.6**: code **2–3 cổng** trong `lab10/guards.py` (`pre_guard` / `write_gate`); chạy `eval --suite base --stage after` + `unittest` để chắc **không ca mới hỏng** → điền B7.1. Câu **2.7**: 2 bước tránh rò rỉ dữ liệu (B7.2). Câu **2.8**: 1 tính chất + 2 ticket hiểm `--adhoc` (B7.3), giữ cho demo. |
| **Ly** | Câu **2.9**: mục `business` trong `config/operating_gates.json` (trần hoàn/ngày, ngân sách/ticket, phạm vi pilot, roi_min) + lý do có số → B7.4. |
| **Đức** | Câu **2.10**: mục `operations` + `legal` (PIC, người duyệt, số người trực, công suất, SLA, điều kiện dừng, kênh báo tin, PII, ghi lỗi hãng) + viết **Runbook 1–3** (B7.5) + mục **Giờ cao điểm** (B7.6). |
| **Cả nhóm** | Soát cổng không chặn nhầm; chốt các con số. |

**Xong khi:** report `base · after` **không có ca mới hỏng**; test `OK`; `operations.pic` không còn trống.

---

## 5. CP3 · Phút 105–115 · Chốt cổng vòng 1 + quyết định v1

Làm **đúng thứ tự**:
```bash
python3 -m lab10.checkpoint
python3 -m lab10.eval --suite base --stage prepared
python3 -m lab10.gate --run runs/<mã>/report.json
```
| Người | Việc |
|---|---|
| **Hải** | Chạy `checkpoint` (tạo `guards_round1.py`, `operating_gates.round1.json`, `round1.lock`), `eval prepared`, `gate`. **Không sửa** 3 file bản chụp. |
| **Ly** | Điền cột **v1** ở B8: quyết định (Tiếp tục/Thu hẹp/Cải tiến thêm/Dừng), 3 bằng chứng có mã run, dòng `decision_rule`, kho/hãng xấu nhất, ngày quyết định lại. **Chỉ chọn Tiếp tục khi mọi chỉ số bắt buộc đạt và không vượt trần.** |
| **Hải** | Commit & push: `git add lab10/guards.py lab10/guards_round1.py config/operating_gates.json config/operating_gates.round1.json config/round1.lock templates/form-b-evaluation-gates.md` → `git commit -m "LAB 10: chốt cổng vòng 1, quyết định v1"` → `git push -u origin main`. |

**Xong khi:** có mã run base; `T-002@55` xếp loại; lệnh 5 thành công; **đã commit & push**.

---

## 6. CP4 · Phút 125–185 · Khối 3 — Thẻ **S4**

**S4 = "Đêm 11.11: ticket gấp ba, hàng chờ duyệt ngập".** Nguyên nhân chính thuộc **con người & vận hành + kỹ thuật**: LLM nghẽn → trợ lý *fail-open* duyệt nhiều hơn (kể cả đơn chưa đủ điều kiện, đơn do shop bàn giao muộn) và vẫn ghi lỗi hãng; **1 người trực** → hàng chờ ùn; tổng hoàn tự động **vượt trần ngày sale (>300.000đ)**. Ticket để dò: **S4-07**, **S4-08** (nhiều seed). Trên trace chú ý `llm_error`, `llm_fallback`, `proposal.basis`; report chú ý dòng "vượt trần".

**Bước 0 — nhận thẻ (phút 125–135):**
```bash
git fetch https://github.com/VinUni-AI20k/K5_L3_Day10_PoC-to-Pilot_Gate1_cards.git main
git checkout FETCH_HEAD -- incidents/S4
git commit -m "Nhận thẻ S4"
python3 -m lab10.grade --incident S4
git push -u origin main
```
- **Hải:** nhận thẻ + chạy `grade` **trước khi sửa** (mốc **prepared**).
- **Cả nhóm:** ghi `Thẻ đã bốc: S4` vào **đầu Phiếu C**.

| Người | Việc (Phiếu C) |
|---|---|
| **Hải** | **C0** (mã run base/prepared/after), **C1** (cổng vòng 1 đỡ được gì, còn vượt trần nào; S4 có trong pre-mortem không). Câu **3.1**: `trace --suite S4 --ticket S4-07 --seed 11` và `S4-08` nhiều seed → điền **C2** (≥2 lỗi nguồn khác nhau, ≥1 lỗi chìm). Câu **3.6**: thêm ≥1 chỉ số mới vào `lab10/monitors.py` (ví dụ `queue_stuck_rate`) → **C8**. |
| **Đức** | **Phần riêng S4** (mục C3 — *S4 được miễn ô C3, phần riêng nằm ở C1 + **Giờ cao điểm B7.6** đã điền; bổ sung bằng bút khác màu*). Câu **3.3** (giả định môi trường). **Runbook 4–5**. Cập nhật **checklist 9 nhóm (C11)**. |
| **Ly** | Câu **3.2** (specification kiểm được bằng code/số trong report — ví dụ "khi LLM nghẽn thì không tăng tỉ lệ duyệt"). Điền mục `business` nếu nguyên nhân là tiền/phạm vi. |
| **Cả bàn** | Câu **3.1** (tác hại cho ai, đo bằng gì, bao nhiêu ở base). **C4** HAZOP của thẻ (≥3 dòng, mục riêng). **C5** spec + giả định. **C6** fault tree **trước** (đỉnh = tác hại; ≥2 nhánh 2 tầng; mỗi lá có bằng chứng). **C7** bảng sửa. **C9** fault tree **sau**. **C10** Risk register. |

**Sửa (câu 3.5, mục C7) — chọn đúng chỗ:**
- **Con số/vận hành (chính, của Đức + Ly):** `config/operating_gates.json` — `operations.reviewers_on_shift` (thêm người giờ cao điểm), `review_sampling_pct`, `decision_note`, `business.pilot_scope` / `daily_refund_cap_vnd`.
- **Code (Hải):** `lab10/guards.py` — ví dụ chặn fail-open: khi `proposal.basis == "fail_open"` thì `escalate/deny` thay vì duyệt; đối chiếu `cause` với `policy.fault_causes`.
- **Monitor (Hải):** ≥1 chỉ số mới ở `monitors.py` bắt được sự cố S4.

Chạy:
```bash
python3 -m lab10.eval --suite S4 --stage after --note "đổi MỘT thứ: ..."
python3 -m lab10.eval --suite base --stage after --note "kiểm lại bộ nền sau khi sửa"
python3 -m lab10.grade --incident S4
```
**Xong khi:** report có `1 integrity ✅ · 3 visible ✅ · 5 regression ✅ · 6 monitor ✅` (visible/regression chỉ ✅ khi **độ phủ pilot > 0**).

---

## 7. CP5 · Phút 185–200 · Quyết định v2 + gom bài

| Người | Việc |
|---|---|
| **Ly** | Phiếu C **C12**: cột v2 (quyết định, đổi/giữ so v1 vì con số nào, mã run 3 mốc) + 3 dòng bắt buộc (giả định môi trường · giảm hay ngăn · cần đo lại gì trong pilot thật). |
| **Đức** | Điền `submission/submission.json` (`team`, `members` dạng `HoVaTen-MSSV`, `incident:"S4"`, `decision_v1`, `decision_v2`, `three_lines`) → `python3 -m lab10.check_submission --collect` tới khi **`ĐỦ THÀNH PHẦN`**. |
| **Hải** | Giữ code/config cuối chạy sạch ở cả 3 mốc; xử lý lỗi git. |
| **Cả nhóm** | Mỗi người viết mục `## HoVaTen-MSSV` trong `TEAM.md` (đóng góp cụ thể + bằng chứng + exit ticket). Ghi rõ đã dùng AI cho phần nào. |

---

## 8. Phút 200–240 · Demo + nộp

- **200–230:** hai bàn cùng thẻ ghép cặp, mỗi bàn 5'. Chiếu `base · prepared · after`; trả lời: cổng vòng 1 đỡ được gì; phần sửa là **code / con số / người**; con số nào đỡ cho v2. Bàn kia phản biện bằng ticket hiểm (2.8) hoặc đổi thử 1 số trong `operating_gates.json`.
- **Sau demo:** trả mọi số về bản v2 rồi chạy lại `grade --incident S4` + `check_submission --collect`.
- **Nộp:** `git add -u` · `git add submission templates TEAM.md` · commit `"LAB 10: bài nộp"` · push. **Mỗi thành viên** tự nộp link repo trên LMS trước deadline.

---

## Bảng tra nhanh: câu → người

| Câu | Người | Câu | Người |
|---|---|---|---|
| 1.1, 1.6 | Ly | 2.6, 2.7, 2.8 | Hải |
| 1.2, 1.4 | Đức | 2.9 | Ly |
| 1.3 | Hải | 2.10, runbook 1–3, B7.6 | Đức |
| 1.5 | Cả nhóm | B8 (v1) | Ly |
| 2.1, 2.2 | Hải | 3.0, 3.1(trace), 3.6 | Hải |
| 2.3 | Ly | 3.3, phần riêng S4, C9–C11 | Đức |
| 2.4 (HAZOP+checklist), 2.10 | Đức | 3.2, C12(v2) | Ly |
| 2.5 (pre-mortem) | Cả nhóm | 3.4, 3.5, 3.7 | Cả nhóm |

---

## Ghi chú riêng cho S4

- S4 **được miễn điền ô C3** (`check_submission` bỏ qua); "phần riêng" của S4 nằm ở **C1 + mục Giờ cao điểm (B7.6)**.
- Tác hại S4 là **vận hành/kinh doanh** → cách sửa nằm nhiều ở **phạm vi, số người trực, quy trình, giải thích** hơn là code.
- **Thu hẹp phạm vi về 0** hoặc **xếp thật nhiều người trực** không phải cách sửa: độ phủ pilot và ROI đều bị đo (mỗi người trực tốn 30.000đ phí giữ chỗ/ca).

## Cam kết chung
- **Không sửa** file khoá hash, bản chốt vòng 1 (`guards_round1.py`, `operating_gates.round1.json`, `round1.lock`), và tiêu chí sau khi ký.
- Mọi ngưỡng/số phải **giải thích được** lúc demo; ký tiêu chí **trước** lần đo đầu tiên.
- `members` phải khớp `TEAM.md`: `["NgoNgocHai-2A202603939", "TranMinhDuc-2A202603977", "LeThiLy-2A202603989"]`.
- Không commit API key / mật khẩu / `.env`.

---

## CHECKLIST CHI TIẾT THEO THÀNH VIÊN

> Cập nhật 2026-11-19 (sau khi chốt vòng 1). `[x]` = đã xong · `[ ]` = chưa. Việc người khác điền hộ thì ghi rõ để người phụ trách **soát lại**.

### A. HẢI — Kỹ sư cổng + Trưởng nhóm

**Cài đặt / repo (CP1)**
- [x] Fork + đặt tên `K5-L3B-DAY10-Simple-PoCtoPilotGate1`; `origin` đúng.
- [ ] Xác nhận repo **Public** + đã mời Đức/Ly quyền **Write** (tự kiểm trên GitHub).
- [x] Clone + `Ran 13 tests ... OK`.
- [ ] **Sửa danh tính Git về MSSV** — hiện vẫn `ngongochai0804@gmail.com`; chạy `git config user.email "2A202603939@example.com"` và `git config user.name "2A202603939"`.

**Khối 1 (CP2)**
- [x] Câu 1.3 (offline metric bước "chọn độ trễ").
- [x] Canh thứ tự: ký trước lần đo đầu.

**Khối 2A**
- [x] Câu 2.1 chạy base + gate (run `R-base-before-20261119-153723-b45eeb`), ghi B0/B1.
- [x] Câu 2.2 trace `T-002@55` → B2 (lỗi chìm).

**Khối 2B**
- [x] Câu 2.6 code 3 cổng trong `lab10/guards.py`.
- [x] Câu 2.7 hai bước tránh rò rỉ dữ liệu (B7.2).
- [x] Câu 2.8 behavioral test 2 ticket hiểm (B7.3).
- [x] B7.1 (cổng ↔ B4/B6 ↔ mã run `R-base-after-...535bf6`).

**Chốt vòng 1 (CP3)**
- [x] `checkpoint` (hash `12398971`) + `eval prepared` (`R-base-prepared-20261119-161030-535bf6`) + `gate` (tất cả ĐẠT).
- [ ] **Commit + push phần vòng 1** (`guards.py`, `operating_gates.json`, `guards_round1.py`, `operating_gates.round1.json`, `round1.lock`, Phiếu B). ← **ĐANG CHỜ**

**Khối 3 — thẻ S4 (CP4)**
- [x] Copy `incidents/S4/` vào repo (`integrity ok`).
- [ ] Chạy `python -m lab10.grade --incident S4` **trước khi sửa** (mốc prepared) + ghi mã run (C0).
- [ ] Câu 3.1 trace `S4-07`, `S4-08` (nhiều seed) → C2 (≥2 lỗi khác nguồn, ≥1 lỗi chìm).
- [ ] Sửa code nếu cần (`guards.py`: chặn `basis == "fail_open"`) → C7.
- [ ] Câu 3.6 thêm ≥1 monitor mới trong `monitors.py` → C8.
- [ ] `eval --suite S4 --stage after` + `eval --suite base --stage after` + `grade --incident S4` đạt `integrity/visible/regression/monitor ✅`.

**Cuối**
- [ ] Giữ code/config chạy sạch ở 3 mốc; xử lý git; viết mục `## NgoNgocHai-2A202603939` trong `TEAM.md`.

### B. ĐỨC — Vận hành & Pháp lý

- [x] Điền bảng thành viên `TEAM.md` (CP1).
- [x] Câu 1.2 + 1.4 (Phiếu A).
- [ ] Câu 2.4: **HAZOP vòng 1 (B4) + checklist 9 nhóm (B5)** — **CHƯA điền**.
- [x] Câu 2.10: `operations` + `legal` trong `operating_gates.json` *(đã điền ở phiên Hải — ĐỨC SOÁT LẠI)*.
- [x] Runbook 1–3 (B7.5) + Giờ cao điểm (B7.6) *(đã điền ở phiên Hải — ĐỨC SOÁT LẠI)*.
- [ ] Câu 3.3 giả định môi trường → C5.
- [ ] Phần riêng S4: mở lại pre-mortem ở C1 + bổ sung **Giờ cao điểm (B7.6)** bằng bút khác màu (S4 miễn ô C3).
- [ ] Runbook phần 4–5 (C11) + cập nhật checklist 9 nhóm (C11).
- [ ] Điền `submission/submission.json` + `python -m lab10.check_submission --collect` → `ĐỦ THÀNH PHẦN`.
- [ ] Viết mục `## TranMinhDuc-2A202603977` trong `TEAM.md`.

### C. LY — Sản phẩm & Kinh doanh

- [x] Câu 1.1 + 1.6 (Phiếu A).
- [x] Điền `acceptance_criteria.json` + ký (`hash 523ab187`, commit `2e78acd`) + push.
- [x] Câu 2.3 bản đồ dữ liệu + ví dụ drift (B3).
- [x] Câu 2.9 mục `business` của `operating_gates.json` *(đã điền ở phiên Hải — LY SOÁT LẠI)*.
- [x] Cột **v1** ở B8.
- [ ] Câu 3.2 specification kiểm được bằng code/số → C5.
- [ ] Quyết định **v2** (C12) + 3 dòng bắt buộc.
- [ ] Viết mục `## LeThiLy-2A202603989` trong `TEAM.md`.

### D. CẢ NHÓM

- [x] Câu 1.5 → đáp án (b).
- [ ] Câu 2.5 **pre-mortem 4 lăng kính** (B6).
- [ ] Khối 3: câu 3.1 (tác hại) · 3.4 fault tree **trước** (C6) · 3.5 bảng sửa (C7) · 3.7 fault tree **sau** (C9) + Risk register (C10).
- [ ] Demo 3 mốc `base · prepared · after` + trả lời phản biện.
- [ ] Mỗi người tự nộp link repo trên LMS trước deadline.

### E. Việc đang chặn (làm ngay, theo thứ tự)

1. [ ] **Hải**: commit + push phần vòng 1.
2. [ ] **Hải**: `grade --incident S4` (khi chưa sửa) → mốc prepared.
3. [ ] **Đức**: điền B4 (HAZOP) + B5 (checklist 9 nhóm) + B6 (pre-mortem).
4. [ ] **Cả nhóm**: làm Phiếu C cho S4 (Hải trace + Ly 3.2/v2 + Đức 3.3/phần riêng/runbook/C11 + chung 3.4/3.5/3.7).
