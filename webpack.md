# webpack

### plugin 插件

#### 理论知识

1. compiler和compilation是plugin和webpack之间的桥梁
1. compiler包含了webpack的所有配置信息，包含loader，options，plugins，可以理解为webpack的实例
1. compilation包含了当前的模块资源，编译生成文件，变化的文件等，当webpack以开发模式运行时，每当检查到一个文件变化，一次新的compilation被创建
1. compilation对象提供了很多事件回调供插件扩展，通过compilation也可以读取到compiler对象
1. compiler代表了整个webpack从启动到关闭的生命周期，而compilation只是代表了一次新的编译
1. webpack就像一个生产线，这条生产线上的每个处理流程都是单一的，多个流程存在依赖关系，完成当前的处理后才交给下一个流程去处理
1. 插件就是插入到生产线上的一个功能，再特定的时机对生产线上的资源做处理
1. webpack通过Tapable来组织这条生产线，compiler和compilation都继承自tapable，可以直接在这两个对象上广播和监听事件

#### demo

```
class Test {
  /**
   * 在构造函数中获取用户给该插件传入的配置
   * @param options
   */
  constructor(options) {
    this.options=options;
  }
  /**
   * Webpack 会调用 BasicPlugin 实例的 apply 方法给插件实例传入 compiler 对象
   */
  apply(compiler) {
    console.log(2222);
    compiler.plugin('compilation', function (compilation) {
      console.log(111);
    });
  }
}
module.exports = Test;

new Test();
```
