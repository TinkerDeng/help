# module

## 目录

* [download-git-repo](#download-git-repo)
* [rimraf](#rimraf)
* [pify](#pify)
* [less](#less)
* [copy-dir](#copy-dir)
* [git-clone](#git-clone)
* [json-server](#json-server)
* [body-parser](#body-parser)
* [express-session](#express-session)
* [query-string](#query-string)
* [husky](#husky)
* [memory-fs](#memory-fs)
* [serve-favicon](#serve-favicon)

### download-git-repo

[git 地址](https://github.com/flipxfx/download-git-repo)

```js
    /*
    npm install -D download-git-repo
    download(repository, destination, options, callback)
        1. repository
            * `GitHub` - github:owner/name#branch or simply owner/name#branch
            * `GitLab` - gitlab:owner/name#branch
            * `Bitbucket` - bitbucket:owner/name#branch
            * `direct:url`- 直接下载
        2. destination 下载路径
        3. options:**{clone:true}**:git clone 下载代替 http download下载
        4. callback回调函数
    */
    
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

### rimraf

[git 地址](https://github.com/isaacs/rimraf)

```javascript
    //npm install rimraf -D 安装
    import rimraf from "rimraf"
    rimraf.sync(path.resolve(__diranme,"dll")) //删除dll文件
```

### pify

```javascript
    /*
        把回调函数风格的代码改成promise回调形式,promice化工具
        npm install --save-dev pify 
    */
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

### less

```javascript
    //npm i -D less
```

### copy-dir

[git 地址](https://github.com/liepinteam/copy-dir)

```javascript
    //复制文件或者文件夹到另一个路径
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

### git-clone

[git 地址](https://github.com/jaz303/git-clone)

```javascript
    //cnpm i -D git-clone
```

### json-server

```json
    /*
        (mock rest api)
        步骤一：cnpm i -g json-
        步骤二：构建一个json文件,data.json 
        步骤三：json-server data.json
    */
    const json={
            "user:[
                {
                    "id":1
                }
            ],
            "list":[{
                "id":1
            }]
        }
```

### body-parser

```js
    /*
        将请求的数据转成json格式的
        cnpm i -D body-parser
    */
```

### express-session

```js
    /*
        存放服务端的session
        cnpm i -D express-session
    */
```

### query-string

[git地址](https://github.com/sindresorhus/query-string)

```javascript
    //cnpm i -D query-string
        //parse
        const queryString=require("query-string");
        const now = queryString("x=1&y=2");
        {
            x:1,
            y:2
        }
        //parseUrl
        //extract
        //stringify
```

### husky

[huskey git 地址](https://github.com/typicode/husky)

```javascript
    //提交git之前eslint语法验证
    //安装
        //cnpm i -D husky
    //引入方式一：package.json 添加如下语法
        {
            "husky": {
            "hooks": {
              "pre-commit": "npm test",
              "pre-push": "npm test"
            }
          }
        }
    //引入方式二：创建 .huskyrc .huskyrc.json .huskyrc.js
        {
          "hooks": {
            "pre-commit": "npm test"
          }
        }
```

### memory-fs

```javascript
    //在内存中操作文件,不在硬盘中操作文件
    var mfs = require("memory-fs");
    var fs = new mfs()
    fs.mkdirpSync("/a/test/dir"); // 同步创建一个目录
    fs.writeFileSync("/a/test/dir/file.txt", "Hello World"); //同步创建一个文件并写入内容
    fs.readFileSync("/a/test/dir/file.txt","utf-8"); // returns Buffer("Hello World") // 同步读取文件
    
    // Async variants too
    fs.unlink("/a/test/dir/file.txt", function(err) {
    	// ...
    });
    fs.readdirSync("/a/test"); // returns ["dir"]
    fs.statSync("/a/test/dir").isDirectory(); // returns true
    fs.rmdirSync("/a/test/dir");
    fs.mkdirpSync("C:\\use\\windows\\style\\paths");
```


### serve-favicon

[git 地址](https://github.com/expressjs/serve-favicon)

```javascript
    // cnpm i -D serve-favicon
```
