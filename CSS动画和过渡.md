# 动画or过渡or多次动画

## transform

### transform原理
- transform:translateX(0=>300px)
- 直接修改会被合成，需要等一会修改
- transition过渡属性可以自动脑补中间帧，达到动画的效果
- 注意：此方法动画并没有repaint(重新绘制) 比改left性能好

### 常用属性
- 位移：translate
- 缩放：scale
- 旋转：rotate
- 倾斜：skew

#### 注意
- 一般都需要配合transition过渡
- inline元素不支持transform，需要先变成block

### translate 平移
- 通常属性
  ```css
    transform:translateX() 横轴平移;
    transform:translateY() 竖轴平移;
    transform:translateZ() 垂直于屏幕平移(你设置的视的远近);
  ```
- 缩写
  ```css
    transform:translate(x值,y值) ;
    或者是transform:translate3d(x值,y值,z值) ;
  ```
- 若使用z轴，那么需要在父元素设置视点

      perspective：值

- 取值 px、em、百分比

- 学到的经验
  1. 要学会看懂MDN语法实例
  2. translate(-50%,-50%)可做绝对定位元素的居中

### scale 缩放
- 通常属性
  ```css
    transform:scaleX()以X轴为基准缩小或放大;
    transform:scaleY()以Y轴为基准缩小或放大;
  ```
- 缩写  
  ```css
    transform:scale(x,y)
  ```

- 取值：不加单位的数字代表倍数

- 学到的经验
  1. 一般不会用，容易模糊，变形

### rotate 旋转
- 通常属性
  ```css
    transform:rotateX(deg) ;
    transform:rotateY(deg) ;
    transform:rotateZ(deg) ;
  ```

- 缩写
  ```css
    transform:rotate(deg) 默认是以Z轴旋转
  ```

- 学到的经验
  1. 一般用于360度旋转制作loading加载动画
  2. 用的时候记得查看MDN文档

### skew 梯形旋转(方便理解)
- 属性
  ```css
    transform:skewX(deg) ;
    transform:skewY(deg) ;
    transform:skew(deg) ;
  ```

- 需要注意的
  1. 把方形变成平行四边形一样旋转
  2. 用的很少，用的时候查skew MDN文档就好了

### transform 多重效果

- 组合使用
  ```css
    transform:scala(1.5) translate(-100%,-100%) 注意用空格隔开就好了
  ```
- transform:none; 取消所有效果

### 心得
- 学好CSS需要好的想象力，逻辑在这里不重要
- CSS给的属性比较简单，但可以组合成很复杂的东西
- 多看看，多敲敲代码

## transition 过渡

### 作用
- 补充盒子从a点到b点中间的动画

### 语法
- transition：属性名/时长/过渡方式/延迟
 
  例如：transition：left 200ms linear
- 可以用逗号分隔开两个不同属性

  例如：transition：left 200ms,top 400ms
- 可以用all 代表所有属性
  
  例如：transition：all 200ms；
- 过渡方式：
  1. linear：线性过渡
  2. ease：缓动的
  3. ease-in：快进缓动
  4. 如果这里不够用就看MDN

### 注意：
- 过渡必须要有起始
- 一般只有一次动画或者两次

## 多次动画animation和@keyframes

## animation
- 声明关键帧
- 添加动画
- 属性
1. 时长：1s or 100ms
2. 过渡方式：默认是easa 和transition取值一样，如linear
3. 方向：reverse反向动画、alternate开始后回来
4. 填充模式：none、forwards动画结束后停在动画最后的关键帧上、backwards、both(这个待补充，没怎么看明白)
5. 是否暂停：poused暂停或者是running不暂停
6. 以上所有属性都有对应的单独属性，如果只设置其中一个属性就需要把单独属性写全

## @keyframes 定义动画的关键帧
- 语法
```css
@keyframes 动画名称 {
    0% {
        transform:translateX(100px)
    };
    50%{
        transform:translateX(150px)
    };
    100%{
        transform:translateX(200px)
    };

    也可以
    for {
        transform:translateX(100px)
    }
    to {
        transform:translateX(150px)
    }
    每一次运动后下一个关键帧必须要保留上一次的运动，否则会有问题
}
```
## 补充动画的更多实现方法

- 使用多次transform
  1. .a===transform===> .b
  2. .b===transform===> .c
- 如何知道中间点
  
  用setTimeout或监听transitonend事件

