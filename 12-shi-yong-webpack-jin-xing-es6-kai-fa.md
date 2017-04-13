### 3. 使用Webpack快速搭建可以使用ES6开发的项目http://webpackdoc.com/index.html

![](http://images0.cnblogs.com/blog2015/561179/201507/161453372048661.jpg)

> Webpack 是一个模块打包器。它将根据模块的依赖关系进行静态分析，然后将这些模块按照指定的规则生成对应的静态资源。

优势：

* 将依赖树拆分成按需加载的块
* 初始化加载的耗时尽量少
* 各种静态资源都可以视作模块
* 将第三方库整合成模块的能力
* 可以自定义打包逻辑的能力
* 适合大项目，无论是单页还是多页的 Web 应用.

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

