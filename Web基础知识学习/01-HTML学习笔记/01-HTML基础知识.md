@[toc](HTML基础知识)

# 网页基础知识
## 浏览器
&emsp;&emsp;网页主要由文字、图像和超链接等元素构成，除了这些元素网页中还可以包含音频、视频以及Flash等。而浏览器是网页运行的平台，常用的浏览器有IE、火狐（Firefox）、谷歌（Chrome）、Safari和Opera等。

### 浏览器内核
&emsp;&emsp;浏览器内核又可以分成两部分：

+ 渲染引擎(layout engineer或者Rendering Engine)：主要负责取得网页的内容（HTML、XML、图像等等）、整理讯息（例如加入 CSS 等）以及计算网页的显示方式，然后会输出至显示器或打印机。浏览器的内核的不同对于网页的语法解释会有不同，所以渲染的效果也不相同。

+ JS引擎：解析Javascript语言，执行javascript语言来实现网页的动态效果。

&emsp;&emsp;最开始渲染引擎和JS引擎并没有区分的很明确，后来JS引擎越来越独立，内核就倾向于只指渲染引擎。内核的种类很多，但是常见的浏览器内核可以分这四种：

+ Trident：IE内核，Window 10发布后，IE将其内置浏览器命名为Edge，Edge 最显著的特点就是新内核EdgeHTML

+ Gecko：firefox内核，Gecko的特点是代码完全公开，因此其可开发程度很高

+ webkit：Safari内核，是苹果公司开发的浏览器，现在很多人错误地把 webkit叫做chrome内核（即使 chrome内核已经是 blink 了）

+ Chromium/Bink：chrome内核，在Chromium项目中研发Blink渲染引擎（即浏览器核心），内置于Chrome浏览器之中，Blink其实是WebKit的分支，大部分国产浏览器最新版都采用Blink内核。

> *__注意：移动端的浏览器内核主要说的是系统内置浏览器的内核。目前移动设备浏览器上常用的内核有Webkit，Blink，Trident，Gecko等，其中iPhone和iPad等苹果iOS平台主要是WebKit，Android 4.4之前的Android系统浏览器内核是WebKit，Android4.4系统浏览器切换到了Chromium，内核是Webkit的分支Blink，Windows Phone 8系统浏览器内核是Trident。__*

## Web标准
&emsp;&emsp;浏览器的内核不同，它们工作原理、解析方式肯定也不同，显示就会有差别。Web标准的有下面几个好处：

1. 让Web的发展前景更广阔
2. 内容能被更广泛的设备访问
3. 更容易被搜寻引擎搜索
4. 降低网站流量费用
5. 使网站更易于维护
6. 提高页面浏览速度

### Web标准的构成

&emsp;&emsp;Web标准不是某一个标准，而是由W3C和其他标准化组织制定的一系列标准的集合，主要包括：

+ 结构标准：结构用于对网页元素进行整理和分类，主要包括XML和XHTML两个部分。

+ 样式标准：表现用于设置网页元素的版式、颜色、大小等外观样式，主要指的是CSS。

+ 行为标准：行为是指网页模型的定义及交互的编写，主要包括DOM和ECMAScript两个部分

> *__理想状态我们的源码：.HTML、.css、.js__*

# 初识HTML
&emsp;&emsp;HTML（英文Hyper Text Markup Language的缩写）中文译为"超文本标签语言"，主要是通过HTML标签对网页中的文本、图片、声音等内容进行描述。

## HTML的基本框架
&emsp;&emsp;HTML的基本框架如下：

```html
<!DOCTYPE html>
<html>
<head>
    <title></title>
</head>
<body>

</body>
</html>
```

1. html标签：所有HTML标签的一个根节点。
2. head标签：用于存放title、meta、base、style、script、link标签。（*__注意：在head标签中我们必须要设置的标签是title__*）
3. title标签：让页面拥有一个属于自己的标题。
4. body标签：页面在的主体部分，用于存放所有的HTML标签。

## HTML标签
&emsp;&emsp;在HTML页面中，带有"< >"符号的元素被称为HTML标签，如上面提到的&lt;html&gt;、&lt;head&gt;、&lt;body&gt;都是HTML标签。所谓标签就是放在"< >"标签符中表示某个功能的编码命令，也称为HTML标签或HTML元素。

### HTML标签的分类

1. 双标签

```html
<标签名> 内容 </标签名>
```

&emsp;&emsp;该语法中"<标签名>"表示该标签的作用开始，一般称为"开始标签（start tag）"，"</标签名>"表示该标签的作用结束，一般称为"结束标签（end tag）"，和开始标签相比，结束标签只是在前面加了一个关闭符"/"。比如：

```html
<p>我是文字</p>
```

2. 单标签

```html
<标签名 />
```

&emsp;&emsp;单标签也称空标签，是指用一个标签符号即可完整地描述某个功能的标签。比如：

```html
<br />
```

### HTML标签关系
&emsp;&emsp;标签的相互关系就分为两种：

1. 嵌套关系

```html
<head>
  <title> </title>  
</head>
```

2. 并列关系

```html
<head></head>
<body></body>
```

> *__如果两个标签之间的关系是嵌套关系，子元素最好缩进一个tab键的身位。如果是并列关系，最好上下对齐。__*

### HTML标签的语义化

&emsp;&emsp;所谓标签语义化，就是指标签的含义。标签的语义化有以下好处：

1. 方便代码的阅读和维护
2. 同时让浏览器或是网络爬虫可以很好地解析，从而更好分析其中的内容
3. 使用语义化标签会具有更好地搜索引擎优化

## 文档类型<!DOCTYPE>

```html
<!DOCTYPE html>
```

&emsp;&emsp;这句话就是告诉我们使用的是 *HTML5* 的版本，html有很多版本，那我们应该告诉用户和浏览器我们使用的版本号。

&emsp;&emsp; *__&lt;!DOCTYPE&gt;__* 标签位于文档的最前面，用于向浏览器说明当前文档使用哪种HTML或XHTML标准规范，必需在开头处使用 *__&lt;!DOCTYPE&gt;__* 标签为所有的XHTML文档指定XHTML版本和类型，只有这样浏览器才能按指定的文档类型进行解析。

## 字符集

```html
<meta charset="UTF-8">
```

&emsp;&emsp;utf-8是目前最常用的字符集编码方式，常用的字符集编码方式还有gbk和gb2312：

+ gb2312：简单中文，包括6763个汉字
+ BIG5：繁体中文，港澳台等用
+ GBK：包含全部中文字符，是GB2312的扩展，加入对繁体字的支持，兼容GB2312
+ UTF-8：包含全世界所有国家需要用到的字符

> *__以后我们统统使用UTF-8字符集, 这样就避免出现字符集不统一而引起乱码的情况了。__*