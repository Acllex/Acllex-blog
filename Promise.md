# Promise

## Promise 的含义

将异步操作以同步操作的流程表达出来，避免了回调地狱；统一了接口，使异步操作更加容易

## 创建 Promise

```js
return new Promise((resolve, reject) => {});
```

## 使用 Promise.prototype.then()

```js
var p1 = new Promise((resolve, reject) => {
  resolve("成功！");
});

p1.then(
  (value) => {
    console.log(value); // 成功！
  },
  (reason) => {
    console.error(reason); // 出错了！
  }
);
```

## Promise.all()

```js
// Promise.all可以将多个Promise实例包装成一个新的Promise实例。同时，成功和失败的返回值是不同的，成功的时候返回的是一个结果数组，而失败的时候则返回最先被reject失败状态的值。
let p1 = new Promise((resolve, reject) => {
  resolve("成功了");
});

let p2 = new Promise((resolve, reject) => {
  resolve("success");
});

let p3 = Promise.reject("失败");

Promise.all([p1, p2])
  .then((result) => {
    console.log(result); //['成功了', 'success']
  })
  .catch((error) => {
    console.log(error);
  });

Promise.all([p1, p3, p2])
  .then((result) => {
    console.log(result);
  })
  .catch((error) => {
    console.log(error); // 失败了，打出 '失败'
  });
```

## Promise.race()

```js
//Promise.race就是赛跑的意思，意思就是说，Promise.race([p1, p2, p3])里面哪个结果获得的快，就返回那个结果，不管结果本身是成功状态还是失败状态
获得的快，就返回那个结果，不管结果本身是成功状态还是失败状态。


let p1 = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve('success')
  },1000)
})

let p2 = new Promise((resolve, reject) => {
  setTimeout(() => {
    reject('failed')
  }, 500)
})

Promise.race([p1, p2]).then((result) => {
  console.log(result)
}).catch((error) => {
  console.log(error)  // 打开的是 'failed'
})
```
