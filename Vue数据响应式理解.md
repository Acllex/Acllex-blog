# Vue 数据响应式理解

将一个普通的 js 对象传入 vue 的 data 选项中，Vue 会遍历这个对象所有的属性，并使用 Object.defineProperty 把这些属性全部转为 getter/setter。

vue 不能检测到对象属性的添加或者删除，解决方法式手动调用 Vue.set 或者 this.$set。

如果是数组需要变更，vue 也提供了七个方法：

- push()
- pop()
- shift()
- unshift()
- splice()
- sort()
- reverse()
