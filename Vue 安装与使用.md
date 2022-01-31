# Vue 的安装和使用

## Vue 的完整版和运行时版本

Vue 有完整版和 runtime(运行时) 版本，主要区别就是

- 完整版：包含编译器和运行时版本
- 运行时：用来创建 Vue 实例、渲染并处理虚拟 DOM 等的代码
- 编译器：用来将模板字符串编译成为 JavaScript 渲染函数的代码

## template 和 render 使用

- **_template_**

  传入字符串，vue 通过给的字符串生成 render 函数进行虚拟 dom 编译

  ```js
  new Vue({
    el: "#app",
    template: `<div>{{message}}</div>`,
    data: {
      message: "Hello",
    },
  });
  ```

* **_render_**

  render 相较于 template 优先执行

  ```js
  new Vue({
  el: "#app",
  render(h){
      return h('div', [this.message])
  }
  data: {
      message: "Hello",
  },
  });
  ```

## 在 codesandbox.io 中编写 Vue

![codesandbox](/images/codesandbox使用.png)
