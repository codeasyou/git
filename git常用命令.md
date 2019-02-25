常用Git命令清单：

- Workspace:工作区
- Index/Stage:暂存区
- Repository:仓库区（或本地仓库）
- Remote:远程仓库

# 一、新建代码库

  

```reStructuredText
#在当前目录新建一个Git代码库
$ git init

#新建一个目录，将其初始化一个Git代码库
$ git init [project-name]

#下载一个目录和它的整个代码历史
$git clone [url]
```

# 二、配置

```text
#显示当前的Git配置
$ git config --list

#编辑Git配置文件
$ git config -e [--global]

#设置提交代码时的用户信息
$ git config [--global] user.name "[name]"
$ git config [--global] user.email "[address]"
```

# 三、增加删除文件

```text
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
$ git rm [file1],[file2]...

#停止追踪指定文件，但该文件会保留在工作区
$ git rm --cached [file]

#改名文件，并且将这个改名放入暂存区
$ git mv [file-original] [file-renamed]
```

# 四、代码提交

```text
#提交暂存区到仓库区
$ git commit -m [message]

#提交暂存区的指定文件到仓库区
$ git commit [file1] [file2]...

#提交工作区自上次commit之后的变化，直接到仓库区
$ git commit -a

#提交时显示所有的diff信息
$ git commit -v
```



















































