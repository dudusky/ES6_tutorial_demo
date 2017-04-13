### 4.  [数组扩展方法](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/from)

#### Array.from()

> 用于将可遍历的对象转为真正的数组

* 基本用法

  ```JavaScript
  // 将一个类数组对象转换为数组
  (function () {
    var args = Array.from(arguments);
    return args;
  })(1, 2, 3);                            // [1, 2, 3]
 
  // ES5的写法
  var arr1 = [].slice.call(arrayLike); // ['a', 'b', 'c']

  // ES6的写法
  let arr2 = Array.from(arrayLike);  // ['a', 'b', 'c']
  
  // 将类数组对象（arguments）转换成数组
(function () {
    var args = Array.from(arguments);
    return args;
})(1, 2, 3);        // [1, 2, 3]
  
  ```
  ---

  
  #### Array.fill()
  
  > 将一个数组的所有元素从开始索引填充到结束索引
  
 ```
 //语法 value表示填充的值 start（可选）开始索引
 //end（可选）结束索引
 arr.fill(value, start, end)
 ```
 
* 基本案例
 ```
 [1, 2, 3].fill(4)            // [4, 4, 4]
[1, 2, 3].fill(4, 1)         // [1, 4, 4]
[1, 2, 3].fill(4, 1, 2)      // [1, 4, 3]
[1, 2, 3].fill(4, 1, 1)      // [1, 2, 3]
[1, 2, 3].fill(4, -3, -2)    // [4, 2, 3]
[1, 2, 3].fill(4, NaN, NaN)  // [1, 2, 3]
Array(3).fill(4);            // [4, 4, 4]

 ```


 ####数组的map()方法
 > * map() 方法创建一个新数组.
 * map() 方法会给原数组中的每个元素都按顺序调用一次 callback 函数
 * callback 每次执行后的返回值组合起来形成一个新数组
 * callback 函数会被自动传入三个参数：数组元素，元素索引，原数组本身
 
* 基本用法
 ```
 let numbers = [1, 5, 10, 15];
 let roots = numbers.map(function(x) {
    return x * 2;
 });
 ```