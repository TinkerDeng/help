# git

## 目录

* [生成秘钥](#生成秘钥)
* [全局配置](#全局配置)
* [命令](#命令)
* [常用](#常用)
* [生成项目网站](#生成项目网站)
* [gitbook](#gitbook)
* [全局配置](#全局配置)

### 生成秘钥

1. `ssh-keygen -t rsa -c "git邮箱"`		生成秘钥
2. `cd ~/.ssh` 查看生成了 id_rsa(私钥） id_rsa.pub（公钥）
3. 讲公钥的内容copy到gitlab中，生成ssh key
4. `ssh-add -K ~/.ssh/id_rsa 避免每次输入口令`
5. `ssh-keygen -p`或者删掉之前的

### 全局配置

```git
    git config --global user.name "dfc"                             设置用户名
    git config --global user.email "652988976@qq.com"               设置邮箱
    git config --global alias.st status 	                        配置别名st
    git config --global alias.co checkout	                        配置别名co
    git config --list                                               查看git配置列表
    git remote add origin gitUrl                                    本地库和远程库关联
    git config --global color.ui true	                            命令行git显示颜色
    git remote                                                      查看本地库关联的远程库的信息
    git remote -v				                                    查看本地库关联的更详细远程库的信息
    git remote rm remoteName		                                删除本地已经关联的远程库信息
    git diff 				                                        查看修改了什么
    git log    				                                        查看提交记录
    git reflog 				                                        查看回退记录
    git log --graph				                                    查看分支合并图
    git log --pretty=oneline 		                                查看简化后的提交记录    
    git reset --hard HEAD^ 			                                回退到上一个版本
    git reset --hard 1094a 			                                回退错了，撤回到历史的某个版本
    git diff HEAD -- readme.txt 		                            查看工作区和版本库里面最新版本的区别
    git clone gitUrl                                                克隆一个项目到本地 
    git rm -r --cached .                                            把所有文件从版本控制中移除
```

### 常用

```git 
    git push origin --delete branchName             删除远程分支
    git branch -d branchname                        删除本地分支
    git branch -D branchname                        删除本地分支
    git clone -b branchname url                     下载或者拉取指定分支
    git push origin branchName                      把本地库的内容推送到其他分支
    git rm -r --cached .			                清除本地ignore的缓存
    git config core.autocrlf false                  解决git add警告问题
    git clean -df                                   删除git checkout . 之后还存在的多余的文件
```

#### 命令

```
    git add .                                       把文件添加到暂存区
    git commit -m ""                                把文件提交到本地仓库
    git commit -am ""                               等同于前两步
    git config --global color.ui true	            命令行git显示颜色
    git version 				                    查看git版本
    git init 				                        初始化一个仓库
    git add  .				                        把文件修改添加到暂存区
    git commit -m "修改"			                把暂存区的所有内容提交到当前分支
    git status  				                    查看当前的状态
    git show --stat                                 查看提交记录
    git show                                        查看最后一次的提交纪律信息不同
    git diff 				                        查看工作区和版本库的不同
    git diff commitid commitid                      本地仓库中两个版本之间的变动
    git diff --cached                               输出暂存区和本地最近的版本(commit)的different(不同)
    git diff HEAD                                   输出工作区、暂存区 和本地最近的版本(commit)的different(不同)
    git push
    git log    				                        查看提交记录
    git log --pretty=oneline 		                查看简化后的提交记录
    git log --graph				                    查看分支合并图
    //git reset是直接删除指定的commit
    git reset --hard HEAD^ 			                回退到上一个版本.提交记录也会被删除
    git reset --hard HEAD~100                       回退到前100个版本
    git reset --hard 1094a 			                回退错了，撤回到历史的某个版本
    //git revert 使用一次新的提交来回滚之前的提交，也就是添加了一个新的commitid，内容是回退后的内容，不影响历史commit和history
    git revert HEAD                                 撤销前一次 commit
    git revert HEAD^                                撤销前前一次 commit
    git revert commitid                             撤销指定的版本，撤销也会作为一次提交进行保存
    
    git reflog 				                        查看所有的提交记录（包括回退的）
    
    git diff HEAD -- readme.txt 		            查看工作区和版本库里面最新版本的区别
    
    git checkout -- xxx.txt      		            把文件在工作区中的修改全部撤销(回到 git add 之前的状态)(恢复手动误删的文件,因为版本库还有)
    git checkout -- .                               撤销所有add的操作
    git reset HEAD  xxx.txt         	            把文件在暂存区中的修改全部撤销(回到 git commit 之前的状态)
    git rm common.css (git commit)                  从版本库中删除该文件
    
    git branch				                        查看本地所有的分支和当前分支
    git branch xxx				                    创建xxx分支	
    git branch -r				                    查看远程所有的分支
    git branch -a				                    查看所有远程和本地的分支
    git branch -d  xxx                              删除本地xxx分支
    git branch -D  xxx                              强制删除一个分支(没有合并过的)
    git branch -vv                                  展示本地分支关联远程仓库的情况
    git branch -m xxx                               重命名本地分支
    
    git checkout -                                  快速切花分支
    git checkout xxx			                    切换到xxx分支
    git checkout -b xxx			                    创建xxx分支，并切换到dev分支
    git merge xxx				                    把xxx分支合并到当前分支
    git merge --no-ff -m "merge with no-ff" dev     禁用Fast forward（Fast forward模式下删除分支后会丢掉分支信息）
    
    git stash                                       把当前工作线程储藏起来，恢复现场时再用    
    git stash list                                  查看stash列表
    git stash drop                                  删除statsh
    git stash apply                                 恢复，stash不删除
    git stash pop                                   恢复，把stash也删除了
    git stash apply stash@{0}                       恢复制定的的stash,statsh不删除
    
    git rebase                                      可以把本地未push的分叉提交历史整理成直线
    
    git tag                                         版本号列表
    git tag v0.1                                    打个版本号
    git tag v0.9 f52c633                            给特定版本打tag
    git show v0.9                                   查看版本信息
    git tag -d v0.9                                 删除tag版本号
    git push origin v1.0                            推送某个标签到远程
    git describe --tags --abbrev=0                  展示当前分支的最近的tag

    git commit --amend                              修改最后一次注释

```

### 生成项目网站 

1. [参考网址](https://pages.github.com/)
1. 登陆github 创建username.github.io的项目名称(username代表git名称,一定不能变)
1. git clone xxx
1. 创建index.html文件 push
1. 访问 [网址](tinkerDeng.github.io)

### gitbook

```git
    将md文件生成文档
        1. npm install -g gitbook-cli 
        2. 创建 SUMMARY.MD文件,格式如下
            # SUMMARY
            * [项目介绍](README.md)
            * [使用文档](doc/use/README.md)
                *[开发文档](doc/user/user.md)
        3. gitbook init （summary文件里面没有的md文件开始创建）
        4. gitbook build 将md文件生成html文件
```

#### 全局配置

```git 
    git config --global user.name "dengfengcun"                                 设置全局提交用户名
    git config --global user.email "email@example.com"                          设置全局提交邮箱
    git config -l/--list                                                        查看全局配置
    git config --global color.ui true                                           Git显示颜色，会让命令输出看起来更醒目
    git config --global alias.st status 	                                    配置别名st
    git config --global alias.co checkout	                                    配置别名co
    git remote add origin git@gitee.com:denger/demo.git                         本地库和远程库关联
    git remote                                                                  查看远程库的信息
    git remote -v                                                               查看本地库关联的远程库信息
    git remote rm remoteName		                                            删除本地已经关联的远程库信息
    git remote set-url origin git@gitlab.renrenche.com:finance/finance-h5.git   更换git地址
    git push origin master                                                      把本地库的内容推送到远程库
    git push -u origin master                                                   (-u,第一次提交把本地的master分支和远程的master分支关联起来)
    ssh-keygen -t rsa -c "git邮箱"		                                        生成秘钥
```

### 图片

![image](https://note.youdao.com/favicon.ico)


### 常见问题

```
    git pull 提示 no tracking information,则说明本地分支和远程分支的链接关系没有创建
    git branch --set-upstream-to <branch-name> origin/<branch-name>
```
