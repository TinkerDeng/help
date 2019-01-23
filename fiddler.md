# fiddle 代理工具

## 目录

* [功能详解](#功能详解)
    * [手机抓包](#手机抓包)
    * [手机抓包步骤](#手机抓包步骤)
    * [file下面的气泡按钮](#file下面的气泡按钮) 
    * [replay](#replay) 
    * [x](#x) 
    * [模式切换](#模式切换)
* [监控面板](#监控面板)

### 功能详解

#### 手机抓包

[网址](https://blog.csdn.net/shimengran107/article/details/78644862)

#### 手机抓包步骤
1. Tools-> Fiddler Options->Connections，勾选"Allow remote computers to connect" 
1. 打开Fiddler,右上角有一个Online，这里也可以查看IP
1. 保证手机和电脑在同一个网管，给手机设置代理
1. 打开浏览器，输入ip:端口号下载证书
1. 点击最下方的“FiddlerRoot certificate”按钮，下载证书



#### file下面的气泡按钮

> 针对特定的请求添加备注

#### replay

> 回放按钮，对请求进行回放（快捷键r）

#### x

> 清空控制面板
>> 清空全部
>> 过滤到图片的请求
>> 过滤掉非200的请求
>> 过滤到不是来自于浏览器的请求

#### go

> 调试debug
>> 最底下状态栏设置断点，箭头朝上，请求发送的时候断点，朝下，请求相应的时候断点

####  stream 模式切换
     
> 缓冲模式：所有的请求都通过之后一起返回
> 流模式： 实时把服务器返回给客户端

#### decode

> 解压请求

#### keepsession

> 保持回话

#### any process

> 过滤请求
>> 点击一下，一如到chrome浏览器，只监听chrome浏览器的请求

#### find查找功能

#### save 

> 保存当前请求的回话，然后需要使用的时候直接file->open

#### 相机:保存截图

#### textwizard编码/解码

#### tearoff 分离面板

#### MSDN搜索

#### 底部状态面板

##### 黑色区域：控制台

##### capturing:控制fiddle是否工作

##### web browsers 过滤回话来源

> 捕获来自于浏览器的请求
> 捕获来自于非浏览器的请求

##### 数子

> 记录的当前展示的回话的数量

#### 监控面板

1. statistics 数据统计，性能统计 rtt往返时间
2. inspector 对请求进行解包
3. autoresponder 把服务器返回的文件使用本地的文件做代理，选择一个请求，拖进autoresponder面板，选择替换文件，线上如果某一个文件出现问题，把此文件映射到本地的文件看看修改效果
4. composer前后端接口连调，把请求直接拖进面板，通过改变请求参数重新发送请求

#### 工具

##### tools->host->配置host文件地址，改变请求的地址

##### 文件替换

#### 网络限速
 
##### fiddlerscript 下载插件

> onbeforerequest设置速度 (请求，访问速度)

##### 自己开发第三方插件 willow  
