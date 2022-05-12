# CSS动画和效果原理

## 动画的定义
- 由许多静止的画面组成(帧)
- 以一定的速度(如每秒30张)连续播放时
- 肉眼因视觉残像产生错觉，而误认为是活动的

## 动画的概念
- 帧：每个静止的画面都叫帧
- 播放速度：每秒24帧(影视)或每秒30帧(游戏)

## 动画原理
- 每过一段时间(用setInterval做到)
- 将div移动一小段距离
- 知道移动到目标地点

## 性能
- 开发者工具打开绘制-闪烁，绿色表示重新绘制了一遍的元素
- CSS渲染过程依次为 布局——绘制——合成
- 其中布局和绘制有可能被省略

## 浏览器渲染原理
- 步骤
  1. 根据HTML构建文档树(DOM)
  2. 根据CSS构建CSS树(CSSOM)
  3. 将两棵树合并成一颗渲染树(render tree)
  4. Layout 布局(文档流、盒模型、计算大小和位置)
  5. Paint 绘制 (把边框颜色、文字颜色、阴影等画出来)
  6. ComPose 合成(根据层叠关系展示画面)
- 注意：前端老鸟不用left做动画，用transform做，因为节约性能

## 三种更新方式
1. JS/CSS=>样式=>布局=>绘制=>合成 (div.remove)
2. JS/CSS=>样式=>绘制=>合成 改变背景颜色之类的
3. JS/CSS=>样式=>合成 改变transform就可以做到
   
## 如何更新样式
- 一般用JS更新样式
  1. 比如```javascript div.style.background='red'```
  2. 比如```javascript div.style.display='none'```
  3. 比如```javascript div.classList.add('red')```
  4. 比如```javascript div.remove()``` 直接删掉节点

## 如果不知道什么属性走什么流程
- 用 [css流程查询](CSStriggers.com) 来查询

## CSS动画优化
- 答案都在谷歌的网站里(文章)

### JS优化
- 使用requestAnimationFrame代替setTimeout或setInterval

### CSS优化
- 使用will-change或translate

