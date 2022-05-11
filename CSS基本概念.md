# CSS基本概念的学习

## 文档流动方向
- 内联元素从左到右流动，到最后侧换行显示(inline)
- 块级元素从上到下流动，每个元素独占一行(block)
- 行内块元素也是从左到右流动，但不会被分隔成两块换行(inline-block)
- **行内元素不要加块级元素**

## 宽度
- inline 宽度为内部 inline的和，不能用width指定(简单来说它的宽度是由内容决定)
- block 默认自动计算宽度，可用width指定(默认宽度是最大值不是百分之百，尽量不写宽度百分之百，容易出问题)
- inline-block 结合两者的特点，但是宽度可以设置

## 高度
- inline 高度由 line-height(行高) 间接确定，跟height无关，不能设置height
- block 高度由内部文档流元素决定，可以设置 height
- inline-block 跟block相似，可以设置height
- 需要注意
  div 没有内容时高度为0
  span 会有高度

## overflow 的值
- visible 默认的显示溢出部分
- hidden 溢出部分隐藏
- scroll 显示滚动条，但是很丑
- auto 自动显示滚动条，不溢出就不会显示

## 脱离文档流
- float 浮动脱离
- position:absolute/fixe 定位脱离
- 不用这两个属性就不会脱离文档流

## 单位
- 长度
  1. px像素
  2. em字符倍数
  3. 百分数
  4. 整数
  5. rem
  6. vm和vh

- 颜色
  1. 十六进制#FFFFFF 或者#FFF
  2. rgba颜色(0,0,0,0.5) 红绿蓝
  3. hsl颜色(360,50%,50%) 色相饱和度
  4. rgb和十六进制可以相互转换，搜索