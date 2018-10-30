# babel

> javascript编译器，允许你提前使用js语法

## 目录

* [安装](#安装)
* [直接编译](#babel-cli编译)
* [babelrc](#.babelrc)

### 安装

```
npm install --save-dev babel-cli babel-preset-env
```

### babel-cli编译

```
    babel index.js 编译index.js文件
    babel index.js --out-file compiled.js 将结果写入制定的文件
    babel src --out-dir lib
```

### .babelrc
```
{
        presets：[
            es2015
        ],
        plugins:[]，
        env:[
            development:{
                plugins:[]
            },
            production:{
                plugins:[]
            }
        ]
    }
```

### babel-polyfill
    
babel只转换语法，babel-polyfill可以转换新的api
```
npm install --save-dev babel-polyfill
```
#### babel-preset-react

转换jsx语法

```
npm install --save-dev babel-preset-react
```

### babel-preset-env

相当于 es2015 ，es2016 ，es2017 及最新版本

### 自定义babel插件

[astexplorer.net](https://astexplorer.net/#/KJ8AjD6maa) 快速创建一个插件

[ generator-babel-plugin](https://github.com/babel/generator-babel-plugin)生成一个插件模板
 
