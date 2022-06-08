# git 常用命令

1. `git add .`
2. `git commit -m ' ' / git commit -v`
3. `git pull` // 拉
4. `git push` // 推
5. `git branch` // 查看本地分支
6. `git branch -r` // 查看远程分支
7. `git branch -a` // 查看所有分支
8. `git branch 新分支名` // 创建新分支
9. `git checkout 分支名` //切换分支
10. `git checkout -b` 新分支名 // 创建新分支并且切换
11. `git push origin` 分支名 // 将新分支推送到 github
12. `git merge` 分支名 // 将分支合并到当前分支

- Please make sure you have the correct access rights and the repository exists 问题解决
  - `cat ~/.ssh/id_rsa.pub` 然后将 ssh key 复制到 github 上即可
