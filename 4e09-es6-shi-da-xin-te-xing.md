### 9.  对象继承`Class`和 `extends`

> 通过class关键字, 可以定义类, 实现类的继承。

* 基本用法

  ```JavaScript
  //ES6使用class定义类
  class Point {
    //必须使用consructor构造方法
    constructor(x, y) {
      this.x = x;
      this.y = y;
    }
    toString() {
      return '('+this.x+', '+this.y+')';
    }
  }

  //在ES5中使用原型(prototype)定义类
  function Point(x,y){
    this.x = x;
    this.y = y;
  }

  Point.prototype.toString = function () {
    return '('+this.x+', '+this.y+')';
  }
  ```



