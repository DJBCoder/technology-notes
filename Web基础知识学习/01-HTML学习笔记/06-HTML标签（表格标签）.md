@[toc](表格标签)

>  表格现在主要用来处理、显示表格式数据，而不是用来布局。

# 创建表格
&emsp;&emsp;在HTML网页中要想创建表格就需要使用表格相关的标签，创建表格的基本语法格式如下：

```html
<table>
  <tr>
    <td>单元格内的文字</td>
    ...
  </tr>
  ...
</table>
```

&emsp;&emsp;在上面的语法中包含三对HTML标签，分别为&lt;table&gt;&lt;/table&gt;、&lt;tr&gt;&lt;/tr&gt;、&lt;td&gt;&lt;/td&gt;，他们是创建表格的基本标签缺一不可：

+ table：用于定义一个表格
+ tr：用于定义表格中的一行，必须嵌套在table标签中，在table中包含几对tr，就有几行表格
+ td：用于定义表格中的单元格，必须嵌套在&lt;tr&gt;&lt;/tr&gt;标签中，一对&lt;tr&gt; &lt;/tr&gt;中包含几对&lt;td&gt;&lt;/td&gt;，就表示该行中有多少列（或多少个单元格）。

> *__注意：__*
> 1. &lt;tr&gt;&lt;/tr&gt;中只能嵌套&lt;td&gt;&lt;/td&gt;
> 2. &lt;td&gt;&lt;/td&gt;标签，它就像一个容器，可以容纳所有的元素

# 表格属性

属性名| 含义| 常用属性值
-|-|-
border | 设置表格的边框（默认0 无边框）| 像素值
cellspacing |设置单元格与单元格之间的空白间距| 像素值（默认2像素）
cellpadding |设置单元格内容与单元格边框之间的空白间距| 像素值 （默认1像素）
width | 设置表格的宽度| 像素值
height | 设置表格的高度| 像素值
align | 设置表格在网页中的水平对齐方式| left、center、right

```html
<!-- 01-表格属性 -->
<body>
    <table border="1px"
    cellspacing="0"
    cellpadding="5"
    width="500"
    height="300"
    align="center">
        <tr>
            <td>姓名</td><td>年龄</td><td>性别</td>
        </tr>
        <tr>
            <td>张三</td><td>12</td><td>男</td>
        </tr>
        <tr>
            <td>李四</td><td>22</td><td>女</td>
        </tr>
    </table>
</body>
```

# 表头标签
&emsp;&emsp;表头一般位于表格的第一行或第一列，其文本加粗居中。即为设置了表头的表格。设置表头非常简单，只需用表头标签&lt;th&gt;&lt;/th&gt;替代相应的单元格标签&lt;td&gt;&lt;/td&gt;即可。

```html
<body>
    <table border="1px"
    cellspacing="2"
    cellpadding="5"
    width="500"
    height="300"
    align="center">
        <tr>
            <th>姓名</th><th>年龄</th><th>性别</th>
        </tr>
        <tr>
            <td>张三</td><td>12</td><td>男</td>
        </tr>
        <tr>
            <td>李四</td><td>22</td><td>女</td>
        </tr>
    </table>
</body>
```

# 表格结构
&emsp;&emsp;在使用表格进行布局时，可以将表格划分为头部、主体和页脚（页脚有兼容性问题），具体如下所示：

+ thead

&emsp;&emsp;该标签用于定义表格的头部：

```html
<thead></thead>
```

&emsp;&emsp;必须位于&lt; table &gt; 和 &lt; /table &gt;标签中，一般包含网页的logo和导航等头部信息。

+ tbody

&emsp;&emsp;该标签用于定义表格的主体：

```html
<tbody></tbody>
```

&emsp;&emsp;必须位于&lt;table&gt; 和 &lt;/table&gt;标签中，一般包含网页中除头部和底部之外的其他内容。

```html
<body>
    <table>
        <thead>
            <th>姓名</th>
            <th>年龄</th>
            <th>性别</th>
        </thead>
        <tbody>
            <tr>
                <td>张三</td><td>12</td><td>男</td>
            </tr>
            <tr>
                <td>李四</td><td>22</td><td>女</td>
            </tr>
        </tbody>
    </table>
</body>
```

# 表格标题
&emsp;&emsp;使用caption定义表格的标题：

```html
<table>
   <caption>我是表格标题</caption>
</table>
```

&emsp;&emsp;caption标签必须紧随table标签之后，只能对每个表格定义一个标题，通常这个标题会被居中于表格之上。

```html
<body>
    <table>
        <caption>人员信息</caption>
        <tr>
            <th>姓名</th><th>年龄</th><th>性别</th>
        </tr>
        <tr>
            <td>张三</td><td>12</td><td>男</td>
        </tr>
        <tr>
            <td>李四</td><td>22</td><td>女</td>
        </tr>
    </table>
</body>
```

# 合并单元格

+ 合并单元格的标签：
  + 跨行合并：rowspan
  + 跨列合并：colspan

+ 合并单元格的思想：将多个内容合并的时候，就会把多余的表格删除。例如把3个td合并成一个，那就多余了2个，需要删除。

+ 公式：删除的个数 = 合并的个数 - 1

+ 合并的顺序：先上、先左

```html
<body>
    <table border="1px" cellspacing="0">
        <tr>
            <th>姓名</th>
            <th colspan="2">电话</th>
        </tr>
        <tr>
            <td>张三</td>
            <td>1333333333</td>
            <td rowspan="2">浦口区</td>
        </tr>
        <tr>
            <td>李四</td>
            <td>1444444444</td>
        </tr>
    </table>
</body>
```