@[toc](表单标签)

&emsp;&emsp;现实中的表单，类似去银行办理信用卡填写的单子，目的是为了收集用户信息。在HTML中，一个完整的表单通常由表单控件（也称为表单元素）、提示信息和表单域3个部分：

+ 表单控件：包含了具体的表单功能项，如：单行文本输入框、密码输入框、复选框、提交按钮、重置按钮等

+ 提示信息：一个表单中通常还需要包含一些说明性的文字，提示用户进行填写和操作

+ 表单域：它相当于一个容器，用来容纳所有的表单控件和提示信息，可以通过它定义处理表单数据所用程序的url地址以及数据提交到服务器的方法

# input控件
&emsp;&emsp;&lt;input /&gt;标签为单标签，type属性为其最基本的属性，其取值有多种，用于指定不同的控件类型。除了type属性之外，&lt;input /&gt;标签还可以定义很多其他的属性，其常用属性如下表所示。

<table>
<thead>
  <th>属性</th>
  <th>属性值</th>
  <th>描述</th>
</thead>
<tbody>
  <tr>
    <td rowspan="9">type</td>
    <td>text</td>
    <td>单行文本输入框</td>
  </tr>
  <tr>
    <td>password</td>
    <td>密码输入框</td>
  </tr>
  <tr>
    <td>radio</td>
    <td>单选按钮</td>
  </tr>
  <tr>
    <td>checkbox</td>
    <td>复选框</td>
  </tr>
  <tr>
    <td>button</td>
    <td>普通按钮</td>
  </tr>
  <tr>
    <td>submit</td>
    <td>提交按钮</td>
  </tr>
  <tr>
    <td>reset</td>
    <td>重置按钮</td>
  </tr>
  <tr>
    <td>image</td>
    <td>图像形式的提交按钮</td>
  </tr>
  <tr>
    <td>file</td>
    <td>文件域</td>
  </tr>
  <tr>
    <td>name</td>
    <td>由用户自定义</td>
    <td>控件的名称</td>
  </tr>
  <tr>
    <td>value</td>
    <td>由用户自定义</td>
    <td>input控件中的默认文本值</td>
  </tr>
  <tr>
    <td>size</td>
    <td>正整数</td>
    <td>input控件在页面中显示的宽度</td>
  </tr>
  <tr>
    <td>checked</td>
    <td>checked</td>
    <td>定义选择控件默认被选中的项</td>
  </tr>
  <tr>
    <td>maxlength</td>
    <td>正整数</td>
    <td>控件允许输入的最多字符数</td>
  </tr>
</tbody>
</table>

```html
<body>
    <form action="#">
        <!-- 单行文本输入框 -->
        姓名：<input type="text"><br>
        密码：<input type="password"><br>
        性别：<input type="radio" name="gender" value="man" checked> 男 
        <input type="radio" name="gender" value="woman"> 女 <br>
        兴趣爱好：<input type="checkbox" name="hob" value="football">足球
        <input type="checkbox" checked name="hob" value="book">看书 <br>
        <input type="file" name="" id=""> 文件上传<br>
        <input type="image" src="./imgs/1.jpg" alt=""><br>
        <input type="button" value="关闭">
        <input type="submit" value="提交">
        <input type="reset" value="重置">
    </form>
</body>
```

> *__注意：__*
> 1. radio和checkbox 通过相同的name属性值来确认为一组，radio只有确认为一组后才会互斥为单选。
> 2. checkbox和radio 可以通过checked属性来确定为默认选中项

# label标签
&emsp;&emsp;label标签为input元素定义标注，用于绑定一个表单元素, 当点击label标签的时候, 被绑定的表单元素就会获得输入焦点。通过for属性规定label与哪个表单元素绑定：

```html
<body>
    <!-- 第一种方式，使用label包裹 -->
    <label>
        姓名：
        <input type="text">
    </label><br>

    <!-- 第二种方式，指定id -->
    <label for="pwd">密码：</label>
    <input type="password" id="pwd">
</body>
```

# textarea控件
&emsp;&emsp;如果需要输入大量的信息，就需要用到&lt;textarea&gt;&lt;/textarea&gt;标签。通过textarea控件可以轻松地创建多行文本输入框，其基本语法格式如下：

```html
<textarea cols="每行中的字符数" rows="显示的行数">
  文本内容
</textarea>
```

# 下拉菜单
&emsp;&emsp;使用select控件定义下拉菜单的基本语法格式如下：

```html
<select>
  <option>选项1</option>
  <option>选项2</option>
  <option>选项3</option>
  ...
</select>
```

> *__注意：__*
> 1. &lt;select&gt;&lt;/select&gt;中至少应包含一对&lt;option&gt;&lt;/option&gt;。
> 2. 在option 中定义selected =" selected "时，当前项即为默认选中项。

```html
<body>
    <!-- 单选 -->
    籍贯：<select>
        <option value="bj" >北京</option>
        <option value="gz" selected>广州</option>
        <option value="nj">南京</option>
        <option value="sh">上海</option>
    </select>
    <br>
    选择你的爱好：
    <select multiple>
        <option value="football">足球</option>
        <option value="basketball">篮球</option>
        <option value="music">音乐</option>
        <option value="book">看书</option>
    </select>
</body>
```

# 表单域
&emsp;&emsp;在HTML中，form标签被用于定义表单域，即创建一个表单，以实现用户信息的收集和传递，form中的所有内容都会被提交给服务器。创建表单的基本语法格式如下：

```html
<form action="url地址" method="提交方式" name="表单名称">
  各种表单控件
</form>
```

&emsp;&emsp;常用属性：

1. action：在表单收集到信息后，需要将信息传递给服务器进行处理，action属性用于指定接收并处理表单数据的服务器程序的url地址。
2. method：用于设置表单数据的提交方式，其取值为get或post。
3. name：用于指定表单的名称，以区分同一个页面中的多个表单。

> *__注意：每个表单都应该有自己表单域。__*