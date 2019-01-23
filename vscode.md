# vscode

## 目录

- [常用操作](#常用操作)
- [必用快捷键](#必用快捷键)
- [必装插件](#必装插件)
- [snippets](#snippets)
- [我的配置](#我的配置)

### 常用操作

1. `command+ -`:放大缩小整个编辑器
2. `command+b`:隐藏显示侧边栏
3. `editor.mouseWheelZoom": true`:Ctrl+滚轮实现字体缩放

### 必用快捷键

```git
    command+，          打开配置
    command+shift+p     显示所有命令
    command+k+n	        搜索node_modules文件（search node modules插件)
    alt+shift+f         格式化代码（format docuemnt）
    command+alt+i       添加文件头注释
    shift+alt+a         添加多行注释
    command+option+[    代码折叠显示
    command+k+0         折叠所有代码
    command+k+j         展开所有代码
    command+e           ？gotofile搜索项目
    command+p           进入哪个文件,快捷查找文件
    command+shift+f     文件夹中查找
    command+k+s         快捷键列表
    command+f1          在浏览器中运行html文件
    command+b           explorer显示隐藏
    ctrl+r              最近打开的项目
    ctrl+g              跳转到行号
    ctrl+`              打开编辑器终端
    command+delete      删除一行
```

### 必装插件

```
auto rename tag         修改HTML标签时，自动修改匹配的标签
Markdown Paste          从剪切板粘贴图片到markdown文件
                            keymap:command+shift+v
                            config:"pasteImage.path": "./images/" 设置粘贴图片的存储路径
GitLens                 查看谁提交了git代码
vscode-fileheader       新建文件添加文件头注释
vscode-icons            文件的类型图标（html，css ，js）
project-manager         vscode快速切换项目（先保存，1.最底部有个文件夹切换，2.command+alt+p快捷键）
beautiful               格式化代码插件
code runner             一键搭建各种语言的学习测试环境（ctrl+alt+n）
debugger for chrome     和chrome配合调试 （设置断点）
eslint                  npm install -g eslint （eslint --init 初始化）
intellisense for css    css的智能化提示
npm
npm  intellisense
path intellisense       文件路径自动补全
Path Autocomplete       引入文件时路径提示
Typescript Hero         比如自动import
Add jsdoc comments
view in browser         command+f1在浏览器中打开（view in browser插件）
typings auto installer  变量自动补全提醒功能
code snippets           es6代码提示
Bracket Pair Colorizer  不同层级的括号显示不同的颜色，方便查找括号作用域
chinese simpilfied      中文语言包
```

### config 配置

```json
{
  "editor.mouseWheelZoom": true,
  "eslint.autoFixOnSave": true, // 保存应用easlint格式
  "eslint.validate": [
    "javascript",
    "javascriptreact",
    {
      "language": "html",
      "autoFix": true
    },
    {
      "language": "vue",
      "autoFix": true
    }
  ],
  "terminal.external.osxExec": "iTerm.app",
  "terminal.integrated.fontFamily": "Source Code Pro for PowerLine",
  "terminal.integrated.cursorStyle": "line"
}
```

### 好用设置

1. log() 默认第一个，设置=》snippetSuggestions=》value=》设置成 top

```
     "Print to console": {
            "prefix": "log",
            "body": [
                "console.log('$1');",
                "$2"
            ],
            "description": "Log output to console"
        }
    }
    prefix      :这个参数是使用代码段的快捷入口,比如这里的log在使用时输入log会有智能感知.
    body        :这个是代码段的主体.需要设置的代码放在这里,字符串间换行的话使用          \r\n换行符隔开.注意如果值里包含特殊字符需要进行转义.
    $1          :这个为光标的所在位置.
    $2          :使用这个参数后会光标的下一位置将会另起一行,按tab键可进行快速切换
    description :代码段描述,在使用智能感知时的描述

    直接输入log可以立马选择console.log
```

#### vscode 工作去和终端切换设置

1.https://blog.csdn.net/chenh297/article/details/80076437;

```
    1.open keyborad shortcuts
    2.输入focus terminal 蓝色字体

    快捷键：ctrl+j 终端 ctrl+1工作区
```

# 常用快捷键

```
    Alt + F12               	显示代码片段定义
    shift + F12                 显示所有引用
    f2                          重命名
    command+z                   后退
    command+y                   前进

    command+\                   切分窗口
    command + 1/2/3	            切分焦点在不同的切割窗口

    f8                          跳转到下一个错误或者警告
    shift+f8                    跳转到上一个警告或者警告
    control+r                   最近打开的项目
    command+p 				    最近打开的文件，搜索文件
    command+shift+o             跳转到符号
    ctrl+shift+c                电脑打开终端
    command+`                   编辑器打开终端

    command+h                   替换

    command+shift+v             预览markdown文件

    command + Shift + F	        打开全局搜索
    command + shift + h         打开全局替换
    command+f                   查询
    f3                          查询下一个
    shfit+f3                    查询上一个
    alt+enter                   选中所有查询到的内容
    command+f2                  选中所有查询到的内容
    Alt + C / R / W		        不分大小写/使用正则/全字匹配

    command+i                   选中当前行

    command+d                   选中一个词汇
    command+k+d                 移动当前选中的词汇到下个匹配选择的位置,统一替换

    alt+click                   多点编辑
    command+alt+up/down         上下插入光标,多点编辑
    command+u                   撤销最后一个光标

    command+i                   选中当前行

    Shift + Alt + (drag mouse)	鼠标拖动区域，同时在多个行结束符插入光标,统一替换，删除，添加

```

## 快捷键

```
command+o               打开项目文件夹
command+shift+n         快速打开一个编辑器
command+shift+w         快速关闭一个编辑器
command+箭头			移动到顶部或者底部
command+n               新建文件
command+o               打开文件

alt+箭头				向上移动一行
alt+shfit+箭头		    向上复制一行
alt+点击				插入多个光标

command+shift+k			删除一行
command+delete          删除一行

command+inter			向下插入一行
command+shfit+enter		向上插入一行

command+shfit+\			匹配到花括号的闭合处，跳转

home                    跳转到行头
end                     跳转到行尾

command+home            跳转到页头
command+end             跳转到页尾

Ctrl + up/down	        行视图上下偏移
Alt + PgUp/PgDown	    屏视图上下偏移

command+[			    行缩进

command+shfit+[         折叠代码
command+shift+]         展开代码

command+/               添加删除注释
shfit+alt+a             添加多行注释
command+shfit+a         截屏

command+shfit+l或者command+f2		选中所有与当前选中内容相同部分，统一替换
command+f				查找
command+option+f			替换
command+shift+z				撤销返回
control+alt+i				文件头注释
command+m				格式化jsx（jsx-beautify插件）
control+alt+d 				方法注释（document this插件）
command+f1				在浏览器中打开（view in browser插件）
选中文件+enter				重命名
command+b				格式化代码
command+b               左边的导航显示隐藏
alt+shfit+f				格式化代码
command+d				选中一个词
command+shift+t				打开上一个打开的文件
alt+shfit+a				多行注释

command+alt+v           复制剪切板图片（paste image）

command+g 				跳转到行号
command+t               列出所有符号
command+m               按照tab移动焦点
Shift + Alt + right	    从光标处扩展选中全行
Shift + Alt + left	    收缩选择区域
command+k+s             快捷键设置

```

### 插件集合

##### `Local History` 查看本地文件的修改记录

> [链接地址](https://github.com/zabel-xyz/local-history)

```javascript
// 使用一
// command+shift+p
// view:local history
// 使用二
// command+shift+p
// local history : show all
// 在本地的 .history目录里面会有记录
```

##### `search node_modules` 搜索 node_module 插件

> [链接地址](https://marketplace.visualstudio.com/items?itemName=jasonnutter.search-node-modules)

```javascript
// command+k+n 开始查找目录
```

```
4. css peek                             追踪至样式表中 CSS 类和 ids 定义的地方
5. Color Info                           颜色的详细信息
6. atom one dark syntax theme           主题
7. VSCode Great Icons                   给不同类型的文件配置不同的图标
8. eslint
9. vetur                                vue代码支持插件
Auto Close Tag  :                       匹配标签，关闭对应的标签。很实用【HTML/XML】
Auto Rename Tag :                       sublime和webstorm也有这个内置功能，改变标签的时候同时改动开闭合标签；【HTML/XML】
beautify :                              良好的拓展性，可以格式化JSON|JS|HTML|CSS|SCSS,比内置格式化好用
Code Runner  :                          代码编译运行看结果，支持众多语言
colorize :                              会给颜色代码增加一个当前匹配代码颜色的背景，非常好
Document This  :                        JSDOC注解调用，值得易用
Git History  :                          不得不赞的插件，谁用谁知道，功能很赞
HTML CSS Support  :                     这个也是必备插件之一
Path Autocomplete  :                    路径智能补全
Path Intellisense  ：                   路径智能提示.
SCSS IntelliSense Preview :             SCSS智能提醒，配置强大
Syncing:                                这个同步插件要比官方市场那个最高下载量的要好，支持删除同步！！！
Version Lens  :                         可以及时看到package.json内部版本的变动，很实用
Output Colorizer  :                     可以终端日志输出着色，实用
JavaScript (ES6) code snippets :        ES6的代码片段，实用
JavaScript Snippet Pack :               ES5及以下的代码片段，实用
stylelint :                             比内置的要全，更智能
Panda:                                  用了相当久的一套颜色高亮，个人感觉很耐看
Enki Theme (Material Design Inspired) : 当前用的代码高亮，个人感觉很赞
Material Icon Theme  :                  一套扁平化的文件图标，内置的seti也很优秀，还有simple icon 和vscode-icons
Express：                               可以在当前工作区运行服务器
Output Colorizer：                      输出面板从此有了色彩
Trailing Spaces：                       删除多余空行和行尾多余空格
vscode-icons：                          给文件加上好看的图标
CodeMetrics :                           可以计算TS/JS内代码的复杂度(比如函数这些),这些与代码质量和性能是挂钩的
Import Cost:                            就是你import一个东西的时候,可以计算改引入模块的大小!!!厉害吧
Prettier:                               这个东西在github上挺火,可以支持很多种新框架的格式,高度自定义,所以有人封装成了插件..实用!(vue,ng,react,jsx,ts)这些格式化毫无压力
RegExp Preview and Editor:              这个就厉害了.可以完美的展示你写的正则,图形化给你看你写正则的形成
Git Lens:                               暂时没有发现比这个看git记录更为详细了,内置功能很多..很方便
SCSS IntelliSense:                      scss的智能提示
Vue Peek:                               转到定义,这个插件就是让vue也支持这个功能,实用!
Vue VSCode Snippets:                    很全面的vue代码片段
Useful React Snippets:                  React的snippet
ng-zorro snippets:                      ANTD的ng4+版本,阿里发布的..很精致的UI框架
Ionic 3 snippets:                       ionic3的代码片段
rocket-ui:                              颜色很对我眼
npm Intellisense :                      正如标题所说,在写引入模块的时候智能提示!!
NPM Smart Importer :                    与上个的插件的差异是智能补全,比如你 copy 了一些代码,而木有引入部分模块!可以点击引入!
NPM Dependency Links :                  这个就是方便你在初始化脚手架项目之后想了解某些模块,点击直接调到npm 模块发布页面...省去了打开浏览器,搜索....
ExpressJs 4 Snippets :                  如标题所言,里面汇总了70个片段,基本是 ES6的语法的!!
Pug :                                   这是模板语言的代码片段,严格来说并不属于 node,问题这货基本用于服务端渲染的模板语言,一般和 node 的服务端框架搭配...
Auto Import - ES6, TS, JSX, TSX:        这个插件是作者在一个长期不更新的项目加以维护的,类似智能补全的,基本跟进主流
React Native Tools:                     让 vscode可以写 RN 的插件,包括调试!
TSLint Vue :                            让tslint 支持vue单组件内 ts 的语法
css-triggers:这个插件的亮点就是可以看到渲染的流程和理论...可以当做参考工具
HTML SCSS Support: scss的智能补全,支持在 html,ng,vue,.net等使用(布局局限具体看文档).
Autoprefixer: 若是基于脚手架的项目基本配置下就好了(不用这个插件)..这个一般用于你想写点什么或者维护老项目,可以省点时间的
CSS Grid Snippets: CSS Grid 的代码片段,CSS Grid是下一代的布局姿势,不过目前兼容性很渣..成为主流可能要等个三四年,移动端上好一些(但只限于比较新的系统)
Babelrc: 验证babelrc内的语法格式!!
CodeMap: 可以理解为"大纲",支持ts,md,python . 挺实用的
Debugger for Chrome: 更新迭代了那么久,稳定性已经很不错了,非常棒的调试工具.用过都说好
Complete JSDoc Tags : 智能提示补全JSDOC的语法
Git Project Manager: 适合有多个git项目的小伙伴,可以快速跳转,比如打开文件夹慢慢找快 N 倍
Git Branch Warnings: 一个很温馨的提醒,可以高亮某个分支提醒你要慎重,这个小功能感觉以后会内置
jumpy: 羡慕vim党,但是不会耍,想快速跳转到指定位置!这个就可以...
licenser: 可以快速生成开源协议的头部!!,配置自己的用户名和邮箱等,挺实用的
Bookmarks: 给文件某个位置打标签,用来快速跳转的..不知道这个功能到现在为何没内置!!
Markdown Preview Enhanced: 国人出品的精品插件!!!涵盖的东西很多,上至公式下至导出(装了这个其他都是可以选装了),不过你要跟着它提供的文档把对应的功能点依赖给补齐了..适合愿意折腾的
Markdown All in One: 添加了一些内置md 没有的,比如支持 github的 tasklist,table formatter,还有 TOC 和快捷键这些
Markdown+Math: 支持多种数学公式的展示!!
Markdown PDF: 把 MD 转为 PDF,支持emoji,checkbox和语法高亮
Markdown Preview Mermaid Support:支持Mermaid规范的流程表生成
Markdown Emoji: 支持 md 插入emoji..但是用起来支持的力度不怎么够,不知道作者会不会继续维护下去..但是常见的emoji是有的

MySQL: 操作 MYSQL
MongoDB: 操作 MongoDB
mssql: 操作 SQLSERVER,还内置了智能提示(针对T-SQL类的)..微软自家出品,必属精品!!
Python: 微软自家出品,必输精通,装上这个后vscode写 python 体验还是挺不错的
MagicPython: 戴上Magic,有人喜欢有人讨厌,看人吧..针对python魔术方法还有新特性的插件.好不好你说了算
Nasc VSCode Touchbar :提供了挺多实用的功能点,用了感觉还行
Cobalt2 Theme Official: 暗色调的,有一段时间感觉贼喜欢.
Brackets Light Pro : 亮色调的,用来写 MD 看起来很舒服,还有阅读代码(不写的时候)
Highlight Bad Chars: 这个插件的唯一亮点,你可以指定你想要高亮的特殊字符!!万花丛中一点绿!
Live HTML Previewer:编辑器内实时预览 html文件
Debugger for Firefox: 如标题所示,vscode 关联firefox进行调试,和Debugger for chrome一致
Paste JSON as Code: JSON概要快速转换为其他语言的类型格式!(quick-type)
Copy With Imports: 相当牛逼的插件,复制部分引用代码自动引入相关依赖...
React Native Snippet: RN 代码片段
ES7 React/Redux/GraphQL/React-Native snippets: 如标题所示,涵盖的代码片段贼丰富
Marko Syntax Highlighting: ebay 旗下Marko的语法高亮..挺有意思的一个类模板语言的 UI 库
YAML: yaml的高亮,校验及格式化
NPM-Scripts: 在侧边栏可视化执行 npm 命令(项目内的 package.json),小巧实用
File Tree View: 提供几个常见编程语言的函数或状态的树集合展示,可以快速点击跳转!!
JavaScript Test Runner Preview
: 快速执行单元测试,支持 Mocha 和 Jest
OCaml and Reason IDE: 两种语言的支持,后者 facebook 出的(有兴趣的可以去了解,挺超前)
GitLab Workflow: Gitlab 的快速管理工具
VS Live Share Preview: 牛逼哄哄的插件,实时协作..目前是预览版...等正式版了再专门抽时间写一篇这个的用法
Andromeda: 风骚黄绿
Happy Hipster: 清新脱俗的z主题风
Vue Theme: 应该有部分人喜欢这种风格...
react-explorer-addons: 增加鼠标右键直接生成react的组件模板,好不好用,用过的才知道
CSS Blocks: 支持css模块化的智能提示,跳转
perfect-css-modules: css modules ,作用类似同上
React PropTypes Intellisense: React props的智能提示
vscode-styled-components: 对styled-componnents的支持,高亮包括智能提示
styled-components-snippets : styled-components的代码片段
Vue TypeScript Snippets : 针对vue的ts代码片段
Comments in Typescript: 针对TS的注释插件,基于JSDoc定制
Class IO :  可以显示引用类相关的关系(在代码编辑区域显示一个对应的标志位)
ClassLens : 快速跳转到类的相关引用
TSLens: tslens的gutter,可以让你更直观的看到不同类型的引用,支持五种类型

GraphQL: 让VS Code支持GraphQL
npm-import-package-version : 在引入模块的时候直接展示该模块的版本,很实用!!
eggjs: 蛋框的相关帮助插件,代码片段,智能提示等
mpvue snippets: mpvue的一些代码片段,以及部分原生小程序的代码提示
minapp : 用VS Code写小程序必备的插件,里面有众多实用的特性集成
js-test-gen-vscode : 可以针对部分函数直接生成jest单元测试代码
Jest: 让你写Jest代码有IDE的感觉
Mocha Test Explorer: 针对mocha测试的GUI话,会给编辑器多一个独立的版块
Coverage Gutters : 可以直观的看到你代码覆盖率的区域
Polacode : 生成精美的代码截图,很漂亮,根据你当前主题配色生成的
vscode-pigments: 代码页面展示颜色代码并展示对应的颜色,非常实用
Subtle Match Brackets:快速高亮你配置的闭合,对于聚焦我们的光标区块代码很有帮助
vscode-live-server : 非常全面的HTML预览工具,支持众多实际开发需要的特性,比如https,代理,cros
Filter Line : 对于处理日志文件,可以快速筛选出我们需要聚焦的内容
Better Comments: 最好用的注释区域高亮,对于TODO这些支持也很好
:emojisense: : 可配置化(针对语言),智能提示emoji,非常实用..走过路过不要错过
Outrun : 目前用的款式,很喜欢这个调调
Night Owl
Noctis
Cobalt Next
Beautiful UI
Vim : 王牌插件,让vscode支持vim的常用特性,还集成几种常用vim插件的特性,喜欢的不容错过
Class Helper : 对class快速编辑,支持ts,js,php
Bash IDE: 对bash提供类似IDE的体验,跳转,智能提示这些
JSON Helper : 提供大纲功能,可以快速跳转编辑
Shortcut Menu Bar: 把几个很常用的行为做成图标内置在编辑区域内,对于非快捷键熟练的小伙伴有所用处
YAML Support by Red Hat Preview : 涵盖了对YAML的校验,智能提示,对于用这个写配置文件的很有用处
indent-rainbow: 会给缩进添加一种颜色,让你更加直观的看到代码层次
Web Search: 选择代码内容,快速跳转到搜索引擎,支持Google, DuckDuckGo, StackOverflow三种引擎,打开的是默认本地浏览器
vscode-pdfviewer: 直接可以在PDF内阅读PDF文档,支持目录这些
Projects+: 项目管理必备插件,可以快速录入本地项目的地址,打开..非常实用
```

```
    {
        "workbench.colorTheme": "Monokai Dimmed",
        "eslint.autoFixOnSave": true,
        "editor.mouseWheelZoom": true,
        "emmet.triggerExpansionOnTab": true
    }
```

### Angular 2+ && Typescript 2+必备插件推荐

```
Auto Import : 对于一堆组件的我们来说，这货简直贴心，支持JSX和typescript，还有一些细致化的配置参数
exports autocomplete : 和上个功能类似但是不等同，相当实用
TypeLens : 类型引用索引展示，用过visual studio的都看到过，相当强大的一个功能；换个名词可能更多人知道，peek file
TypeScript Import : 专门处理TS内模块导入的，和第一个互补；
Typings  : 这个就是用来处理d.ts的
AngularDoc for Visual Studio Code  : 这个插件可以分析整个项目的依赖生成一个类似思维导图的（经常嗝屁，用了懒加载之后基本不全）， 但是有另外一个相当实用的功能就是可以调用angular-cli的新建指令，在侧边栏右键可以直接看到;
Angular 2, 4 and upcoming latest TypeScript HTML Snippets : 在用这个插件之前，我装了几个NG2 snippet的插件，经过一段时间的比较，发现这个是比较全面和更新比较频繁的。。推荐嗯！！
语法
Latest TypeScript and Javascript Grammar :完美的支持beta及稳定版本的TS语法

```

### snippets 用户代码片段

> `文件=》首选项=》用户代码片段=》新建全局代码片段`

```json
{
  "h5 sample": {
    "prefix": "h",
    "body": [
      "<!DOCTYPE html>",
      "<html lang=\"zh-CN\">\n",
      "<head>",
      "\t<meta charset=\"UTF-8\">",
      "\t<meta name=\"viewport\" content=\"width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=0,minimal-ui:ios\">",
      "\t<meta http-equiv=\"X-UA-Compatible\" content=\"ie=edge\">",
      "\t<title>Document</title>",
      "\t<link rel=\"stylesheet\" href=\"$1\">",
      "\t<script src=\"$2\"></script>",
      "</head>\n",
      "<body>\n$3",
      "</body>\n",
      "</html>"
    ],
    "description": "html5 template"
  }
}
```

### 我的配置

```javascript
    {
        "workbench.colorTheme": "Visual Studio Dark",
        "eslint.autoFixOnSave": true,
        "emmet.triggerExpansionOnTab": true,
        "window.zoomLevel": -1,
        "editor.fontSize": 18,
        "files.autoSave": "afterDelay",
        "eslint.autoFixOnSave": true,
        "eslint.validate": [
            "javascript",
            "javascriptreact",
            {
            "language": "html",
            "autoFix": true
            },
            {
            "language": "vue",
            "autoFix": true
            }
        ],
        "workbench.sideBar.location": "left",
        "explorer.confirmDelete": false,
        "editor.mouseWheelZoom": true
    }
```
