# C3 个人笔记 2 月 11 日

css3 用来为网页中元素设置样式

### 引入方式

css 的引入分为内联样式、内部样式、外部样式

- 内联样式

```bash
<p style="属性名:属性值; font-size:20px;">企鹅二他打字</p>  #语法标准 内联样式只对当前元素生效
```

- 内部样式

```bash
<head>
  <style>
  	p{
  	  color:red;
  	  font-size:15px;
  	}
  </style>
</head>
#该写法可以多多个标签设置样式，方便修改，但内部样式表只对当前页面生效
```

- 外部样式

为所有 css 样式创建一个专门的文件夹来存放

```bash
<link rel="stylesheet" href="css文件目录">
#这种方式可以使样式在不同页面复用，更好利用浏览器缓存机制，提高用户体验
```

## 规范

### 注释

css 中注释与 html 不同，css 中使用 /\* \*/

### 基本语法

```bash
选择器{
   声明块；
}
#通过选择器选择指定元素
#声明块就是要为元素设置样式
```

## 常用属性

### 字体 font

font 属性可以同时定义字体类型(黑体)、大小、粗细、字体样式（倾斜）

```css
div{
font: style weight size/line-height famliy;
}
可以通过上述代码直接设置多个属性值，顺序不可颠倒，不需要的属性可以省略但必须保留family和size，否则不起作用

```

- font-family：定义字体类型

  ```css
  p{font-family:"黑体";}  设置p标签字体为黑体，也可以设置多个字体，之间用逗号隔开  一般在body中设置字体
  /*
  其属性可选值
  serif：衬线字体   sans-serif：非衬线字体
  monospace：等宽字体
  */



  /*
  定义自己想要的字体  定义完毕用直接使用自己起的名
  */
  @font-face{
      font-family:"luoli";    给字体起一个名
      scr:url();    字体路径/
  }
  p{
      font-family:luoli;
  }
  ```

- font-size：设置文本大小

- font-color：设置前景色

- font-weight：设置文本的粗细

  其属性值有 bold（加粗）、bolder（更粗）、lighter（更细）

  其属性值也可以是数字（不加单位），400=normal 700=bold

- font-style：设置文本样式 其常用属性有 italic（倾斜）

- font-variant 属性设置小型大写字母的字体显示文本，这意味着所有的小写字母均会被转换为大写，但是所有使用小型大写字体的字母与其余文本相比，其字体尺寸更小

### 文本

#### 行高

行高指的是文字占有的实际高度，我们可以通过 line-height 设置字体的行高

- 行高可以使指定大小（px、em），也可是一个整数（行高将会是字体的指定倍数）
- 字体框时字体存在的格子，设置 font-size 就是设置字体框的高度
- 行高会在字体框的上下平均分配
- 将行高和高度设置为一样的值，使单行文字垂直居中，行高还可以用来设置文字的行间距（行间距=行高减去字体大小）

#### 水平对齐和垂直对齐

- text-align 文本水平对齐方式，可选值 left、right、center、justify（两端对齐）
- vertical-align 设置元素垂直对齐方式，可选值 baseline（默认值 基线对齐）、top（顶部对齐）、bottom、middle

#### 文本溢出处理

text-voerflow 设置文本溢出的显示方式，其属性值有

- clip（修剪文本）
- ellipsiss（显示省略符号来代表被修剪的文本）
- string（使用给定的字符串来代表被修剪的文本）

#### 文本修饰

1. 下划线

```css
a {
  text-decoration: underline color style;
  /*   通过text-decoration属性设置来修饰文本,可选值有voerline（上划线）、underlin（下划线）、line-through（删除线）、none（无），color可以指定其颜色，style指定样式（类似边框）
   
    */
}
```

2. 多余文字省略号显示

```css
p {
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
/*
  white-space设置网页如何处理空白
  可选值normal(默认，空白被忽略)、nowrap（不换行）、pre（与pre标签效果相同）
*/
```

#### 文本其他属性

- text-transform 属性改变文本中字母大小写样式，其属性值有 uppercase（字母大写）、lowercase（字母小写）、capitalize（首字母大写）
- 文本字符间距：letter-spacing
- 文本字间距：word-spacing
- text-index：设置文本缩进
- direction 属性规定文本的方向 / 书写方向，其属性值有 ltr（从左到右-默认）、rtl（从右到左）
- unicode-bidi 属性与 direction 属性一起使用，设置或返回是否应重写文本
- text-shadow：x，y，z，color，设置文本阴影
- word-wrap： 属性允许长单词或 URL 地址换行到行，其属性值有 normal（只在允许的断字点换行）、break-word（在长单词或 URL 地址内部进行换行）
- word-break 属性规定自动换行的处理方法，其属性有 normal、break-all（允许在单词内换行）、keep-all（只能在半角空格或连字符处换行）
- writing-mode 属性规定水平还是垂直地排布文本行，其属性值有 horizontal-tb（让文本从左到右水平流动，从上到下垂直流动）、vertical-rl（从上到下，从右到左）、vertical-lr（从上到下，从左到右）

### display

该属性用来设置元素显示的类型，下面介绍其可选值

- inline：将元素设置为行内元素
- block：将元素设置为块元素
- inline-block：将元素设置为行内块元素 既可以设置宽高也不会独占一行 （开发还是要避免使用）
- none：使元素不在页面中显示
- table：将元素变成块级表格来显示

### background

- 同时设置 background-iamge 和 background-color 时图像压在颜色上面，当设置多张背景图片时，在写 url 时前面的图片会默认层级比后面的高

- background-clip： 规定背景颜色的显示区域，其属性值有 border-box（默认值）、padding-box（背景不在边框显示）、content-box（背景只出现在内容区）

- background-origin：背景图片偏移量计算的原点，其属性值有 padding-box（默认值从内边距处开始计算）、content-box（背景图片原点从内容区开始计算）、border-box（从边框处开始计算）

- background-size ：设置背景图片大小 contain （图片内容完全显示，不一定会铺满容器）

- 用 background-position 来设置图像在元素中的位置

  ```css
  background-positon: x y;
  /*
  x和y代表坐标可以是方位无顺序要求(left、right、bottom、top、center)  当只写一个值如right则水平靠右，垂直居中  
  也可以是具体值（第一个值一个是x轴、第二个值是y轴）  px或者百分比   当只写一个值，垂直居中或水平居中
  
  上述两种方式可以混合使用
  */
  ```

- background-attachment 设置背景图像是否固定或者随着页面的其余部分滚动

  ```css
  background-attachment: fixed(固定的) / scroll(滚动的，它是默认值);
  ```

- 图像边框

  ```css
  /*在这里，重复图像的中间部分，来创建边框*/
  div {
    border: 10px solid transparent;
    border-image: url(https://www.w3school.com.cn/i/border.png) 30 round;
    padding: 15px;
  }

  /*
  将round改为stretch,图像的中间部分被拉伸，来创建边框
  */
  ```

#### 复合写法

```css
background: color url() no-repeat fixed centr top;
/*
   background-size要写在background-position后面用/分隔,origin写在clip前边，其他没有顺序规定
*/
```

#### 精灵图（2 月 19 日）

解决浏览器资源加载，把多个图片合成一张就不用浏览器每次都发送请求，提高用户体验，但精灵图只适用于背景图。使用步骤如下

1.  确认好要使用的图标，测量图标大小
2.  创建相应大小的元素，将图片设置为元素的背景图片
3.  设置背景图片偏移量，以正确显示图标

#### 线性渐变

从一个颜色向另一个颜色过渡，渐变是图片需要 background-image 设置，线性渐变是沿着一条直线改变

```css
.box {
  background-image: linear-gradient(to right, x apx, y, ....);
}
/* 
   通过linear-gradiant()属性值设置线性渐变，x和y都表示颜色，表示从x向y发生改变（默认从上向下），可以写多种颜色，默认情况下这多种颜色平均分配
   apx表示从a像素开始向y颜色渐变，apx的地方x颜色最浓
   加上to right表示从左向右变，同理可以换成to top、to left、也可以同时to top left表示从右下向左上
   也可以在颜色前加上deg表示旋转度数
*/
```

#### 径向渐变

从中心向四周呈放射性变化，基本用法与线性渐变一致，不同的是默认情况下其圆心形状由元素宽高决定，但可以通过一以下方式改变

```css
.box {
  background-image: radial-gradient(a b，at c d, x, y, ....);
}
/* 
  a b（像素）共同指定径向渐变大小
  at c d（像素）指定渐变圆心的位置，cd也可以为方向值
*/
语法： .box {
  background-image: radial-gradient(大小 at 位置, 颜色1 位置, 颜色2 位置, ....);
}
/*
    大小可以是circle、ellipse（椭圆）、closest-side/corner（近边/角）、farthest-side/corner（远边/角），也可是两个指定像素值（空格隔开）
    
*/
```

## 其他属性

- cursor 规定鼠标指针放在一个元素边界范围内时所用的光标形状（形状） 属性太多具体参考文档
- opacity 属性设置元素的不透明级别
- counter-reset 属性设置某个选择器出现次数的计数器的值
- counter-increment 属性设置某个选取器每次出现的计数器增量
- object-fit 属性用于指定应如何调整 <img> 或 <video> 的大小以适合其容器，其属性值有

  1.  fill - 默认值。调整内容大小，不保证内容（图片/视频）原有的比例，内容铺满容器
  2.  contain - 保持内容原来的比例进行缩放，直至能将其放入元素的内容框（不一定铺满容器）
  3.  cover - 调整内容的大小，图片铺满容器保持其原有比例，多余部分将被裁剪。
  4.  none - 不对替换的内容调整大小，图片原有宽高不变，超出部分被剪掉，保留下来的内容使图片的正中央
  5.  scale-down - 保持原有比例。当图片实际宽高小于所设置的图片宽高时，显示效果与 none 一致；否则，显示效果与 contain 一致。

- column-count 属性规定元素应该被划分的列数
  - column-gap 属性规定列之间的间隔，其默认值是 normal（1em）
  - column-rule-style 设置在多列布局中被画在两列之间的规则（线条）的样式，类似于边框的线条样式
  - column-rule-width 设置在多列布局中被画在两列之间的规则（线条）的宽度
  - column-rule-color 设置在多列布局中被画在两列之间的规则（线条）的颜色
  - column-rule 上面三条属性的简写
  - column-span 属性规定元素应横跨多少列
  - column-width 属性规定列的宽度

## 继承

当我们为一个元素设置样式其所有后代元素都会应用该样式，可以利用继承设置一些所有元素的通用样式，但不是所有的样式都会被继承，具体各个元素继承性要参考文档

## 选择器

### 常用选择器

#### 元素选择器

根据标签名来选中指定元素

```bash
p{ } #选中所有p标签
div{ }#选中所有div标签
```

#### id 选择器

通过个元素设定一个 id，来达到唯一标识该标签的效果，只对一个元素起作用，元素 id 不能相同

```bash
<style>
    #red{color: red;}
</style>
<p>企鹅二他打字</p>
<p id="red">设置该字体为红色</p>
# 井号代表id的意思，red代表id名字，这是就选中了id名为red的p标签
```

#### 类选择器(class)

它的 id 选择器类似，不同的是类选择器可以为不同标签可以设置相同的类名，一个元素可以设置多个类名

```bash
<style>
    .red{color: red;}
</style>
<h1 calss="red yellow">企鹅二他打字</h1>
<p calss="red">设置该字体为红色</p>
# .代表类(class)的意思，red表示类名，这同时选中类名为red的p和h1标签
```

#### 通配符选择器(\*)

选中页面中的所有元素

### 复合选择器（交集）

用多个条件选中元素

```bash
div.red {font-size: 30px;}
<div class="red">我是div</div>
#上述是用两个选择器来选中元素，可以再次基础上增加选择器个数，如果选择器中包含元素选择器，必须以元素选择器作为开始
```

#### 选择器分组（并集）

```html
<!-- 同时选择多个选择器对应的元素 -->
h1,span {color: pink;}
<h1>去去去</h1>
<span>啊啊啊</span>
```

### 关系选择器

#### 父子选择器

```html
<div>
  我是div
  <p>
    我是div里的p
    <span>我是p里的span</span>
  </p>
  <span>我是div里的span</span>
</div>
div>span{ }
<!--选中div子元素中的span  >就是选择其左边元素的所有子元素-->
```

#### 后代选择器

选中指定元素内的所有后代元素

- 语法：a b{ } 表示选中 a 标签下的所有 b 标签，空格隔开

#### 兄弟选择器

选中下一个兄弟

- 语法：a+b{} 表示选中**_紧挨着_**a 标签且和 a 同级的 b 标签如下图

![](../../练习文件/h5-css3/c3/兄弟选择器.jpg)

- 语法：a~b{} 表示选中 a 标签**_下面_**所有同级兄弟 b 标签

### 属性选择器

1. a[x]{ }，表示选择有 x 属性名的 a 标签

```bash
<p title>11111</p>
p[title]{ }
```

2. a[x=“b”]{ } 表示选择有属性 x 且属性值为 b 的 a 标签

```bash
<p title="aaa">11111</p>
p[title=aaa]{ }
#注意属性值最好是字母开头
#当鼠标放在1111上时会有aaa的提示信息
```

3. a[x^=“b”]{ } 表示选择有属性 x 且属性值以为 b**开头**的 a 标签，不能是整个单词
4. a[x$=“b”]{ } 表示选择有属性 x 且属性值以为 b**结尾**的 a 标签
5. a[x*=“b”]{ } 表示选择有属性 x 且**含有**属性值 b 的 a 标签
6. a[x~=“b”]{ } 表示选择有属性 x 且**含有**属性值 b 的 a 标签
7. [x|=b] 表示选则所有带有 x 属性且以 b 开头的标签（必须是整个单词）

### 伪类选择器(不是实际存在的类) （2 月 12 日）

**伪类用来描述一个元素的特殊状态**

#### :first-child、last-child、nth-child( ) 、only-child

这类伪元素只有在该元素是其父元素的第一个元素/最后一个时才能被选中

```bash
<ul>
    <li>a</li>
    <li>b</li>
    <li>c</li>
</ul>
ul>li:fitst-child{ }
#不论该结构怎么改变总是选中第一个子元素
#last-child 总是选择最后一个子元素
#nth-child(x)  x是几就选择第几个元素  x为n为所有子元素 x为2n或者even只选中偶数位的元素  x为2n+1或odd选中奇数位元素
# p:only-childe 表示选中对于其父元素来说只有一个子元素标签的p
```

#### :first-of-type、last-of-type、nth-of-type( )、only-of-type

该组伪类元素与上面类似，不同之处在于该组伪类元素选择的是同类型的第一个子元素

```bash
<ul>
	<span>1</span>
    <li>a</li>
    <li>b</li>
    <li>c</li>
</ul>
ul>li:fitst-child{ }
#此时会选中内容为a的li标签，若使用first-child则不会选中


#h2：only-of-type 表示对于其父元素的众多子元素中他是唯一的一类元素  如下例
 <div class="test1">
        <p>你好</p>
        <h2>55，我是子元素中，h2类型元素只有一个，用only-of-type匹配的上</h2>
</div>
#若把p换成h2则不被选中
```

#### ：empty

选中没有内容和子元素的元素

#### ：focus

当元素获取焦点时的状态

#### :not（） 否定伪类选择器

该伪类是将符合条件的元素从选择器中去除 如下图

![](../../练习文件/h5-css3/c3/伪类选择器.jpg)

#### 超链接伪类选择器

- a:link 表示未访问过的链接的/正常的链接

  ```bash
  a:link {color: black; font-size: 50px;}
  a:visited { color: blueviolet;}
  <a href="www.baidu.com">正常链接</a>
  <a href="#">访问过的链接</a>
  ```

- a:visited 表示访问过的 只能修改颜色

  ```bash
  a:link {color: black; }
  a:visited { color: blueviolet;  font-size50px;}
  #当把font-size属性放到visivted中时，字体不会变化，由于正常网站是供多人访问的，这种不显示变化的方式可以保护个人隐私，所以a:visited只能修改链接颜色
  ```

- a:hover 表示鼠标悬停时，此伪类不是 a 标签专用

  ```bash
  a:hover{color:red; }
  <a href="#">当鼠标放到这里变成红色</a>
  ```

- a:active 表示鼠标点击的状态 此伪类不是 a 标签专用

- a:hover 必须位于 a:link 和 a:visited 之后才能生效，a:active 必须位于 a:hover 之后才能生效

### 伪元素选择器 （不存在的元素）

**伪元素表示元素特殊位置**

#### ::first-letter 表示第一个字母

```bash
p::fitst-letter{color:red; }
#表示选中p标签里的第一个字母 将其设置为红色
```

#### ::first-line 使用同上 表示选中第一行

#### ::selection 表示鼠标选中的内容

![](../../练习文件/h5-css3/c3/伪元素选择器.jpg)

#### ::before ::after （重要）

表示选中元素的起始/结束位置，必须结合 content 使用

```bash
p::beorfe{ }
<p>测试123</p>
#此时选中‘测’之前的位置
```

#### 选择器练习

https://flukeout.github.io/

### 选择器权重

#### 样式冲突

当我们通过不同的选择器为一个相同元素设置相同的样式不同的值

#### 优先级比较

1. 内敛样式（1000）>id 选择器（100）>类和伪类选择器（10）>元素选择器（1）
2. 比较优先级时，需要将所有的选择器优先级进行相加计算，优先级越高，则最优先显示 ，选择器的累加不会超过其最大数量级
3. 分组选择器单独计算
4. 如果优先级相等，则离元素近的显示
5. 继承的样式没有优先级，统配选择器优先级大于继承的
6. 可以通过在一个样式属性值的后边加上**！improtant**，来让这个样式获得最高优先级，超过内联

## 长度单位

### 像素

像素是一个长度单位单位是 px，由一个一个小点构成，在前端发开中像素分两种 css 像素和物理像素

- 物理像素：显示器分辨率中 1920x1080 就是物理像素
- css 像素：编写网页时，我们用的就是 css 像素，浏览器在网页时，需要将 css 像素转换为物理像素然后再呈现，默认情况下在 pc 端 1 个 css 像素=1 个物理像素
- 可以通过查看视口的大小，来观察 css 像素和物理像素的比值

### em 和 rem

- em 是相对于元素自身的字体大小来计算的 1em=1font-size，h5 默认字体大小是 16px
- rem 与 em 类似，rem 是根据根元素的字体大小来计算的

## 颜色单位

### 英文名表示

直接用 red、green、blue 等来代表颜色，在 css 中直接使用颜色名描述非常鸡肋也很不方面

### RGB

- RGB 就是通过 red、green、blue 三种颜色的不同浓度来调配出不同的颜色，每一种颜色的范围在 0-255 之间，根据光的三原色计算，其本质就是把颜色转换成了数字

```html
<div class="box"></div>
.box{ backgroud-color:rag(x,x,x); }
<!-- 
上述是rgb语法 全0是黑色  全255是白色
-->
```

### RGBA

- 用法跟 RGB 一样，就是多了一个透明度属性，需要四个参数，其范围在 0-1

  ```html
  <div class="box"></div>
  .box{ backgroud-color:rag(x,x,x); }
  <!-- 
  上述是rgb语法 全0是黑色  全255是白色
  -->
  ```

### 16 进制 RGB

- 语法：#红色绿色蓝色，每两位表示一种颜色其范围是 00-ff
- 如果颜色两两重复则可以简写 例如：#aabbcc—>#abc

### HSL(了解)

- CSS 提供的一种颜色表示方式，H-色相，S-饱和度，L-亮度，在前端开发中不常用，下面介绍语法

```html
<div class="box"></div>
.box{ backgroud-color:hsl(x,x,x); }
<!-- 
 第一个参数范围是0-360，第二个参数是0%-100%，第三个也是0%-100%
-->
```

## 文档流

- 网页是一个多层的结构，通过 css 来为每一层设置样式，用户只能看到最上面的层，最底层成为文档流，他是网页的根基，我们创建的元素默认都是在文档流中进行排列的

- 对于元素来说主要有两个状态

  1.  在文档流中
  2.  不在文档流中(脱离文档流)

- 处在文档流中的块级元素其宽度默认撑满其父元素（和父亲一样宽），高度默认被其内容/子元素撑开，自上向下垂直排列
- 处在文档流中的行级元素，其宽度和高度取决于内容，自左向右水平排列

## 盒模型 （2 月 13 日）

- CSS 将页面中所有元素都设置为一个矩形的盒子，页面布局就是将变为盒子的元素摆放到不同位置
- 盒模型主要由内容区（content）、边框（border）、内边距（padding）以及外边距（margin）组成

### 块级元素盒模型

1. 正常情况下内容区的大小由 width 和 height 属性设置

2. 边框大小由 border 属性来设置，边框大小会影响整个盒子大小

   ```html
   .box{ border-width:20px 30px 40px 50px; 分别为四边设置不同的值，顺序是上右下左 border-width:10px 20px 30px;
   当设置三个值时，顺序是上、左右都为第二个值、下 border-style： ;
   当其值为soild表示实线、dotted表示点状虚线、dashed表示线状虚线、double表示双实线 }
   <div class="box">div</div>
   <!-- 通常边框至少要设置三个属性分别为边框粗细、颜色以及样式,可以通过一个border同时设置三个属性值，也可以分别设置border-width、border-color、border-style 
   还可以为单一一边设置属性 border-top、border—bottom等
   -->
   ```

3. 内边距是内容区与边框之间的距离，给元素设置内边距会改变盒子的大小，此时所设置背景颜色会延伸到内边距上，一个盒子可视区由内容区、内边距和边框构成，其属性设置和 border 一样
4. 外边距是盒子与盒子之间的距离，给盒子设置外边距不会影响盒子可视区的大小（影响盒子实际占用空间大小）但会改变盒子的位置，其属性设置和 border 一样，默认情况下当我们给一个盒子设置左或上外边距时移动的是盒子自身，而设置右或下边距时移动的是其他的盒子，margin 为负值时向反方向引动

### 行内元素盒模型

1. 行内元素不支持设置宽度和高度，其内容区大小就是内容所占大小

2. 给行内元素设置 padding 和 border 都会影响盒子的大小，但不会影响垂直方向上页面的布局

   ![](../../练习文件/h5-css3/c3/行内元素盒模型.jpg)

### 盒子水平布局

#### 过度约束

- 一个元素在其父元素中水平方向的位置由 margin、border、width、padding 共同决定

- 一个元素在其父元素中，水平布局**必须满足**以下等式：子元素的 margin（左右）+border（左右）+width+padding（左右）=父元素的内容区大小

  ```html
  .box1{width=800px; height=200px; border:5px soild red} .box2{width=200px; height=200px;}
  <div class="box1">
    <div class="box2"></div>
  </div>
  <!--
  如上当box2相加为0+0+0+200+0+0+0=200，不等于box1的800，这种情况称为过度约束，则等式会自动调整
    调整方式如下：
  	 当七个值中没有auto的情况下，会自动调整margin-right的值使等式成立
      
  七个属性之中margin-right/left和width可以设置为auto，width的默认值是auto
  	如果某个属性为auto，则会调整该属性的值以使等式成立
  -->
  ```

### 盒子垂直布局

- 在父元素不设置高度的情况下，其高度默认被子元素撑开

- 当子元素的大小超过父元素，则会产生溢出

  ```css
  .box1 {
    width: 200px;
    height: 200px;
    background-color: red;
  }
  .box2 {
    width: 100px;
    background-color: #bfa;
    height: 300px;
  }
  /* box1为父元素box2为子元素，此时会产生溢出现象*/
  ```

#### 溢出处理

使用 overflow 属性设置父元素如何处理溢出的子元素，其属性值有

- visible：默认值 不处理（可见）
- hidden：隐藏溢出的内容 （溢出部分裁剪）
- scroll：溢出部分以滚动条形式显示 双方向滚动条（溢出部分裁剪）
- auto：根据需要生成滚动条

### 外边距折叠

相邻两个元素在垂直方向会有外边距折叠问题

- 如果相邻的两个元素是兄弟关系，则外边距取较大值（两者都是正值），如果两个外边距一正一负，则取两者的和。兄弟间的外边距重叠问题是我们希望发生的，所以不需要处理

- 父子元素相邻外边距，子元素的外边距（上外边距）会传递给父元素，这时会影响到页面布局

  ![](../../练习文件/h5-css3/c3/外边距折叠.jpg)

#### 解决方案

针对上述父子元素外边距问题目前有两个方法：一种是不用外边距、一种是给父元素设置边框把两个元素外边距隔开，但就目前来讲都不是很好的处理方式

- 通过 before 伪元素标签来给父子元素设置一个边界

  ```css
  .box3::after {
    content: "";
    display: table;
  }
  ```

### 盒子大小 （2 月 14 日）

默认情况下由内 容区+边框+内边距三部分组成，但我们可以通过 box-sizing 属性来定义盒子尺寸的计算方式，其属性有

- content-box：宽度和高度用来设置内容区大小
- border-box：宽度和高度用来指定盒子大小

## 轮廓、阴影、圆角

### 轮廓

我们可以通过 outline 来为元素设置轮廓他的显示效果及用法和 border 一样，但它不会改变盒子大小，也不会影响其他元素的布局

- 可以通过 outline-offset 来给轮廓和边框之间设置距离，同样不占用空间

### 阴影

通过 box-shadow 来给元素设置阴影效果，不影响页面布局

语法 box-shadow：x y z w color ；

- 其中 x 表示水平方向偏移量（x 为正值向右移动）
- y 表示垂直方向偏移量（y 为正值向下移动）
- color 表示阴影颜色一般用 rgba 表示
- z 表示模糊度（z 越大越模糊）
- w 表示阴影尺寸

### 圆角

为元素设置圆角 ，可以分别为四个角单独设置也可以同时设置四个角，属性值为像素

- border-top-left/right-radius 为上左或上右设置圆角
- border-bottom-left/right-radius 为下左或下右设置圆角
- border-radius 当设置四个个属性值时表示四个角（左上、右上、左下、右下），三个值（左上、右上和左下、右下），两个值（左上右下、右上左下），当只有一个值且为 50%时该元素变成一个圆

## 设置默认样式

通常浏览器会给元素添加一些默认样式，这样会影响我们页面的布局，在开发同我们要先去除浏览器的默认样式

## 浮动 （2 月 15 日）

通过给元素设置浮动可以让它向其父元素的左侧或右侧移动，以达到元素水平排列，当给元素设置浮动以后，就不必遵循过度约束的等式，设置了浮动的元素会脱离文档流不再占用文档流中文位置

- float 可选值：none（默认）、left、right

- 浮动元素不会从父元素中移出，不会超过其浮动兄弟元素的高度

- 浮动元素不会盖住文档流元素的文字，文字会自动环绕在其周围

  ![](../../练习文件/h5-css3/c3/浮动.jpg)

- 脱离文档流的元素块不再独占一行，当没有指定宽度高度时，其高度和宽度被其子元素 / 内容撑开
- 脱离文档流的行内元素，其特点会和脱离文档流的块元素一样

### 高度塌陷

我们希望一个父元素会根据其子元素内容决定高度时，当子元素浮动后，他会脱离文档流，而其父元素没有高度的情况下，子元素无法撑起父元素，导致父元素高度丢失，从而改变页面中其他元素的布局，下面介绍其解决方法

#### BFC（块级格式化环境）

BFC 是 css 中的一个隐函属性，设置 bfc 的元素会变成一个独立的布局区域，它有以下特点：

1. 设置 bfc 的元素不会被浮动元素覆盖
2. 设置 bfc 的元素父元素，其子元素和它不会产生外边距重叠问题
3. 设置 bfc 的元素可以包含浮动元素
4. 开启 bfc 都是间接开启，都会存在一些副作用

```
开启bfc的方法：
 1.设置元素浮动，虽然解决了高度塌陷问题，但它就脱离文档流，也会改变页面布局  （不推荐）
 2.将元素设置为行内块元素 （不推荐）
 3.将元素的overflow设置一个非为visible的值，这种方式副作用最小
```

#### 浮动清除 clear

如果我们不希望某个元素受到浮动元素的影响而改变位置，我们可以通过 clear 属性来清除浮动元素对当前元素带来的影响，clear：both 清除影响影响大的一边，下面介绍如果通过 clear 解决高度塌陷问题

- clear 配合伪元素 after 在不影响页面结构的情况下完美解决

  ![](../../练习文件/h5-css3/c3/clear解决塌陷.jpg)

  由于 after 伪元素的内容默认是一个行内元素不会独占一行，所以要在里面设置 display 把其换成块级元素

## 定位 position（2 月 16 日）不会大量使用

定位是一种更为高级的页面布局手段，通过定位可以将元素摆放到页面的任意位置

### 包含块

- 正常情况下包含块就是离当前元素得最近的块级祖先元素

- 绝对定位元素的包含块就是离他最近的开启了定位的块级祖先元素，若它的所有祖先元素都没开启定位则相对于根元素进行定位

### 元素的层级

对于开启定位的元素我们可以通过 z-index 属性改变元素的层级，属性值为整数，数值越大层级越高，祖先元素层级再高也不会覆盖后代元素

### 相对定位

position：relative（相对定位-定位元素与定位位置的距离） 设置了相对定位的元素，需要设置偏移量（offset）改变元素位置

1. 偏移量分为 top、bottom、left、right
2. 相对定位就是定位元素参照于该元素在文档流的位置进行定位的
3. 设置相对定位的元素的层级会变高，但不会脱离文档流，不会改变元素的性质块还是块
4. 设置相对定位的元素改变位置后不会影响其他元素的布局

### 绝对定位

positon：absolute（绝对定位） 需要设置偏移量（offset）改变元素位置

1. 设置绝对定位的元素的会脱离文档流，会改元素的性质（行内变成块，块的宽高默认由内容决定）
2. 设置绝对定位的元素会提升层级
3. 绝对定位元素参照于该元素的包含块进行定位（其宽度也会参照包含块）
4. clip 属性剪裁绝对定位元素，其值是 shape 设置元素的形状。唯一合法的形状值是：rect (_top_, _right_, _bottom_, _left_)

#### 绝对定位水平布局

相比于正常水平布局多了两个值（left 和 right），9 个值相加等于包含块内容区的宽度，规则和之前过度约束中等式一样，只不过现在调整的是 right，可以设置 auto 的有 width、margin、left 和 right

- 设置 left 和 right 为 0，margin：0 auto 让元素水平方向居中（前提是设置了绝对定位的元素有宽度）

#### 绝对定位垂直布局

同上边水平布局相同，只是将 left 和 right 换成了 bottom 和 top，继承父亲的高度而不是内容撑起高度，与普通垂直布局不同必须满足等式

- 设置 bottom 和 top 为 0，margin：auto 0 让元素垂直方向居中（前提是设置了绝对定位的元素有高度）（注：在正常文档流中不可以）

### 固定定位

position：fixed（固定定位） 固定定位也是一种绝对定位，唯一不同的是固定定位参照于浏览器视口调整元素位置，固定定位的元素不会随网页滚动条滚动

### 粘滞定位

position：sticky（粘滞定位） 粘滞定位特点和相对定位基本一致，不同的是粘滞定位可以在元素到达某一位置时将其固定

## 网格布局

网格布局擅长于将一个页面划分为几个主要区域，以及定义这些区域的大小、位置、层次等关系（前提是 HTML 生成了这些区域），网格布局让我们能够按行或列来对齐元素，网格容器的子元素可以自己定位，以便它们像 CSS 定位的元素一样，真正的有重叠和层次。

## 图标字体 2 月 17 日

将图标设置为字体，这样方便我们操作图标的大小、颜色，而且图标字体对比图片不会失真、体积小，一般通过 font-face 引入图标字体

### font awesome

- 下载好字体库将 css 和 webfonts 两个文件夹放入项目目录中 注：这两个文件夹必须在同一目录下

- 将 css 文件夹下的 all.css 引入

#### 使用场景

1. 通过类名引入

```html
<i class="fas/fab xxx"></i>
<!--
通常用i标签标识图标  fas和fab固定格式不能变     xxx查询文档找到想要使用的图标类名   
-->
```

2. 找到要设置图标的元素通过 before 或 after，在 content 中设置编码和字体样式

```css
li:before{
    content:"xxx";   图标编码，通过font awesome文档查询
    font-familt:"Font Awesome 5 Free / Font Awesome 5 Brands" 这两种是免费的
}
/* 使用Font Awesome 5 Brands时需要加上 font-weight：900  */
```

3. 通过实体的方式来设置图标

```html
<span class="fas / fab">&#x;</span>
<!-- 在&#x后加上图标编码 -->
```

### Icon font 阿里图标字体库 (用户上传涉及版权)

Icon font 使用方式比较灵活可以当做字体引入，也可以下载图片格式使用，下面讲解使用方法

1. 将需要使用的图标加入购物车
2. 在购物车中添加自己的项目，让后把添加到购物车中的图标添加至项目
3. 图标管理->我的项目中找到图标，将图标下载至本地（这里边包含使用说明）
4. 将下载好的文件添加到个人项目中，引入 iconfont.css 文件

#### 使用场景

1. 通过类引入

   ```html
   <i class="iconfont  xxx"></i>
   <!-- 这里iconfont固定,xxx表示想要使用的图标类名（在使用说明里查询） -->
   ```

2. 通过实体引入

   ```html
   <i class="iconfont">&#x</i>
   <!-- 这里类名固定，让后在&#x后加上图标编码（在使用说明里查询） -->
   ```

## 过渡 transition

过渡就是从一个状态到另一种状态，过渡可以设置一个属性发生变化时的切换方式，过渡必须是从一个有效值向另一个有效值进行切换，其属性如下

- transition-property：设置对哪些 CSS 属性（height、width）执行过渡，各个属性用逗号隔开，也可以用 all（属性值）对所有属性执行过渡，只要是可以计算的、有数值的属性都可以执行过渡
- transition-duration：设置过渡效果执行时间（一般是以秒和毫秒作为单位，1s=1000ms）
- transition-timing-function：规定速度效果的速度曲线（过渡快慢），其属性值有
  1.  ease（默认值，慢速开始-先加速-在减速）、
  2.  linear（匀速运动）
  3.  ease-in（加速运动）
  4.  ease-out（减速运动）
  5.  cubic-bezier（）贝塞尔曲线表达
  6.  steps（）分步执行
- transition-delay：过渡效果的延迟（从什么时候开始执行过渡）
- 其中必须设置 property 和 duration

### 复合写法

过渡的复合写法没有顺序要求，但要注意如果同时设置延迟时间和过渡时间，则第一个时间代表过渡时间第二个时间代表延迟时间

## 动画 animation

### 关键帧

动画执行中各个阶段的变化，一秒钟内内容变化的个数就是帧数，css 中设置关键帧需要使用@keyframes，其具体设置方法如下

```css
@keyframes 关键帧名称 {
  from {
    /* from表示动画从哪开始,to也可以写为0% */
    margin-left: 0;
  }
  to {
    /* to表示从哪结束，from也可以写为100% */
    margin-left: 700px;
  }
}
```

### 动画设置

为想要添加动画的元素设置动画属性，动画常用属性如下

- animation-name：这里就是之前设置的关键帧的名称
- animation-duration：动漫执行时间跟过渡用法一致
- animation-delay：设置动画延迟
- animation-timing-function：同上过渡一致
- animation-iteration-count：动画执行次数，其属性值有 infinite（执行无限次）
- animation-direction：指定动画运行方向，其属性值有
  1.  normal（默认值，从 from 到 to 执行）
  2.  reserve（从 to 到 from 执行）
  3.  alternate（设置重复后先 from 到 to，再从 to 到 from）
  4.  alternate-reserve（设置重复后先从 to 到 from，再从 from 到 to）
- animation-play-state：设置动画执行状态，其属性有 running（运行）、paused（暂停）
- animation-fill-mode：设置动画填充模式，其属性值有
  1.  none（默认值，在没有设置动画执行次数时，执行一次后回到元素 初始位置）
  2.  forwards（在没有设置动画执行次数时，执行一次后停止在关键帧的结束位置）
  3.  backwards（动画延迟等待时，元素就处于 from 的状态）
  4.  both（结合 forwards 和 backwards）

### 复合写法

动画的复合写法也没有顺序要求，但要注意如果同时设置延迟时间和过渡时间，则第一个时间代表过渡时间第二个时间代表延迟时间

## 变形 transform （2 月 21 日）

改变元素的位置和形状，一个元素只能一个 transform，不会影响页面布局，其函数如下

- translateX()：平移（分 X、Y、Z 方向），其值可以是像素也可以是百分比（针对自己）
- rotate()：旋转可以使元素沿着 x、y 或 z 轴旋转指定角度，其值是 deg（度）正值顺时针、负值逆时针
- backface-visibility：设置元素是否显示背面
- scale()：对元素针对其本身大小进行缩放（可以是 X 轴可以是 Y 轴，Z 轴需要设置 3D 效果才能看到）
- skew(x，y)：倾斜 也可以分为 skewX（）和 skewY（）
- transform-style: 规定变形如何在 3D 空间中呈现被嵌套的元素，其属性值有 preserve-3d（子元素将保留其 3D 位置）、flat（默认值不保留）

transform-origin：设置变形的原点，其属性值有 center（默认），可以指定 X 和 Y 两个方向的距离来改变原点

### Z 轴平移

z 轴一般就是人眼和元素之间的距离，距离越大，元素离人越近，z 轴平移属于立体效果（近大远小），默认情况下网页不支持透视，如果想要看到 z 轴平移的效果，需要给设置网页的视距

```css
html {
  persprctive: 800px; /*设置网页的视距为800像素*/
}
```

## 弹性布局

可以使元素更加灵活，可以随着页面的大小而改变，减少浮动布局存在的问题

弹性容器和弹性元素有各自要设置的属性

### 弹性容器

要想使用弹性布局必须先将一个元素设置为弹性容器，有两种方式一种是设置 display 为 flex（块级弹性容器），另一种是设置 display 为 inline-flex（行内弹性容器），其属性如下

- flex-direction：指定弹性容器中弹性元素的排列方式（决定主轴），其属性值可以是 column（纵向排列从上向下）、row（默认值，水平排列从左向右）、row-reverse（水平排列从右向左）
- flex-wrap：设置元素是否在弹性容器中自动换行，其属性值可以是
  1.  nowrap（默认值，不换行）
  2.  wrap（沿着侧轴的方向自动换行）
  3.  wrap-reverse（沿着侧轴的反方向换行）
- flex-flow：可以同时设置 felx-direction 和 flex-wrap 两个属性
- justify-content：设置**主轴**上有多余可用空间时元素如何排列，其属性值有
  1.  flex-start（沿主轴起始方向排列）
  2.  flex-end（沿主轴终止方向排列）
  3.  center（居中排列，空白部分均匀分配在两边）
  4.  space-around（将空白分配到每个元素两侧）
  5.  space-evenly（均匀分配空白）
  6.  space-between（将空白分均匀分配在弹性元素之间）
- align-items：设置**侧轴**上元素间如何排列，其属性值可以是
  1.  stretch（默认值，将一行元素的高度设置为相同的值）
  2.  flex-start（沿侧轴起始方向对其）
  3.  flex-end（沿侧轴终止方向对齐）
  4.  center（居中对齐）
  5.  baseline（基线对齐）
- align-content：设置**侧轴**上有多余可用空间时元素如何排列（设置对象是所有行，且只有在多行弹性盒子容器中才生效），其属性值跟 justify-content 一致

**主轴**：弹性元素的排列方向成为主轴

**侧轴**：与主轴垂直的方向称为侧轴

### 弹性元素

弹性容器的直接子元素就是弹性元素（弹性项），一个元素可以同时是弹性容器和弹性元素，其属性如下

- flex-grow：用来指定弹性元素的伸展系数（当父元素有多余空间时，子元素如何伸展），其属性值可以是数字（默认 0 表示不伸展，1 表示平均分配，值越大分配的空间越多）
- flex-shrink：用来指定弹性元素的收缩系数（当父元素的空间不足以容纳所有子元素时，子元素如何收缩），其属性值可以是数字（默认 1 表示等比收缩，0 表示不收缩），缩减大小是根据缩减系数和元素大小来计算的
- flex-basis：指定在分配多余空间之前，元素在主轴占据的基础长度（如果主轴是横向的则该长度代表元素的 width，如果主轴是纵向的则代表元素的 height），其默认值是 auto（参考元素自身的高度或宽度）
- flex：前面三个元素的简写，按 grow、shrink、basis 的顺序写，其属性值有—默认值是 initial（代表 0,1，auto），auto（1,1，auto）
- align-self：用来覆盖当前元素上的 align-items
- order： 用来决定弹性元素的排列顺序，数值越小，排列越靠前，默认为 0

## less （css 预处理）

Less 是 CSS 的增强版，增加了许多新特性，less 可以使我们编写更少的代码、实现更强大的样式

### css 的不足

css 中很多变量（——color）和函数兼容性不好

### less 的使用

less 的语法和 css 大体一致，浏览器无法直接 less 代码，必须先将 less 转换为 css（Easy Less 插件）

### 变量

```less
@name:red;  //@开头后面加变量名来声明一个变量 ，冒号后面跟变量值
@b:box1;
.box{
    color:@name;  //使用变量
}



.@{b}{     // 当变量以类型出现时要加大括号
   color:@name;
    background-image:url("@{b}/1.png")   //以图片地址出现时的格式
}


//使用场景
.box1{
    width:100px;
    height:$width;  //这样引用后height值为100px
}
```

### 父元素和扩展

```less
.box1 {
  .box2 {
    color: yellow;
  }
  > .box3 {
    color: red; //解析后表示box1的子元素box3
  }
  &: hover // & 就表示外层父元素 ;
}

.p1() {
  //当给选择器后边加括号，解析less时css中不会显示.p1的相关属性，实际上是创建了一个mixins，专门给别的选择器复制使用
  width: 100px;
  height: 100px;
}
.p2:extend(.p1) {
  //p2 在p1的基础上扩展（选择器分组 ）
  color: aquamarine;
}
.p3 {
  .p1; //直接对指定的样式引用，相对于对复制了p1的样式
}
```

### 混合函数

混合函数内可以直接定义变量

```less
.test(@w:100px,@h) {
  //定义一个带参函数，可以指定默认值
  width: @q;
  height: @h;
  color: red;
}
div {
  .text(200px,300px); //调用函数并传参
}
```

#### 其他用法

在 less 中所有的数值可以直接参与算术运算

```less
.b1 {
  width: 100px+100px;
  height: 100px;
  border: 1px solid black;
}
```

- 在当前 less 文件引入其他 less 文件 import “ xxx.less”; （整合）这样可以模块化开发，创建多个 lees 文件一个模块分一个 less 文件（动画模块、定义变量、布局），这样方便维护哪里出问题去哪个文件修改

## 自定义类

1. 定义一个.clearfix 类可以同时解决高度塌陷和外边距重叠问题

```css
.clearfix::after,
.clearfix::before {
  content: "";
  display: table;
  clear: both;
}
```

## 元素居中

- 水平居中

  1.  设置 margin 为 auto，可让子元素在父元素中水平居中显示，前提是元素设置了宽度（块级元素水平居中）
  2.  行内元素水平居中给父亲设置 text-align： center
  3.  绝对定位，前提是元素有宽度
  4.  弹性布局，设置父元素 justify-content 为 center

- 垂直居中

  1.  绝对定位，前提是元素有高度
  2.  弹性布局，设置父元素 align-items 为 center
  3.  给一个父元素设置 display：table，会将元素设置为单元格，可以用 vertical-align 控制其中元素垂直方向的位置（了解）
  4.  相对定位+translate

- 想让元素内文字垂直居中，给元素设置 line-heiht 值为其自身的 height 值

- 配合 padding 可让元素水平垂直居中

- 字体大小不同的文本垂直对齐 vertical-align: middle

- 绝对定位设置 left、right、bottom 和 top 都为 0，margin：auto；元素水平垂直居中（前提是该元素有宽度和高度）

- 使用绝对定位配合变形，transform：translate（-50%，-50%），left 和 top 设置为 50%，这种方式既不用设置元素宽高，又不用在意内容多少，都可让元素居中

- 设置父元素 display 为 flex，justify-content 为 center，align-items 为 center，元素居中

- 设置父元素 display 为 flex，子元素 margin 为 auto，元素居中

## 隐藏元素

- 给元素设置 display：none，不占据任何空间
- 给元素设置 visibility：
  - 其属性有 visible（默认值）可见、hidden 隐藏元素（元素依然占用空间）

## 移动端适配

默认情况下，移动端的网页都会将视口设置为 980 像素（css 像素），以确保 pc 端网页可以在移动端正常访问 ，编写移动端页面时，必须要确保有一个合理的像素比

- 可以通过查看视口的大小，来观察 css 像素和物理像素的比值
  - 通过 meta 标签来设置视口大小

不同设备的视口和像素比不同，所以同样的宽度在不同的设备下显示不同，所以在移动端开发时，就能不使用 px 进行布局

### vw

vw 表示视口的宽度，100vw 等于一个视口的宽度，vw 这个单位永远相对于视口宽度进行计算

### vw 适配

代码如下

```css
/*  
  我们已知100vw等于一个视口的宽度，通常移动端设计图的的宽度为750px，100vw=750px那么 0.13333vw=1px ，浏览器能设置的最小字体大小为12px，如果比12小默认就是12px 
*/
html {
  font-size: 5.3333px;
}
/*此时相当于font-size为40px  
这样我们开发移动端页面时，可以使用为单位rem来计算元素大小，比如设计图中一个元素宽度为35px，我们在编写页面时的宽度就是35/40个rem
*/
```

## 响应式布局

网页可以根部不同的设备或窗口大小呈现出不同的效果，响应式布局一个网页可以适用于所有设备，响应式布局的关键是媒体查询

### 媒体查询 css3 特性

可以为不同的设备或设备的不同状态分别设置样式

```css
/*媒体查询的使用*/
style {
  @media 查询规则 （） and （） {
  }
}
```

- 媒体查询的类型： 可以使用， 选择多个设备 他们之间是或的关系

  1.  all 所有设备
  2.  print 打印设备
  3.  screen 屏幕
  4.  speech 屏幕阅读器

- 媒体特性： 可以用 and 链接多个条件，他们之间是与的关系
  1.  min-width（视口大于指定宽度时生效）和 max-width（视口小于指定宽度时生效）

### 断点

断点就是样式切换的分界点，也就是网页在这个点时会发生变化，一般常用断点有：

- 当视口小于 768（max-width：768px） 超小屏幕
- 视口大于 768（min-width：768px） 小屏幕
- 视口大于 992 （min-width：992px） 中型屏幕
- 视口大于 1200 （min-width：1200px） 大屏幕

## bootstrap

使用时需要在项目根目录中创建 bootstrap 文件夹，引入 bootstrap.css 和 js 等样式文件，其结构请参考[官网](https://v3.bootcss.com/getting-started/)

### 布局容器

- bootstrap 中已经内置好了一个容器他的**类名是 container**，这个类是就是响应式布局中媒体查询的一些常用断点

- 还有就是**container-fluid**类，它适用于移动端页面开发

### 网格布局

将页面布局换分为等宽的列，通过定义列数来模块化页面布局

## 案例

#### 1.三角实现

```html
<html>
  <style>
    div {
      width: 0;
      height: 0;
      border: 50px solid;
      border-color: red pink black green;
    }
  </style>
  <body>
    <div class="tooltip"></div>
  </body>
</html>
```

![](../../练习文件/h5-css3/c3/css三角.jpg)

还可以通过边框和旋转实现

#### 2.开启固定定位元素固定

由于开启绝对定位的元素是相对于视口进行定位的，当视口的大小改变定位元素的位置也会发生改变

```
绝对定位/固定定位在水平布局上满足以下等式：
   left + margin-left + boder-left + padding-left + left + padding-right + border-right + margin-right + right = 视口的宽度（不固定），当left/right未设置时默认auto
   我们可以通过设置left/right为百分比的值来先让元素固定在屏幕的某一位置，再通过修改margin-right/left来确保元素定位
```

## 网页图标

通过 link 标签 rel 属性的属性值为 icon，一般该图标放在网站根目录下，命名为 favicon.icon

```html
<link rel="icon" href="" />
```

​

## 浏览器资源加载

当我们在代码中中引入图片、视频等外部资源，当我们首次访问页面时，需要浏览器单独发送请求加载，浏览器的资源加载是按需加载的（用就加载，不用不加载）
