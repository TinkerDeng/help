# typescript

> javascript的超集，遵循es6规范，基于类的面向对象编程

## 目录

* [安装环境](#安装环境)
* [tsconfig.json](#tsconfig.json)
* [语法](#语法)


### 安装环境

```
    npm install -g typescript
    tsc --init #初始化一个.tsconfig.json的文件
```

### tsconfig.json
 
 ```javascript
    {
        "compilerOptions": {
            "module": "commonjs",   //指定生成哪个模块系统代码
            "target": "es6",        //目标代码类型
            "noImplicitAny": false, //在表达式和声明上有隐含的'any'类型时报错。
            "sourceMap": false,     //用于debug   
            "rootDir":"./src",      //仅用来控制输出的目录结构--outDir。
            "outDir":"./build",     //重定向输出目录。   
            "watch":true            //在监视模式下运行编译器。会监视输出文件，在它们改变时重新编译。
        },
        "include":[
            "./src/**/*"
        ],
        "exclude":[
            "views",
            "static"
        ]
    }
 ```

### 语法

```javascript
    
    // Any类型
    let notSure: any = 4;
    notSure = "maybe a string instead";
    notSure = false; // okay, definitely a boolean
    
    // Void类型:只能为它赋予undefined和null
    function warnUser(): void {
        console.log("This is my warning message");
    }
    
    
    // Object类型
    declare function create(o: object | null): void;
    
    // 数组类型
    let list: number[] = [1, 2, 3];
    let list: Array<number> = [1, 2, 3];
    let list: any[] = [1, true, "free"];
    let ro: ReadonlyArray<number> = [1,2,3];//只读数组，修改了之后不能更改
    
    // 元祖类型:表示一个已知元素数量和类型的数组,各元素的类型不必相同
    let x: [string, number];
    x = ['hello', 10];
    
    
    // 枚举类型:定义值 默认从0编号
        enum Color {Red = 1, Green, Blue} 
        let c: Color = Color.Green;
        // 由枚举的值得到它的名
        enum Color {Red = 1, Green, Blue}
        let colorName: string = Color[2];
    // 状态枚举
        export enum EStatus {
            BAN = 0,
            OPEN = 1,
            HIDE = 2,
            NOTBUY = 3
        }
        
    // 类型断言：也叫类型转换
        // 方法一
            //let someValue: any = "this is a string";
            //let strLength: number = (<string>someValue).length;
        // 方法二
            //let someValue: any = "this is a string";
            //let strLength: number = (someValue as string).length;
    
    //接口:对值所具有的结构进行类型检查
        interface LabelledValue {
          label: string;// 必须包含一个label属性且类型为string
          color?: string; // 可选属性
          readonly width:number; // 只读属性
           [propName: string]: any; // 除了上面的属性还带有任意数量的其他属性
        }
        function printLabel(labelledObj: LabelledValue) {
          console.log(labelledObj.label);
        }
        
    // 接口：定义函数类型:像是只有参数列表和返回值类型的函数,参数名不需要与接口里定义的名字相匹配
        interface SearchFunc {
            (source: string, subString: string): boolean;
        }
        let mySearch: SearchFunc;
        mySearch = function(source: string, subString: string) {
          let result = source.search(subString);
          return result > -1;
        }
    // 接口：约束数组类型
        interface StringArray {
          [index: number]: string;
        }
        let myArray: StringArray;
        myArray = ["Bob", "Fred"];
```

### interface

```
    interface ClockInterface{
        setTime(timer){};
    }
    class ChineseClock implements ClockInterface{
        setTime(){}
    }
    class WestClock implements ClockInterface{
        setTime(){};
    }
    
    function getCurrentClock(clockInt:ClockInterface,timer){
        ClockInterface.setTime(timer);
    }
    const chieseClock=new ChineseClock();
    const westClock=new WestClock();
    
    getCurrentClock(chieseClock,xxxx);
    getCurrentClock(westClock,xxxx);
    
```
