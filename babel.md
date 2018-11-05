# babel

> babel是一个转译器，把同种语言的高版本规则翻译成低版本规则，允许你提前使用js语法

> 转译三个阶段:parsing、transforming、generating
>> 1.解析:将代码字符串解析成抽象语法树
>> 2.变换:将抽象语法树遍历转译
>> 3.生成：根据变换后的抽象语法树再生成代码字符串
>> 整体：ES6代码输入 ==》 babylon进行解析 ==》 得到AST
==》 plugin用babel-traverse对AST树进行遍历转译 ==》 得到新的AST树
==》 用babel-generator通过AST树生成ES5代码

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
 
