### 1.  块级作用域 `let`和`const`

##### [let的特性](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/let)

* 块级作用域
* 可以赋初始值, 也可以不用赋值.
* 没有作用域提升 [变量提升](http://www.liaoxuefeng.com/wiki/001434446689867b27157e896e74d51a89c25cc8b43bdb3000/0014344993159773a464f34e1724700a6d5dd9e235ceb7c000)
* 暂时性死区\(TDZ\)

* 基本用法和常见错误

  ```
  let pet = "dog";
  if(ture) {
    let a = 10;
    var b = 20;
  }
  a// 
  b//

  //TDZ
  function fun() {
    console.log(name);
    let name = "Tidy";
  }
  ```

* 作用域

```JavaScript
   var myVar = "golobal var"

   function fun() {
     console.log(`函数体顶部未声明前的var: myVar: ${myVar} `)
    var myVar = "function var"
    if(true) {
      var myVar = "block var"
       console.log(`if语句里的var:myVar: ${myVar}`)
    }
    console.log(`函数体底部声明后的var: myVar: ${myVar}`)
  }
   console.log(`全局作用域下的var: myVar: ${myVar} `)

    fun()
```

---

##### [const的特性](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/const)

* 声明一个只读的常量, 赋值后常量的值就不能改变, 
* 初始化必须赋值.
* 常量名一般为大写字母.
* 块级作用域.
* 暂时性死区\(TDZ\)

* 基本用法和常见错误

  ```JavaScript
  const PI = Math.PI

  PI = 23 // TypeError: Assignment to constant variable / "PI" is read-only 不能重新赋值

  const MY_COLOR // SyntaxError: Missing initializer in const declaration 初始化需赋值

  //TDZ
  if (true) {
    console.log(MAX); // ReferenceError
    const MAX = 5; //必须先声明后使用
  }
  ```

* 代码演示:  由let, const, var声明的变量在不同情况下Global,  function,  Block的作用域

* 问题: `let`, `var`, `const`的区别有哪些? 它们有什么特定的使用场景?



