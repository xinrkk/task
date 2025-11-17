# CSS学习笔记


> —康思晟

## 学习背景

制作静态网页

## 学习内容的目录

- CSS 定义
- CSS 基础结构
- CSS选择器
- 颜色与单位
- 文字样式
- 盒子模型
- 布局相关属性
- 背景样式
- 边框
- 动画

***

## 学习内容

### CSS 定义

- CSS（Cascading Style Sheets）层叠样式表，用来控制 HTML 的外观样式，包括颜色、字体、布局、动画等。

### CSS 基础结构

1. 内联样式  

        <p style="color:red;">文字</p>
2. 内部样式

        <style>
        p {
          color: red;
        }
        </style>
3. 外部样式

    <link rel="stylesheet" href="style.css">


### CSS选择器

#### 1.基本选择器

    /* 标签选择器 */
    p {}
    /* 类选择器 */
    .box {}
    /* id 选择器 */
    #header {}
    /* 通配符 */
    * {}


#### 2.基本选择器

    /* 后代选择器 */
    div p {}
    /* 子代选择器 */
    div > p {}
    /* 兄弟选择器 */
    h1 + p {}
    h1 ~ p {}

#### 3.属性选择器
input[type="text"] {}
a[target="_blank"] {}

### 颜色与单位

#### 1.颜色

- 英文名：red
- 十六进制：#ff0000
- GB：rgb(255,0,0)
- 透明度：rgba(255,0,0,0.5)

#### 2.单位

- px：像素

- em：相对父元素字体

- rem：相对根元素字体（推荐）

- %：百分比

- vw / vh：视口宽高

### 文字样式
    p {
      font-size: 16px;
      font-weight: bold;
      color: #333;
      line-height: 1.5;
      text-align: center;
      text-decoration: underline;
    }


### 盒子模型

元素包含：

1. content

2. padding

3. border

4. margin

    - .box {
      width: 200px;
      padding: 20px;
      border: 1px solid #000;
      margin: 10px;
      }
### 布局相关属性
1. display

- display: block;
display: inline;
display: inline-block;
display: flex;   /* 最常用 */
display: grid;   /* 现代布局 */
2. Flex 布局

- .container {
  display: flex;
  justify-content: center; /* 主轴对齐 */
  align-items: center;     /* 侧轴对齐 */
  }
3. Grid 布局

- .grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 10px;
  }
### 背景样式

    .box {
      background-color: #f0f0f0;
      background-image: url("bg.jpg");
      background-size: cover;
      background-repeat: no-repeat;
    }
### 边框
    .box {
      border: 1px solid #000;
      border-radius: 10px;
    }

### 动画
1. 过渡
    @keyframes move {
      from { left: 0; }
      to { left: 100px; }
    }

    .box {
      position: relative;
      animation: move 2s infinite alternate;
    }
2. 动画

    @keyframes move {
      from { left: 0; }
      to { left: 100px; }
    }

    .box {
      position: relative;
      animation: move 2s infinite alternate;
    }

***

## 参考资料

[bilibli](https://www.bilibili.com/video/BV1BT4y1W7Aw/?spm_id_from=333.1387.favlist.content.click&vd_source=fa477bfbb6c95eecbe18a26a8bebf61e)
[w3school](https://www.w3school.com.cn/css/index.asp)
