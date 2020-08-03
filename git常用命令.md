常用Git命令清单：

- Workspace:工作区
- Index/Stage:暂存区
- Repository:仓库区（或本地仓库）
- Remote:远程仓库

### 一、新建代码库

```js
#在当前目录新建一个Git代码库
$ git init

#新建一个目录，将其初始化一个Git代码库
$ git init [project-name]

#下载一个目录和它的整个代码历史
$git clone [url]
```

### 二、配置

Git 的配置文件为 .gitconfig , 它可以在用户主目录下（全局配置），也可以在项目目录下（项目配置）

```js
#显示当前的Git配置
$ git config --list

#编辑Git配置文件
$ git config -e [--global]

#设置提交代码时的用户信息
$ git config [--global] user.name "[name]"
$ git config [--global] user.email "[address]"
```

### 三、增加删除文件

```js
#添加指定文件到暂存区
$ git add [file1] [file2] ...

#添加指定目录到暂存区，包括子目录
$ git add [dir]

#添加当前目录的所有文件到暂存区
$ git add .

#添加每个变化前，都会要求确认
#对于同一个文件的多处变化，可以实现分次提交
$ git add -p

#删除工作区文件，并将这次删除放入暂存区
$ git rm [file1][file2]...

#停止追踪指定文件，但该文件会保留在工作区
$ git rm --cached [file]

#改名文件，并且将这个改名放入暂存区
$ git mv [file-original] [file-renamed]
```

### 四、代码提交

```js
#提交暂存区到仓库区
$ git commit -m [message]

#提交暂存区的指定文件到仓库区
$ git commit [file1] [file2]...

#提交工作区自上次commit之后的变化，直接到仓库区
$ git commit -a

#提交时显示所有的diff信息
$ git commit -v
```

### 五、分支

```js
#列出所有本地分支
$ git branch

#列出所有远程分支
$ git branch -r

#列出所有本地分支和远程分支
$ git branch -a

#新建一个分支，但依然停留在当前分支
$ git branch [branch-name]

#新建一个分支，并切换到该分支
$ git checkout -b[branch]

#新建一个分支，并与指定的远程分支建立追踪关系
$ git branch --track [branch][remote-branch]

#切换到当前分支，并更新工作区
$ git checkout [branch-name]

#切换到上一个分支
$ git checkout -

#合并指定分支到当前分支
$ git merge [branch]

#选择一个commit,合并到当前分支
$ git cherry -pick[commit]

#删除分支
$ git branch -d [branch-name]

#删除远程分支
$ git push origin --delete[branch-name]

```

### 六、标签

```js
#列出所有标签
$ git tag

#新建一个tag 在当前 commit
$ git tag[tag]

#新建一个tag 在指定 commit
$ git [tag][commit]

#删除本地tag
$ git tag -d[tag]

#删除远程tag
$ git push origin:refs/tags/<tagName>

#查看tag信息
$ git show [tag]

#提交指定 tag
$git push [remote] --tags

#新建一个分支，指向某个tag
$git checkout -b [branch][tag]
```

### 七、查看信息

```js
#显示所有变更的文件
$git status

#显示当前分支的版本历史
$git log

#显示commit历史，以及每次 commit 发生变成的文件
$git log --stat

#搜索提交历史，根据关键字
$git log -s[keyword]

#显示指定文件相关的每一次diff
$git log -p[file]

#显示过去5次提交
$git log -5 --pretty

#显示所有提交过的用户，按提交次数排序
$git short log -sn

#显示指定文件是什么人在什么时间修改过
$ git blame [file]

#显示暂存区和工作区的差异
$ git diff

#显示暂存区与上一个 commit 的差异
$ git diff -cached [file]

#显示暂存区与当前分支最新commit之间的差异
$ git diff HEAD

#显示两次提交之间的差异
$ git diff [first-branch]...[second-branch]

#显示你今天写了多少行代码
$ git diff --shortstat"@{0 day ago}"

#显示当前分支的最近几次提交
$ git reflog
```

### 八、远程同步

```js
#下载远程仓库的所有变动
$ git fetch [remote]

#显示所有远程仓库
$ git remote -v

#显示某个远程仓库的信息
$ git remote show[remote]

#增加一个新的远程仓库并命名
$ git remote add [shortname][url]

#取回远程仓库的变化，并于本地分支合并
$ git pull [remote][branch]

#上传本地指定分支到远程仓库，即使有冲突
$ git push [remote] --force

#上传本地指定分支到远程分支
$ git push [remote][branch]

#推送所有分支到远程仓库
$ git push [remote] --all

```

### 九、撤销

```js
#恢复暂存区的指定文件到工作区
$ git checkout [file]

#恢复某个 commit 的指定文件到暂存区和工作区
$ git checkout [commit][file]

#恢复暂存区的所有文件到工作区
$ git checkout .

#重置暂存区的指定文件，与上一次 commit 保持一致，但工作区不变
$ git reset [file]

#重置暂存区与工作区，与上一次 commit 保持一致
$ git reset --hard
```

### 十、其他

```js
#生成一个可供发布的压缩包
$ git archive
```




































