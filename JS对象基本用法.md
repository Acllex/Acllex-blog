# JS 对象基本用法

## 声明对象的两种语法

```javascript
let obj = {
    'name': 'aaa',
    'age': 12
}

let obj = new Object({'name': 'aaa', 'age': 12})
```
## 如何删除对象的属性

```javascript
let obj = {
    'name': 'aaa',
    'age': 12
}
delete obj['age']
console.log(obj['age']); // undefined
```
## 如何查看对象的属性

```javascript
let obj = {
    'name': 'aaa',
    'age': 12
}

Object.keys(obj)    // ['name','age']

obj['name']  // 'aaa'
obj.name  // 'aaa'
```

## 如何修改或增加对象的属性

```javascript
let c = {};
let obj = {
    'name': 'aaa',
    'age': 12
}
obj['name'] = 'bbb'; // 增、改自身
Object.assign(obj,{age: 13, x: 111}); // 批量增改
obj._proto_['toString'] = 'xxx';    // 改共有属性
Object.prototype['toString'] = 'xxx'  // 改共有属性
obj._proto_ = c;    // 改原型
Object.create(c);   // 改原型

/* 所以_proto_的语句都不推荐使用 */ 

```

## 'name' in obj和obj.hasOwnProperty('name') 的区别

* in运算符不能识别哪些属性是对象自身的，哪些属性是继承的
* hasOwnProperty方法可以判断是否为对象自身的属性

```javascript
let obj = { name: 'aaa' }; 
'name' in obj // true 
'toString' in obj // true

console.log(obj.hasOwnProperty('toString')) // false
```