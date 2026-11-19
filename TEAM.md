# Team

## Thông tin nhóm

- Tên nhóm (`TenNhom`, không dấu, không khoảng trắng): `Simple`
- Lớp: `L3B`
- Repo của bàn: `K5-L3B-DAY10-Simple-PoCtoPilotGate1`
- Thẻ sự cố đã bốc (S1–S8): *(để trống tới phút 125)*

## Thành viên

Họ tên đầy đủ và MSSV của **mọi** thành viên; bàn 3 người thì để trống dòng 4. Vai: Kỹ sư cổng · Sản phẩm và kinh doanh · Vận hành và pháp lý (README mục 3, phút 0–15).

| STT | Họ và tên | MSSV | Vai | Trưởng nhóm |
| --: | --------- | ---- | --- | :---------: |
|   1 | Ngô Ngọc Hải | 2A202603939 | Kỹ sư cổng | ✓ |
|   2 | Trần Minh Đức | 2A202603977 | Vận hành và pháp lý |  |
|   3 | Lê Thị Ly | 2A202603989 | Sản phẩm và kinh doanh |  |

Ghi `members` trong `submission/submission.json` theo dạng `"HoVaTen-MSSV"`, khớp bảng trên.

## Cá nhân

Mỗi thành viên tự viết một mục bên dưới (chép mẫu, đổi tiêu đề thành họ tên không dấu và MSSV, ví dụ `## NguyenVanAn-20241234`).

## NgoNgocHai-2A202603939

### Phần việc phụ trách

Kỹ sư cổng: `lab10/guards.py`, `lab10/monitors.py`; chạy các lệnh `lab10.eval`, `lab10.trace`, `lab10.gate`, `lab10.checkpoint`. Câu 1.3, 2.1, 2.2, 2.6–2.8, 3.1 (trace), 3.6. Trưởng nhóm, phụ trách repo.

### Đóng góp cụ thể

...

### Bằng chứng

Mã commit, mã lần chạy (`runs/<mã>`), dòng trong phiếu.

### Exit ticket

Một điều học được, một điều còn chưa chắc.

## TranMinhDuc-2A202603977

### Phần việc phụ trách

Vận hành và pháp lý: `config/operating_gates.json` (mục `operations`, `legal`), runbook, `submission/`, `TEAM.md`. Câu 1.2, 1.4, 2.4 (HAZOP + checklist 9 nhóm), 2.10, 3.3, phần riêng theo thẻ, runbook 4–5.

### Đóng góp cụ thể

...

### Bằng chứng

Mã commit, mã lần chạy (`runs/<mã>`), dòng trong phiếu.

### Exit ticket

Một điều học được, một điều còn chưa chắc.

## LeThiLy-2A202603989

### Phần việc phụ trách

Sản phẩm và kinh doanh: `config/acceptance_criteria.json`, mục `business` trong `config/operating_gates.json`; nội dung Product & Business trong `templates/form-a-criteria.md`, `form-b-evaluation-gates.md`, `form-c-incident.md`. Câu 1.1, 1.6, 2.3, 2.9, 3.2; chủ trì tổng hợp quyết định Gate 1 v1 (B8) và v2 (C12). Phối hợp câu chung 1.5, 2.5 và phân tích sự cố. Cập nhật đóng góp cá nhân trong TEAM.md.

### Đóng góp cụ thể

Tham gia xây dựng mục tiêu hệ thống và tiêu chí Product & Business tại Phiếu A câu 1.1 và 1.6; xây dựng Data Map và ví dụ policy drift tại Phiếu B mục B3; đề xuất bốn Business Gates tại B7.4. Các Business Gates vẫn là DRAFT, chưa được nhóm phê duyệt.

Sử dụng Codex hỗ trợ audit repository, phân tích yêu cầu và review tài liệu.

### Bằng chứng

`8c82874`: bản nháp tiêu chí Product & Business; `a3b5c51`: nội dung Data Map B3; `ca978d1`: Business Gates DRAFT B7.4; `35540f9`: merge PR #1. Commit merge không đồng nghĩa với phê duyệt nghiệp vụ. Xem Phiếu A câu 1.1, 1.6 và Phiếu B mục B3, B7.4.

### Exit ticket

**Một điều học được:** Tiêu chí chấp nhận cần được ký trước khi đánh giá. Quyết định Gate 1 phải dựa trên bằng chứng thực nghiệm, đồng thời cân nhắc chất lượng, an toàn, chi phí và khả năng vận hành.

**Một điều còn chưa chắc:** Cách áp dụng điều kiện “Tiếp tục” đã ký cho Gate 1 v1 khi nhóm chưa được giao gói sự cố.
