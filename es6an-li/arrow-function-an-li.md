<!-- $theme: default -->
<!-- $size: 16:9 -->


箭头函数 arrow function
===

![](http://i1.piimg.com/567571/f27f2fa148c205c5.png)

---






# 箭头函数的优势

* 简洁的语法

![](http://i2.muimg.com/567571/85e209ce9173bfdd.png)

箭头函数

```JavaScript
let add = (a, b) => a + b
```

---

# 箭头函数   VS   普通函数
箭头函数

```JavaScript
(a, b) => a + b
```
普通函数

```aJavaScript
function(a, b) {
  return a + b;
}
```
#简洁的语法 arrow function +1

---


* 语法

```JavaScript
    () => { ... } // 没有参数 no parameter
    
     x => { ... } // 一个参数 one parameter
     
(x, y) => { ... } // 多个参数 several parameters
```
---


* 函数体内表达式

```JavaScript
x => x * x  // expression

// 等同于
x => { return x * x } 

// 如返回一个对象需要使用圆括号
() => ({nmae: "Tidy",
        age: 22,
        gender: 0})
```

```JavaScript
// ES6 箭头函数
const squares = [1, 2, 3].map(x => x * x);

// 普通函数
const squares = [1, 2, 3].map(function (x) { return x * x });
```
---


* 没有this绑定

  传统hack方法: `that = this`
  
  
案例一

```javascript
// ES5
"use strict";
var bob = {
  _name: "Bob",
  _friends: [],
  printFriends: function printFriends() {
    // 需要将this的当前的作用域赋值给that
    var that = this;
    this._friends.forEach(function (f) {
      // 默认this指向window
      return console.log(that._name + " knows " + f);
    });
  }
};

bob._friends = ['Lily', 'Sam', 'Jone'];
bob.printFriends();
```
使用箭头函数解决了this的绑定问题

```JavaScript
// 创建一个对象bob
var bob = {
  _name: "Bob",
  _friends: [],
  printFriends() {
    
// this绑定
    this._friends.forEach(f =>
      console.log(this._name + " knows " + f));
  }
};
```

---
## 注意事项
* 错误场景一
> => 后不要换行

    ```JavaScript
    let fun = (x, y) =>
    if (x > y) {
        return x;
    } else {
         return y;
    }
    ```

* 错误场景二
> 返回一个对象字面量要加圆括号

    ```JavaScript
  () => ({name: 'Lily', age: 22})
    ```

* 错误场景三
> 不要在构造函数内使用this

    ```JavaScript
    let Person = function(name, age) {
      this.name = name;
      this.age = age;
      sayName: () => console.log(this.name + 'is' this.age)
    }


    ```
    
* 错误场景三
> 箭头函数没有argumens属性

    ```JavaScript
    let Person = function(name, age) {
      this.name = name;
      this.age = age;
      sayName: () => console.log(this.name + 'is' this.age)
    }


    ```




