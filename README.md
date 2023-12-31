# Learning Git
*desciption:* Git学习与使用记录

## Git简介

1. Git与其他版本控制系统(包括Subversion和近似工具)相比，其对打数据的方式更像是一个**快照流直接记录**，而非**差异比较**。
2. Git中的绝大多数操作都是**本地执行**，这也意味着在离线或者没有 VPN 时，几乎可以进行任何操作。。
3. Git 中所有的数据在存储前都计算校验和，然后以校验和来引用。这意味着**Git中所有的操作都是有迹可循的**。
4. 执行的Git操作，几乎只是往Git数据库中**添加数据**，很难从数据库中删除数据，即Git几乎不会执行任何可能导致文件不可恢复的操作。
5. Git有三种状态：**已提交(committed)、已修改(modified)、已暂存(staged)**。
6. Git有三种工作阶段：**工作区、暂存区、Git仓库目录**。
7. Git基本工作流程：**在工作区中修改文件、将你想要下次提交的更改选择性地暂存，这样只会将更改的部分添加到暂存区、提交更新，找到暂存区的文件，将快照永久性存储到 Git 目录**。
8. Git提供命令行工作模式，该模式下，可以执行Git的**所有命令**。

## Git使用

### 基本配置

|描述|命令|实例|
|:---|:---|:---|
|配置git的user name|git config --global user.name  + 名字|git config --global user.name "your_name"|
|配置git的user email|git config --global user.email + 邮箱|git config --global user.email + "your_email@your_email.com"|
|生成ssh-key密钥|ssh-keygen -t rsa -C + 邮箱|ssh-keygen -t rsa -C "[your_email@your_email.com](mailto:your_email@your_email.com)"|

### 初次使用

|描述|命令|实例|
|:---|:---|:---|
|创建文件夹|mkdir + 文件夹|mkdir LearningGit|
|查看仓库的状态|git status||
|初始化一个Git仓库|git init||
|创建文件|touch + 文件名|touch README.md|
|编辑文件|vim + 文件名|vim README.md|
|添加文件|git add + 文件名|git add README.md|
|提交文件|git commit -m + 信息|git commit -m "README commit"|
|查看当前的远程仓库地址和原仓库地址|git remote -v||
|关联远程仓库|git remote add origin + ssh url|<div>git remote add origin git@github.com:Charles-XuXingchen/LearningGit.git</div><div><br></div>|
|本地推送到远程|git push -u origin + 分支名|git push -u origin master|

### 分支操作

|描述|命令|实例|
|:---|:---|:---|
|查看分支|git branch||
|创建分支|git branch + 分支名|git branch slave|
|切换分支|git checkout + 分支名|git checkout slave|
|重命名分支|git branch -m + 分支名|git branch -m temp|
|删除分支|git branch -d + 分支名|git branch -d temp|
|比较主分支和子分支|git diff + 子分支名|git diff temp|
|合并子分支到主分支|git merge + 子分支名|git merge temp|

### 标签操作

|描述|命令|实例|
|:---|:---|:---|
|查看标签|git tag ||
|添加标签|git tag + 标签名|git tag v1.0|
|删除本地标签|git tag -d + 标签名|git tag -d v1.0|
|本地标签推送到远程|git push origin master + 标签名|git push origin master v1.0|
|删除远程标签|git push origin master :refs/tags/标签名|git push origin master :refs/tags/v1.0|
|查看某个标签的详细信息|git show + 标签名|git show v1.0|
|首先查看历史提交的各commit_id| git log --oneline||
|给忘记创建标签的历史提交创建标签|git tag -a 版本号 commit_id -m '版本号'|git tag -a v0.5 9c5f294 -m 'v0.5'|

### 持续更新

