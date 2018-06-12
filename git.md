# git

## 全局配置
```
git config --global user.name "Your Name"
git config --global user.email "email@example.com"

git config --global alias.st status 	配置别名st
git config --global alias.co checkout	配置别名co

git remote add origin git@gitee.com:liaoxuefeng/learngit.git 本地库和远程库关联
ssh-keygen -t rsa -c "git邮箱"		生成秘钥
git rm -f --cached .			        清除本地ignore的缓存

```

## 命令
```
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
