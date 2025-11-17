# Javascript学习笔记


> —康思晟

## 学习背景
制作自己的静态网页

***
## 学习内容的目录

- Javascript 定义
- javascript 基础结构
- 变量
- 常见数据类型
- 运算符
- 条件语句
- 循环
- 函数
- 数组与对象
- DOM操作


***
## 学习内容

### JavaScript 定义

- JavaScript（简称 JS）是一门运行在浏览器端的脚本语言，用来实现网页中的交互效果。

- 点击按钮弹出提示

- 下拉菜单、轮播图

- 表单验证

- 与服务器通信（Ajax）

### JavaScript 基础结构

1. 内联式

        <button onclick="alert('Hello JS')">点我</button>

2. 内部脚本

        <script>
          console.log("Hello JS");
        </script>

3. 外部脚本

        <script src="app.js"></script>

### 变量

#### 1.var
    var a = 10;

#### 2.let
    let age = 18;
    age = 19;

#### 3.const
    const PI = 3.14;



### 常见数据类型

- Number（数字）

- String（字符串）

- Boolean（布尔值）

- Null

- Undefined

- Symbol

- BigInt

### 运算符
1. 算术运算

+, -, *, /, %

2. 自增自减

a++;
b--;

3. 比较运算

==     // 值相等
===    // 值和类型都相等


### 条件语句
    let age = 18;
    
    if (age >= 18) {
        console.log("成年");
    } else {
        console.log("未成年");
    }
### 循环
1. for循环

        for (let i = 0; i < 5; i++) {
            console.log(i);
        }

2. while循环

        let i = 0;
        while (i < 5) {
            console.log(i);
            i++;
        }
### 函数
1. 普通函数

        function add(a, b) {
          return a + b;
        }

2. 箭头函数

        const add = (a, b) => a + b;
### 数组与对象
1. 数组
        let arr = [1, 2, 3];
        console.log(arr[0]);

- 常用方法
arr.push(4);   // 尾部添加
arr.pop();     // 尾部删除
arr.shift();   // 开头删除
arr.unshift(0); // 开头添加



2. 对象

        let person = {
          name: "Tom",
          age: 18,
        };
        
        console.log(person.name);
### DOM操作
1. 获取内容

document.getElementById("box");
document.querySelector(".title");

2. 修改内容

element.innerHTML = "Hello";

3. 修改样式

element.style.color = "red";

4. 绑定事件

        button.onclick = function() {
          alert("clicked");
        };

***
## 参考资料
[bilibli](https://www.bilibili.com/video/BV1BT4y1W7Aw/?spm_id_from=333.1387.favlist.content.click&vd_source=fa477bfbb6c95eecbe18a26a8bebf61e)
[w3school](https://www.w3school.com.cn/js/index.asp)
[菜鸟教程](https://www.runoob.com/js/js-tutorial.html)