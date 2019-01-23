 
# native技术
 
1. react native 原生开发 
2. weex 原生开发
 
### h5与native通信
 
1. 判断是app环境 useragent
2. js core:callback方法
3. url schema

### url schema
```
    前端定义的方法,native实现
    var NativeBridge={};
    NativeBridge.getAddress=function(fn){
        //brige在这个函数体里面要有h5与native通信的方式,磨平我们整个差异
        requestHybrid({
            tagName:"xxxx",
            callback:function(){
                fn(data);
            }
        });
    }
    
    // 发出类似的请求
    hybrid://getAddress?callbackId=id
    
    
    直接调用
    NativeBridge.getAddress();
```

 
