### 2.  ES6转码工具Babel使用方法

![](http://www.ruanyifeng.com/blogimg/asset/2016/bg2016012501.png)

>  Babel是一个ES6转码器, 可以将ES6代码转换为ES5代码.
>
>  好处是可以使用ES6的语法, 而不用担心当前的环境是否完全支持ES6.
>
>  例如使用箭头函数, Babel可以将其转换为普通函数, 就能在不支持ES6的环境中执行了.
>
>  Babel在线转换http://babeljs.cn/repl/


*In*
```javascript
//ES6 arrow function 
[1, 2, 3].map((n) => n + 1);
```

*Out*
```javasrcpit
[1, 2, 3].map(function(n) {
    return n + 1;
});
```


---
#### 1. 准备工作:

  *  创建一个项目名为`babel_test`的文件夹.
  *  创建一个标准为ES6的js文件, 内容为`[1, 2, 3].map((n) => n + 1);`,  保存为`es6.js`.
  *  创建两个文件夹,分别名为`src`和`lib`.
  *  创建`package.json`文件和`.babelrc`文件(参见第三点).


----------


#### 2. 安装babel-cli命令行工具
> 在[node官网](https://nodejs.org/en/download/)安装node.js, 然后就可以使用npm包管理工具来安装babel-cli命令行工具

```JavaScript
  # 在项目目录如d:\babel_test\下安装babel-cli
  $ npm install --save-dev babel-cli

  # 安装最新的转码规则
  $ npm install --save-dev babel-preset-latest
```


----------


#### 3. 在项目目录下创建隐藏文件`.babelrc`文件和`package.json`文件(可选)

> 注意, 所有 Babel工具和模块的使用，都必须先写好`.babelrc`.

`pakage.json`配置内如下: 

```
{
  "devDependencies": {
    "babel-cli": "^6.0.0"
  },
  "scripts": {
    "build": "babel src -d lib"
  },
}
```
 `.babelrc`配置内容如下:

```
     {
        "presets": [
          "latest"
        ],
        "plugins": []
      }
```


----------

#### 4. Babel-cli的基本使用方法:
```    
# es6.js为ES6代码 使用bable命令编译要转换的ES6代码
$ babel es6.js
   
# 使用-o指令 将转码结果写入到一个文件
$ babel es6.js -o es5.js
    
# 使用-d 将ES代码所在目录转码到另外一个目录
$ babel src -d lib
    
# 如果配置好package.json文件 可以使用以下快捷方式 等同于src -d lib
$ npm run build
``` 


----------

#### 5. babel-polyfill 的使用

> babel-plyfull可以转换babel不能转换的语法.
babel默认只转换JavaScript的语法, 而不转换新的 API, 比如`Iterator`, `Set`, `Maps`, `Promise`等全局对象.

* 安装如下

  ```
  $ npm install --save babel-polyfill
  ```

* 使用方式

  ```
  import 'babel-polyfill';

  //或者
  require('babel-polyfill');
  ```

---



---

####7. 打包、构建
项目结束后，代码要压缩、混淆、合并等，只需要在命令行执行
```
$ webpack
```