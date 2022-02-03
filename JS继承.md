# JS 的继承方法

## 原型继承

```javascript
function inheritObject(obj) {
  // 声明一个过渡函数对象
  function F() {}
  F.prototype = obj;
  // 返回过渡对象的一个实例，该实例的原型继承了父对象
  return new F();
}

let book = {
  name: "js book",
  alikeBook: ["css book", "html book"],
  read: () => {
    console.log("read book is funny");
  },
};

// newBook继承了book
let newBook.prototype = inheritObject(book);
newBook.name = "JavaScript Book";
newBook.alikeBook.push("json book");
console.log(newBook.alikeBook);
let newBook2 = inheritObject(book);
console.log(newBook2.alikeBook);
// 值类型的属性被复制，引用类型的属性被共用
```

## 寄生组合式继承

```javascript

```

## class 继承

```javascript
class Book {
  constructor(bookName) {
    this.bookName = bookName;
    this.alikeBook = ["css book", "html book"];
  }
  add(alikeBook) {
    this.alikeBook.push(alikeBook);
  }
}

class ComputerBook extends Book {
  constructor(bookName) {
    super(bookName);
  }
}
class AudioBook extends Book {
  constructor(bookName) {
    super(bookName);
  }
}
let jsBook = new ComputerBook("js book");
let cssBook = new ComputerBook("css book");
jsBook.add("json book");
cssBook.add("flash book");
console.log(jsBook);
console.log(cssBook);
// 属性都是被复制，不会出现公用情况
```
