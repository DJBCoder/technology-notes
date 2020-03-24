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

# 注释
## 单行注释
&emsp;&emsp;用来描述下面一个或多行代码的作用：

```javascript
// 这是一个变量
var name = 'hm';
```

## 多行注释
&emsp;&emsp;用来注释多条代码：

```javascript
/*
var age = 18;
var name = 'zs';
console.log(name, age);
*/
```

# 变量

+ 什么是变量：变量是计算机内存中存储数据的标识符，根据变量名称可以获取到内存中存储的数据
+ 为什么要使用变量：使用变量可以方便的获取或者修改内存中的数据

## 使用变量

+ var声明变量

```javascript
var age;
```

+ 变量的赋值

```javascript
var age;
age = 18;
```

+ 同时声明多个变量

```javascript
var age, name, sex;
age = 10;
name = 'zs';
```

+ 同时声明多个变量并赋值

```javascript
var age = 10, name = 'zs';
```

## 变量在内存中的存储

```javascript
var age = 18;
```

![1496981558575](images/1496981558575.png)

## 变量的命名规则和规范

+ 规则（必须遵守的，不遵守会报错）：
  + 由字母、数字、下划线、$组成，不能以数字开头
  + 不能是关键字和保留字，例如：for、while。
  + 区分大小写

+ 规范（建议遵守的，不遵守不会报错）：
  + 变量名必须有意义
  + 遵守驼峰命名法：首字母小写，后面单词的首字母需要大写。例如：userName、userPassword

# 数据类型
&emsp;&emsp;在C、Java等语言中，声明变量的时候就确定了数据类型；而JavaScript中声明的时候并没有确定变量的类型，所以JavaScript是弱类型的语言，在使用的过程中可以改变数据的类型。（弱类型只是在声明的时候不知道类型，在执行的过程中会确定变量的类型）

## 简单数据类型

### Number类型

+ 数值字面量（数值的固定值的表示法），如：110
+ 进制
  + 十进制，如 *__var num = 9;__* ，在进行算数计算的时候，八进制和十六进制表示的数值最终都会被转换成十进制
  + 十六进制，如 *__var num = 0xA;__* ，数值范围 *0~9以及A～F*
  + 八进制，如 *__var num = 07;__* ，数值范围是 *0~7* 。

  > *__注意：__* 如果字面值中的数值超出了范围，那么前导零将会被忽略，后面的数值将会被当作十进制数解析，如：
  > ```javascript
  > var num = 019; // 对应十进制的19
  > var num = 08;  // 对应十进制的8
  >```
+ 浮点数
  + 定义方法：
  ```javascript
    var num1 = 2.3;
    var num2 = 5e-324; // 科学计算法，表示5乘以10的-324次方
  ```
  + 浮点数的精度问题：浮点数的最高精度是17位小数，但在进行计算的时候其精确度远远不如整数：
  ```javascript
    var result = 0.1 + 0.2; // 结果不是0.3，而是0.3000000000004
  ```
  > 所以不要判断两个浮点数是否相等
+ 特殊数值：
  + 最小值：Number.MIN_VALUE（5e-324）
  + 最大值：Number.MAX_VALUE（1.7976931348623157e+308）
  + 无穷大：Infinity
  + 无穷小：-Infinity
+ 数值判断
  + NaN（not a number）：NaN与任何值都不相等，包括其本身
  + isNaN（is not a number）：判断是否是一个数字
  ```javascript
    isNaN(num)
  ```

### 字符串String类型

+ 字符串字面量，可以适应单引号和双引号：

```javascript
var str1 = 'str1';
var str2 = "str2";
```

+ 转义符

![1498289626813](images/1498289626813.png)

+ 字符串长度

&emsp;&emsp;使用length属性用来获取字符串的长度：

```javascript
var str = '黑马程序猿 Hello World';
console.log(str.length);
```

+ 字符串拼接

&emsp;&emsp;字符串拼接使用 *__+__* 连接：

```javascript
console.log('hello' + ' world');
console.log('100' + '100');
console.log('11' + 11);
console.log('male:' + true);
```

> 两边只要有一个是字符串，那么+就是字符串拼接功能

### Boolean布尔类型

+ Boolean字面量：true和false，注意需要区分大小写

+ 计算机内部存储：true为1，false为0

### Undefined和Null

+ undefined表示一个声明了没有赋值的变量，变量只声明的时候值默认是undefined
+ null表示一个空，变量的值如果想为null，必须手动设置

## 获取变量的类型
&emsp;&emsp;使用typeof来获取数据的类型：

```javascript
var age = 18;
console.log(typeof age);  // 'number'
```

## 数据类型转换
### 转换成字符串类型

+ 使用toString()方法

```javascript
var num = 5;
console.log(num.toString());
```

+ 使用String()方法

&emsp;&emsp;有些值没有toString()，这个时候可以使用String()，比如：undefined和null。

```javascript
var num = 5;
console.log(String(num))
```

+ 使用拼接字符串的方式
&emsp;&emsp;当 + 两边一个操作符是字符串类型，一个操作符是其它类型的时候，会先把其它类型转换成字符串再进行字符串拼接，返回字符串。所以可以使用和空字符串拼接的方式实现转成字符串的操作：

```javascript
var num = 12;
num = num + ""
```

### 转换成数值类型

+ 使用Number()方法

&emsp;&emsp;Number()可以把任意值转换成数值，如果要转换的字符串中有一个不是数值的字符，返回NaN。

```javascript
console.log(Number('12')) //12
console.log(Number('12a')) //NaN
```

+ 使用parseInt()方法

&emsp;&emsp;使用该方法会解析到第一个不为数字的字符结束，如果第一个就是非数字字符，则返回NaN。

```javascript
var num1 = parseInt("12.3abc");  // 返回12，如果第一个字符是数字会解析知道遇到非数字结束
var num2 = parseInt("abc123");   // 返回NaN，如果第一个字符不是数字或者符号就返回NaN
```

+ 使用parseFloat()

&emsp;&emsp;parseFloat()把字符串转换成浮点数，它parseInt非常相似，不同之处是parseFloat会解析第一个"."，直到遇到第二个"."或者非数字结束。如果解析的内容里只有整数，解析成整数。

```javascript
var num1 = parseFloat("123.32abc") // 123.32
```

+ 使用运算符

```javascript
var str = '500';
console.log(+str);  // 取正
console.log(-str);  // 取负
console.log(str - 0);
```

### 转换成布尔类型

&emsp;&emsp;使用Boolean()方法，0、''(空字符串)、null、undefined和NaN会转换成false  其它都会转换成true。

```javascript
var str = "123"
console.log(Boolean(str))
```

# 操作符
## 算术运算符
&emsp;&emsp;+（加）、-（减）、*（乘）、/（除）、%（取余），和实际的数学运算符相同。

```javascript
console.log(5 + 2)  // 7
console.log(5 - 2)  // 3
console.log(5 * 2)  // 10
console.log(5 / 2)  // 2.5
console.log(5 % 2)  // 1
```

## 一元运算符
&emsp;&emsp;一元运算符：只有一个操作数的运算符。

+ 自加运算符（++）：自身加1，分为前置++和后置++，前置++就是先进行自加，然后再进行其它运算；后置++则相反：

```javascript
var i = 10
console.log(++i + 1) // 12
console.log(i++ + 1) // 12
```

+ 自减运算符（--）：自身减1，用法和自加相似。

## 逻辑运算符(布尔运算符)

+ &&（与）：两个操作数同时为true，结果为true，否则都是false
+ ||（或）：两个操作数有一个为true，结果为true，否则为false
+ !（非）取反

```javascript
console.log(true && false) // false
console.log(true || false) // true
console.log(!true) //false
```

## 关系运算符(比较运算符)

+ <（小于）、>（大于）、>=（大于等于）、<=（小于等于）、==（等于）、!=（不等于）、===（完全等于）、!==（不完全等于）

+ ==与===的区别：==只进行值得比较，===类型和值同时相等，则相等

```javascript
console.log('55' == 55);  // true
console.log('55' === 55); // false 值相等，类型不相等
console.log(55 === 55); // true
```

## 赋值运算符
&emsp;&emsp;=、+=、-=、*=、/=、 %=：

```javascript
var num = 0;
num += 5; //相当于  num = num + 5;
```

## 运算符的优先级
&emsp;&emsp;优先级从高到底：

1. ()：优先级最高
2. 一元运算符：++、--、!
3. 算数运算符：先 *、/、%，后 +、-
4. 关系运算符：>、>= 、< 、<=
5. 相等运算符：==、!=、===、!==
6. 逻辑运算符：先&&，后||
7. 赋值运算符

