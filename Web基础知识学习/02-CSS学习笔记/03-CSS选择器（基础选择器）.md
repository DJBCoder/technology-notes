@[toc](CSS选择器)

&emsp;&emsp;要想将CSS样式应用于特定的HTML元素，首先需要找到该目标元素。在CSS中，执行这一任务的样式规则部分被称为选择器（选择符）。

# 标签选择器（元素选择器）
&emsp;&emsp;标签选择器是指用HTML标签名称作为选择器，按标签名称分类，为页面中某一类标签指定统一的CSS样式。其基本语法格式如下：

```css
标签名 {属性1:属性值1; 属性2:属性值2; 属性3:属性值3; }

/* 或者 */

元素名{属性1:属性值1; 属性2:属性值2; 属性3:属性值3; }
```

> 标签选择器最大的优点是能快速为页面中同类型的标签统一样式，同时这也是他的缺点，不能设计差异化样式。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>标签选择器</title>
    <style>
        /* 所有的p标签添加 */
        p {
            font-size: 20px;
        }

        /* 为所有的span标签提供样式 */
        span {
            font-style: italic;
        }
    </style>
</head>
<!-- 01-标签选择器 -->
<body>
    <p>这里是一段p标签的内容</p>
    <span>这里是span中的内容</span>
    <p>这里是一段p标签的内容</p>
</body>
</html>
```

# 类选择器
&emsp;&emsp;类选择器使用“.”（英文点号）进行标识，后面紧跟类名，其基本语法格式如下：

```css
.类名 {属性1:属性值1; 属性2:属性值2; 属性3:属性值3; }
```

&emsp;&emsp;标签调用的时候用 *__class=“类名”__*  即可，如：

```html
<p class="类名">...</p>
```

&emsp;&emsp;类选择器最大的优势是可以为元素对象定义单独或相同的样式。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>类选择器</title>
    <style>
        span {
            font-size: 100px;
            font-weight: 200;
        }
        .blue {
            color: blue;
        }
        .red {
            color: red;
        }
        .orange {
            color: orange;
        }
        .green {
            color: green;
        }
    </style>
</head>
<!-- 02-类选择器 -->
<body>
    <span class="blue">G</span>
    <span class="red">o</span>
    <span class="orange">o</span>
    <span class="blue">g</span>
    <span class="green">l</span>
    <span class="red">e</span>
</body>
</html>
```

## 命名规范

1. 长名称或词组可以使用中横线来为选择器命名
2. 不建议使用“_”下划线来命名CSS选择器
3. 不要纯数字、中文等命名，尽量使用英文字母来表示

## 多类名选择器
&emsp;&emsp;我们可以给标签指定多个类名，从而达到更多的选择目的。语法格式如下：

```html
<标签名 class="类名1 类名2 ..."></标签名>
```

1. 样式显示效果跟HTML元素中的类名先后顺序没有关系,受CSS样式书写的上下顺序有关
2. 各个类名中间用空格隔开

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>多类名选择器</title>
    <style>
        .red {
            color: red;
        }
        .blue {
            color: blue;
        }
        .b-font {
            font-size: 16px;
        }
        .s-font {
            font-size: 14px;
        }
    </style>
</head>
<!-- 03-多类名选择器 -->
<body>
    <div class="s-font red">字体大小14px，红色</div>
    <div class="s-font blue">字体大小14px，蓝色</div>
    <div class="b-font red">字体大小16px，红色</div>
</body>
</html>
```

# id选择器
&emsp;&emsp;id选择器使用“#”进行标识，后面紧跟id名，其基本语法格式如下：

```css
#id名{属性1:属性值1; 属性2:属性值2; 属性3:属性值3; }
```

&emsp;&emsp;该语法中，id名即为HTML元素的id属性值，大多数HTML元素都可以定义id属性，元素的id值是唯一的，只能对应于文档中某一个具体的元素。

&emsp;&emsp;id选择器的用法基本和类选择器相同：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>id选择器</title>
    <style>
        #id-select {
            color: red;
            font-size: 20px;
        }
    </style>
</head>
<!-- 04-id选择器 -->
<body>
    <p id="id-select">这是id选择器</p>
</body>
</html>
```

## id选择器和类选择器区别

+ W3C标准规定，在同一个页面内，不允许有相同名字的id对象出现，但是允许相同名字的class
+ 类选择器好比人的名字，是可以多次重复使用的
+ id选择器好比人的身份证号码，不得重复，只能使用一次
+ id选择器和类选择器最大的不同在于使用次数上

# 通配符选择器
&emsp;&emsp;通配符选择器用“*”号表示，它是所有选择器中作用范围最广的，能匹配页面中所有的元素。其基本语法格式如下：

```css
* { 属性1:属性值1; 属性2:属性值2; 属性3:属性值3; }
```

&emsp;&emsp;例如下面的代码，使用通配符选择器定义CSS样式，清除所有HTML标记的默认边距。

```css
* {
  margin: 0;                    /* 定义外边距*/
  padding: 0;                   /* 定义内边距*/
}
```

# 伪类选择器
&emsp;&emsp;伪类选择器用于向某些选择器添加特殊的效果，比如给链接添加特殊效果，可以选择第1个、第n个元素。类选择器是一个点，比如：*__.demo {}__* 。而伪类用冒号，比如： *__:link{}__*