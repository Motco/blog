title: CSS常见样式1
---

#### 1. 行内元素与块级元素
- HTML中的元素可分为两种类型：内联元素与块级元素，这些元素的类型是通过文档类型定义（DTD）来指明；还可以通过 `display: block` 或 `display:inline`来转换块级元素和内联元素
- 行内元素(`inline element`)，又称内联元素
  - 一般行内元素只能包含文本和其他行内元素
  - 行内元素默认在一行，不会以新行开始
  - 宽度(width)、高度(height)、内边距(padding)和外边距(margin)都不可改变
  - 宽度默认是它的文字和图片的宽度，不可改变

    以|下|均|为|行|内|元|素
    :--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:
    `<a>` | `<b>` | `<big>` | `<i>` | `<small>` | `<tt>` | `<abbr>` | `<acronym>`
    `<cite>` | `<code>` | `<dfn>` | `<em>` | `<kbd>` | `<strong>` | `<samp>` | `<time>`
    `<var>` | `<bdo>` | `<br>` | `<img>` | `<map>` | `<object>` | `<q>` | `<script>`
    `<span>` | `<sub>` | `<sup>` | `<button>` | `<input>` | `<label>` | `<select>` | `<textarea>`


- 块级元素(`block element`)
  - 一般块级元素可以包含行内元素和其他块级元素
  - 默认情况下，块级元素会新起一行
  - 宽度，高度和内外边距都可控制
  - 宽度默认是它容器的100%，除非设定一个宽度

    语义|块级元素|块级元素|语义
    :--:|:--:|:--:|:--:
    联系方式信息 | `<address>` | `<article>` | 文章内容
    伴随内容 | `<aside>` | `<audio>` | 音频播放
    块引用  | `<blockquote>` | `<canvas>` | 绘制图形
    定义列表中定义条目描述 | `<dd>` | `<div>` |文档分区
    定义列表 |`<dl>` | `<fieldset>` | 表单元素分组
    图文信息组标题 | `<figcaption>` |`<figure>` | 图文信息组
    区段尾或页尾 | `<footer>` | `<form>` | 表单
    标题级别 | `<h1>`, `<h2>`<br/>`<h3>`, `<h4>`<br/>`<h5>`, `<h6>`<br/> | `<header>` | 区段头或页头
    标题组 | `<hgroup>` | `<hr>` | 水平分割线
    不支持脚本或禁用<br/>脚本时显示的内容 | `<noscript>` | `<ol>` |有序列表
    表单输出 | `<output>` | `<p>` | 段落
    一个页面区段 | `<section>` | `<table>` | 表格
    表脚注 | `<tfoot>` | `<ul>` | 无序列表
    视频 | `<video>` | - | -

#### 2. CSS继承
- `CSS` 的继承性，指的是应用在一个标签上的那些 `CSS` 属性被传到其子标签上。当一个元素的继承属性(inherited property)没有指定值时，则取父元素计算值(computed value)
  - 典型例子 `color` 属性 :
    ```
      p { color: green }
    ```
    HTML：
    ```
      <p>This paragraph has <em>emphasized text</em> in it.</p>
    ```
    文本 `"emphasized text"` 将会呈现为绿色，因为 `em` 元素继承了 `p` 元素 `color` 属性的值

  - 以下都是可继承属性：

    *refer to [Which CSS properties are inherited? | stackoverflow](https://stackoverflow.com/questions/5612302/which-css-properties-are-inherited)*
    + border-collapse
    + border-spacing
    + caption-side
    + color
    + cursor
    + direction
    + empty-cells
    + font-family
    + font-size
    + font-style
    + font-variant
    + font-weight
    + font-size-adjust
    + font
    + font-stretch
    + letter-spacing
    + line-height
    + list-style-image
    + list-style-position
    + list-style
    + list-style-type
    + orphans
    + quotes
    + tab-size
    + text-align
    + text-align-last
    + text-indent
    + text-decoration-color
    + text-justify
    + text-shadow
    + text-tranform
    + visibility
    + white-space
    + widows
    + word-break
    + word-spacing
    + word-wrap

- 非继承属性(reset property),当元素的一个非继承属性(reset property)没有指定值时，则取属性的初始值(initial value)
  - 典型例子如 `border` 属性：
    ```
      p { border: medium solid }
    ```
    HTML：
    ```
      <p>This paragraph has <em>emphasized text</em> in it.</p>
    ```
    文本 `"emphasized text"` 没有边框，因为`border-style`属性的初始值为 `none`

  - 以下都是非继承属性，大多与定位，浮动，盒模型相关：

    *refer to [CSS 哪些属性默认会继承, 哪些不会继承? | segmentfault](https://segmentfault.com/q/1010000000269211)*
    + border (border-color , border-style , border-width , border-spacing...)
    + padding (padding-left , padding-right , padding-top , padding-bottom)
    + margin (margin-left , margin-right , margin-top , margin-bottom)
    + outline (outline-color , outline-style , outline-width)
    + background (background-color , background-image , background-position...)
    + height（min-height , max-height）
    + width（min-width , max-width）
    + clip
    + display
    + overflow
    + position
    + float
    + z-index
    + clear
    + table-layout
    + vertical-align
    + unicode-bidi
    + content
    + text-decoration
    + page-break-after (page-break-before)
    + left (right , top , bottom)

### 3. 知识扩展
- 块级元素和行内元素水平居中实现方法
  - 块级元素水平居中：`margin:0 auto;`
  - 行内元素水平居中：`text-align:center;`

- 单行文本溢出加 `...` 如何实现?
  ```
    white-space: nowrap; /* 超过宽度不换行 */
    overflow: hidden; /* 超过宽度字符隐藏 */
    text-overflow: ellipsis; /* 超过宽度字符隐藏后变成“...” */
  ```

- `px`, `em`, `rem`有什么区别?
  - `px` 在缩放页面时无法调整那些使用它作为单位的字体、按钮等的大小
  - `em` 的值不是固定的，会继承父级元素的字体大小，代表倍数
  - `rem` 的值不是固定的，始终是基于根元素 `<html>` 的，也代表倍数

  *refer to [CSS：区别px、em、rem | segmentfault](https://segmentfault.com/a/1190000005936910)*

- 字体设置
  - `font` - 简写属性，在一个声明中设置所有的字体属性
  - `font-family` - 设置字体系列
  - `font-size` - 设置字体的尺寸
  - `font-style` - 设置字体样式
  - `font-variant` - 以小型大写字体或者正常字体显示文本
  - `font-weight` - 设置字体的粗细
  - `line-height` - 设置行高（默认垂直居中性）

  示例
  ```
    body{
      font: 12px/1.5 tahoma,arial,'Hiragino Sans GB','\5b8b\4f53',sans-serif;
    }
  ```
  - `12px/1.5`：设置字体12px，行高1.5倍
  - `tahoma,arial,'Hiragino Sans GB','\5b8b\4f53',sans-serif`
    - 设置字体样式，若字体不存在，则按照先后顺序调用
    - 字体间有空格时要添加引号
    - `\5b8b\4f53`是字体的`unicode`编码格式，代表的是宋体
