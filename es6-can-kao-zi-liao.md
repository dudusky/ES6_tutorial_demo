## 五. 参考资源

### 1. 严格模式`'use strict';`
* 变量必须声明后再使用
* 函数的参数不能有同名属性，否则报错
* 不能使用with语句
* 不能对只读属性赋值，否则报错
* 不能使用前缀0表示八进制数，否则报错
* 不能删除不可删除的属性，否则报错
* 不能删除变量delete prop，会报错，只能删除属性delete global[prop]
* eval不会在它的外层作用域引入变量
* eval和arguments不能被重新赋值
* arguments不会自动反映函数参数的变化
* 不能使用arguments.callee
* 不能使用arguments.caller
* 禁止this指向全局对象
* 不能使用fn.caller和fn.arguments获取函数调用的堆栈
* 增加了保留字（比如protected、static和interface）


### 2. ES6新特性在Babel下的兼容性列表
|ES6特性|	兼容性|
|--|-|-|
|箭头函数|	支持|
|类的声明和继承	|部分支持，IE8不支持|
|增强的对象字面量|	支持
|字符串模板	|支持
|解构|	支持，但注意使用方式
|参数默认值，不定参数，拓展参数|	支持
|let与const	|支持
|for of	|IE不支持
|iterator, generator|	不支持
|模块 module、Proxies、Symbol|	不支持
|Map，Set 和 WeakMap，WeakSet|	不支持
|Promises、Math，Number，String，Object 的新API	|不支持
|export & import|	支持
|生成器函数	|不支持
|数组拷贝|	支持


### 3. ES6资源
#### 文档
* [MDN ES6官网文档](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript) *最新,最全面的权威ES6指南*
* [Github ES6资源收集](https://github.com/ericdouglas/ES6-Learning)
* [ES6入门 阮一峰著](http://es6.ruanyifeng.com/) *语法, AIP速查手册,适合初学者入门*
* [ES6和ES5的比较 英语](http://es6-features.org/#SpreadOperator) *案例演示*
* [ES6的兼容和规范](http://imweb.io/topic/561f9352883ae3ed25e400f5)
* [ES6 tutorial](http://ccoenraets.github.io/es6-tutorial/)
*ES6的最新案例实践*
* [ES6 案例](http://qnimate.com/post-series/ecmascript-6-complete-tutorial/) *基础案例*


####工具推荐: 
* [ES6在线转换](http://babeljs.cn/repl/) *在线测试ES6新特性*
* Chrom开发者插件`Scratch JS`   *ES6转换ES5,调试ES6代码*