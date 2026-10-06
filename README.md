
# Báo cáo Bài 2: Quản lý nhánh và Giải quyết xung đột (Merge Conflict)

## 1. Mục tiêu
Tạo nhánh phụ, cố ý gây xung đột gộp nhánh trên file README.md, và giải quyết xung đột thủ công để tạo ra một commit gộp (merge commit).

## 2. Các bước thực hiện

1. Khởi tạo repo và tạo commit đầu tiên trên nhánh `main`:
    - `git init`
    - Tạo file README.md với một dòng nội dung ban đầu
    - `git add README.md`
    - `git commit -m "Initial commit tren main"`

2. Tạo và chuyển sang nhánh phụ `feature-update`, sửa nội dung dòng đầu rồi commit:
    - `git checkout -b feature-update`
    - Sửa README.md (dòng đầu) thành nội dung của nhánh feature
    - `git add README.md`
    - `git commit -m "Cap nhat README tren nhanh feature-update"`

3. Quay lại nhánh `main`, sửa CÙNG dòng đó theo nội dung khác rồi commit:
    - `git checkout main`
    - Sửa README.md (cùng dòng) thành nội dung của nhánh main
    - `git add README.md`
    - `git commit -m "Cap nhat README tren nhanh main"`

4. Gộp nhánh để tạo xung đột:
    - `git merge feature-update`
    - Kết quả: CONFLICT (content): Merge conflict in README.md

## 3. Các bước giải quyết xung đột THỦ CÔNG

1. Mở file README.md, Git đã chèn các ký hiệu đánh dấu xung đột:
    - `<<<<<<< HEAD` : bắt đầu phần nội dung của nhánh hiện tại (main)
    - `=======` : ranh giới ngăn cách hai phần
    - `>>>>>>> feature-update` : kết thúc phần nội dung của nhánh feature-update

2. Đọc và so sánh nội dung của cả hai nhánh.

3. Chỉnh sửa thủ công: xóa toàn bộ ba ký hiệu `<<<<<<<`, `=======`, `>>>>>>>` và quyết định giữ lại nội dung cuối cùng (gộp nội dung của cả hai nhánh thành một dòng hoàn chỉnh).

4. Lưu file sau khi đã làm sạch các ký hiệu xung đột.

5. Đánh dấu đã giải quyết xong và hoàn tất commit gộp:
    - `git add README.md`
    - `git commit -m "Giai quyet xung dot va gop nhanh feature-update vao main"`

## 4. Kiểm tra kết quả

Chạy lệnh:
`git log --graph --oneline`


