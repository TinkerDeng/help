# react-native

## 目录

* [介绍](#介绍)
* [开发工具](#开发工具)
* [定义组件](#定义组件)
* [生命周期](#生命周期)
* [导入与导出](#导入与导出)
* [ref](#ref)
* [事件](#事件)
* [调试技巧](#调试技巧)

#### 介绍 

> 开发移动端跨平台APP的技术框架

> 它内部构建了一个用于渲染js的引擎

#### 安装工具

1. node.js
2. React Native Command Line
3. Android Stadio/XCode(ios)

#### 初始化

```git
    npm install -g react-native-cli
    react-native init FirstApp
    
    // android命令行运行
        //启动一个android的模拟器 
            emulator -avd 5 -gpu off 
        //或者已经有一个连接电脑的设备
     
        
    react-native run-android
```
#### 开发工具

1. webstorm
2. nuclide+watchman(mac)

#### 定义组件

```javascript
/*es6方式*/
    import React,{Component} from "react";
    import {Text} from "react-native";
    export default class Test extends Component{
        static defaultProps={
            name:"test"
        }
        state={ //方式二
            size:80
        }
        constructor(props){
            super(props);
            this.state={ //方式一
                
            }
        }
        static propTypes={ //类型检查
            name:PropTypes.string.isRequired
        }
        render(){
            const obj={name:1,age:20}
            return <Text {...obj}>test</Text>
        }
    }
    
/*es5方式*/

    const Test=React.createClass({
        render(){
            return <Text>test</Text>
        }
    });
    module.exports=Test;
    
/*函数式:无状态，无法使用this，不能操作生命周期方法*/

    function TestComponent(props){
        return <Text>test{props.name}</Text>
    }
    module.exports=TestComponent;
    
/*继承*/

    class abc{
        constructor(name,age){
            this.name=name;
            this.age=age;
        }
    }
    class ccc extends abc{
        constructor(){
            super("test",20)
        }
    }
/*样式*/
    <view style={style.container}></view>
    const style=StyleSheet.create({
        container:{
            textAlign:"center",
            color:"#ff0000"
        }
    });
```

#### 生命周期

```git
    getDefaultProps                                 (es6 static defaultProps)
    gitInitialState                                 (es6 constructor(props))
    componentWillMount
    render
    componentDidMount
    componentWillReceiveProps(nextProps)            (组件的props发生变化时)
    shouldComponentUpdate(nextProps,nextState)      (是否渲染组件)
    componentWillUpdate(nextProps,nextState)        (如果上面返回true的话执行)
    render
    componentDidUpDate(prevProps,prevState)
    componentWillUnmount                            (组件离开时)
```

#### 导入与导出

```javascript
    export {x:1,y:2}
    import {x,y} from "./xxx.js"
```

#### ref

```
    res是组件被渲染后，指向组件的一个引用
    <Test ref="xxx"></Test>
    <Test ref={xxx=>{this.test=xxx}}></Test>
    this.refs.xxx.method //获取组件里的方法
```

#### 事件

```
    onPress                         单击执行事件
    onLongPress                     用户长时间按压(delayLongPress 长按延时多长时间执行)
    onPressIn (delayPressIn)      单击开始回调 
    onPressOut (delayPressOut)    点击结束回调
    disable                         禁用按钮
    TouchableWithoutFeedback:       响应用户的点击事件，不显示视觉反馈
    
    TouchableHighlight:             响应用户的点击事件，背景会变暗的效果(onPress)
        //属性
        activeOpacity:0.84 设置不透明度 
        underlayColor:遮罩颜色
        onHideUnderlay:当手指结束点击时衬底会被隐藏
        onShowUnderlay:当手指刚开始显示时衬底会显示
        style:定义view的按钮样式
        <TouchableHighlight><view style={style.button}>aaa</view></TouchableHighlight>
        
    TouchableOpacity:               响应用户的点击事件，降低按钮的透明度
        //属性
        activeOpacity:0.84 设置不透明度 
        
    TouchableNativeFeedback:        响应用户的点击事件,水波纹的效果（只支持android）
        // 属性
        background={TouchableNativeFeedback.SelectableBackground()}
```

#### 组件

```
    Alert
    <Image source="" resizeMode></Image>
```

#### 调试技巧

```

```
