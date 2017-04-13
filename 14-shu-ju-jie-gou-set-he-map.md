### 5. [Set和Map数据结构](http://www.liaoxuefeng.com/wiki/001434446689867b27157e896e74d51a89c25cc8b43bdb3000/0014345007434430758e3ac6e1b44b1865178e7aff9082e000)

#### [Set](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Set)

> Set类似于数组, 区别是内部成员的值不能重复.
>
> Set是一个构造函数,可以创建Set数据结构.
>
> Set实例的操作数据的方法: add\(value\), delete\(value\)
>
> Set实例的遍历方法之一: `forEach()` 使用回调函数遍历每个成员.

* 基本用法:

  ```JavaScript
    /*
    使用Set和forEach方法实现数组去重
    */

    //创建一个Set的实例s
    const s = new Set();

    //使用forEach遍历数组, 使用add()添加到s里
    [2, 3, 5, 4, 5, 2, 2].forEach(x => s.add(x));

    //输出s里的成员变量
    for (let i of s) {
      console.log(i);
    }
    // 2 3 5 4
  ```

  ​

#### [Map](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Map)

> Map类似于对象,是键值对的集合, 但是“键”的范围不限于字符串, 各种类型的值（包括对象）都可以当作键.
>
> Map是一个构造函数,可以创建Map数据结构.
>
> Map实例的操作数据的方法: add\(value\), delete\(value\), set\(value\), get\(value\)
>
> Map实例的遍历方法之一: `forEach()`

* 基本用法:

  ```JavaScript
  var map = new Map([ ["name", "张三"], ["title", "Author"]]);

  map.size // 2
  map.has("name") // true
  map.get("name") // "张三"
  map.has("title") // true
  map.get("title") // "Author"
  ```

* 代码演示\(2\)

  ```
  var names = ['Michael', 'Bob', 'Tracy'];
  var scores = [95, 75, 85];

  var m = new Map([['Michael', 95], ['Bob', 75], ['Tracy', 85]]);
  m.get('Michael'); // 95
  ```



