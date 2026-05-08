Lưu ý khi đặt tên commit, branch
1. Quy ước khi đặt tên commit
- fix: abc ddd -> một commit thuộc loại sửa lỗi trong codebase của mình
- feat: abc ddd -> một commit thuộc loại giới thiệu 1 tính năng mới trong codebase của mình
- build: abc -> set up cấu hình, chạy thử sản phẩm
- docs: , style: 
* VD: git commit -m "feat: create a page login"
       git commit -m "fix: error when login in website"

2. Quy ước khi đặt tên branch
a. Các nhánh luồng cố định: 
feature -> dev -> test -> staging -> main (production)
b. Các nhánh tạm thời: 
B1. feature:
- syntax:
feature/create-login-page
feature/add-billing-method
feature/create-landing-page-about-customer
feature/year-2026_support-dark-theme
B2. bugfix
- syntax:
bugfix/fix-validation-on-form-login
B3. hotfix( không tuân theo luồng one-way flow)
- syntax:
hotfix/fix-display-wrong-name-on-home-page

B4. experimental
- syntax:
experimental/dark-theme-support

B5. build
- syntax:
build/abc-aaa
B6. Merging
- syntax
merging/abc-aaaa


II. Quy trình làm việc với nhánh feature
1. Tạo nhánh mới từ nhánh dev
-> git checkout -b ten-nhanh
2. Đẩy nhánh vừa tạo lên repo online
-> git push -u origin ten-nhanh
3. Trong quá trình làm, cập nhật nhánh main vào nhánh feature
-> git checkout ten-nhanh
-> git merge main
-> Sau 1 thời gian, code xong tính năng
4. Khi làm xong, quay về main
-> git checkout main
-> Gộp feature vào main
git merge --no-ff ten-nhanh
5. Đẩy main lên repo online
-> git push origin main
