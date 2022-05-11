# 记录下在饥人谷学习到的HTML入门的知识点（1）

## 目录
1. HTML起源
2. HTML起手规范
3. 常用章节标签
4. 全局属性标签 
5. 常用内容标签

## 好用的网站
- [饥人谷JS bin](http://js.jirengu.com)
- [HTML教程-网道](https://wangdoc.com/html/)
- [CodeSandbox](https://codesandbox.io/dashboard/home)

  ```html<meta name="viewport" content="width=device-width, initial-scale=1.0, minimum-scale=1.0, maximum-scale=1.0, user-scalable=no">
  ```
## HTML起源
- 是由Tim Berners-Lee爵士在1990年开发出来的，发明初衷是想实现输入网址就能看到网页这个行为，获取信息能更方便

- www的简单理解是由 URL+HTTP+HTML组成的

- 最原始的HTML只有18个元素，发展到至今已经有110个以上的元素


## HTML起手规范
```html
<!DOCTYPE html>
<!-- 文档类型 -->
<html lang="zh-CN">
<!-- 这个表示语言 en是英文 zh-CN是中国中文 -->

<head>
    <meta charset="UTF-8">
    <!--这个是不能变的 UTF-8 是支持全人类所有语言的 变了可能会乱码-->
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <!-- 默认让IE用最新内核打开网页 -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <!-- viewport=视窗，照抄  防止页面缩放 -->

```

## 常用章节标签

- h1~h6 表示标题h1表示最大，h6表示最小

- section 章节标签

- article 文章标签

- p 段落标签 会让前后换行

- header 头部标签 在网页最上面

- footer 脚部标签 在网页最下面

- main 主要内容标签

- aside 旁支内容标签

- div 划分标签 可以划分一个区域

## 全局属性标签

- class 给标签分类，标记标签

- conteneditable 让标签内的内容可以在网页上编辑

- hidden 隐藏标签内的内容

- id 给标签起一个id js可以调用 （一般情况下尽量不用 除非不用会死）

- style 给标签定义风格

- tabindex 定义标签被键盘上tab键操作的顺序 数字从小打大
*（有两个特殊值 0表示最后访问 -1表示不被tab访问）*

- title 用来显示被省略的完整内容 可以自定义其中内容

## 常用内容标签

- ol+li 有序列表标签 ol内只能有li标签

- ul+li 无需列表标签 也只能有li标签

- dl+dt+dd 描述列表标签 
dt：被描述的对象、标题<br>
dd：描述的内容

- pre 把代码内的空格和回车体现到网页里，要把内容放在pre标签内

- code 文字等宽标签 一般用于写代码 配合pre标签使用

- hr 分割线标签 类似某乎分割线

- br 换行代码 打断这一行

- a 链接标签 后面会详细学 
```html
      “target=_blank ”
      <!--新窗口打开链接-->
```

- em 强调 默认样式是斜体

- strong 重要 默认样式是加粗

- quote 引用标签 没太搞明白咋用待会查一下

- blockquote 块级引用 会换行
