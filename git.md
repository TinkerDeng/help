# git

## 目录

* [全局配置](#全局配置)
* [命令](#命令)
* [生成秘钥](#生成秘钥)

### 生成秘钥

1. `ssh-keygen -t rsa -c "git邮箱"`		生成秘钥
2. `cd ~/.ssh` 查看生成了 id_rsa(私钥） id_rsa.pub（公钥）
3. 讲公钥的内容copy到gitlab中，生成ssh key

### 全局配置

```git
git config --global user.name "Your Name"
git config --global user.email "email@example.com"

git config --global alias.st status 	配置别名st
git config --global alias.co checkout	配置别名co

git remote add origin git@gitee.com:liaoxuefeng/learngit.git 本地库和远程库关联
git rm -f --cached .			        清除本地ignore的缓存

```

### 命令
```git
git remote -v				                    查看本地库关联的远程库信息
git remote rm remoteName		            删除本地已经关联的远程库信息
git config --global color.ui true	      命令行git显示颜色
git version 				                    查看git版本
git init 				                        初始化一个仓库
git add  				                        把文件修改添加到暂存区
git commit -m "修改"			              把暂存区的所有内容提交到当前分支
git status  				                    查看当前的状态
git diff 				                        查看修改了什么
git push
git log    				                      查看提交记录
git reflog 				                      查看回退记录
git log --graph				                  查看分支合并图
git log --pretty=oneline 		            查看简化后的提交记录
git reset --hard HEAD^ 			            回退到上一个版本
git reset --hard 1094a 			            回退错了，撤回到历史的某个版本
git diff HEAD -- readme.txt 		        可以查看工作区和版本库里面最新版本的区别
git checkout -- xxx.txt      		        把文件在工作区中的修改全部撤销
git reset HEAD  xxx.txt         	      把文件在暂存区中的修改全部撤销(git add)
git checkout -b xxx			                创建xxx分支，并切换到dev分支
git branch				                      查看本地所有的分支和当前分支
git branch -r				                    查看远程所有的分支
git branch -a				                    查看所有远程和本地的分支
git branch xxx				                  创建xxx分支	
git checkout xxx			                  切换到xxx分支
git branch -d  xxx			                删除本地xxx分支
git merge xxx				                    把xxx分支合并到当前分支
```


###  git教程

> git入门指南

****

### 命令

|命令|意义|
|---|---
|git --version|查看版本
|git config --global user.name "username"|配置用户名
|git config --global user.email "email"|配置邮箱
|git init |初始化一个仓库
|git remote |查看远程库的信息
|git remote -v |查看更详细远程库的信息
|git remote add origin git@github.com:michaelliao/learngit.git|本地和远程仓库关联
|git clone xxx|克隆一个项目到本地
|git add . |把文件添加到暂存区
|git commit -m ""|把文件提交到本地仓库
|git commit -am " "|等同于前两步
|git rm -r --cached .|把所有文件从版本控制中移除
|git status|查看状态
|git diff|查看git status具体修改了哪儿
|git log |查看提交日志信息
|git log --pretty=oneline |简化版的日志信息
|git log --pretty=oneline --abbrev-commit|
|git reset --hard HEAD^|回退到上一个版本
|git reset --hard 1094a|回退到一个固定版本
|git reflog |查看所有提交日志，包括回退的
|git diff HEAD|查看工作区和本地仓库里面最新版本的区别
|git diff HEAD -- readme.txt|查看特定文件在工作区和本地仓库里面最新版本的区别
|git diff commitID commitID|展示本地仓库中任意两个commit之间的不同
|git diff --cached|暂存区和本地最近的版本(commit)的different(不同)
|git diff HEAD|输出工作区、暂存区和本地最近的版本(commit)的different(不同)
|git checkout .|撤销所有工作区的修改(git add 之前)
|git checkout -- xxx |撤销特定文件在工作区的修改(git add 之前)
|git reset HEAD .|撤销所有暂存区的修改，重新放回工作区  (git add 之后)
|git reset HEAD <file>|撤销特定文件在暂存区的修改，重新放回工作区 (  git add之后)
|rm xxx|删除文件
|git rm xxx|删除文件
|git branch -vv|展示本地分支关联远程仓库的情况
|git branch | 查看本地分支
|git branch -d dev |删除dev分支
|git branch dev | 创建分支
|git branch -r|查看所有远程分支
|git branch -a|查看所有远程分支和本地分支
|git branch -vv|查看本地分支和远程分支的关联状态
|git checkout dev |切换到dev分支
|git checkout -b dev|创建dev分支并切换到dev分支
|git checkout -b <branch-name> origin/<branch-name>|创建并切换到远程分支
|git push origin --delete <remote-branchname>|删除远程分支
|git branch -m <new-branch-name>|重命名本地分支
|git branch -u origin/mybranch|关联远程分支
|git merge dev |把dev分支合并到当前分支
|git merge --no-ff branchname|merge代码的时候添加描述文字
|git log --graph |查看分支合并图
|git tag|查看标签列表
|git tag v1.0 | 创建一个标签
|git tag v0.9 f52c633|对特定标签打tag
|git describe --tags --abbrev=0|展示当前分支的最近的tag
|git fetch --all && git reset --hard origin/master|抛弃本地所有的修改，回到远程仓库的状态
|git update-ref -d HEAD|把所有的改动都重新放回工作区，并清空所有的commit，这样就可以重新提交第一个commit了
|git stash|把当前工作现场“储藏”起来，等以后恢复现场后继续工作
|git stash list|
|git show|
|git stash|
|git stash ls|


****

### git教程

Git的版本回退速度非常快，因为Git在内部有个指向当前版本的HEAD指针，当你回退版本的时候，Git仅仅是把HEAD从指向append GPL：

![](https://github.com/TinkerDeng/gitTest/blob/master/images/0.jpeg)

****

### 版本库

Git为我们自动创建的第一个分支master，以及指向master的一个指针叫HEAD

* git add      把文件添加到暂存区
* git commit   把暂存区内容提交到当前分支

![](https://github.com/TinkerDeng/gitTest/blob/master/images/1.jpeg)
![](https://github.com/TinkerDeng/gitTest/blob/master/images/3.jpeg)



### 暂时不懂的api

* 删除已经合并到master的分支
    * git branch --merged master | grep -v '^\*\|  master' | xargs -n 1 git branch -d

#### git diff HEAD -- common.css 

> 查看工作区和版本库里面最新版本的区别

```diff
- body{color:#ff0000;}
+ #app{font-size:20px;}
```


