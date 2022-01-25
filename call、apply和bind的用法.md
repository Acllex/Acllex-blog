# call、apply 和 bind 的用法

## call 方法

call 可以指定上下文的 this，接受连续参数

```javascript
function add(a, b) {
  return a + b;
}
add.call(add, 2, 3); // 5
```

## apply 方法

apply 的作用和 call 一样，只是在调用时传参的方式不同；接受的是数组参数

```javascript
function add(a, b) {
  return a + b;
}
add.apply(add, [2, 3]); // 5
```

## bind 方法

bind 接受的参数和 call 一样，只是 bind 不会立刻调用，它会生成一个新函数，你可以在需要的时候调用

```javascript
function add(a, b) {
  return a + b;
}
const add1 = add.bind(add, 2, 3);
add1(); // 5
```
