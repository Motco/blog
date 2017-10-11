title: CSS浮动与定位
---

#### 1. `float` 的影响
- `float` 属性指定一个元素应沿其容器的左侧或右侧放置，允许文本和内联元素环绕它
  - 浮动的元素可以向左或向右移动，直到它的外边缘碰到块框或另一个浮动元素的边框为止
  - 由于浮动元素不在文档的普通流中，所以文档的普通流中的块框表现得像浮动元素不存在一样

- `float` 属性的影响
  - 父元素，如果父元素没有设置高度，且其子元素都为浮动元素，那么其高度会发生坍塌
  - 其他浮动元素，其它浮动元素会贴在浮动元素的后面，如果剩余的空间不够，那么其它元素会分配到下一行
  - 普通元素，普通元素会占据浮动元素原来的位置
  - 文字，文字能识别到浮动元素的存在，会围绕着浮动元素

  *refer to [CSS属性：float | MDN ](https://developer.mozilla.org/en-US/docs/Web/CSS/float)*

#### 2. 清除浮动
- 清除浮动指当一个盒子使用 `float` 属性，解决其父级对象盒子高度无法撑开的问题
- 清除浮动的方法
  - 父元素设置 `overflow: hidden;` 会自动适配高度，即创建一个[「BFC」](https://www.w3.org/TR/CSS22/visuren.html)
    + 需要配合 `width` 或者 `*zoom: 1;` 触发 `ie` 的 `haslayout` 属性来兼容 `ie6` 和 `ie7`
    + 超出的内容会被隐藏，因此不宜和 `position` 配合使用
    + 若设置成 `overflow: auto;`，内容超出时会出现滚动条

  - 父元素中的最后一个子元素设为 `<br clear="both"/>`，或其他空元素，样式设为 `clear: both;`
    + 当 `clear` 属性应用于非浮动块时，会将它的 `border edge` 移动到所有相关浮动元素
    `margin edge` 的下方，导致[「margin collapsing」](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Mastering_margin_collapsing)不起作用
    + 当 `clear` 属性应用于浮动元素时，会将它的 `margin edge` 移动到所有相关浮动元素
    `margin edge` 的下方，导致后面的浮动元素的位置无法高于它之前的元素

  - 父元素设置伪元素 `:after`，同时添加以下属性
    ```
      .parent-container:after {
        content:"";     /* 内容须设为空 */
        display:block;
        clear:both;
      }
      .parent-container {
        *zoom: 1;       /* 触发ie6，7的 haslayout 属性 */
      }
    ```
  - 父元素设置 `float`，同子元素一起浮动，较少使用
  - 父元素设置 `height`，适用于浮动元素高度确定的情况，较少使用
  - 父元素设置 `display` 属性值为 `table`，`table-cell`，`inline-block`等，不推荐使用

  *refer to [float | W3C](https://www.w3.org/TR/CSS22/visuren.html#flow-control)，[清理浮动的几种方法](http://w3help.org/zh-cn/casestudies/001)，[那些年我们一起清除过的浮动 | iyunlu](http://www.iyunlu.com/view/css-xhtml/55.html)*

#### 3. `CSS`定位
- `CSS`有三种基本定位机制，除非专门指定，否则所有框都在普通流中定位：
  - 普通流 （默认定位 `static` 和相对定位 `relative`）
  - 浮动 （`float`）
  - 绝对定位 （`absolute`）

  `CSS` 定位相关属性：

    属性 | 描述
    :-- |:--
    position | 将元素放置到一个静态的、相对的、绝对的、或固定的位置中
    top/right/bottom/left | 定义元素的外边距边界与其包含块边界之间的偏移
    overflow | 当元素的内容溢出其区域时的显示方式
    clip | 定义一个剪裁矩形，用来剪裁绝对定位元素
    vertical-align | 定义元素的垂直对齐方式
    z-index | 定义元素的堆叠次序

- `position` 属性规定的元素定位类型
  - `static`
    + 默认属性，指定元素使用文档的普通流
    + 此时 `top`, `right`,` bottom`, `left` 和 `z-index` 属性无效
  - `relative`
    + 生成相对定位的元素，相对于其正常位置进行偏移
    + 元素位置通过 `left`, `top`, `right` 以及 `bottom` 的值来指定
    + 元素仍会占据原来的空间，不会破坏页面原始布局
    + 可以通过设置 `z-index` 属性来控制这些框的堆叠次序
  - `absolute`
    + 生成绝对定位的元素，相对于最近的非 `static` 定位的祖先元素进行定位
    + 绝对定位的元素可以设置外边距 `margin`，且不会与其他边距合并
    + 不会预留空间，脱离了文档的普通流，可以覆盖页面上的其它元素
    + 可以通过设置 `z-index` 属性来控制这些框的堆叠次序
  - `fixed`
    + 生成绝对定位的元素，类似 `absolute`，不过是相对于浏览器窗口进行定位
    + 页面顶部的导航条，回到顶部按钮等基本采用此定位方式

    其他全局值：
  - `inherit`
    + 从父元素继承，`IE8`之前不支持
  - `initial`
    + 设置 `CSS` 属性为它的默认值，可作用于任何 `CSS` 样式
  - `unset`
    + 如果该属性是默认继承属性，该值等同于 `inherit`
    + 如果该属性是非继承属性，该值等同于 `initial`

  *refer to [CSS定位 | w3school](http://www.w3school.com.cn/css/css_positioning.asp)，[CSS定位浮动 | segmentfault](https://segmentfault.com/a/1190000003856280#articleHeader2)，[chokcoco:CSS进阶系列 | github](https://github.com/chokcoco/iCSS)，[CSS属性position | MDN](https://developer.mozilla.org/zh-CN/docs/Web/CSS/position)*

- `z-index` 属性设置元素的堆叠顺序
  + 拥有更高堆叠顺序的元素总是会处于堆叠顺序较低的元素的前面，即覆盖较小的那个
  + 元素可拥有负的 `z-index` 属性值，会在未设置 `z-index` 元素的后面
  + 仅能在定位元素（即 `position` 属性值是非 `static` 的元素）上奏效

  *refer to [理解CSS的z-index属性 | MDN](https://developer.mozilla.org/zh-CN/docs/Web/Guide/CSS/Understanding_z_index)，[层叠上下文 | MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index/The_stacking_context)*

- `position: relative` 和负 `margin` 的区别
  + `position: relative`元素偏移时，仍会占据原来的空间，不会破坏页面原始布局
  + 负 `margin` 偏移时，元素占据的空间会随着 `margin` 绝对值的增大而减小，当前容器的布局也会做出相应变化

#### 4. `BFC` 块格式化上下文
- 块格式化上下文（block formatting context）是`Web`页面的可视化`CSS`渲染出的一部分。它是一个独立的渲染区域，规定了内部块级元素如何布局，并且与这个区域外部毫不相干。
- `BFC` 由以下任意项生成
  - `float` 属性值不为 `none`
  - `overflow` 属性值不为 `visible`
  - `position: absolute | fixed`
  - `display: inline-block | table-cell | table-caption`
  - ...

- `BFC` 的作用
  - 防止两个相邻块级盒子垂直外边距折叠
  - 清除浮动，避免父元素高度坍塌
  - 避免文字环绕浮动元素
  - 多列布局

  *refer to [块格式化上下文 | MDN](https://developer.mozilla.org/zh-CN/docs/Web/Guide/CSS/Block_formatting_context)，[译文：理解CSS中的块级格式化上下文 | segmentfault](https://segmentfault.com/a/1190000003068557#articleHeader5)，[布局方案之-多列布局 | csdn](http://blog.csdn.net/u012999771/article/details/49253059)*

#### 5. `Margin Collapsing` 外边距合并
- 外边距合并指的是，当两个垂直外边距相遇时，它们将形成一个外边距。

    合并后的外边距的高度为两个发生合并的外边距的高度中的较大者；若存在负值，将取两者之和。可分以下三种情况：
  - 相邻的兄弟元素
    + 第一个元素的下外边距与第二个元素的上外边距会发生合并
  - 父元素与子元素（没有内边距或边框隔开）
    + 第一个子元素的上外边距和父元素的上外边距
    + 最后一个子元素的下外边距和父元素的下外边距
  - 空元素（没有边框或填充）
    + 自身上下外边距重合
    + 如果这个外边距遇到另一个元素的外边距，它还会发生合并

- 外边距不合并的方法

  只有普通文档流中块框的垂直外边距才会发生外边距合并，行内框、浮动框或绝对定位之间的外边距不会合并。因此可采用以下方法：
  - 设置 `inline-block`，浮动元素`float`，或绝对定位 `absolute | fixed`
  - 针对父子元素，还可以给父元素设置 `border` 或 `padding`，或设置 `overflow: hidden | scroll | auto;`

  父子元素外边距合并[示例](http://js.jirengu.com/hiranaloka/1/edit)：

    ![0736s.png](http://www.z4a.net/images/2017/10/09/0736s.png)

  *refer to [CSS 外边距合并 | w3school](http://www.w3school.com.cn/css/css_margin_collapsing.asp)*


  [「代码1」](http://js.jirengu.com/dovoholuve/1/edit)，
  [「代码2」](http://js.jirengu.com/gufepicano/2/edit)，
  [「代码3」](http://js.jirengu.com/fivitigelu/2/edit)，
  [「代码4」](http://js.jirengu.com/wupimeduru/2/edit)
