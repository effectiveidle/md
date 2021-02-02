# Git

## Git简介

- 分布式版本控制系统


- Git诞生

Linus用c语言开发

- 集中式vs分布式

集中式的版本库存放在中央服务器，分布式每个人的电脑里都有完整的版本库，但通常也有一台中央服务器

## 创建版本库

又名仓库，repository，版本控制系统只能跟踪文本文件的改动，二进制文件没法跟踪

- 初始化一个Git仓库

  git init

- 添加文件到Git仓库

  1.git add <file>

  2.git commit -m <message>

- 查看工作区状态

  git status

- 查看修改内容

  git diff

## 版本回退

- git log：查看提交历史，以确定回退到哪个版本，单行显示+参数--pretty=oneline

  HEAD指向当前版本

- git reset --hard <commit_id>：在版本的历史之间穿梭

- git reflog：查看命令历史


## 工作区和暂存区

文件夹就是一个工作区，Working Directory

.git是Git版本库(Repository)，版本库里的index(或stage)是暂存区，master是自动创建的第一个分支

![git-repo](../img/clip_image001.jpg)

把文件往Git版本库里添加的时候是分两步执行：

第一步是用git add，把文件修改添加到暂存区(Stage)

第二步是用git commit提交更改，把暂存区的所有内容提交到当前分支

## 管理修改

Git优秀的地方在于Git跟踪并管理的是修改，而非文件

## 撤销修改

git restore <file>，把文件在工作区的修改撤销

git restore --staged <file>把暂存区的的修改撤销

## 删除文件

删除工作区文件，也可用git restore <file>恢复

git rm从版本库里删除文件

## 远程仓库

- git remote -v：查看远程库信息，显示可以抓取和推送的origin的地址

### 添加远程库

- git remote add <name> git@github.com:effectiveidle/learngit.git，本地仓库与远程关联
- git remote rm <name>：删除已关联的远程库
- git push -u github master：推送到远程库(加了参数-u后，以后可直接用git push代替git push origin master)
- git pull github master：从远程库拉取到本地

### 从远程库克隆 

创建仓库后clone到本地，修改后再push

## 分支管理

- git branch <name>：创建分支
- git switch <name>：切换分支
- git branch：查看分支
- git merge <name>：合并某分支到当前分支
- git branch -d <name>：删除分支

### 分支策略

在实际开发中，master分支是非常稳定的，仅用来发布新版本，平时不能在上面干活，干活都在dev分支上，每个人都有自己的分支，到版本发布时，再把dev分支合并到master上

## 标签管理

- git tag <tagname>：添加标签，首先要切换到打标签的分支
- git tag：查看所有标签
- git show <tagname>：查看标签信息
- git push origin <tagname>：推送某个标签到远程
- git push origin --tags：推动全部未推送过的本地标签
- git tag -d <tagname>可以删除一个本地标签；
- git push origin :refs/tags/<tagname>：删除一个远程标签。