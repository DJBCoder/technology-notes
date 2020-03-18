@[toc](其他CSS样式)

# 元素的显示与隐藏
&emsp;&emsp;在CSS中有三个显示和隐藏的单词比较常见，它们分别是display、visibility和overflow。它们的主要目的是让一个元素在页面中消失，但是不在文档源码中删除。

## display
&emsp;&emsp;display设置或检索对象是否及如何显示：

+ none：隐藏对象 
+ block：转换为块级元素并显示元素
+ inline：转换为行内元素并显示元素
+ inline-block：转换为行内块元素并显示元素

> *__特点：__* 隐藏之后不再保留位置。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }
        div {
            width: 200px;
            height: 200px;
        }
        div:first-child {
            background-color: red;
            display: none;
        }
        div:last-child {
            background-color: pink;
        }
    </style>
</head>
<body>
    <div></div>
    <div></div>
</body>
</html>
```

## visibility
&emsp;&emsp;设置或检索是否显示对象：

+ visible：对象可视
+ hidden：对象隐藏

> *__特点：__* 隐藏之后继续保留原有位置。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }
        div {
            width: 200px;
            height: 200px;
        }
        div:first-child {
            background-color: red;
            visibility: hidden;
        }
        div:last-child {
            background-color: pink;
        }
    </style>
</head>
<body>
    <div></div>
    <div></div>
</body>
</html>
```

## overflow 溢出
&emsp;&emsp;检索或设置当对象的内容超过其指定高度及宽度时如何管理内容：

+ visible：不剪切内容也不添加滚动条。
+ auto：超出自动显示滚动条，不超出不显示滚动条
+ hidden：不显示超过对象尺寸的内容，超出的部分隐藏掉
+ scroll：不管超出内容否，总是显示滚动条

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }
        div {
            width: 100px;
            height: 200px;
            border: 1px solid red;
            overflow: auto;
        }
    </style>
</head>
<body>
    <div>
        asdasdasdasdasdasdasdasdasdasd
        asdasdasdasdasdasdasdasdasdasd
        asdasdasdasdasdasdasdasdasdasd
        asdasdasdasdasdasdasdasdasdasd
        asdasdasdasdasdasdasdasdasdasd
        asdasdasdasdasdasdasdasdasdasd
    </div>
</body>
</html>
```

# CSS用户界面样式
&emsp;&emsp;所谓的界面样式就是更改一些用户操作样式，比如：更改用户的鼠标样式、表单轮廓等。

## 鼠标样式
&emsp;&emsp;设置或检索在对象上移动的鼠标指针采用何种系统预定义的光标形状：

```css
cursor: 属性值; 
```

&emsp;&emsp;常用属性说明：

+ default：小白
+ pointer：小手 
+ move：移动
+ text：文本

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <ul>
        <li style="cursor:default">我是小白</li>
        <li style="cursor:pointer">我是小手</li>
        <li style="cursor:move">我是移动</li>
        <li style="cursor:text">我是文本</li>
    </ul>
</body>
</html>
```

> *__注意：__* 尽量不要用hand，因为火狐不支持。而是应该使用pointer（ie6以上都支持）。

## 轮廓
&emsp;&emsp;是绘制于元素周围的一条线，位于边框边缘的外围，可起到突出元素的作用：

```css
 outline : outline-color ||outline-style || outline-width 
```

```html
<body>
    <input type="text" style="outline: 1px solid red;">
</body>
```

> 但是我们平时都是去掉的，最直接的写法是：*__outline: 0;__* 或者 *__outline: none;__*

## 防止拖拽文本域
&emsp;&emsp;通过设置 *__resize：none;__* 可以防止火狐、谷歌等浏览器随意的拖动文本域。

+ 右下角可以拖拽： 

```html
<body>
    <textarea></textarea>
</body>
```

&emsp;&emsp;右下角不可以拖拽： 

```html
<body>
    <textarea  style="resize: none;"></textarea>
</body>
```

# 垂直对齐

+ 带有宽度的块级元素居中对齐是： *__margin: 0 auto;__*
+ 文字居中对齐是： *__text-align: center;__*

&emsp;&emsp;vertical-align是用来设置或检索对象内容的垂直对其方式：

```css
vertical-align : 属性值
```

&emsp;&emsp;下面是垂直对齐的几种方式：

+ baseline
+ top
+ middle
+ bottom

![垂直对齐的几种方式](./images/垂直对齐的几种方式.jpg)

&emsp;&emsp;vertical-align不影响块级元素中的内容对齐，它只针对于行内元素或者行内块元素，特别是行内块元素， *__通常用来控制图片/表单与文字的对齐__* 。

## 图片、表单和文字对齐
&emsp;&emsp;可以通过vertical-align控制图片和文字的垂直关系了，默认的图片会和文字基线对齐。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        img {
            vertical-align: middle;
        }
    </style>
</head>
<body>
    <img src="./erweima.png" alt="">这里一段文字
</body>
</html>
```

## 去除图片底侧空白缝隙
&emsp;&emsp;有个很重要特性：图片或者表单等行内块元素的底线会和父级盒子的基线对齐。这样就会造成一个问题：图片底侧会有一个空白缝隙。解决的方法就是：  

1. 设置 *__img vertical-align:middle__* 等，让图片不要和基线对齐
2. 给img添加 *__display：block;__* 转换为块级元素就不会存在问题了。

# 溢出的文字隐藏
## word-break:自动换行

+ normal：使用浏览器默认的换行规则
+ break-all：允许在单词内换行
+ keep-all：只能在半角空格或连字符处换行

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        div {
            width: 120px;
            height: 20px;
            border: 1px solid #f00;
            word-break: break-all;
        }
    </style>
</head>
<body>
    <div>
        my name is andy
    </div>
</body>
</html>
```

> 主要处理英文单词

## white-space
&emsp;&emsp;white-space设置或检索对象内文本显示方式，通常我们使用于强制一行显示内容 

+ normal：默认处理方式
+ nowrap：强制在同一行内显示所有文本，直到文本结束或者遭遇br标签对象才换行。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        div {
            width: 120px;
            height: 20px;
            border: 1px solid #f00;
            white-space: nowrap;
        }
    </style>
</head>
<body>
    <div>
        啊啊啊啊啊啊啊啊啊啊啊啊啊啊
    </div>
</body>
</html>
```

> 可以处理中文

## text-overflow 文字溢出
&emsp;&emsp;设置或检索是否使用一个省略标记（...）标示对象内文本的溢出：

```css
text-overflow : clip | ellipsis
```

+ clip：不显示省略标记（...），而是简单的裁切 
+ ellipsis：当对象内文本溢出时显示省略标记（...）

> *__注意:__* 必须有两个前提条件：
> 1. 首先需要强制一行内显示：white-space: nowrap;
> 2. 需要使用overflow属性：overflow: hidden;

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        div {
            width: 120px;
            height: 20px;
            border: 1px solid #f00;
            white-space: nowrap;
            text-overflow: ellipsis;
            overflow: hidden;
        }
    </style>
</head>
<body>
    <div>
        啊啊啊啊啊啊啊啊啊啊啊啊啊啊
    </div>
</body>
</html>
```