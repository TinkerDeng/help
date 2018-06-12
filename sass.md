# sass 学习指南

@charset "UTF-8";

## 基本语法

* $defaultBgColor:#ff0000;
* $color:#ff0000;变量

## @extend 继承
```
    .class1{
        border:1px solid #ddd;

    }
    .class2{
        @extend .class1;
        color:#ff0000;
    }
```

## @mixin可以重用的代码快,可以传递参数，设置初始值
```
    @mixin left($value: 10px) {
　　　　float: left;
　　　　margin-right: $value;
　　}
　　div{
　　    @include left();
　　}
```
## if条件判断
```
    p{
        @if lightness($color) > 30% {
    　　　　background-color: #000;
    　　} @else {
    　　　　background-color: #fff;
    　　}
    }
```

## 自定义函数
```
    @function double($n) {
　　　　@return $n * 2;
　　}

　　#sidebar {
　　　　width: double(5px);
　　}
```

## demo
```
    @mixin placeholders{
        ::-webkit-input-placeholder {
            font-family: $fontFamily;
            color: $placeholderColor;
         }
    }
    @mixin flexBox{
        display: -webkit-box; /* 老版本语法: Safari, iOS, Android browser, older WebKit browsers. */
        display: -moz-box; /* 老版本语法: Firefox (buggy) */
        display: -ms-flexbox; /* 混合版本语法: IE 10 */
        display: -webkit-flex; /* 新版本语法: Chrome 21+ */
        display: flex; /* 新版本语法: Opera 12.1, Firefox 22+ */
    }
    @mixin flex-item {
        -webkit-box-flex: 1.0;
        -moz-box-flex: 1;
        -webkit-flex: 1;
        -ms-flex: 1;
        flex: 1;
    }
    /*从上到下排序*/
    @mixin flex-box-vertical {
        -webkit-box-direction: normal;
        -moz-box-orient: vertical; /*Firefox*/
        -webkit-box-orient: vertical;
        -ms-box-orient: vertical; /*Firefox*/
        -o-box-orient: vertical;
        -moz-flex-direction: column;
        -webkit-flex-direction: column;
        -ms-flex-direction: column;
        -o-flex-direction: column;
        flex-direction: column;
    }
    /*从左到右排列*/
    @mixin flex-box-horizontal {
        -webkit-box-direction: normal;
        -moz-box-orient: horizontal; /*Firefox*/
        -webkit-box-orient: horizontal;
        -ms-box-orient: horizontal; /*Firefox*/
        -o-box-orient: horizontal;
        -moz-flex-direction: row;
        -webkit-flex-direction: row;
        -ms-flex-direction: row;
        -o-flex-direction: row;
        flex-direction: row;
    }
    /*垂直居中对齐*/
    @mixin align-item-center{
        -webkit-box-align: center;
        -moz-align-items: center;
        -webkit-align-items: center;
        -ms-align-items: center;
        -o-align-items: center;
        align-items: center;
    }
    /*垂直底部对齐*/
    @mixin flex-box-bottom {
      -webkit-box-align: end;
      -moz-align-items: flex-end;
      -webkit-align-items: flex-end;
      -ms-align-items: flex-end;
      -o-align-items: flex-end;
      align-items: flex-end;

    }
    /*水平居中对齐*/
    @mixin justify-content-center {
       -webkit-box-pack: center;
       -moz-justify-content: center;
       -webkit-justify-content: center;
       -ms-justify-content: center;
       -o-justify-content: center;
       justify-content: center;
    }
    /*水平居左对齐*/
    @mixin justify-content-left {
       -webkit-box-pack: start;
       -moz-justify-content: flex-start;
       -webkit-justify-content: flex-start;
       justify-content: flex-start;
    }
    /*水平居右对齐*/
    @mixin justify-content-right {
       -webkit-box-pack: end;
       -moz-justify-content: flex-end;
       -webkit-justify-content: flex-end;
       justify-content: flex-end;
    }
    /*媒体类型*/
    $media-types:(
        landscape: "(orientation: landscape)",//横屏
        portrait:  "(orientation: portrait)",//竖屏
        xs:"(max-width:767px)",//手机横竖屏
        s:"(min-width: 768px) and (max-width: 1024px)",//ipad横竖屏
        m:"(min-width: 1025px) and (max-width: 1280px)",//笔记本
        l:"(min-width: 1281px) and (max-width: 1440px)",//台式机
        xl:"(min-width: 1441px)"//超大型台式机
    )
    /*z-index层级*/
    $z-index:(
        zindexDropdown:        1000 !default;
        zindexFixedTopbar:     1010 !default;
        zindexTooltip:         1020 !default;
        zindexAlert:           1030 !default;
        zindexModal:           1100 !default;
    )
    div{
        z-index:map-get($z-index, zindexDropdown)
    }
    /*common-color*/
    $common-color:(
        $warningColor: #514721 !default;
        $errorColor: #8A1F11 !default;
        $successColor:#264409 !default;
        $infoColor: #205791 !default;
    )
```
