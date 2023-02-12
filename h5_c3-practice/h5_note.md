# H5个人笔记  2月8日



通常情况下软件一般由服务器和客户端组成

```bash
客户端展示页面，供客户使用
服务器为客户端(软件)提供服务，处理业务逻辑
```

浏览器就是为了把网页渲染出来。![w3c](C:\Users\LENOVO\Desktop\练习文件\h5-css3\w3c.jpg)

### 网页的结构

根据W3C标准，一个网页主要由结构、表现、行为组成

### 字符编码

####  编码

- 当一段文字存储到内存中时，将字符转换为二进制码的过程

#### 解码

- 将二进制码转换为字符的过程

#### 字符集（charset）

- 编码和解码所采用的规则，当编码和解码所采用的字符集不同会产生乱码问题

#### 常见字符集

ASCII、GB2312、GBK、UTF-8

## HTML5

```ba
	一个HTML页面最基本的三个标签为html、head和body，html中的标签一般都成对出现（除了img、input等自结束标签）
```

h5的文档声明

```bash
<!doctype html>  #放在html标签之前 来告诉浏览器当前使用的是h5
```

### head、body

head标签的内容不会出现在网页中，用户所能看见的内容都在body中

### 注释

用<!- -   - ->来扩起想要注释的内容，被注释的内容不会再网页中显示，注释不能嵌套 

### 绝对路径和相对路径

#### 相对路径

相对路径就是目标文件与当前文件的相对关系

图例    

![](C:\Users\LENOVO\Desktop\练习文件\h5-css3/相对路径2.jpg)

![](C:\Users\LENOVO\Desktop\练习文件\h5-css3/相对路径1.jpg)

```bash
./表示当前路径   ../表示当前文件目录的上一级目录 
以1为中心 那么相对于1来说 2和他在同一目录下  通过 ./2.html 找到
以a为中心 那么1相对于a来说 1和a不在同一目录下 通过../1.html 找到
```

#### 绝对路径

绝对路径就是该文件在电脑硬盘存在的位置

###  常用标签（元素）及属性

```bash
属性应在标签的开始部分设置，属性以键值对的形式出现，设置属性时要有空格与标签和其他属性区分开，不同属性有各自的意义应根据文档规定编写，属性值要用一对引号引起来

标签之前可以互相嵌套
	
	
<font color="red" font="12px">aaaa</font> #此行代码可以将aaa以红色显示在网页中
```

#### meta 2月9日

- 不需要页面显示，所以写在head中
- 通过meta标签设置网页的字符集
- meta用来设置网页的***元数据***

```bash
<meta charset="utf-8"> #设置网页字符集为utf-8
<meta name="keywords"  content="xxxx,xxx,xxx">  #指定元数据的名称  keywords表示网站的关键字供浏览器搜引擎来找到该网站,content指定数据的内容 用逗号隔开
<meta http-equiv="refresh" content="s,rul"> #将网页经过s秒重定向到url这个地址
```

#### title

title中的内容会显示在浏览器标题栏，也会作为搜索结果的链接显示该内容

#### p和pre

p为块级元素独占一行，不保留源代码中p标签里内容的格式。

pre同样为块级元素，但pre会保留源代码中pre标签里内容的格式。

#### 计算机输出标签

- code：该标签用于表示计算机源代码，在该标签内的文本将用等宽、类似电传打字机样式的字体显示出来
- tt：作用同上，h5不支持
- var：示变量的名称，或者由用户提供的值，常与code标签和pre标签一起使用，用来显示计算机编程代码范例及类似方面的特定元素，用 var标签标记的文本通常显示为斜体。

#### 不常用标签

- bdo 标签可覆盖默认的文本方向

#### 列表（标签都为块级元素）

列表一共分成有序列表、无序列表和自定义列表，列表之间可以互相嵌套

##### 无序列表

使用ul标签来创建有序列表，li来表示列表项

```html
<ul>
    <li>行为</li>
    <li>结构</li>
    <li>表现</li>
</ul>
```

##### 有序列表

使用ol标签来创建有序列表，li来表示列表项

 ```html
 <ol>
     <li>行为</li>
     <li>结构</li>
     <li>表现</li>
 </ol>
 ```

##### 定义列表

使用dl标签来创建定义列表，dt来表示定义内容，dd对内容进行解释，一个dt可以用多个dd来解释

```html
<dl>
    <dt>结构</dt>
    <dd>用html编写</dd>
    <dt>表现</dt>
    <dd>用css编写</dd>
    <dt>行为</dt>
    <dd>用js编写</dd>
 </dl>
```

#### 超链接

使用a标签实现，主要完成页面跳转，a标签可以嵌套任何除了自己的元素

```BASH
 <a href="xxxxxx" target="">sss</a>
 #其中 href为要跳转的链接地址    
 #target打开该链接的方式，其常见的为两个值为_self和_blank，默认为_self在当前页面打开,_blank为在新页面打开
 # 若href的值为javascript:;时，点击此链接不会发生任何改变，单纯作为一个占位符来标识这是一个超链接
```

##### 描点链接

a标签还可以实现本页面跳转,通过给想要跳转的位置的标签一个id属性(唯一标识)

```bash
<a href="#bottm" >去底部</a>
<a href="#" id="bottom">回到顶部</a>
```

##### 邮箱链接

```html
<a href="mailto:xxxx@xxx.com?cc=756237734@qq.com
  &bcc=378657961@qq.com
  &subject=主题是学习mailto
  &body=这里是有%0d%0a邮件内容">邮箱链接</a>
 
<!--
 mailto标签代表发邮件到xxxx@xxx.com这个里面
 cc为抄送的意思：比如发给第张三后，还想发给李四，并且相互之间都知道发给了哪些人
 bcc为密送的意思：也就是我发给了张三，还想发给李四，并且不想让张三知道我发给了李四，就可以用密送
 body代表邮件的内容，如果想在BODY进行换行，只需要在行与行之间加入"%0d%0a"，使用 %20 来替换单词之间的空格
 如果要使用mailto同时实现多个功能的话，第一个功能必须以“?”开头，后面的每一个功能都以 “&”开头
-->
```



#### img（行内块元素）

用于向当前页面引入一个外部图片

```bash
<igm src=""  alt="" height="" width="">
#src代表图片路径  
#alt代表图片无法加载时的提示信息 其次搜索引擎会根据alt中的内容来识别图片
#heigh和width分别设置图片的高度和宽度，如果只设置一个另一个会等比缩放
```

##### 常见图片格式和特点

- jpg：支持颜色丰富，不支持透明效果和动图   一般用来显示照片
- gif：颜色较少，支持简单透明，支持动图      
- png：颜色多，支持复杂透明，不支持动
- webp：兼容差

#### 表格

表格主要用于展示数据

```bash
<table>
    <tr>
      <td>1</td>
      <td>2</td>
      <td>3</td>
    </tr>
</table>
# table用于定义表格，tr代表行，td代表列
# th代表表格的表头部分，通常表头代表表格第一行内容
```

##### 表格常用属性

- align：有left、right、center三个值，分别让表格在左右中显示

- border：设置表框粗细

- cellpadding：规定单元格边框与其内容的距离

- cellsapcing：规定单元格之间的距离

##### 单元格合并

跨行合并 rowspan

```bash
<tr>
      <td rowspan="2">4</td>
      <td>5</td>
      <td>6</td>
</tr>
<tr>
	  <td>7</td>
      <td>8</td>
      <td>9</td>
</tr>
#rowspan=2代表把两个合并为1个 删除多余行
```

跨列合并 colspan

```bash
<tr>
      <th colspan="2">1</th>
      <th>2</th>
      <th>3</th>
</tr>
#colspan=2代表把两个合并为1个 删除多余列
```

#### 表单

表单用来收集输入或者点击信息

一个表单由表单域、表单元素、提示信息三个部分组成

##### form

用来定义一个表单域，下面介绍form常用属性

- aciton：用于指定表单数据的提交地址

- method：用于设置表单数据提交方式，一般有get和post

- name：指定名单的名称

###### input与其属性

```bash
语法：
<form action="#"  method="" name="">
 <input type="xx" name="xx" value="" checked="" maxlength="" placeholder="">
</form>
```

- type：指定类型常用属性值有button、checkbox(复选框)、file、hidden(定义隐藏输入字段)、image、radio(单选按钮)、password、text、submit(提交数据按钮)

- name：可以设定表单元素的名字，以供后期提交数据来区分

- value：规定input元素的值

- checked：规定此 input 元素首次加载时被选中

- placeholder：显示提示信息，用于帮助用户填写输入字段的提示

	1. radio、checkbox

		```bash
		性别：男<input type="radio"> 女<input type="radio"> 
		爱好：睡觉<input type="checkbox" name="hobby"> 吃饭<input type="checkbox" name="hobby">
		#只有当所有ridio标签设定相同的名字才可以实现多选一
		#checkbox同rodio一样，通常设置相同的名字
		```

###### label标签

- <label> 标签为 input 元素定义标注，label通过id绑定一个表单元素，当点击label标签内的文本时，浏览器就会自动将焦点选择对应的表单元素，用来增加用户体验

```bash
性别：<label for="male">男</label><input type="radio" name="sex" id="male">
     <label for="famale">女</label><input type="radio" name="sex" id="famale">
#label标签的for属性与input的id对应      
```

#### select下拉列表

```bash
<select>
      <option>1</option>
      <option selectd="selected">2</option>
</select>
# selected表示设置其为默认选项
```

#### textarea文本域

该标签定义一个多行输入的文本

### 实体

如果我们需要在网页中书写特殊符号，则需要使用html中的实体（转义字符）

简而言之实体就是用来表示特殊符号的

```bash
语法： &实体的名字;    #例如空格 &nbsp;
&gt;   #大于号
&lt;   #小于号 
&copy;  #版权符号
```

详细实体字符请参考 [这里](https://www.runoob.com/html/html-entities.html "https://www.runoob.com/html/html-entities.html")

### 行内元素和块元素

块元素独占一行，用于对网页进行布局，常用块级元素为div，div没有任何语义

行内元素不会独占一行，一般用来包裹文字，常用块级元素为span，span没有任何语义

p标签中不能放任何块元素

### 语义化标签

- 在编写页面时，html专门用来负责网页结构的编写，所以在使用html标签是，应该关注标签的语义，而不是他的样式

#### hgruop

- 此标签专门用来为标题标签分组，将同一组相关标题放入此标签

#### 标题标签

- h1-h6一共有6个标题标签，其重要性逐级递减，一般一个页面只有一个h1标签

#### 引用标签

- blockquote块元素表示长引用，q行内元素表示短引用（会加双引号，但不关注）

#### h5新增

- header：网页头部      
- main：网页主题部分（一个页面中只有一个）   
- footer：网页的底部    
- nav：网页的导航  
-  aside：侧边栏     
- article：独立文档
- section：当其他标签无法表示时使用

### 音视频   2月10日

#### audio 音频标签

向页面中引入音频，默认不允许用户自己控制播放和停止

```bash
<audio src="xxxx" controls autoplay loop></audio>
#src指定要引入音频的地址  controls表示允许用户控制播放和暂停  autoplay打开页面音频自动播放，一般不适用    loop音频循环
<audio>
	<source scr="">
	<embed src="" >
</audio>
#除了使用src来指定音频路径外   还可以使用source来指定，此外source可以引入多个音频，embed对不支持audio标签的浏览器版本显示
```

#### video 视频标签

向页面中引入视频，默认不允许用户自己控制播放和停止

```bash
#用法与audio相同
```



 

