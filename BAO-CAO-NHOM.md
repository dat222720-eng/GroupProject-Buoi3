# Báo cáo Nhóm – Buổi 3: Quy trình làm việc với Git

**Nhóm:** GroupProject-Buoi3  
**Thành viên:**  
- Đạt (Leader) – Quản lý repo, quy trình merge, tag/release  
- Kiệt – Thực hiện nhánh cá nhân, review PR, làm conflict  
- Nam – Thực hiện nhánh cá nhân, review PR, làm conflict

## 1. Quy trình làm việc nhóm

- Mô hình nhánh: `main` (ổn định) → `develop` (tập trung thay đổi) → `feature-*` (mỗi cá nhân) → `test-*` (thử nghiệm)
- Chu trình làm việc:
  1) Leader tạo repo + `develop`  
  2) Mỗi thành viên tạo `feature-[tên]`, `test-[tên]`  
  3) Commit nhỏ, có ý nghĩa (Conventional Commits: `feat/ fix/ chore/ docs/ refactor...`)  
  4) Tạo PR → thành viên khác review/comment → Leader merge (Squash & merge)  
  5) Xử lý xung đột khi cần (resolve conflicts)  
  6) Đánh **tag v1.0**, sửa nhỏ, **tag v1.1**

**Công cụ:** Git + GitHub (PR/Review/Resolve conflicts/Releases)

---

## 2. Các bước đã thực hiện (tóm tắt kết quả)

- **Hoạt động 1:** Mỗi người có ≥2 branch (`feature-*`, `test-*`) – có ảnh chụp `git branch -a`.  
- **Hoạt động 2:** Mỗi người ≥3 commit trên nhánh cá nhân – có ảnh `git log --oneline --graph`.  
- **Hoạt động 3:** Tạo PR, gán reviewer, comment, merge (Squash) – đính kèm ảnh PR merged + comment.  
- **Hoạt động 4:** Dàn xếp **conflict** cùng dòng trong `README.md` → resolve, merge – có ảnh marker và sau khi sửa.  
- **Hoạt động 5:** Tạo `v1.0`, `v1.1`, checkout tag – đính kèm ảnh `git tag -n`, `git status` (HEAD detached).

(Liệt kê link PR/Commit chính nếu có: …)

---

## 3. Vấn đề & cách khắc phục

| Vấn đề | Nguyên nhân | Cách xử lý |
|---|---|---|
| Clone lỗi vì URL placeholder | Dán `<host>/<org>` thay vì URL thật | Dùng đúng HTTPS/SSH repo; kiểm tra `git remote -v` |
| Không push được nhánh | Chưa đặt upstream | `git push -u origin <branch>` |
| PR báo **Conflicting files** | Hai nhánh sửa cùng dòng/khối | **Resolve conflicts** trên GitHub hoặc local; xoá marker `<<<<<<< ======= >>>>>>>`, commit “resolve” |
| Log lộn xộn, khó đọc | Commit quá to, không chuẩn message | Chia nhỏ commit, dùng Conventional Commits |
| Lẫn giữa reset/revert/restore | Chưa phân biệt mục đích | Trong nhóm: ưu tiên `revert` khi đã push; `reset` trước khi push; `restore` để khôi phục file |

---

## 4. Cảm nhận cá nhân

**Đạt (Leader):**  
- Học được cách điều phối PR, enforce review, và dùng `Squash & merge` để giữ lịch sử sạch.  
- Tag/release giúp đánh dấu mốc, dễ rollback.  

**Kiệt:**  
- Thấy rõ lợi ích commit nhỏ: review nhanh, biết chính xác chỗ lỗi khi CI fail.  
- Trải nghiệm resolve conflict thực tế, hiểu vì sao phải pull thường xuyên.  

**Nam:**  
- Tạo PR/Review mang tính “peer learning”: đọc code của bạn giúp cải thiện chuẩn code cá nhân.  
- Tag checkout ở `HEAD detached` giúp xem lại đúng trạng thái phát hành.

(Mỗi người viết 5–7 dòng riêng của mình.)

---

## 5. So sánh: làm việc **có Git** vs **không có Git**

- **Có Git**:  
  - Lịch sử rõ ràng (ai làm gì, khi nào) → truy vết & rollback nhanh.  
  - Branch cô lập → ít đè code, dễ phân công.  
  - PR/Review → chất lượng code tốt hơn, chia sẻ kiến thức.  
  - Tag/Release → đánh dấu phiên bản, hỗ trợ phát hành & hotfix.

- **Không Git**:  
  - Dễ ghi đè file nhau (copy-paste), khó đồng bộ.  
  - Không có lịch sử thay đổi → khó tìm nguyên nhân lỗi.  
  - Khó làm việc song song, khó tích hợp.

**Kết luận:** Áp dụng Git + quy trình chuẩn giúp nhóm làm việc hiệu quả, giảm rủi ro, nâng chất lượng sản phẩm.

---
