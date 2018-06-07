# npm

    账号：denglier

## 命令
```
npm -v                                  查看npm版本
npm version                             更新版本然后运行上面的代码再发布
npm adduser                             创建npm账号
npm publish                             发布一个新的包或一个新版本
npm login                               将账号信息存储在本地客户端
npm config ls                           确认账号信息已经存储在客户端
npm publish                             发布程序包
npm config set save-exact true          锁定版本号
npm config list                         查看
npm i express --save --save-exact       固定版本号
npm shrinkwrap                          锁定包括依赖dependencies
npm root                                查看依赖项目所在的目录
npm root -g                             查看全局模块安装目录
npm view jquery versions                查看模块全部版本
npm view xxx  dependdencies             查看包的依赖关系
npm view xxx  --versions                查看一个包的所有版本
npm search xxx                          查找模块
npm repo xx                             打开npm仓库地址git地址
npm update xxx                          升级依赖包至最新版本
npm prune                               清除未使用的模块
npm  list                               查看已安装的模块
npn config set package-lock false       禁用lock锁定
npm view webpack repository.url         查看包的源文件地址
npm view 模块名  engines                查看当前模块依赖的node最低版本号
npm outdated                            检查包是否已经过时

```
## nrm   切换国内国外的源

```
npm i nrm -g     安装                       
nrm ls           查看列表
nrm use cnpm     切换源

```
## npm ls

```
npm ls以树形结构打印依赖包极其版本
npm ls —json 以json格式输出
npm ls —global 输出全局依赖信息
npm ls —prod 仅输出dependencies的依赖
npm ls --dev 仅输出devDependenci的依赖
npn ls --depth 1输出一层依赖关系
```
