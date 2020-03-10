@[toc](CSS背景样式)

&emsp;&emsp;CSS可以添加背景颜色和背景图片以及对图片的设置。

background-color | 背景颜色
-|-
background-image | 背景图片地址
background-repeat | 是否平铺
background-position | 背景位置
background-attachment | 背景固定还是滚动
背景的合写（复合属性）|background:背景颜色 背景图片地址 背景平铺 背景滚动 背景位置

# 颜色背景

&emsp;&emsp;语法：

```css
background-color: red;
/*
这里除了可以使用内置的颜色名称，还可以使用十六进制颜色值和rgb
background-color: #fff;
background-color: rgb(0,255,0)
*/
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        div {
            width: 200px;
            height: 200px;
            background-color: #ed3;
        }
    </style>
</head>
<body>
    <div>

    </div>
</body>
</html>
```

# 图片背景
&emsp;&emsp;语法：

```css
background-image : none | url (url)
```

+ none：无背景图（默认的）
+ url：使用绝对或相对地址指定背景图像

&emsp;&emsp;background-image属性允许指定一个图片展示在背景中（只有CSS3才可以多背景），可以和 background-color连用。如果图片不重复地话，图片覆盖不到地地方都会被背景色填充；如果有背景图片平铺，则会覆盖背景颜色。

> *__注意__* 提倡背景图片后面的地址url不要加引号