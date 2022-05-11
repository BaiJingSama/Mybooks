# 记录学到的form、input标签

## 目录
1. 注意事项
2. form表单标签
3. input标签
---

## 注意事项

- 不监听click（点击事件）

- form的input要有name

- form里必须要有submit才能提交表单

- input里添加required属性就代表该组件为必须填写，否则无法提交

---

## form 表单标签

### 作用

发get或post请求，然后刷新页面

### action属性
你要把表单提交到哪里就在action里填写

### method属性
可以设置 get和post（目前不太懂，未来补充）

### 属性autocomplete
可以填写on或off，代表是否给用户填写的建议，可以提高用户体验

### 属性target
代表提交页面的响应，是否打开一个新的页面提交基本和a标签的target属性一致

### 事件

- onchange 用户输入改变时

- onfocus 用户鼠标移动到时

- onblur 用户鼠标离开时

----

## input 标签

### 属性

- text 文本输入框

- submit 提交按钮

- color 颜色选择器

- password 密码输入框

- ridio 单选框（必须保证一个题目的选项name一致才能被认定为一道题的选项）

- checkbox 多选框（必须保证多个选项的name一致才能被认定为一组）

- file 上传一个文件（加上multiple就可以上传多个文件）

- hidden 看不见的input，一般是给javascript使用

- email 邮箱输入框

- tel 号码输入框

- search 搜索输入框

### 其他常用

- textarea 多行输入标签

CSS：resize：none 可以不让用户拖动
可以设置宽、高，固定

- select 用户选择标签

option标签 添加选项


