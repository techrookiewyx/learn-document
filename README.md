# learning-log

以下内容为个人在学习HMLT和CSS记录仅供参考

### 1. HTML

#### 1.1 网页简史

1. 网页由图片、视频、文字等元素组成
2. Web标准规定网页由结构、表现、行为组成

#### 1.2 HTML简介

1. HMTL文件中的基础结构
2. 字符的编码，乱码产生的原因以及解决方法
3. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/h5/meta-label.html) | meta设置页面字符集、语言类型等元数据
4. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/h5/structure-label.html) | HTML语义化标签
5. HMLT文档类型声明、书写语法、普通标签和自结束标签
6. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/h5/02-SemanticLabel.html) 常用标签：排版标签、文本格式化标签
7. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/h5/01-first-page.html) | 常用标签的常用属性、属性的设置（键值对存在）
8. 标签之间的关系（包含、并列），注释的使用（注意：注释不可嵌套）
9. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/h5/line-block.html) | 行内元素与块级元素的区别与各自特点，常见的块级元素和行内元素

#### 1.3 HTML常见嵌入元素

1. 了解图片的不同的格式和各自的特点
2. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/h5/img.html) | 绝对路径和相对路径，HTML中图片标签以及常用属性的使用 
3. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/case/h5/077.html) | 图片映射（img配合map和area标签）
4. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/h5/06-medium.html) | 音视频标签以及其常用属性
5. 旧版浏览器对音视频的兼容（使用embed）

#### 1.4 超链接

1. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/h5/link.html) | 普通超链接的语法格式，链接打开的三种方式
2. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/h5/mao.html) | 图片超链接、锚点链接的创建方法
3. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/case/h5/024.html) | 邮箱链接的创建以及其中各个字段的含义

#### 1.5 列表

1. 列表的分类（有序、无序、自定义），各种列表创建方式以及常用属性
2. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/h5/03-list-link.html) | 列表之间的嵌套，通过type修改列表符号类型
3. 列表使用场景—导航栏（需要后边学习浮动实现）

#### 1.6 表格

1. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/case/h5/037.html) |  表格的创建方式，表头标题标签的使用以及常用属性
2. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/h5/table.html) |  表格结构化标签（thead、tbody、tfoot）
3. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/case/h5/040.html) |  单元格合并，边框合并

#### 1.7 表单

1. 表单的创建语法，常用属性，input的常用类型（注意单选按钮需要指定相同的name值）
2. label绑定input的方法，以及fleldset标签的使用
3. 下拉列表和文本域
3. [综合案例](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/h5/07-case.html) 



有关HTML的更多案例可以参考[这里](https://github.com/wzjyx676425826/learn-document/tree/main/case/h5)

可以查看详细的个人的HTML[笔记](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/h5_note.md)，更多详细知识可以参考[文档](https://developer.mozilla.org/zh-CN/docs/Web/HTML)

### 2. CSS

#### 2.1 CSS基础

1. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/css/demo/CSS-use.html) |  CSS(层叠样式表的作用)，基本语法、书写规范以及注释
2. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/css/01-use.html) |  CSS的引入方式以及其各自的优先级
3. 一些css通用属性
4. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/css/demo/length-unit.html) |  简单文本属性，长度单位（注意一下em和rem的区别）
5. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/css/demo/color-unit.html) |  有关背景的常用属性，4种常用表示颜色的属性
6. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/css/demo/style-inherit.html) |  样式的继承以及覆盖

#### 2.2 CSS选择器

1. 常用选择器：元素、id、类、通配符选择器
2. 复合选择器、分组选择器
3. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/css/02-selector.html) |  关系选择器：父子、后代、兄弟选择器
4. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/css/demo/attribute-selector.html) |  属性选择器(选中有特定属性的标签)
5. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/css/03-selector2.html) |  伪类选择器和伪元素选择器
6. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/css/demo/selector-weight.html) |  样式的的加权计算、优先级的比较

#### 2.3 盒模型

1. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/css/05-BoxModel.html) |  了解盒模型的概念和组成
2. 块级元素的盒模型与行内元素的盒模型
3. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/css/06-Box_X_Layout.html) |  盒子水平布局（满足过度约束的等式），盒子水平居中（要为元素设置宽度）
4. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/css/demo/margin-merge.html) |  盒子水平布局，解决元素溢出以及外边距折叠问题
5. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/css/demo/box-bit.html) |  改变盒模型大小的计算方式
6. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/css/12-shadow_radius.html) |  盒子的轮廓、圆角以及阴影

#### 2.4 浮动

1. 文档流的概念、文档流内外元素的特点
2. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/css/15-case4.html) |  浮动元素的特点，浮动的使用场景
3. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/css/13-float.html) |  高度塌陷问题，BFC开启方式，浮动的清除
4. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/css/demo/clearfix.html) |  使用after伪元素解决高度塌陷问题

#### 2.5 定位

1. 了解包含块以及元素层级的概念
2. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/css/demo/absolute.html) |  相对定位的参照点以及开启相对定位元素的特点及使用
3. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/css/demo/relative.html) |  绝对定位的参照点以及绝对定位元素特点及使用
4. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/css/16-position.html) |  固定定位和粘性定位的特点以及使用
5. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/css/17-absolute.html) |  通过绝对定位使元素居中

#### 2.6 字体、文本以及背景

1. 字体族的定义，图标字体的使用
2. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/css/19-text.html) |  行高、基线
3. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/css/demo/font.html) |  字体属性的复合写法
4. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/css/demo/text.html) |  文本溢出、阴影、文本修饰以及其他文本属性
5. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/css/demo/background.html) |  背景的复合写法
6. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/css/21-Gradient.html) |  背景的渐变效果

#### 2.7 过渡、动画、变形

1. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/css/24-transition.html) [米兔](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/css/25-case8.html) |  过渡常用属性以及属性值以及使用，过渡的复合写法
2. 动画常用属性以及各个属性的属性值
3. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/css/27-case9.html) |  关键帧的设置、动画的复合写法
4. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/css/28-transform.html) |  变形中平移、旋转、缩放的函数的常用值
6. 网页的视距

#### 2.8弹性布局

1. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/css/32-flex.html) |  弹性容器、弹性元素以及主轴和侧轴的概念，基本的使用方式
2. [代码](https://github.com/wzjyx676425826/learn-document/blob/main/h5_c3-practice/css/34-flex2.html) |  弹性容器的样式
3. 弹性元素的样式
