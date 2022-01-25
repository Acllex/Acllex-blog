# 浅析 MVC

## MVC 是什么

- M: Model(模型),数据处理,和后端交互数据
- V: View(视图),用户界面显示
- C: Controller(控制器),处理各种事件,调用和更新 Model 层的数据

```js
// 数据层
const M = {
  data: {}, //数据
  create: {}, // 增
  delete: {}, // 删
  update: {}, // 改
  get: {}, // 查
};

// 视图层
const V = {
  el: null, // 需要操作的元素
  html: `html代码`,
  init() {
    V.el = 需要操作的元素;
  },
  render() {}, // 重新渲染视图
};

// 控制层
const C = {
  init(container) {}, // 初始化
  events: { 事件以哈希表的方式存储 }, //事件
  method() {}, // 使用到的函数
  autoBindEvent() {}, //表驱动事件监听
};
```

## EventBus 的作用和 API

当我们模块化之后，每个模块之间的信息传递就需要用到 EventBus 解决模块和对象间的通信。它主要包含以下方法

1. on 用于监听事件
2. trigger 用于触发事件
3. off 卸载监听

```js
// 发送消息
EventBus.$emit("aMsg", "我是消息");

// 监听接收消息
EventBus.$on("aMsg", callback());

// 移除事件的监听
EventBus.$off("aMsg");

// 移除所有事件的监听
EventBus.$off();
```

## 表驱动编程

表驱动编程就是声明一个哈希表，用来记录映射关系，就不需要大量的重复代码了

```js
const list = { 小李: 18, 小王: 12, 小张: 13 };

const find = (name) => {
  if (name in list) return list[name];
};
```

## 模块化

1. 使代码逻辑更加清晰，每一个模块只处理自身的事务，更容易阅读和理解
2. 使代码解耦，减少代码之间的纠葛，使代码修改变得比较容易
3. 更利于团队合作，每一个人负责自己的模块编写，提高变成效率
4. 提高代码复用率，将写好的代码封装成模块，在需要时直接调用
