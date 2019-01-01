# yarn

## 目录

* [命令](#命令)

### 命令

```git
    
    yarn init                           初始化一个
    yarn init -y                        跳过会话，直接通过默认值生成 package.json
    yarn install                        安装项目的所有依赖
    yarn install --force                就算node_modules有相应的包也会重新下载
    
    yarn add [package]                  添加依赖，默认在dependencies下
    yarn add [package]@[version]
    yarn add [package]@[tag]
    
    yarn add [package] --dev            简写-D,在devDependencies下
    yarn add [package] --peer
    yarn add [package] --optional
    
    yarn upgrade [package] --latest     升级到最新版本
    yarn upgrade [package]
    yarn upgrade [package]@[version]
    yarn upgrade [package]@[tag]
    
    yarn remove [package]               移除依赖包
    
    yarn info [package]                 查看某个包的版本信息
    yarn info [package] --json          查看某个包的版本信息输出json形式
    
    yarn list                           列出项目中所有的依赖
    yarn list --depth=0                 限制依赖的深度
    
    yarn config set key value           设置yarn配置
    yarn config get key                 读取值
    yarn config delete key              删除
    yarn config list                    显示当前配置
    yarn config set registry https://registry.npm.taobao.org # 设置淘宝镜像
    
    
    sudo yarn cache list            # 列出已缓存的每个包
    sudo yarn cache dir             # 返回 全局缓存位置
    sudo yarn cache clean           # 清除缓存
```
