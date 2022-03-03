# Vue 父子组件传值

## 父组件向子组件传值

```html
<!-- 父组件 -->
<Child :msg="data"></Child>
```

```js
// 子组件
// 使用数组
props: ["msg"],
// 或者使用对象
props: {
    msg: String,
    isTrue: Boolean,
}
```

## 子组件向父组件传值

子组件需要通过事件向父组件传值

```html
<!-- 子组件 -->
<button @click="submit"></button>
```

```js
// 子组件
export default {
  methods: {
    submit() {
      this.$emit("childFn", "来自子组件的消息");
    },
  },
};
```

```html
<!-- 父组件 -->
<Child @childFn="parentFn"></Child>
```

```js
// 父组件
export default {
  methods: {
    parentFn(payload) {
      console.log(payload);
    },
  },
};
```
