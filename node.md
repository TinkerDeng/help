# node

## 目录

* [模块](#模块)

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




