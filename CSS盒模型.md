# 盒模型学习

## 两种盒模型
- border-box
  是包括边框的盒模型，包含content、padding、border
  更被推荐使用的盒模型，因为border模型可以更好的设置width、border、padding
  公式：border-box width = 内容宽度 + padding + border
- content-box
  内容盒模型，只包括内容
  公式：content-box width = 内容宽度
- 盒模型的构成
  由外到内：margin-border-padding-content

## margin 合并
- 兄弟合并
  在同一个父盒子内的多个子盒子如果设置了margin上下的值会合并
- 父子合并
  第一个子元素和最后一个子元素会跟父盒子的margin上下值合并
- 只有上下合并，左右不合并
- 解决：
  1. display：inline-block
  2. overflow:hidden
  3. 设置padding或border
