# node

## 目录

* [fs模块](#fs)
* [模块](#模块)

### fs

```
// 异步读取数据 如果是相对路径是相对于当前进程（process.cwd()）所在的路径
 fs.readFile('./image.png', function (err, buffer) {
   if (err) throw err;
 });
```



### 模块

##### rimraf

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

##### less

```git
import less from 'less';
```




