## Symbol
### 用来创建非字符串属性的名称
* Symbol 键的属性不会在对象的 JSON 中显示，也不会在 for-in 循环和Object.keys中被枚举出来
* Object.getOwnPropertySymbols提供了一种检索对象的 Symbol 键的方法
```javascript
    Object.getOwnPropertySymbols(myObject)
    > [Symbol(), Symbol()]

    myObject[ Object.getOwnPropertySymbols(myObject)[0] ]
    > "Value of myObject[ symbol1 ]"
```