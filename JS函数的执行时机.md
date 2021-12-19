# JS 函数的执行时机

- js 函数执行分为同步和异步
- 同步是指当该函数被调用时要按顺序把代码执行完，再返回
- 异步是指调用该函数时，会先返回，一些代码稍后执行

```javascript
let i = 0； // 全局变量
for(i = 0; i<6; i++){
    // 异步
    setTimeout(()=>{
        console.log(i) // 6个6
    },0)
}
// i是全局作用域中的，在for循环执行完之后，才执行的异步函数，也就是说，i为6时，for循环完成，才执行了6次console.log(i)
```

如何打出 0-5 呢？

```javascript
for (let i = 0; i < 6; i++) {
  setTimeout(() => {
    console.log(i); // 0,1,2,3,4,5
  }, 0);
}
// 这里let会单独创建一个作用域,相当于有6个i
```

如何不用 let，打出 0-5 呢？

```javascript
for (var i = 0; i < 6; i++) {
  !(function (i) {
    setTimeout(() => {
      console.log(i); // 0,1,2,3,4,5
    }, 0);
  })(i);
}
// 这里用立即执行函数单独创建一个作用域,也相当于有6个i
```
