@[toc](CSS补充知识)

# 优雅降级和渐进增强

+ 所谓渐进增强（progressive enhancement）：针对低版本浏览器进行构建页面，保证最基本的功能；然后再针对高级浏览器进行效果、交互等改进和追加功能达到更好的用户体验。
+ 优雅降级（graceful degradation）：一开始就构建完整的功能，然后再针对低版本浏览器进行兼容。

> + 区别：渐进增强是向上兼容，优雅降级是向下兼容。
> + 建议：现在互联网发展很快，我们很多情况下没有必要再时刻想着低版本浏览器了，而是一开始就构建完整的效果，根据实际情况，修补低版本浏览器问题。

# 浏览器前缀

浏览器前缀 | 浏览器
-|-
-webkit- | Google Chrome, Safari, Android Browser
-moz-    | Firefox
-o-      | Opera
-ms-     | Internet Explorer, Edge
-khtml-  | Konqueror

# 背景渐变
&emsp;&emsp;在线性渐变过程中，颜色沿着一条直线过渡：从左侧到右侧、从右侧到左侧、从顶部到底部、从底部到顶部或着沿任何任意轴。

> 兼容性问题很严重，必须加上流啊冷凝器的私有前缀

&emsp;&emsp;语法格式：

```css
background:-webkit-linear-gradient(渐变的起始位置， 起始颜色， 结束颜色)；
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
            width: 300px;
            height: 50px;
            background: linear-gradient(top,red,green);
            background: -webkit-linear-gradient(top,red,green);
            margin: 180px auto;
       }
    </style>
</head>
<body>
<section>
    <div></div>
</section>
</body>
</html>
```

```css
background:-webkit-linear-gradient(渐变的起始位置， 颜色 位置，颜色 位置....)；
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
            width: 300px;
            height: 50px;
            background: -webkit-linear-gradient(top,red 0%,green 20%, yellow 80%);
            margin: 180px auto;
       }
    </style>
</head>
<body>
<section>
    <div></div>
</section>
</body>
</html>
```

# CSS W3C统一验证工具

+ CssStats：CssStats是一个在线的CSS代码分析工具
  + 网址：http://www.cssstats.com/
+ W3C统一验证工具：它可以检测本地文件
  + 网址：http://validator.w3.org/unicorn/

# CSS 压缩
&emsp;&emsp;可以通过css压缩工具把css进行压缩。

 + w3c css压缩：网速比较慢
   + 网址：http://tool.chinaz.com/Tools/CssFormat.aspx

 + 站长之家进行快速压缩
   + 网址：http://tool.chinaz.com/Tools/CssFormat.aspx  
