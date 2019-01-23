# less

## 目录

* [编译工具](#编译工具)
* [语法](#语法)

### 编译工具

1. koala[网址](http://koala-app.com/index-zh.html)（软件可以设置中文的）

### 语法

```css
    @charset "utf-8"
    
    /*注释会被保留*/
    // 注释不会被保留
    
    @color:#ff0000;
    body{
        color:@color;
    }
    /*混合*/
        .border{border:1px solid #ddd}
        .xxx{.border;}
    /*混合-传参*/
        .border(@border_width:3px){
            border:@border_width solid #ddd;
        }
        .xxx{.border(10px)}
    /*匹配模式*/
        .rangle(top,@color,@width){
            border-top-width:@width;
            border-bottom-color:@color;
        }
        .rangle(bottom,@color,@width){
            border-bottom-width:@width;
            border-bottom-color:@color;
        }
        .rangle(@_,@color,@width){
            width:0;
            height:0;
            overflow:hidden;
        }
    /*@arguments*/
        .border(@width:10px,@color:#ff0000,@style:solid){
            border:@arguments;
        }
    /*避免编译:less不主动帮计算*/
        .width{
            width:~"calc(50-1-)";
        }
        
```
