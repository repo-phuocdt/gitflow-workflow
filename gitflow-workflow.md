# Git Workflow

## Thực hiện 1 chức năng mới và hot fix trên live

Checkout từ branch master

`git checkout master`
`git pull origin master`
`git checkout -b <feature_branch>`

Sau khi code xong chức năng,
Thực hiên pull `git pull origin master` để lấy code mới nhất trên master và xem có bị conflict hay không.
Tiếp theo, push code lên với 2 Pull request.
1 Pull request vào branch master.
1 Pull request vào branch develop.

### Pull request develop bị conflict

Thực hiện checkout `git checkout -B fix/conflict/develop`.
`git pull origin develop`
Sau khi fix conflict xong thì push code lên và tạo Pull request vào branch `develop`

### Pull request staging bị conflict

Hãy luôn giũ branch chính của mình không bị dính code của những branch khác nên thực hiện như sau.
Thực hiện checkout `git checkout -B fix/conflict/staging`.
`git pull origin <branch bị conflict>`.
Sau khi fix conflict xong thì push code lên và tạo Pull request vào branch `<branch bị conflict>`.

## Thực hiện fix bug trên staging

- __Lưu ý__: Bug chức năng ở branch nào thì fix ở branch đó

`git checkout <branch chức năng bị bug>`
Sau khi fix bug xong thì tạo 2 Pull request.
1 Pull request vào branch staging.
1 Pull request vào branch develop.

### Pull request develop bị conflict

Thực hiện checkout `git checkout -B fix/conflict/develop`.
`git pull origin develop`
Sau khi fix conflict xong thì push code lên và tạo Pull request vào branch `develop`

## Thực hiện fix bug trên staging mà chức năng bị bug phụ thuộc vào chức năng khác

- __Lưu ý__: Khi deploy lên live bắt buộc phải lên cùng lúc những chức năng liên quan với nhau

`git checkout <branch chức năng bị bug>`
Pull những chức năng liên quan ảnh hưởng tới nhau
`git pull origin <những branch liên quan>`
Sau khi fix bug xong thì tạo 3 Pull request.
1 Pull request vào branch master.
1 Pull request vào branch staging.
1 Pull request vào branch develop.

### Pull request master bị conflict

Thực hiện checkout `git checkout -B fix/conflict/master`.
`git pull origin master`
Sau khi fix conflict xong thì push code lên và tạo Pull request vào branch `master`

### Pull request develop bị conflict

Thực hiện checkout `git checkout -B fix/conflict/develop`.
`git pull origin develop`
Sau khi fix conflict xong thì push code lên và tạo Pull request vào branch `develop`
