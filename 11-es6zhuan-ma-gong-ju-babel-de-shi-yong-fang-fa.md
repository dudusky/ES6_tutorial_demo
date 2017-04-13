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

### 3. 使用Webpack快速搭建可以使用ES6开发的项目http://webpackdoc.com/index.html

![](http://images0.cnblogs.com/blog2015/561179/201507/161453372048661.jpg)

> Webpack 是一个模块打包器。它将根据模块的依赖关系进行静态分析，然后将这些模块按照指定的规则生成对应的静态资源。

优势：

* 将依赖树拆分成按需加载的块
* 初始化加载的耗时尽量少
* 各种静态资源都可以视作模块
* 将第三方库整合成模块的能力
* 可以自定义打包逻辑的能力
* 适合大项目，无论是单页还是多页的 Web 应用

---
####1. 安装 webpack
通过 npm 在全局环境下安装 webpack：
全局安装
```    
$ npm install webpack -g
```

建议在项目下安装一份局域的 webpack：

```
$ npm install webpack --save-dev
```

---

####2. 初始化项目
* 创建一个项目目录 命名为my-webpack 

```
// 创建一个 package.json文件，用于保存项目版本、依赖关系等
$ npm init -y
```
      
* 在当前目录下安装 webpack

```
$ npm install webpack --save-dev
```
      
* 这时项目下有两个内容：
    package.json 文件
    node_modules 文件夹

* 创建一个index.html文件
```
<!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <title>webpack 教程</title>
  </head>
  <body>
  <script src="./bundle.js"></script> <!-- 在 index.html 文件中添加这一行代码 -->
  </body>
  </html>
```
---

####3. webpack 配置
 *  项目根目录新建一个 webpack.config.js，这是 webpack 默认的配置文件名称，添加以下内容：
```
module.exports = {
      entry: './main.js',
      output: {
          path: __dirname, // 输出文件的保存路径
          filename: 'bundle.js' // 输出文件的名称
      }
  }
```
  
---
####4. 实时刷新
* main.js 或它所引用的模块的变化通知webpack，重新生成 bundle.js


 ```
 // 实时监控你的js代码
$ webpack --watch
 ```




*  在全局环境中安装 webpack-dev-server

 ```
 // 安装服务器， 实时更新你的js代码
 $ npm install webpack-dev-server -g
 ```
 
* 在项目根目录下执行命令：
 ```
 $ webpack-dev-server
 ```
  
* 在http://localhost:8080/webpack-dev-server/index.html 网址上打开我们的 index.html




---


5. 第三方库
```
$ npm install jquery --save
// 更多


```



6. 模块化
 * 模块化javascript
 使用ES5的模块引入jQuery模块
```
 import $ from 'jQuery'
```

// 使用babel 将ES6转成ES5
* 安装 babel-loader

  ```
  $  npm install babel-loader babel-core babel-preset-es2015 --save-dev 
   ```

* 配置 webpack.config.js

在 module.exports 值中添加 module：

```
module.exports = {
  entry: {
      app: ['./main.js']
  },
  output: {
      filename: 'bundle.js'
  },
  module: {
      loaders: [{
          test: /\.js$/,
          loaders: ['babel?presets[]=es2015'],
          exclude: /node_modules/
      }]
  }
}
```

---

####7. 打包、构建
项目结束后，代码要压缩、混淆、合并等，只需要在命令行执行
```
$ webpack
```