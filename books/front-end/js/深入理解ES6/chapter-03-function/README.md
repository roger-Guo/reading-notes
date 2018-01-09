## 函数
#### 元属性 new.target
```javascript
    function Person(name) {
        if (typeof new.target !== 'undefined') {
            this.name = name;
        } else {
            throw new Error('必须通过new关键字来调用Person');
        }
    }

    var person = new Person('Nicholas');
    var notAPerson = Person.call(person, 'Michael'); // 报错
```
#### 展开运算符
```javascript
    // 展开运算符
    let [first, ...rest] = colors;

    // 克隆数组 也可以用contact方法克隆
    let [...clone] = colors;

    // 拷贝对象
    let a = {a: 1, b: 2}
    let b = {...a, c: 3} // {a: 1, b: 2, c: 3}
```
#### __`Object.getPropertyOf()`__
#### __`Object.setPropertyOf()`__
#### super 指向对象原型的指针
##### 对象原型函数中的this指向该对象 该对象如果作为另一个对象的原型 那么this指向另一个对象
##### 匿名函数的this执行window
```javascript
    let person = {
        getGreeting() {
            return 'hello';
        }
    };

    let friend = {
        getGreeting() {
            return super.getGreeting() + ', hi!';
        }
    }

    // super此时始终执行person
    Object.setPropertyOf(friend, person);

    // 多重继承 super非常有用
    let relative = Object.create(friend);
```