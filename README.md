# Git Workflow of QOffice

## Thực hiện chức năng mới và Hot fix trên master

__Lưu ý__: Luôn luôn phải checkout từ branch `master`

Cú pháp:
- `git checkout master`
- `git pull origin master`

Checkout ra branch mới để thực hiện chức năng
Cú pháp:
- `git checkout -b <feature_branch>`

Sau khi code xong chức năng thì commit code
Cú pháp:
- `git add .` là lấy tất cả file thay đổi hoặc lấy từng file `git add <tên file>`
- `git commit -m "<nội dung commit>`

Thực hiện pull branch `master` để lấy code mới nhất và xem có bị conflict hay không.
Cú pháp:
- `git pull origin master`

######Nếu có conflict với master
Sau khi fix conflict thì commit code
Cú pháp:
- `git add .` là lấy tất cả file thay đổi hoặc lấy từng file `git add <tên file>`
- `git commit -m "<nội dung commit>`

Thực hiện push code
Cú pháp:
`git push origin HEAD` hoặc `git push origin <feature_branch>`

Tạo Pull request vào 2 branch `master` và `develop`

### Thực hiện fix conflict trên develop
__Lưu ý__: Luôn luôn phải checkout branch mới để chức nằng branch chính không bị dính code của những chức năng branch khác.

Từ branch chức năng hiện tại checkout ra branch fix conflict
Cú pháp:
- `git checkout -B fix/conflict/develop`
- `git pull origin develop`

Sau khi fix conflict thì commit code
Cú pháp:
- `git add .` là lấy tất cả file thay đổi hoặc lấy từng file `git add <tên file>`
- `git commit -m "<nội dung commit>`

Thực hiện push code
Cú pháp:
`git push origin HEAD` hoặc `git push origin fix/conflict/develop`

Tạo Pull request vào branch `develop`

## Thực hiện đưa chức năng lên staging

Lấy branch chức năng cần muốn đưa lên `staging`

Tạo Pull request vào branch `staging`

######Nếu có conflict với staging
__Lưu ý__: Luôn luôn phải checkout branch mới để chức nằng branch chính không bị dính code của những chức năng branch khác.

Từ branch chức năng hiện tại checkout ra branch fix conflict
Cú pháp:
- `git checkout -B fix/conflict/staging`
- `git pull origin staging`

Sau khi fix conflict thì commit code
Cú pháp:
- `git add .` là lấy tất cả file thay đổi hoặc lấy từng file `git add <tên file>`
- `git commit -m "<nội dung commit>`

Thực hiện push code
Cú pháp:
`git push origin HEAD` hoặc `git push origin staging`

Tạo Pull request vào branch `staging`

## Thực hiện fix bug trên staging

__Lưu ý__: Bug chức năng ở branch nào thì fix ở branch đó

Cú pháp:
`git checkout <branch chức năng bị bug>`

Sau khi fix bug thì commit code
Cú pháp:
- `git add .` là lấy tất cả file thay đổi hoặc lấy từng file `git add <tên file>`
- `git commit -m "<nội dung commit>`

Thực hiện push code
Cú pháp:
`git push origin HEAD` hoặc `git push origin <branch chức năng bị bug>`

Tạo Pull request vào 2 branch `staging` và `develop`

######Nếu có conflict với develop
__Lưu ý__: Luôn luôn phải checkout từ branch mới để code branch chính không bị dính code của những branch khác.

Từ branch chức năng hiện tại checkout ra branch fix conflict
Cú pháp:
- `git checkout -B fix/conflict/develop`
- `git pull origin develop`

Sau khi fix conflict thì commit code
Cú pháp:
- `git add .` là lấy tất cả file thay đổi hoặc lấy từng file `git add <tên file>`
- `git commit -m "<nội dung commit>`

Thực hiện push code
Cú pháp:
`git push origin HEAD` hoặc `git push origin develop`

Tạo Pull request vào branch `develop`