# jQuery 学习总结

### 获取元素

```javascript
$(document); //选择整个文档
$("#myId"); //选择ID为myId的元素
$("div.myClass"); //选择class为myClass的div元素
$("input[name=first]"); // 选择name属性等于first的input元素
$("a:first");
$("tr:odd");
$("#myForm:input"); // 选择表单中的input元素
$("div:visible"); //选择可见的div元素
$("div:gt(2)"); // 选择所有的div元素，除了前三个
$("div.animated"); //选择当前处于动画状态的div元素
```

### 改变结果集

运用过滤器对结果进行筛选

```javascript
$("div").has("p"); //选择包含p元素的div元素
$("div").not(".myClass"); //选择class不等于myClass的div元素
$("div").filter(".myClass"); //选择class等于myClass的div元素
$("div").first(); //选择第1个div元素
$("div").eq(5); //选择第6个div元素
$("div").next("p"); //选择div元素后面的第一个p元素
$("div").parent(); //选择div元素的父元素
$("div").closest("form"); //选择离div最近的那个form父元素
$("div").children(); //选择div的所有子元素
$("div").siblings(); //选择div的同级元素
```

### 链式操作

```javascript
$("div").find("h3").eq(2).html("Hello");

$("div") //找到div元素
  .find("h3") //选择其中的h3元素
  .eq(2) //选择第3个h3元素
  .html("Hello"); //将它的内容改为Hello

// jQuery还提供了.end()方法，使得结果集可以后退一步：
$("div")
  .find("h3")
  .eq(2)
  .html("Hello")
  .end() //退回到选中所有的h3元素的那一步
  .eq(0) //选中第一个h3元素
  .html("World"); //将它的内容改为World
```

### 创建、复制和删除元素

1. 创建新元素

   ```javascript
   $("<p>Hello</p>");
   $('<li class="new">new list item</li>');
   $("ul").append("<li>list item</li>");
   ```

2. 复制元素使用 **_.clone()_**
3. 删除元素使用 **_.remove()_** 和 **_.detach()_** 。两者的区别在于，前者不保留被删除元素的事件，后者保留，有利于重新插入文档时使用
4. 清空元素内容（但是不删除该元素）使用 **_.empty()_**

### 移动元素

- **_.insertAfter()_** 和 **_.after()_**：在现存元素的外部，从后面插入元素
- **_.insertBefore()_** 和 **_.before()_**：在现存元素的外部，从前面插入元素
- **_.appendTo()_** 和 **_.append()_**：在现存元素的内部，从后面插入元素
- **_.prependTo()_** 和 **_.prepend()_**：在现存元素的内部，从前面插入元素

1. **_.insertAfter()_**

   ```javascript
   $("div").insertAfter($("p")); //把div元素移动p元素后面
   ```

2. **_.after()_**

   ```javascript
   $("p").after($("div")); //把p元素加到div元素前面
   ```

表面上看，这两种方法的效果是一样的，唯一的不同似乎只是操作视角的不同。但是实际上，它们有一个重大差别，那就是返回的元素不一样。第一种方法返回 div 元素，第二种方法返回 p 元素。你可以根据需要，选择到底使用哪一种方法。

### 操作元素：取值、赋值和修改

常见的函数如下

1. **_.html()_** 取出或设置 html 内容
2. **_.text()_** 取出或设置 text 内容
3. **_.attr()_** 取出或设置某个属性的值
4. **_.width()_** 取出或设置某个元素的宽度
5. **_.height()_** 取出或设置某个元素的高度
6. **_.val()_** 取出某个表单元素的值

修改元素属性

```javascript
.attr() //获取匹配的元素集合中的第一个元素的属性的值。设置每一个匹配元素的一个或多个属性。
.prop() //获取匹配的元素集中第一个元素的属性（property）值为匹配的元素设置一个或多个属性（properties）。
.removeAttr() //为匹配的元素集合中的每个元素中移除一个属性（attribute）。
.removeProp() //为集合中匹配的元素删除一个属性（property）。
.val()  //获取匹配的元素集合中第一个元素的当前值。设置匹配的元素集合中每个元素的值。
$("img").attr("src", "img/a.jpg"); //修改src属性
$("img").attr("width", "100px"); //修改width属性
```
