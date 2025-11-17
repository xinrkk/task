# HTML学习笔记


> —康思晟

## 学习背景
制作自己的静态网页

***
## 学习内容的目录

- HTML 定义
- HTML 基础结构
- 常用 HTML 标签
- 常用布局标签
- 表格 Table
- 表单 Form
***
## 学习内容

### HTML 定义

- HTML（HyperText Markup Language）超文本标记语言
用于构建网页结构，是网页的“骨架”。

- 标记语言（使用标签）

- 描述结构，不负责样式

- 由浏览器进行解析和渲染

### HTML 基础结构

< !DOCTYPE html >  
<html>  
<head>  
    <meta charset="UTF-8">  
    <title>我的网页</title>  
</head>  
<body>  
    <h1> Hello HTML </h1>   
</body>    
</html>  
    - < !DOCTYPE html >：声明 HTML5 文档类型
    - <html>：网页根元素
    - <head>：网页配置、标题、编码、引用 CSS/JS
    - <body>：网页可见内容（文本、图片、按钮等）  

### 常用 HTML 标签

#### 1.标题标签
    <h1>大标题</h1>
    <h2>二级标题</h2>
    <h3>三级标题</h3>

#### 2.段落与换行
    <p>这是一个段落。</p>
    <br> <!-- 换行 -->

#### 3.文本格式化
    <b>加粗</b>
    <i>斜体</i>
    <u>下划线</u>
    <mark>高亮</mark>

#### 4.超链接
    <a href="https://www.example.com" target="_blank">访问网站</a>

#### 5.图片
    <img src="image.jpg" alt="说明文本" width="300">

#### 6.列表
- 无序列表
        <ul>
          <li>苹果</li>
          <li>香蕉</li>
        </ul>


- 有序列表
        <ol>
          <li>第一步</li>
          <li>第二步</li>
        </ol>


### 常用布局标签
#### 1.块级布局容器——div
    <div>这是块级容器</div>

#### 2.行内容器——span
    <span>这是行内文本</span>

#### 3.语义化标签
| 标签          | 作用   |
| ----------- | ---- |
| `<header>`  | 头部   |
| `<nav>`     | 导航栏  |
| `<main>`    | 主内容  |
| `<section>` | 章节内容 |
| `<article>` | 文章内容 |
| `<footer>`  | 页脚   |


### 表格 Table
    <table border="1">
      <tr>
        <th>姓名</th>
        <th>成绩</th>
      </tr>
      <tr>
        <td>小明</td>
        <td>95</td>
      </tr>
    </table>  
    1. <table> 表格
    2. <tr> 表格行
    3. <th> 表头
    4. <td> 单元格数据

### 表单 Form
    <form action="/submit" method="POST">
        <label>姓名：</label>
        <input type="text" name="username">
        <label>密码：</label>
        <input type="password" name="pwd">
        <input type="submit" value="提交">
    </form>
- input type="text"

- input type="password"

- input type="checkbox"

- input type="radio"

- textarea

- select

***
## 参考资料
[bilibli](https://www.bilibili.com/video/BV1BT4y1W7Aw/?spm_id_from=333.1387.favlist.content.click&vd_source=fa477bfbb6c95eecbe18a26a8bebf61e)
[w3school](https://www.w3school.com.cn/html/index.asp)
