# 理解 Vue 中的.sync 修饰符

当前的 .sync 修饰符在 Vue 中是作为一个语法糖存在的。它被扩展为一个自动更新父组件属性的 v-on 监听器。

```html
<Child :num.sync="number"></Child>
<!-- 被扩展成 -->
<Child :num="number" @update:num="number=$event"></Child>
```

```html
<!-- 具体示例 -->
<div id="app">
  <div>{{number}}</div>
  <Child :num.sync="number"></Child>
  <!-- 被扩展成 -->
  <!-- <Child :num="number" @update:num="number=$event"></Child> -->
</div>
<script>
  Vue.component("Child", {
    template: `<div @click="$emit('update.num', num+1)">点我+1</div>`,
    props: ["num"],
  });
  new Vue({
    el: "#app",
    data: { number: 0 },
  });
</script>
```
