# 布局基础、float布局、flex布局

## 布局基础

### 布局是什么

把页面分成一块一块的，按上中下，左中右的排列。

### 布局分类

1. 固定宽度：一般为960px/1000px/1024px

2. 不固定宽度：靠文档流的布局原理布局，主要应用在手机端。

3. 响应式布局，在PC端固定宽度，web端不固定，是一种混合布局

### 布局思路

- 从大到小：先把最大的盒子配置好，完善内部每个小布局

- 从小到大：先完成小布局，组合完成大布局

两种其实都行，新人用第二种，熟手用第一种

### 布局的方法

- 是否需要兼容IE9？

1. 是：用float布局

左浮动两个，固定宽度，不要响应式

**给父元素添加clearfix**

- 如果不需要兼容IE9，那么是否只兼容最新浏览器

1. 是：用grid布局

2. 否：用flex布局

**必要的时候采用负margin**

-----

## float布局

### 步骤

- 子元素上加float：left(right) 和 width
- 父元素上加clearfix **(非常重要)**

### outline

- 如果border会干扰布局大小，就可以用outline代替border，outline不占border空间。

### 居中
- 如果盒子有宽度可以进行如下操作
- 只对块元素有用
```css
margin:0,auto;
/*但这种方法不如下面的方法*/
margin-left:auto;
margin-right:auto;
/*这个方法不会让上下外边距被覆盖*/
```
### **平均布局(重点)**
- 如果最后右侧外边距有溢出，可以在父盒子与子盒子之间新建一个x盒子，给它设置一个margin-right或left：负值，这个值取决于你溢出的像素除2。

### 不同布局
- 两栏布局(顶条)
- 三栏布局(内容)
- 四栏布局(导航)
- 平均布局(产品展示区)
- 双飞翼(淘宝前端发明，已过时)

### 经验与总结
- 留一些空间，或最后盒子不设置宽度，或者只给盒子设置最大宽度。
- 不需要响应式，因为手机没有IE
- IE6/7会把margin算成双倍值，解决方法如下：
  1. 将错就错：针对IE6/7减半margin，多写一个只有IE6/7才认识的_margin:XX;覆盖。
  2. 神来一笔：加一个display：inline-block;
- 上述布局，加上头与尾，基本满足所有PC要求
- 手机页面不需要用float进行布局
- float需要自己算宽度，不灵活，但应付IE足矣。

---

## flex 布局

### 容器
- container父元素

- items 子元素

### **container属性**

### 让元素变成flex容器
```css
1.display:flex;
2.display:inline-flex;
```
### 改变items流动方向
```css
给父元素添加flex-direction:
属性:
row 从左到右流动，默认
column 从上到下流动
在row或column加-reverse，是反向排列的意思
```
### 改变items是否折行
```css
给父元素添加flex-wrap:
属性：
no-wrap 不折行，默认挤在一行显示
wrap 折行，让一行排列不下的items换行
wrap-reverse 反向折行
```
### 主轴对齐方式(水平方向)
```css
给父元素添加justify-content:
属性：
flex-start 默认，都挤在左边
flex-end 都挤在右边
center 挤在一起居中
between 左右贴边，平均分配空间 
```
### 次轴对齐方式(垂直方向)
```css
给父元素添加align-items：
属性：
stretch 不留空，把父盒子垂直空间占完，默认
center 居中对齐
flex-start 全部靠上对齐
flex-end 全部靠下对齐
```
### 多行次轴对齐(垂直方向)
```css
给父元素添加align-content：
属性：
stretch 默认
flex-start 全部靠上对齐
flex-end 全部靠下对齐
center 挤一起居中对齐
space-between 上下顶住平均分配空间
space-around 空余空间平均分配
```

### **item属性**

### 排列顺序
- 给item写order：
- order后面数字越大代表越靠后显示
- 默认数字是0，可以是负数，负数比零更靠前显示
  
### 控制元素长胖
- item盒子添加flex-grow：
数字越大，在页面拉伸时item拿到的空间越多

### 控制元素变瘦
- item盒子添加flex-shrink：
数字为0，则该item不会被影响
默认为1，大家一起变瘦

### 控制基准宽度
- item盒子添加flex-basis：
- 可以用width代替
- 默认为auto

### 让某一个item盒子单独上下对齐
- 在该元素中写align-self
- flex-end 只有它往下对齐
- 更多属性用的查资料

### 经验和总结
- 永远不要把width和height写死，除非特殊情况
- 可以用min或者max指定宽高
- 电脑一般写死宽高，手机不写死
- flex基本能满足所有布局
- flex和margin-xx:auto配合效果极其好

### 什么叫写死
1. 写死:
- width:100px
  
2. 不写死：
- width:50%;
- max-width:100px;
- width:30vw 屏幕宽度百分比
- min-width:80%

3. 特点：
- 不适用px，或者加min或max前缀