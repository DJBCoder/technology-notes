@[toc](CSS字体外观样式)

# 字体样式
## 字号大小（font-size）
&emsp;&emsp;font-size属性用于设置字号，该属性的值可以使用相对长度单位，也可以使用绝对长度单位。其中，相对长度单位比较常用，推荐使用像素单位px，绝对长度单位使用较少：

<table>
    <tr>
        <td>类型</td>
        <td>单位</td>
        <td>说明</td>
    </tr>
    <tr>
        <td rowspan="2">相对长度单位</td>
        <td>em</td>
        <td>相对于当前对象内文本的字体尺寸</td>
    </tr>
    <tr>
        <td>px</td>
        <td>像素，最常用</td>
    </tr>
    <tr>
        <td rowspan="4">绝对长度单位</td>
        <td>in</td>
        <td>英寸</td>
    </tr>
    <tr>
        <td>cm</td>
        <td>厘米</td>
    </tr>
    <tr>
        <td>mm</td>
        <td>毫米</td>
    </tr>
    <tr>
        <td>pt</td>
        <td>点</td>
    </tr>
</table>

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>字号大小</title>
    <style>
        h2 {
            font-size: 30px;
        }
        h4 {
            font-size: 14px;
        }
        p {
            font-size: 12px;
        }
    </style>
</head>
<body>
    <h2>企业简介</h2>
    <h4>公司由来</h4>
    <p>阿斯顿阿斯顿爱上打算大实打实的奥迪阿斯顿奥
    迪阿斯顿奥迪爱上多少啊打算大声点阿斯顿爱上的</p>
    <h4>公司发展</h4>
    <p>阿斯顿阿斯顿爱上打算大实打实的奥迪阿斯顿奥
    迪阿斯顿奥迪爱上多少啊打算大声点阿斯顿爱上的</p>
    <h4>课程安排</h4>
    <p>阿斯顿阿斯顿爱上打算大实打实的奥迪阿斯顿奥
    迪阿斯顿奥迪爱上多少啊打算大声点阿斯顿爱上的</p>
</body>
</html>
```

## 字体（font-family）
&emsp;&emsp;font-family属性用于设置字体，网页最常用的字体有宋体、微软雅黑、黑体等，例如将网页中所有段落文本的字体设置为微软雅黑，可以使用如下方法：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>字体样式</title>
    <style>
        p {
            font-family: "微软雅黑";
        }
    </style>
</head>
<body>
    <p>这里有一段文本</p>
</body>
</html>
```

&emsp;&emsp;可以同时指定多个字体，中间以逗号隔开，表示如果浏览器不支持第一个字体，则会尝试下一个，直到找到合适的字体：

```css
p {
    font-family: "微软雅黑", "宋体";
}
```

> *__使用技巧：__*
> 1. 现在网页中普遍使用14px+。
> 2. 尽量使用偶数的数字字号，ie6等老式浏览器支持奇数会有bug。
> 3. 各种字体之间必须使用英文状态下的逗号隔开。
> 4. 中文字体需要加英文状态下的引号，英文字体一般不需要加引号。当需要设置英文字体时，英文字体名必须位于中文字体名之前。
> 5. 如果字体名中包含空格、#、$等符号，则该字体必须加英文状态下的单引号或双引号，例如 *__font-family: "Times New Roman";__*
> 6. 尽量使用系统默认字体，保证在任何用户的浏览器中都能正确显示

### CSS Unicode字体
&emsp;&emsp;在CSS中设置字体名称，直接写中文是可以的。但是在文件编码（GB2312、UTF-8 等）不匹配时会产生乱码的错误，并且xp系统不支持类似"微软雅黑"的中文。有下面两种方法来解决：

+ 你可以使用英文来替代，比如：*__font-family:"Microsoft Yahei"__*

+ 在CSS直接使用Unicode编码来写字体名称可以避免这些错误。使用Unicode写中文字体名称，浏览器是可以正确的解析的。*__font-family: "\5FAE\8F6F\96C5\9ED1"__* ，表示设置字体为“微软雅黑”。

&emsp;&emsp;常用的字体编码：

字体名称 | 英文名称 | Unicode 编码
- | - | -
宋体 | SimSun| \5B8B\4F53
新宋体 | NSimSun |\65B0\5B8B\4F53
黑体 |SimHei | \9ED1\4F53
微软雅黑 | Microsoft YaHei | \5FAE\8F6F\96C5\9ED1
楷体_GB2312 | KaiTi_GB2312| \6977\4F53_GB2312
隶书 | LiSu | \96B6\4E66
幼园 | YouYuan| \5E7C\5706
华文细黑 | STXihei | \534E\6587\7EC6\9ED1
细明体  | MingLiU  | \7EC6\660E\4F53
新细明体| PMingLiU | \65B0\7EC6\660E\4F53

> *__注意：__* 为了照顾不同电脑的字体安装问题，我们尽量只使用宋体和微软雅黑中文字体

## 字体粗细（font-weight）
&emsp;&emsp;字体加粗除了用b和strong标签之外，还可以使用CSS来实现，但是CSS是没有语义的。

&emsp;&emsp;font-weight属性用于定义字体的粗细，其可用属性值：normal、bold、bolder、lighter、100~900（100的整数倍）。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>字体粗细</title>
    <style>
        p {
            font-weight: blod;
        }
        span {
            font-weight: 100;
        }
    </style>
</head>
<!-- 03-字体粗细 -->
<body>
    <p>这里是一段文本</p>
    <span>这里是span中的内容</span>
</body>
</html>
```

> *__小技巧：__*数字 400 等价于 normal，而 700 等价于 bold，但是我们更喜欢用数字来表示。

## 字体风格（font-style）
&emsp;&emsp;字体倾斜除了用i和em标签之外，可以使用CSS来实现，但是CSS是没有语义的。

&emsp;&emsp;font-style属性用于定义字体风格，如设置斜体、倾斜或正常字体，其可用属性值如下：

+ normal：默认值，浏览器会显示标准的字体样式。

+ italic：浏览器会显示斜体的字体样式。

+ oblique：浏览器会显示倾斜的字体样式。

```html
<body>
    <p style="font-style: italic;">斜体</p>
    <p style="font-style: normal;">正常</p>
    <p style="font-style: oblique;">倾斜</p>
</body>
```

> *__小技巧：__* 平时我们很少给文字加斜体，反而喜欢给斜体标签（em，i）改为普通模式。

## 综合设置字体样式
&emsp;&emsp;font属性用于对字体样式进行综合设置，其基本语法格式如下：

```css
选择器 {font: font-style  font-weight  font-size/line-height  font-family; }
```

> *__注意：__* 
> 1. 使用font属性时，必须按上面语法格式中的顺序书写，不能更换顺序
> 2. 各个属性以空格隔开
> 3. 其中不需要设置的属性可以省略（取默认值），但必须保留font-size和font-family属性，否则font属性将不起作用。

```html
<body>
    <!-- 完整版本 -->
    <p 
    style="font: italic 400 10px '微软雅黑';">
    完整的字体综合样式</p>

    <!-- 省略版本 -->
    <p
    style="font: 20px '微软雅黑';">
    省略版本
    </p>
</body>
```

# 文本外观样式
## 文本颜色（color）
&emsp;&emsp;color属性用于定义文本的颜色，其取值方法如以下3种：

1. 预定义的颜色值，如：red，green，blue等

2. 十六进制，如：#FF0000，#FF6600，#29D794等，实际工作中，十六进制是最常用的定义颜色的方式

3. RGB代码，如：红色可以表示为rgb(255,0,0)或rgb(100%,0%,0%)。（ *__需要注意的是，如果使用RGB代码的百分比颜色值，取值为0时也不能省略百分号，必须写为0%__* ）

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>文本颜色</title>
    <style>
        /* 使用预定义颜色 */
        .red {
            color: red;
        }

        /* 使用十六进制 */
        .green {
            color: #00ff00;
        }

        /* 使用rgb */
        .blue {
            color: rgb(0,0,255);
        }
    </style>
</head>
<!-- 01-文本颜色 -->
<body>
    <span class="red">red</span>
    <span class="green">green</span>
    <span class="blue">blue</span>
</body>
</html>
```

### 颜色半透明
&emsp;&emsp;文字颜色到了CSS3我们可以采取半透明的格式了语法格式如下：

```css
color: rgba(r,g,b,a);  
/*
1. a是alpha，透明的意思  
2. 取值范围 0~1之间
3. 如：color: rgba(0,0,0,0.3)  
*/
```

```html
<!-- 06-半透明颜色 -->
<body>
    <h1 style="color: rgba(255,0,0,0.5);">这里有一段文本</h1>
</body>
```

## 行间距（line-height）
&emsp;&emsp;line-height属性用于设置行间距，就是行与行之间的距离，即字符的垂直间距，一般称为行高。line-height常用的属性值单位有三种，分别为：

+ 像素px
+ 相对值em
+ 百分比%

&emsp;&emsp;实际工作中使用最多的是像素px。一般情况下，行距比字号大7、8像素左右就可以了。

```html
<body>
    <p style="line-height: 25px;">
        阿斯顿阿斯顿爱上多少啊的阿斯顿阿斯顿爱上打算d爱上d
        奥迪阿斯顿阿斯顿阿斯顿阿斯顿阿斯顿阿斯顿阿斯顿撒的阿斯顿撒的阿斯顿
        阿斯顿阿斯顿阿斯顿阿斯顿撒的阿斯顿阿斯顿阿斯顿阿斯顿
        阿斯顿撒的阿斯顿阿斯顿阿斯顿撒打算d阿斯顿asd阿斯顿。
    </p>
</body>
```


> **使用技巧**：在一行内的盒子内，我们设定行高等于盒子的高度，就可以使文字垂直居中。(盒子只有一行文本有效，多了就不行了)

## 文本的装饰
&emsp;&emsp;text-decoration通常我们用于给链接修改装饰效果：

值 | 描述
- | -
none| 默认。定义标准的文本
underline | 定义文本下的一条线(下划线也是我们链接自带的)
overline | 定义文本上的一条线
line-through | 定义穿过文本下的一条线

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .none{
            text-decoration: none;
        }
        .underline{
            text-decoration: underline;
        }
        .overline{
            text-decoration: overline;
        }
        .linethrough{
            text-decoration: line-through;
        }
    </style>
</head>
<body>
    <span class="none">aaaa</span><br>
    <span class="underline">aaaa</span><br>
    <span class="overline">aaaa</span><br>
    <span class="linethrough">aaaa</span><br>
</body>
</html>
```

## 水平对齐方式（text-align）
&emsp;&emsp;text-align属性用于设置文本内容的水平对齐，相当于html中的align对齐属性。其可用属性值如下：

+ left：左对齐（默认值）
+ right：右对齐
+ center：居中对齐

```html
<!-- 03-水平对齐方式 -->
<body>
    <p style="text-align: center;">center对齐</p>
    <p style="text-align: left;">左对齐</p>
    <p style="text-align: right;">右对齐</p>
</body>
```

## 首行缩进（text-indent）
&emsp;&emsp;text-indent属性用于设置首行文本的缩进，其属性值可为不同单位的数值、em字符宽度的倍数、或相对于浏览器窗口宽度的百分比%，允许使用负值。建议使用em作为设置单位。1em就是一个字的宽度，如果是汉字的段落，1em就是一个汉字的宽度。

```html
<!-- 04-首行缩进 -->
<body>
    <p style="text-indent: 2em;">阿斯顿奥迪撒的奥迪阿斯顿阿斯顿爱上打算打算的阿斯顿
        阿斯顿阿斯顿阿斯顿阿斯顿阿斯顿阿斯顿撒的
        阿斯顿阿斯顿爱上大声点阿斯顿阿斯顿阿斯顿阿斯顿阿斯顿阿斯顿
        阿斯顿撒的阿斯顿阿斯顿撒打算打算打算打算d阿斯顿
        阿斯顿撒的阿斯顿撒的阿斯顿阿斯顿阿斯顿
        撒打算打算的
    </p>
</body>
```

## 字间距和单词间距
### 字间距（letter-spacing）
&emsp;&emsp;letter-spacing属性用于定义字间距，所谓字间距就是字符与字符之间的空白。其属性值可为不同单位的数值，允许使用负值，默认为normal。

```html
<body>
    <p style="letter-spacing: 3em;">Hello World</p>
    <p style="letter-spacing: 3em;">我是DJBCoder</p>
</body>
```

### 单词间距（word-spacing）
&emsp;&emsp;word-spacing属性用于定义英文单词之间的间距，对中文字符无效。和letter-spacing一样，其属性值可为不同单位的数值，允许使用负值，默认为normal。

```html
<body>
    <p style="word-spacing: 3em;">Hello World</p>
    <!-- 有中文，所以无效 -->
    <p style="word-spacing: 3em;">我是DJBCoder</p>
</body>
```

> *__注意：__* word-spacing和letter-spacing均可对英文进行设置。不同的是letter-spacing定义的为字母之间的间距，而word-spacing定义的为英文单词之间的间距。

## 文字阴影效果
&emsp;&emsp;我们可以给文字添加阴影(Shadow)效果：

```css
text-shadow:水平位置 垂直位置 模糊距离 阴影颜色;
```

值 | 描述
- | -
h-shadow | 必须，水平阴影的位置，允许负值
v-shadow | 必须，垂直阴影的位置，允许负值
blur | 可选，模糊的距离
color | 可选，阴影的颜色

```html
<!-- 07-阴影效果 -->
<body>
    <h1 
    style="text-shadow: 2px 2px 3px rgba(0,0,0,0.4);"
    >这里是标题</h1>
</body>
```
