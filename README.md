# Git Workflow

## Thực hiện 1 chức năng mới và hot fix trên live

Checkout từ branch master

1. `git checkout master`
2. `git pull origin master`
3. `git checkout -b <feature_branch>`

4. Sau khi code xong chức năng,
5. Thực hiên pull `git pull origin master` để lấy code mới nhất - trên master và xem có bị conflict hay không.
6. Tiếp theo, push code lên với 2 Pull request.
7. 1 Pull request vào branch master.
8. 1 Pull request vào branch develop.

### Pull request develop bị conflict

1. Thực hiện checkout `git checkout -B fix/conflict/develop`.
2. `git pull origin develop`
3. Sau khi fix conflict xong thì push code lên và tạo Pull request vào branch `develop`

### Pull request staging bị conflict

1. Hãy luôn giũ branch chính của mình không bị dính code của những branch khác nên thực hiện như sau.
2. Thực hiện checkout `git checkout -B fix/conflict/staging`.
3. `git pull origin <branch bị conflict>`.
4. Sau khi fix conflict xong thì push code lên và tạo Pull request vào branch `<branch bị conflict>`.

## Thực hiện fix bug trên staging

- __Lưu ý__: Bug chức năng ở branch nào thì fix ở branch đó

1. `git checkout <branch chức năng bị bug>`
2. Sau khi fix bug xong thì tạo 2 Pull request.
3. 1 Pull request vào branch staging.
4. 1 Pull request vào branch develop.

### Pull request develop bị conflict

1. Thực hiện checkout `git checkout -B fix/conflict/develop`.
2. `git pull origin develop`
3. Sau khi fix conflict xong thì push code lên và tạo Pull request vào branch `develop`

## Thực hiện fix bug trên staging mà chức năng bị bug phụ thuộc vào chức năng khác

- __Lưu ý__: Khi deploy lên live bắt buộc phải lên cùng lúc những chức năng liên quan với nhau

1. `git checkout <branch chức năng bị bug>`
2. Pull những chức năng liên quan ảnh hưởng tới nhau
3. `git pull origin <những branch liên quan>`
4. Sau khi fix bug xong thì tạo 3 Pull request.
5. 1 Pull request vào branch master.
6. 1 Pull request vào branch staging.
7. 1 Pull request vào branch develop.

### Pull request master bị conflict

1. Thực hiện checkout `git checkout -B fix/conflict/master`.
2. `git pull origin master`
3. Sau khi fix conflict xong thì push code lên và tạo Pull request vào branch `master`

### Pull request develop bị conflict

1. Thực hiện checkout `git checkout -B fix/conflict/develop`.
2. `git pull origin develop`
3. Sau khi fix conflict xong thì push code lên và tạo Pull request vào branch `develop`
