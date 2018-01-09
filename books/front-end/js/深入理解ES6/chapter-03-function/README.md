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
 