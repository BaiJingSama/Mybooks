# CSS grid布局

## 介绍
- 一维用flex布局
- 二维用grid布局
- grid也分为container和items

## **container**

### 成为grid-container
```css
dis-play:grid;
dis-play:inline-grid;
```

### 行和列
```css
grid-template-columns：40px 50px auto 50px 40px;
代表同时申明了盒子中有五列和分别的宽度
grid-template-rows:25% 100px auto;
代表同时申明了盒子中有三行和分别的行高
宽度和宽度可以用(fr)份，分成平均值
```
### item设置范围
```css
grid-row-start:从哪一行开始
grid-column-start:从哪一列开始
grid-row-end:从哪一行结束
grid-column-end:从哪一列结束
```

### 行和列进阶版
- 创造盒子
```css
grid-template-areas:
"a b c"
"d e f"
"g h i"
申明了盒子内三行三列，每个区域都可以指定一个或多个item
```
- 指定区域
```css
要指定某个item给a
就在该item中写：
grid-area:a;
```
- 可以设置宽高，边距

### 边距
```css
grid-gap: 子盒子之间的宽度
grid-row-gap: 子盒子行与行的间距
grid-column-gap: 子盒子列与列的间距
```

### 如果有某个值需要重复
- 在需要重复的地方写repeat(x次,值)
- 需要注意逗号隔开