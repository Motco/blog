title: CSS 基础
tags: styleguide, CSS import
---

#### 1. CSS 定义与作用
- **层叠样式表(Cascading Style Sheets)**，是一种用来为结构化文档（如`HTML`文档或`XML`应用）添加样式（字体、间距和颜色等）的计算机语言，由
[**W3C**](https://www.w3.org/) 定义和维护。
- **`CSS` 作用：** 可用来决定文件的颜色、字体、排版等显示特性，最主要的目的是将文件的内容与显示分隔开来，改善文件结构
  - 文件的可读性加强
  - 文件的结构更加简洁
  - 文件的结构更加灵活
  - 作者和读者可以自己决定文件的显示
- **`CSS` 语法：** `CSS` 规则由两个主要的部分构成：选择器，以及一条或多条声明
  - 选择器通常是您需要改变样式的 `HTML` 元素
  - 每条声明由一个属性（property）和一个值（value）组成

&emsp;&emsp;&emsp;&emsp;![语法](http://www.w3school.com.cn/i/ct_css_selector.gif)<br/>
&emsp;&emsp;&emsp;&emsp;`selector {declaration1; declaration2; ... declarationN }`

#### 2. CSS 引入的3种方式
- **外部样式表：** 将 `CSS` 保存在一个独立的扩展名为 `.css` 的样式表文件中，再引用该样式表文件的方式有两种
  - 链接式：从HTML的
 `<link>` 元素中引用它。这种方法可以说是最好的，因为你可以使用一个样式表来设置多个文档的样式，并且需要更新 `CSS` 的时候只要在一个地方更新
      ```
        <head>
          <link rel="stylesheet" type="text/css" href="mystyle.css">
        </head>
      ```

  - 导入式：使用 `@import` 导入样式规则，这种方法既可以用在`<style>`标签里；也可以用在外部 `CSS` 文件中，但必须位于开头才能生效
      ```
        <style>
          @import url("文件路径");
          @import "style.css";
        </style>
      ```
  - 两种方式的区别
    -  `link` 是 `HTML` 标签，通过 `href` 属性来引入外部 `CSS` 样式表，会同页面
    一起加载；而 `@import` 属于 `CSS2.1` 新加样式，引用的文件则会等页面全部下载完毕后再被加载
    -  `link` 支持使用`JavaScript`控制DOM改变`CSS`样式；而 `@import` 不支持
    -  `link` 是`XHTML`标签，因此无兼容问题；而`@import`是在`CSS2.1`提出的（IE5以上才能识别），因此过低版本的浏览器不兼容


- **内部样式表：** 指不使用外部 `CSS` 文件，而是将 `CSS` 放置在`<style>`
  元素中，该元素包含在 HTML `head` 内。在某些情况下很有用（也许你正在使用一
  个内容管理系统，不能直接修改 `CSS` 文件）；但在网站中，`CSS` 将需要在每个页面重复，并且更新时要更改的多个位置
    ```
        <head>
        <style>
        body {
          background-color: lightblue;
        }

        h1 {
          color: navy;
          margin-left: 20px;
        }
        </style>
        </head>
    ```

- **内联样式：** 是仅影响一个元素的`CSS`声明，包含在`style` 属性中。它还混合了
  `CSS` 表示的样式信息和 `HTML` 的结构信息，使 `CSS` 难以阅读和理解，增加了维护难度
    ```
        <h1 style="color:blue;margin-left:30px;">This is a heading</h1>
    ```

#### 3. `CSS` 书写规范
- 通用格式规范
  - 缩进，使用`soft tab`（2个空格），不要使用 `tab` 或者混合 `tab` 和空格的缩进
    ```
    .selector {
      margin: 0;
      padding: 0;
    }
    ```
  - 分号，每个属性定义末尾都要加分号
    ```
    .element {
      width: 20px;
      height: 20px;
    }
    ```
  - 需要换行的情况
    + `{` 后和 `}` 前
    + 每个属性 `;` 后
    + 多个规则的分隔符 `,` 后
  - 需要加空格的情况
    + 属性值前
    + 属性值中的 `,` 后
    + 选择器 `>`, `+`, `~` 前后
    + 选择器与 `{` 之间
    + 注释 `/*` 后和 `*/` 前
  - 不需加空格的情况
    - 行末
    - 属性名和 `:` 之间
    - 多个规则的分隔符 `,` 前
    - 属性值中括号 `(` 后和 `)` 前
  - 注释，注释统一用 `/* ... */`
  - 需要加引号的情况
    - 属性的定义统一使用双引号
    - `url` 的内容要用引号
    ```
    .element:after {
      content: "";
      background-image: url("logo.png");
    }

    li[data-type="single"] {
      ...
    }
    ```
  - 颜色，使用16进制时用简写的小写字母
  - 不允许有空的规则
  - 去掉小数点前的 0
  - 属性值 `0` 后不要加单位
  - 用 `border: 0;` 代替 `border: none;`
  - 属性书写顺序，同一 `rule set` 下属性应按功能分组，并以`布局 > 尺寸 > 文本相关 > 视觉效果` 的顺序书写 <br/><br/>
*see more at [Code Guide @AlloyTeam](http://alloyteam.github.io/CodeGuide/#css)，[styleguide @fex-team](https://github.com/fex-team/styleguide), [cnblog: 书写规范](http://www.cnblogs.com/iceyhu/p/4424150.html) and [勤奋蜂前端编码规范](https://www.gitbook.com/book/proyang/codeguide/details)*

#### 4. 文件路径
- 如何在饥人谷Js bin中展示图片
  - 上传本地图片到网络图床，获取外链，通过 `<img src="..." alt="image">` 展示或用`CSS`背景图实现
  - 开启本地服务器，通过相对路径读取
  - 使用网络资源，获取现有网络图片链接
- 文件路径
  - `css/a.css` 相对路径，当前工作目录的子目录`CSS`下的`a.css`文件
  - `./css/a.css` 同上
  - `b.css` 当前工作目录下的`b.css`文件
  - `../imgs/a.png` 当前工作目录的父目录下的同级目录`imgs`下的`a.png`文件
  - `/Users/hunger/project/css/a.css` 绝对路径，从根目录开始到`a.css`文件
  - `/static/css/a.css` 绝对路径，从服务端根目录开始到`a.css`文件
  - `http://cdn.jirengu.com/kejian1/8-1.png` 绝对路径，指向网域下的`8-1.png`图片



