# HTML学习笔记

 **HTML是由伯纳斯-李（Tim Berners Lee）发明的。**   

 **HTML的起手**
```HTML
<!DOCTYPE html> 文档类型
<head></head> 页面中不显示
<html lang="en"></html> html标签 lang可以改为zh-CN
<meta charset="utf-8"> 字符编码
<meta http-equiv="X-UA-Compatible" content="IE=edge"> 使用最新内核
<meta name="viewport" content="width=device-width, initial-scale=1.0"> 禁用缩放，兼容手机
<title>Document</title> 页面标题
<body></body> 网页内容
```
 


**常用的表章节的标签**   
1. h1-h6标签 1-6级标题
2. section标签 章节
3. article标签 文章
4. p标签 段落
5. header 头部区域
6. main 主要内容，一个页面最好只有一个main
7. aside 旁支内容
8. footer 脚部
9. div 划分

**全局属性**
1. class 类名
2. contenteditable 内容可以被编辑
3. hidden 隐藏
4. id id名称表示全局唯一，但其实并不是，不推荐使用
5. style 设置标签样式
6. tabindex 没有鼠标时通过tab操作页面，0最后选中，-1不会被选中
7. title 显示完整的内容

**常用的内容标签**
1. ol + li 有序列表
2. ul + li 无序列表
3. dl + dt + dd 带有标题的列表
4. pre 保留HTML标签中的空格、tab、回车
5. code 代码 字母等宽
6. hr 分割线
7. br 自动换行符
8. a 超链接 href(跳转的页面),target(_blank在新窗口打开)属性
9. em 语气强调 斜体
10. strong 内容强调 加粗
11. quote 行内引用
12. blockquote 块级引用


