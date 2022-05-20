# npm

### npm基础命令
1. npm link[参考](https://blog.csdn.net/weixin_42274805/article/details/123474053)

* 同一目录下使用,npn link ../module1 则会在项目的node_module下创建一个module1的超链接,连接到module1项目中
* 不同目录下使用module1下使用npm link 则会先把模块连接到全局下,然后再在项目中使用 npm link module1则会在项目中创建一个module1-nam的超链接,连接到全局目录下

1. npm ci[参考](https://blog.csdn.net/csdn_yudong/article/details/84929546)
  * 该项目必须有一个 package-lock.json 或 npm-shrinkwrap.json。避免第三方包增量更新时导致的错误.
  * 如果 package-loc 中的依赖项与 package.json 的依赖项不匹配，npm ci 则将退出并显示错误，而不是更新 package-lock。
  * npm ci 只能一次安装整个项目：使用此命令无法添加单个依赖项。
  * 如果 node_modules 已经存在，它将在 npm ci 开始安装之前自动删除。
  * 它永远不会写入 package.json 或任何包锁：安装基本上是冻结的

### npm包发布

### npm包group packages



### package.json文件
