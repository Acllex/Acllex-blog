# CSS 部分知识总结

## 浏览器渲染原理

1. 根据HTML构建HTML树（DOM）
2. 根据CSS构建CSS树（CSSOM）
3. 将两棵树合并成一棵渲染树（render tree）
4. Layout布局（文档流、盒模型、计算大小和位置）
5. Paint绘制（把边框颜色、文字颜色、阴影等画出来）
6. Compose合成（根据层叠关系展示画面）

## CSS 动画的两种做法（transition和animation）

**transform**
```CSS
transform: translate() //位移，两个值，对应X、Y轴，transition: translate(-50%，-50%)可以让绝对定位元素居中
transform: translateX() //沿X轴位移
transform: translateY() //沿Y轴位移
transform: scale() //缩放，也分为X、Y轴
transform: rotate() //旋转，单位是deg
transform: skew()  //倾斜
/* 要配合 transition 才有动画效果 */
/* inline元素要变成block元素才支持transform */
```
**animation**
```CSS
/* 使用 @keyframes 定义动画*/
@keyframes name {
  0% {
    transform: scale(1);
  }
  100% {
    transform: scale(1.5);
  }
}
/* 使用 animation 调用动画 */
animation: name 3s ease-in 1s infinite reverse running;
/* 动画名称 动画时间 过渡方式 延迟动画时间 动画次数 方向 动画状态*/
```