### 2. [变量/参数的结构赋值](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)

* 变量的结构赋值

 ```JavaScript
 let singer = { first: "Bob", last: "Dylan" }; 

 let { first: f, last: l } = singer;  // 相当于 f = "Bob", l = "Dylan"

 let [x, y] = [1, 2, 3];  // x = 1, y = 2
 ```



* 函数参数的结构赋值

  ```JavaScript
  function add([x, y]) {
    return x + y;
  }
  console.log(add([2, 4])); //6
  ```

* 为函数参数设置初始值

  ```JavaScript
  //ES6参数赋值
  function f(x, y = 10, z = 20) {
    return x + y + z;
  }
  f(2) //32

  //ES5函数中的参数不能赋值
  function f (x, y, z) {
      if (y === undefined)
          y = 7;
      if (z === undefined)
          z = 42;
      return x + y + z;
  };
  f(1) //50
  ```


* [Rest参数](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Functions/Rest_parameters)

  > 设置更多的参数作为一个数组(与类数组argument不同), 好处是可以使用数组方法.

  ```JavaScript
  function f (x ,y, ...restAr) {
    var a = restAr
    console.log(a) //array
    console.log(a.length) //4
    return console.log(((x + y) * a.length)) //12
  }
  f(1, 2, "hi", 9, 20, 55) 
  ```
  
  * 数组参数

    ​    连接数组

  ```JavaScript
  //使用ES6
  var params = [ "hello", true, 7 ]
  var other = [ 1, 2, ...params ] // [ 1, 2, "hello", true, 7 ]

  //ES5写法
  var params = [ "hello", true, 7 ];
  var other = [ 1, 2 ].concat(params); // [ 1, 2, "hello", true, 7 ]
  ```


    将字符串字符分割转换为数组

  ```
  //使用ES6
  var str = "foo"
  var chars = [ ...str ] // [ "f", "o", "o" ] 

  //使用ES5
  var str = "foo"
  var chars = str.split("");  // [ "f", "o", "o" ]
  
 ```