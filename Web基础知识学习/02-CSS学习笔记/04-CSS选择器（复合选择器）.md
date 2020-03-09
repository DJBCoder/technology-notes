@[toc](复合选择器)

&emsp;&emsp;复合选择器是由两个或多个基础选择器，通过不同的方式组合而成的，目的是为了可以选择更准确更精细的目标元素标签。

# 交集选择器
&emsp;&emsp;交集选择器由两个选择器构成，其中第一个为标签选择器，第二个为class选择器，两个选择器之间不能有空格，如：h3.special。

![交集选择器](./images/jiao.png)

&emsp;&emsp;交集选择器是并且的意思(即...又...)，比如：*__p.one__* 选择的是类名为one的p标签。

> 用的相对来说比较少，不太建议使用。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        p.red{
            color: red;
        }
    </style>
</head>
<body>
    <p>这里是一段文本，样式没有设置</p>
    <p class="red">这里是一段文本，字体是红色</p>
</body>
</html>
```

# 并集选择器
&emsp;&emsp;并集选择器（CSS选择器分组）是各个选择器通过 *__逗号__* 连接而成的，任何形式的选择器（包括标签选择器、class类选择器id选择器等）都可以作为并集选择器的一部分。如果某些选择器定义的样式完全相同或部分相同，就可以利用并集选择器为它们定义相同的CSS样式：

![并集选择器](./images/bing.png)

&emsp;&emsp;并集选择器是和的意思，就是说只要逗号隔开的，所有选择器都会执行后面样式。比如：

```css
.one,
p,
#test {
    color: #F00;
}  
```

&emsp;&emsp;表示所有class为one的标签、p标签和id为test的标签，这三个选择器对应的所有的标签都会执行颜色为红色。通常用于集体声明。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        p,
        .s,
        #app {
            color: red;
        }
    </style>
</head>
<body>
    <p>这里是一段文本</p>
    <span class="s">这里是span文本</span>
    <div id="app">这里是一段div文本</div>
</body>
</html>
```

# 后代选择器
&emsp;&emsp;后代选择器又称为包含选择器，用来选择元素或元素组的后代，其写法就是把外层标签写在前面，内层标签写在后面，中间用空格分隔。当标签发生嵌套时，内层标签就成为外层标签的后代：

![后代选择器](./images/hou.png)

&emsp;&emsp;子孙后代都可以这么选择，或者说它能选择任何包含在内的标签。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        #app span {
            color: red;
        }
    </style>
</head>
<body>
    <div id="app">
        <span>这里是子元素的文本</span>
        <div>
            <span>这是孙子元素的文本</span>
        </div>
    </div>
</body>
</html>
```

# 子元素选择器
&emsp;&emsp;子元素选择器只能选择作为某元素子元素的元素。其写法就是把父级标签写在前面，子级标签写在后面，中间跟一个 &gt; 进行连接，注意，符号左右两侧各保留一个空格：

![子元素选择器](./images/zi1.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        #app > span {
            color: red;
        }
    </style>
</head>
<body>
    <div id="app">
        <span>这里是子元素的文本</span>
        <div>
            <span>这是孙子元素的文本</span>
        </div>
    </div>
</body>
</html>
```

# 属性选择器
&emsp;&emsp;选取标签带有某些特殊属性的选择器我们成为属性选择器：

选择器| 含义
-|-
E[attr]|存在attr属性即可
E[attr=val] | 属性值完全等于val
E[attr*=val] | 属性值里包含val字符并且在任意位置
E[attr^=val] | 属性值里包含val字符并且在"开始位置"
E[attr$=val] | 属性值里包含val字符并且在"结束位置"

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        div[attr] {
            color: red;
        }
        div[attr*=to] {
            color: orange;
        }
        div[attr^=to] {
            color: palegreen;
        }
        div[attr$=fo] {
            color: rebeccapurple;
        }
        div[attr=koo]{
            color: royalblue;
        }
    </style>
</head>
<body>
    <div attr="ao">这里是一段文本</div>
    <div attr="oto">这里是一段文本</div>
    <div attr="too">这里是一段文本</div>
    <div attr="ofo">这里是一段文本</div>
    <div attr="koo">这里是一段文本</div>
</body>
</html>
```

# 伪元素选择器（CSS3)

1. E::first-letter：文本的第一个单词或字（如中文、日文、韩文等）

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        div::first-letter {
            color: red;
            font-size: 20px;
        }
    </style>
</head>
<body>
    <div>这里是一段文本</div>
</body>
</html>
```

2. E::first-line：文本第一行

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        div::first-line {
            color: red;
            font-size: 20px;
        }
    </style>
</head>
<body>
    <div>这里是一段文本这里是一段文本这里是一段文本这里是一段文本
        这里是一段文本这里是一段文本这里是一段文本这里是一段文本
        这里是一段文本这里是一段文本这里是一段文本
        这里是一段文本这里是一段文本
    </div>
</body>
</html>
```

3. E::selection：可改变选中文本的样式

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        div::selection {
            color: red;
        }
    </style>
</head>
<body>
    <div>这里是一段文本这里是一段文本这里是一段文本这里是一段文本
        这里是一段文本这里是一段文本这里是一段文本这里是一段文本
        这里是一段文本这里是一段文本这里是一段文本
        这里是一段文本这里是一段文本
    </div>
</body>
</html>
```

4. E::before和E::after

&emsp;&emsp;在E元素内部的开始位置和结束位创建一个元素，该元素为行内元素，且必须要结合content属性使用。

```css
div::befor {
  content:"开始";
}
div::after {
  content:"结束";
}
```

> E:after、E:before 在旧版本里是伪元素，CSS3的规范里“:”用来表示伪类，“::”用来表示伪元素，但是在高版本浏览器下E:after、E:before会被自动识别为E::after、E::before，这样做的目的是用来做兼容处理。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        div::before {
            content: "开头";
        }
        div::after {
            content: "结尾";
        }
    </style>
</head>
<body>
    <div>这里是一段文本</div>
</body>
</html>
```

# CSS书写规范
## 空格规范

1. 选择器 与 { 之间必须包含空格，如：.selector { }
2. 属性名与之后的:之间不允许包含空格，:与属性值之间必须包含空格，如：font-size: 12px;

## 选择器规范
&emsp;&emsp;当一个rule包含多个selector时，每个选择器声明必须独占一行，示例：

```css
/* good */
.post,
.page,
.comment {
    line-height: 1.5;
}

/* bad */
.post, .page, .comment {
    line-height: 1.5;
}
```

&emsp;&emsp;建议选择器的嵌套层级应不大于3级，位置靠后的限定条件应尽可能精确，示例：

```css
/* good */
#username input {}
.comment .avatar {}

/* bad */
.page .header .login #username input {}
.comment div * {}
```

## 属性规范

&emsp;&emsp;属性定义必须另起一行，示例：

```css
/* good */
.selector {
    margin: 0;
    padding: 0;
}

/* bad */
.selector { margin: 0; padding: 0; }
```

&emsp;&emsp;属性定义后必须以分号结尾，示例：

```css
/* good */
.selector {
    margin: 0;
}

/* bad */
.selector {
    margin: 0
}
```