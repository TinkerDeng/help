
## CSS3动画,你写过什么?

#### 测试题,看大家对css了解多少

	1. perspective是用来干嘛的?
	2.cubic-bezier你用过吗，是干嘛的?
	3.z-index层叠上下文的层叠顺序知道是什么吗?
	4.transform有哪些值，都是干嘛的?
	5.:nth-of-type(n)和:nth-child(n)是什么意思，有什么区别?
	6.<label for=””></label> label标签的for是干嘛的?
	http://www.htmleaf.com/Demo/201506222087.html
	
#### 开发到现在遇到的问题？
	1.android手机上line-height不居中
		很诡异，同一个手机有的居中，有的不居中
	2.input框被键盘挡住
	3.单边阴影问题
	
###### line-height 在移动端的居中问题

参考网址：
	```https://www.cnblogs.com/dolphinX/p/3236686.html```
	
原因：
	```
	1.使用rem单位，字体大小出现小数点
	2.并且字体大小是奇数显示
	3.字体大小小于12px
	解决方案
	1.border:1px solid transparent;box-sizing:border-box;
	2.display:table;   display：table-cell;vertial-align:middle;
	3.font-size:48px;transform:scale(0.5);transform-origin:0% 0%;
	```
##### input框被键盘挡住

解决方案：
	1.原生滚动(body滚动)input不会被挡住
	2.flex-direction:column; justify-content:flex-end;
		只能解决一屏情况下input偏底部或固定在底部的情况
	3.监听onfus事件,改变element的scrollTop事件，
      需要判断ios，android环境
	4.element.scrollIntoView(true)或者scrollIntoViewNeeded()
     配合body{height:100%}   测试没有效果,不靠谱

##### 单边阴影问题

```box-shadow:	10px    10px    10px          10px            #ff0000          inset
		x轴       y轴       模糊值    扩展半径   阴影的颜色  内阴影```

### 动画应用场景

http://www.haodoxi.com/demo/35/
http://www.jq22.com/yanshi17899
http://h5.eqxiu.com/s/0Sohnquq
http://www.17sucai.com/preview/1/2016-10-20/jQuery-dtk/index.html
https://codepen.io/Manoz/pen/pydxK
https://www.html5tricks.com/demo/html5-boy-run-animation/index.html

### 三个DEMO演示

#### transition 加入购物车特效
#### transform 3d转换动画
#### animation 动画

### 贝塞尔曲线

百度百科定义：
		```又称贝兹曲线或贝济埃曲线，是应用于二维图形应用程序的数学曲线。一般的矢量图形软件通过它来精确画出曲线，贝兹曲线由线段与节点组成，节点是可拖动的支点，线段像可伸缩的皮筋，我们在绘图工具上看到的钢笔工具就是来做这种矢量曲线的。贝塞尔曲线是计算机图形学中相当重要的参数曲线，在一些比较成熟的位图软件中也有贝塞尔曲线工具。```
		
网址：
		```http://cubic-bezier.com/#.81,.05,1,.54```
		








#### 最后给大家推荐一本CSS书

![Alt text](./1528350897930.png)

#### 谢谢大家
