# **Github 基本操作**

## **创建仓库(repository)**

```text
git init
```

## **克隆(clone)仓库到本地**

```text
git clone https://github.com/<YourName>/YourRepoName.git
```

## **在本地进行修改和提交**

```text
# 暂存
git add README.md
git add .
# 提交本地仓库
git commit -m "Update Messages"
```

## **将本地提交推送(push)到Github**

```text
# 添加远程版本库
git remote add origin https://github.com/<YourName>/YourRepoName.git
# 推送
git push -u origin main
```

## **查看提交历史**

查看当前分支的提交历史

```text
git log
```

查看某个特定分支的提交历史

```text
git log <branch-name>
```

其中 `<branch-name>` 是要查看的分支的名称。

`git log` 命令支持许多选项和参数，例如使用 `--author` 选项按作者筛选提交记录，使用 `--since` 和 `--until` 选项按时间段筛选提交记录等等。可以通过运行 `git log --help` 命令来查看所有选项和参数的帮助信息。

## **撤销提交**

撤销提交有两种情况：一种是撤销本地未推送到远程仓库的提交，另一种是撤销已经推送到远程仓库的提交。

### **撤销本地未推送到远程仓库的提交**

如果你在本地提交了代码，但是还没有推送到远程仓库，可以使用以下两种方法撤销提交：

1. 使用 git reset 命令。该命令会将当前分支指向指定的提交，并且将代码库重置为该提交的状态。如果不带参数，则默认将当前分支指向上一次提交。git reset HEAD~1 # 撤销上一次提交
2. 使用 git revert 命令。该命令会创建一个新的提交来撤销指定的提交。这种方法不会删除任何历史记录。git revert HEAD # 撤销上一次提交

### **撤销已经推送到远程仓库的提交**

如果你已经将代码推送到远程仓库，并且其他人已经对该提交进行了修改，那么就需要使用 `git revert` 命令来创建一个新的提交来撤销之前的提交。

1. 首先使用 `git log` 命令查看要撤销的提交的哈希值。
2. 然后使用 `git revert <commit-hash>` 命令创建一个新的提交。
3. 最后使用 `git push` 命令将新的提交推送到远程仓库。

## **分支管理**

常用的分支管理命令包括：

- git branch：列出所有分支，以及当前所在的分支。
- git branch [branch name]：新建一个分支。
- git checkout [branch name]：切换到指定分支。
- git checkout -b [branch name]：新建一个分支，并切换到该分支。
- git merge [branch name]：将指定分支合并到当前分支。
- git branch -d [branch name]：删除指定分支。
- git branch -D [branch name]：强制删除指定分支。