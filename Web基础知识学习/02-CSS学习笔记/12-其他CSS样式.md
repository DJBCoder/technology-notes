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