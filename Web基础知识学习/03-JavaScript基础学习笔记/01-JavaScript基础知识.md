@[toc](JavaScript基础知识)

# JavaScript介绍
## JavaScript是什么
&emsp;&emsp;JavaScript是一个编程语言，提供了流程控制语句。Netscape在最初将其脚本语言命名为LiveScript，后来Netscape在与Sun合作之后将其改名为JavaScript。JavaScript最初受Java启发而开始设计的，目的之一就是“看上去像Java”，因此语法上有类似之处，一些名称和命名规范也借自Java。Java和JavaScript只是名字很像而已：

+ Java ：服务器端的编程语言
+ JavaScript：运行在客户端(浏览器)的编程语言

> + JavaScript是一种运行在 *__客户端__* 的 *__脚本语言__*
> + JavaScript的解释器被称为JavaScript引擎，为浏览器的一部分，广泛用于客户端的脚本语言，最早是在HTML（标准通用标记语言下的一个应用）网页上使用，用来给HTML网页增加动态功能。

## JavaScript的应用场景
&emsp;&emsp;JavaScript最初的目的是为了处理表单的验证操作。但是发展到现在几乎无所不能：

1. 网页特效
2. 服务端开发(Node.js)
3. 命令行工具(Node.js)
4. 桌面程序(Electron)
5. App(Cordova)
6. 控制硬件-物联网(Ruff)
7. 游戏开发(cocos2d-js)

## JavaScript和HTML、CSS的区别

1. HTML：提供网页的结构，提供网页中的内容
2. CSS: 用来美化网页
3. JavaScript: 可以用来控制网页内容，给网页增加动态的效果

## JavaScript的组成

![12](./images/1496912475691.png)

+ ECMAScript：JavaScript的核心，定义了JavaScript的语法规范。描述了语言的基本语法和数据类型，ECMAScript是一套标准，定义了一种语言的标准与具体实现无关。
+ DOM（文档对象模型）：一套操作页面元素的API。DOM可以把HTML看做是文档树，通过DOM提供的API可以对树上的节点进行操作
+ BOM（浏览器对象模型）：一套操作浏览器功能的API。通过BOM可以操作浏览器窗口，比如：弹出框、控制浏览器跳转、获取分辨率等

## JavaScript的书写位置

+ 写在行内

```html
<body>
    <input type="button" value="按钮" onclick="alert('Hello World')">
</body>
```

+ 写在script标签中

```html
<body>
    <script>
        alert('Hello World')
    </script>
</body>
```

+ 写在外部js文件中，在页面中引入

```javascript
// js文件
alert('Hello World')
```

```html
<body>
    <!--引入了外部的js，所以这个标签中间不可以编写javascript代码-->
    <script src="./index.js"></script>
</body>
```

> *__注意：__* 引用外部js文件的script标签中不可以写JavaScript代码。

