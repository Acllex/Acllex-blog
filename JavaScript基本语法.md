# JavaScript基本语法

## 表达式和语句

* 表达式是指为了得到返回值的计算式
* 语句是为了完成某种任务而进行的操作，以分号结尾，一个分号就表示一个语句结束
```javascript
1+3  //表达式
var a = 1+3; // 赋值语句，声明变量a，将1+3的运算结果赋值给a
```
* 二者的区别
  1. 表达式一般都有值，语句可能有也可能没有
  2. 语句一般会改变环境（声明赋值）
  3. 上面两句不绝对

## 标识符规则

* 第一个字符，可以是任意 Unicode 字母（包括英文字母和其他语言的字母），以及美元符号（$）和下划线（_）。
* 第二个字符及后面的字符，除了 Unicode 字母、美元符号和下划线，还可以用数字0-9。
## if else语句

```javascript
if(布尔值){
  // 满足条件执行的语句
}else{
  // 不满足条件时，执行的语句
}
// 还可以进行多次判断
if(a === 1){

}else if(a === 2){

}else if(a === 3){

}else{

}
```
## while for语句

```javascript

// while
while (条件){
  语句;
}

// 或者
while (条件) 
  语句;

// 例如
let i = 0;

while (i < 100) {
  console.log('i 当前为：' + i);
  i = i + 1;
}

// for
for (初始化表达式; 条件; 递增表达式)
  语句
// 或者
for (初始化表达式; 条件; 递增表达式) {
  语句
}
// 例如
let x = 3;
for (let i = 0; i < x; i++) {
  console.log(i);
}
```
## break continue

* break语句用于跳出代码块或循环。
```javascript
  for (let i = 0; i < 5; i++) {
    console.log(i);
    if (i === 3)
      break;
  }
// 0
// 1
// 2
// 3
```
* continue语句用于立即终止本轮循环，返回循环结构的头部，开始下一轮循环。
```javascript
  for (let i = 0; i < 5; i++) {
    if (i === 3)
      continue;
    console.log(i);
  }
// 0
// 1
// 2
// 4
```

## label

* JavaScript 语言允许，语句的前面有标签（label），相当于定位符，用于跳转到程序的任意位置，标签的格式如下。
```javascript
label:
  语句
```
* 标签可以是任意的标识符，但不能是保留字，语句部分可以是任意语句。
* 标签通常与break语句和continue语句配合使用，跳出特定的循环。
```javascript
// 和break配合
top:
  for (let i = 0; i < 3; i++){
    for (let j = 0; j < 3; j++){
      if (i === 1 && j === 1) break top;
      console.log('i=' + i + ', j=' + j);
    }
  }
// i=0, j=0
// i=0, j=1
// i=0, j=2
// i=1, j=0

// 和continue配合
top: 
  for (let i = 0; i < 3; i++){ 
    for (let j = 0; j < 3; j++){ 
      if (i === 1 && j === 1) continue top; console.log('i=' + i + ', j=' + j); 
    } 
  } 
  // i=0, j=0 
  // i=0, j=1 
  // i=0, j=2 
  // i=1, j=0 
  // i=2, j=0 
  // i=2, j=1 
  // i=2, j=2
```
* 标签也可以用于跳出代码块
```javascript
foo: {
  console.log(1);
  break foo;
  console.log('本行不会输出');
}
console.log(2);
// 1
// 2
```