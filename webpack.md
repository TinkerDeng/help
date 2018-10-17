# webpack

> **webpack是当下最热门的前端资源模块化管理和打包工具**

## 目录

* [自定义插件](#自定义插件plugin)
  * [理论知识](#理论知识)
  * [compiler事件钩子](#compiler事件钩子)
  * [注意问题](#问题注意)
  * [案例演示](#demo)
* [参考链接](#参考链接)
  
### 自定义插件plugin

#### 理论知识

1. compiler和compilation是plugin和webpack之间的桥梁
1. compiler包含了webpack的所有配置信息，包含loader，options，plugins，可以理解为webpack的实例
1. compilation包含了当前的模块资源，编译生成文件，变化的文件等，当webpack以开发模式运行时，每当检查到一个文件变化，一次新的compilation被创建
1. compilation对象提供了很多事件回调供插件扩展，通过compilation也可以读取到compiler对象
1. compiler代表了整个webpack从启动到关闭的生命周期，而compilation只是代表了一次新的编译
1. webpack就像一个生产线，这条生产线上的每个处理流程都是单一的，多个流程存在依赖关系，完成当前的处理后才交给下一个流程去处理
1. 插件就是插入到生产线上的一个功能，再特定的时机对生产线上的资源做处理
1. webpack通过Tapable来组织这条生产线，compiler和compilation都继承自tapable，可以直接在这两个对象上广播和监听事件
1. compilation.getStats()这个函数相当重要，能得到生产文件以及chunkhash的一些信息

#### compiler事件钩子

##### entry-option 初始化option（同步）
##### run 开始编译（异步）
##### compile 真正开始编译，在创建compilation对象之前（同步）
##### compilation 生成好了compilation对象，可以操作这个对象啦（同步）
##### make 从entry开始递归分析依赖，准备对每个模块进行build（并行）
##### after-compile(编译build过程完成)(异步）
##### emit（再将内存中assets内容写入磁盘文件夹之前）（异步）

> **代表源文件的转换和组装已经完成，可以读取到最终输出的资源，代码块，模块，以及一俩，并且可以修改删除输出资源的内容**

```javascript
compiler.plugin('emit', function (compilation, callback) {
      // compilation.chunks 存放所有代码块，是一个数组
      compilation.chunks.forEach(function (chunk) {
        // chunk 代表一个代码块
        // 代码块由多个模块组成，通过 chunk.forEachModule 能读取组成代码块的每个模块
        chunk.forEachModule(function (module) {
          // module 代表一个模块
          // module.fileDependencies 存放当前模块的所有依赖的文件路径，是一个数组
          module.fileDependencies.forEach(function (filepath) {
          });
        });

        // Webpack 会根据 Chunk 去生成输出的文件资源，每个 Chunk 都对应一个及其以上的输出文件
        // 例如在 Chunk 中包含了 CSS 模块并且使用了 ExtractTextPlugin 时，
        // 该 Chunk 就会生成 .js 和 .css 两个文件
        chunk.files.forEach(function (filename) {
          // compilation.assets 存放当前所有即将输出的资源
          // 调用一个输出资源的 source() 方法能获取到输出资源的内容
          let source = compilation.assets[filename].source();
        });
 });
 
 // 输出的资源会存放在compilation.assets是一个键值对，键为需要输出的文件名称，值为文件对应的内容
compiler.plugin('emit', (compilation, callback) => {
  // 设置名称为 fileName 的输出资源
  compilation.assets[fileName] = {
    // 返回文件内容
    source: () => {
      // fileContent 既可以是代表文本文件的字符串，也可以是代表二进制文件的 Buffer
      return fileContent;
      },
    // 返回文件大小
      size: () => {
      return Buffer.byteLength(fileContent, 'utf8');
    }
  };
  callback();
});


// 读取 compilation.assets 的代码如下
compiler.plugin('emit', (compilation, callback) => {
  // 读取名称为 fileName 的输出资源
  const asset = compilation.assets[fileName];
  // 获取输出资源的内容
  asset.source();
  // 获取输出资源的文件大小
  asset.size();
  callback();
});
```
##### after-emit(在讲内存中assets内容写入磁盘文件夹之后）（异步）

> **webpack成功编译和输出文件后执行（可以执行发布操作，例如把文件上传到服务器)**

```
compiler.plugin('done', (stats) => {
    // 在 done 事件中回调 doneCallback
    this.doneCallback(stats);
});
```

##### done 完成所有的编译过程（同步）,得到的内容 stats
##### failed 编译失败的时候（同步），得到的内容error

> **在构建出现异常导致构建失败的时候发生**

```
  compiler.plugin('failed', (err) => {
        // 在 failed 事件中回调 failCallback
        this.failCallback(err);
    });
```



##### watch-run

> **当入口模块或以来的模块发生变化时，就会触发一次新的compilation，在开发中要知道哪个文件导致的新的compilation**

```
// 当依赖的文件发生变化时会触发 watch-run 事件
compiler.plugin('watch-run', (watching, callback) => {
    // 获取发生变化的文件列表
    const changedFiles = watching.compiler.watchFileSystem.watcher.mtimes;
    // changedFiles 格式为键值对，键为发生变化的文件路径。
    if (changedFiles[filePath] !== undefined) {
      // filePath 对应的文件发生了变化
    }
    callback();
});
```
##### after-compile

> **webpack默认只会监视入口及其依赖的文件的变化，为了监视html的变化，需要把html文件加入到依赖列表中**

```
  compiler.plugin('after-compile', (compilation, callback) => {
  // 把 HTML 文件添加到文件依赖列表，好让 Webpack 去监听 HTML 模块文件，在 HTML 模版文件发生变化时重新启动一次编译
    compilation.fileDependencies.push(filePath);
    callback();
});
```

#### 问题注意

1. 只要能拿到 Compiler 或 Compilation 对象，就能广播出新的事件，所以在新开发的插件中也能广播出事件，给其它插件监听使用
1. 在一个插件中修改了 Compiler 或 Compilation 对象上的属性，会影响到后面的插件，因为他们是同一个引用
1. 异步的事件附带两个参数，第二个参数为回调函数，在插件处理完成后需要调用callback才能进入下一个处理流程

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

// 判断当前配置使用使用了 ExtractTextPlugin，
function hasExtractTextPlugin(compiler) {
  // 当前配置所有使用的插件列表
  const plugins = compiler.options.plugins;
  // 去 plugins 中寻找有没有 ExtractTextPlugin 的实例
  return plugins.find(plugin=>plugin.__proto__.constructor === ExtractTextPlugin) != null;
}


compiler.plugin("done", (stats) => {
  const pkg = require("./package.json");
  const notifier = require("node-notifier");
  const time = ((stats.endTime - stats.startTime) / 1000).toFixed(2);
  notifier.notify({
    title: pkg.name,
    message: `WebPack is done!\n${stats.compilation.errors.length} errors in ${time}s`,
    contentImage: "https://path/to/your/logo.png",
  });
});
```
#### compilation事件钩子
##### normal-module-loader 普通模块loader，真实地一个一个加载模块图
##### seal编译封闭阶段
##### optimize优化编译
##### optimize-modules 模块的优化
##### optimize-chunks webpack的chunk优化阶段，可以拿到模块的依赖，loader等
##### additional-assets（异步）可以为compilation对象创建额外的assets，可以异步的在最后的assets中加入自己自定义的一些资产
##### optimize-chunk-assets优化 chunk 的 assets 的事件钩子，这个优化阶段可以改变 chunk 的 assets 以达到重新改变资源内容的目。assets 被存储在 this.assets 中，但是它们并不都是 chunk 的 assets。一个 chunk 有一个 files 属性指出这个 chunk 创建的所有文件。附加的 assets 被存储在 this.additionalChunkAssets。
##### optimize-assets 优化所有的assets（异步），在这个阶段可以通过this.assets拿到所有的assets，并进行自定义操作，类似optimize-chunk-assets，但是拿不到chunks
##### compilation实例演示
```
// 往assets资源里面新增一个svg资源的案例
compiler.plugin('compilation', function (compilation) {
    compilation.plugin('additional-assets', function (callback) {
        download('https://some.host/some/path/some.svg', function (resp) {
            if (resp.status === 200) {
                compilation.assets['webpack-version.svg'] = toAsset(resp);
                callback();
            }
            else {
                callback(new Error('[webpack-example-plugin] Unable to download the image'));
            }
        })
    });
});
// 为chunk添加头信息
compilation.plugin("optimize-chunk-assets", function (chunks, callback) {
    chunks.forEach(function (chunk) {
        chunk.files.forEach(function (file) {
            compilation.assets[file] = '/**some comments info**/\n' + compilation.assets[file];
        });
    });
    callback();
});
//拿到所有的assets
compilation.plugin("optimize-assets", function (asstes, callback) {
    console.log(assets);
    // 可以直接操作 assets 里面的 file
    callback();
});
```

### 参考链接
* [webpack原理之plugin](https://segmentfault.com/a/1190000012840742)
### 配图
[图片]()
