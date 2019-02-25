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
```

