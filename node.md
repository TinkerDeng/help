# node

## 目录

* [fs模块](#fs)
* [模块](#模块)
  * [download-git-repo](#download-git-repo)
  * [rimraf](#rimraf)
  * [pify](#pify)
  * [copy-dir](#copy-dir)

### fs
[地址](http://javascript.ruanyifeng.com/nodejs/fs.html)

### nodec常用模块

#### download-git-repo

> [地址](https://github.com/flipxfx/download-git-repo#downloadrepository-destination-options-callback)

> 安装

```
   npm install -D download-git-repo
```

> download(repository, destination, options, callback)

1. repository

* `GitHub` - github:owner/name#branch or simply owner/name#branch
* `GitLab` - gitlab:owner/name#branch
* `Bitbucket` - bitbucket:owner/name#branch
* `direct:url`- 直接下载

1. destination 下载路径

1. options:**{clone:true}**:git clone 下载代替 http download下载

1. callback回调函数

> demo

```git

  download('bitbucket:flipxfx/download-git-repo-fixture#my-branch', 'test/tmp', { clone: true }, function (err) {
    console.log(err ? 'Error' : 'Success')
  })

  download('direct:https://gitlab.com/flipxfx/download-git-repo-fixture.git', 'test/tmp', { clone: true }, function (err) {
   console.log(err ? 'Error' : 'Success')
 })
 
 download('flipxfx/download-git-repo-fixture', 'test/tmp', function (err) {
   console.log(err ? 'Error' : 'Success')
 })
 
```

#### rimraf

> 以包的形式包装rm -rf命令,就是用来删除文件和文件夹的 [链接](https://www.npmjs.com/package/rimraf)

```node
 import rimraf from "rimraf"
 rimraf.sync(path.resolve(__diranme,"dll")) //删除dll文件
```
##### pify

> 把回调函数风格的代码改成promise回调形式,promice化工具

```node
//安装
    npm install --save-dev pify 
//使用
    const fs = require('fs');
    const pify = require('pify');
    // promise化单一的方法
    pify(fs.readFile)('package.json', 'utf8').then(data => {
    	console.log(JSON.parse(data).name);
    });
    // promise化一个模块里面的所有方法
    pify(fs).readFile('package.json', 'utf8').then(data => {
    	console.log(JSON.parse(data).name);
    });
```

#### less

```git
import less from 'less';
```

#### copy-dir

> 复制文件或者文件夹到另一个路径
> [链接](https://github.com/liepinteam/copy-dir)

```javascript
 
var path = require('path');
var copydir = require('copy-dir');
copydir.sync('/my/from/path', '/my/target/path', function(stat, filepath, filename){
  // 过滤一些不需要拷贝的文件
  if(stat === 'file' && path.extname(filepath) === '.html') {
    return false;
  }
  if (stat === 'directory' && filename === '.svn') {
    return false;
  }
  return true;
}, function(err){
  console.log('ok');
});
```




