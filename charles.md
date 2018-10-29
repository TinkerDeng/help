# charles

<font color="#ff0000">charles代理切记关闭防火墙 切记</font>

## 目录

* [文档地址](#文档地址)
* [注意事项](#注意事项)
* [api](#api)

### 文档地址

[掘金](https://juejin.im/post/5b8350b96fb9a019d9246c4c)

### 注意事项

1. **电脑上一定要把proxy>macos proxy（window proxy）勾上**
2. **tool>map local:把当前的请求地址定位到指定的文件***
3. **tool>map remote：把当前的请求接口定位成其他的接口**
4. **tool>rewrite：改变请求的内容返回**

### api

#### throttle 节流 模拟网络 模拟网速慢

- Proxy>Throttle Setting>Enable Throttling

#### recording settings  

- 过滤(只监听过滤的域名的文件) proxy>recording settings>include>add   http baidu.com
- 在一个网址上选择focus,然后其他的请求就会被放到一个叫Other Host的文件夹里面

#### 断点

> 要针对某一个请求设置断点，只需要在这个请求网址右击选择Breakpoints就可以断点某一个请求了

#### 内容替换

> Tools->Rewrite Settings

#### Map Remote 请求重定向

> Tools->`Map Remote`开发中一般都是测试环境，想对比一下和线上版本的区别的话，可以将测试的请求重定向到正式环境下

### 图片资源
![](/assets/charles.png)
![](/assets/charles_tool.jpg)
