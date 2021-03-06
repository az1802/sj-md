[eslint基本介绍](https://zhuanlan.zhihu.com/p/112724972)
# lint工具发展过程
最开始jsLint->jsHint 不能对规则进行扩展。最终出现了elsint。将代码解析成AST语法书然后可以使用任意规则来检测AST是否符合预期。

# 基本环境配置
1 npm install -g eslint
2 eslint --init  //初始化eslint配置文件.eslintrc.js



# 禁用eslint规则

### 配置选项

使用.eslintrc.js  .eslintrc.json .eslintrc.yaml对eslint进行配置



### env

### root



### globals
全局变量配置
```json
{
  "global":{
    "$":false //true表示变为writable false表示readonly
  }
}
```
global中一个个声明全局变量会比较繁琐，所以需要使用env设置。类似于babel的presets;
```json
{
  "env": {
    "amd": true,
    "commonjs": true,
    "jquery": true
  }
}[]
```
### rules 
自定义规则
+ off 0   关闭规则
+ warn 1  开启规则，并发出警告
+ error 2 开启规则，提示错误
```json
{
  "rules": {
    // 使用数组形式，对规则进行配置,第一个参数为是否启用规则,后面的参数才是规则的配置项
    "quotes": [
      "error",
      "single",
      {
        "avoidEscape": true
      }
    ]
  }
}
```
### extends扩展
直接使用别人已经写好的lint规则配置，方便快捷。eslint开头即为官网的扩展一共两个(eslint:recommended,eslint:all);
plugin:开头是插件类型直接在plugins属性中进行设置。
eslint-config-开头即npm包。
```json
{
  "extends": [
    "eslint:recommended",
    "plugin:react/recommended",
    "eslint-config-standard",
  ]
}
```
### plugins规则
虽然官方提供了上百种的规则可供选择，但是这还不够，因为官方的规则只能检查标准的 JavaScript 语法，如果你写的是 JSX 或者 Vue 单文件组件，ESLint 的规则就开始束手无策了。

这个时候就需要安装 ESLint 的插件，来定制一些特定的规则进行检查。ESLint 的插件与扩展一样有固定的命名格式，以 eslint-plugin- 开头，使用的时候也可以省略这个头。
```json
{
  "plugins": [
    "react", // eslint-plugin-react
    "vue",   // eslint-plugin-vue
  ],
  "extends": [
    "plugin:react/recommended",
  ]
}
```
eslint-plugin-react 源码 可以看到：
```json
module.exports = {
  // 自定义的 rule
  rules: allRules,
  // 可用的扩展
  configs: {
    // plugin:react/recommended
    recomended: {
      plugins: [ 'react' ]
      rules: {...}
    },
    // plugin:react/all
    all: {
      plugins: [ 'react' ]
      rules: {...}
    }
  }
}
```
### 忽略文件eslintIgnore
```json
{
  "eslintIgnore": ["hello.js", "world.js"]
}
```

### parser(解析器类型)





### 自动修复

1. vscode中,command+p唤起vscode命令框,输入>eslint即可进行快捷键的选择.

2. vscode中的eslint插件增加保存自动修复错误的配置.

   ```json
   {
   	"editor.codeActionOnSave":{
   		"source.fixAll.eslint":true //保存时自动修复存在修复规则的问题
   	}
   }
   ```

   



