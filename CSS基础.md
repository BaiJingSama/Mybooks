# CSS基础学习

## **补充： border调试法**(十分重要)
1.  在写新的元素时或者怀疑哪个元素出问题时，给它加上border
2.  border如果没有在页面中出现，说明选择器出问题了
3.  border如果出现了，看边界是否符合设置的预期效果
4.  bug解决，再删除border

## CSS的发明
- 李爵士的同事赖先生(Hako Wium lie)在1994年提出的


## CSS的含义
- 样式层叠
  可以多次对同一选择器进行样式申明。

- 选择器层叠
  用不同选择器对同一元素进行样式申明

- 文件层叠
  可以用多个文件进行层叠

- 总结
  这些特点使得CSS极度灵活也留下后患


## 怎么知道哪些浏览器支持哪些特性
- 笨办法
  把代码用几十种浏览器全跑一遍

- 好用的办法
  使用 [CSS浏览器查询](http://caniuse.com)
  由开发者自发组成的开发者社区

## CSS是艺术
- 需要用感性的思维理解CSS，跳脱了解的东西，用新的方法把页面做好看即可。

- 所见即所学
  大多数时候不要问为什么，要明白原来是这样这句话

## 语法1
```css
选择器{
    属性名: 属性值;
    /* 注释 */
    /* 只有这一种注释 */
}
```
- 注意事项
  1.  所有符号都是英文的
  2.  一定要区分大小写
  3.  没有 // 注释
  4.  最后一个属性可以不加分号，但不要省略
  5.  任何地方写错了都不会报错

## 语法2 at语法
```css
@charset "UTF-8"; /* 指的是文件编码 */
@import url (2.css);
@media (min-width:100px)and(max-width:200px){
    语法1
} 
```
- 注意事项
  1.  charset 必须在第一行
  2.  前两个at语法必须在结尾写分号
  3.  charset 是字符集的意思，UTF8是字符编码
  4.  encoding 是历史遗留问题

## 如何调试
1.  w3c验证器 [w3c验证服务](https://jigsaw.w3.org/css-validator/)
2.  VScode看颜色提示 
3.  Webstorm 看颜色
4.  开发者工具的警告

## 查资料
- 谷歌搜索[关键词]+[MDN]
- CSS tricks
- 张鑫旭的博客

## 标准指定者
- CSS spec 搜索
- 可以看中文CSS2.1标准
- 目前最广泛的就是CSS2.1

## 练习的素材
- 国外：
  1.  freepik搜PSD web[freepik](https://www.freepik.com/search?format=search&query=web&type=psd)
  2.  下载以后需要复制作者信息加到自己做的东西里。

- 国内：
  365PSD里的ui套件，可以免费下载[365PSD](https://cn.365psd.com/free-psd/ui-kits)

- 效果图：
  [dirbbble.com](https://dribbble.com/search/web)

- 注意事项：
  1.  不要过度模仿，多做无益
  2.  PC窗口做两个，手机端做两个，UI套件做两个就足够了。
