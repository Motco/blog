## <a name="jp0">CSS选择器</a>
&emsp;&emsp;[1. `class`和`id`的使用](#jp1)<br/>
&emsp;&emsp;[2. CSS选择器类别](#jp2)<br/>
&emsp;&emsp;[3. CSS样式优先级](#jp3)<br/>
&emsp;&emsp;[4. CSS链接的四种状态](#jp4)<br/>



#### <a name="jp1">1. `class` 和 `id` 的使用场景</a>
- 类选择器（Class selectors）
  - 通过设置元素的 `class` 属性，可以为元素指定类名，类名由开发者自己指定
  - 在写样式表时，类选择器是以英文句号 `.` 开头的
  - 为了将类选择器的样式与元素关联，必须将 `class` 指定为一个适当的值
  - 文档中的多个元素可以拥有同一个类名
    ```
    <h1 class="important">
        This heading is very important.
    </h1>

    <p class="important">
        This paragraph is very important.
    </p>
    ```
    选择所有类名为`important`的元素：<br/>
    ```
    .important {
        color: red;
    }
    ```


- `ID`选择器（ID selectors）
  - 通过设置元素的 `id` 属性为该元素制定`ID`，`ID`名由开发者指定
  - 在写样式表时，`ID` 选择器是以 `#` 开头的
  - 每个`ID`在文档中必须是唯一的 <br/>
    ```
    <p id="intro">
        This is a paragraph of introduction.
    </p>
    ```
    选择`ID`为`intro`的元素：<br/>
    ```
    #intro {
        font-weight: bold;
    }
    ```


#### <a name="jp2">2. CSS选择器类别</a> [TOP](#jp0)
- 选择器的类别<br/>
  *refer to [Selectors introduction | MDN](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Selectors)*
  ![53-15.png](http://www.z4a.net/images/2017/09/19/53-15.png)

- 常用的选择器
  - 类选择器：`.class {color: lightbule; }`
  - `id`选择器：`#id {color: lightbule; }`
  - 通用选择器：`* {color: lightbule; }`
  - 标签选择器：`p {color: lightbule; }`
  - 组合使用
    - `#nav li {color: lightbule; }`
    - `p.class.class {color: lightbule; }`
    - `div[class=error] {color: lightbule; }`

- 几种常见伪类选择器<br/>
  *refer to [Pseudo-classes and pseudo-elements | MDN](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Introduction_to_CSS/Pseudo-classes_and_pseudo-elements)*
  - `:checked`表示任何处于选中状态的`radio`，`checkbox`，或`select`元素中的`option`元素
    + `input[type="radio"]:checked` 表示页面上的所有选中的radio按钮
    + `input[type="checkbox"]:checked` 表示页面上的所有选中的checkbox按钮
    + `option:checked` 表示页面上的所有选中的select的选项
      ```
      /* any "checkable" element */
      :checked {
          width: 50px;
          height: 50px;
      }

      /* only radio elements */
      input[type="radio"]:checked {
          margin-left: 25px;
      }

      /* only checkbox elements */
      input[type="checkbox"]:checked {
          display: none;
      }

      /* only option elements */
      option:checked {
          color: red;
      }
      ```
  - `:first-child` 代表了父元素下的第一个元素
    ```
    /* HTML示例 */
    <div>
        <p>This p is styled, as it is a p AND the first child of its parent.</p>
        <p>This p is not styled; it is not the first child!</p>
    </div>
    ```
    以下`CSS`只对第一个`p`标签生效：
    ```
    p:first-child {
        color: lime;
        background-color: black;
        padding: 5px;
    }
    ```
  - `:nth-child(an+b)` 匹配在父元素下第 `an+b` 个节点的元素，`n` 为正值或零，`a`和`b`都必须为整数
    ```
      0n+3，匹配兄弟元素中的第三个；
      1n+0，匹配父级下的每一个元素；
      2n+0，匹配第2，4，6...个元素，可用`even`代替；
      2n+1，匹配第1，3，5...个元素，可用`odd`代替；
    ```
    + `tr:nth-child(2n+1)`或`tr:nth-child(odd)` - - 匹配HTML表格中的奇数行；
    + `tr:nth-child(2n)`或`tr:nth-child(even)` - - 匹配HTML表格中的偶数行;
    + `span:nth-child(1)` - - 匹配子元素中第一个且为`span`的标签，同`:first-child`；
    + `span:nth-child(-n+3)` - - 匹配前三个子元素中的`span`标签

  - `:nth-last-child(an+b)` 语法同上，不过是从结尾处开始反序计数

  - `:first-of-type` 匹配兄弟元素各种类别中第一次出现的元素
    ```
    /* HTML示例 */
    <div>
      <span>This span is first and will be lime</span>
      <span>This span is second and will bot</span>
      <span>what about this <em>nested element(new one and will be lime)</em></span>
      <strike>This is another type(new one and will be lime)</strike>
      <span>This span is fourth.</span>
    </div>
    ```
    以下`CSS`只对同类别的第一次出现的的标签生效：
    ```
    div :first-of-type {
      color: lime;
    }
    ```

  - `:focus`通过键盘或鼠标激活焦点时生效（例如表单输入）；和`:active`的差异分析
    + 默认情况下，`:active`和`:focus`都处于未触发状态；
    + 通过`tab`键循环来**选中**可聚焦元素（`a`，`input`，`textarea`等）,会触发`:focus`但不影响`:active`；
    + 当**点击**（鼠标点击或选中后按`space`键）不可聚焦元素时，会触发`:active`，不影响`:focus`；
    + 当**点击**可聚焦元素时，会同时触发`:active`和`:focus`；
    + 按照先后定义的优先级规则，若`:focus`位于之后，则会覆盖`:active`使其失效

      *refer to [What is the difference between :focus and :active? | stackoverflow](https://stackoverflow.com/questions/1677990/what-is-the-difference-between-focus-and-active)*


- 选择器示例
  ```
    #header{ }                     - - id 为 header 下的所有元素
    .header{ }                     - - 类为 header 下的所有元素
    .header .logo{ }               - - 类为 header 下所有 logo 类下的元素
    .header.mobile{ }              - - 同时在同级类 header 和 mobile 下的元素
    .header p, .header h3{ }       - - 类为 header 下所有 p 标签和 h3 标签中的元素
    #header .nav>li{ }             - - id 为 header 下所有 nav 类下的第一级 li 标签中的元素
    #header a:hover{ }             - - id 为 header 下所有 a:hover 伪类中的元素
    #header .logo~p{ }             - - id 为 header 下所有 logo 类之后的同级元素中所有含 p 标签中的元素
    #header input[type="text"]{ }  - - id 为 header 下所有 input 标签中属性类型为 text 的元素

    div:first-child       - - 匹配父级元素下的第一个子元素且该元素为 div 的元素；
    div:first-of-type     - - 匹配兄弟元素中 div 元素类别中的第一个 div ；
    div :first-child      - - 匹配 div 元素下第一个子元素；
    div :first-of-type    - - 匹配 div 元素下每种子元素类别中的第一个元素
  ```

#### <a name="jp3">3. CSS 样式优先级</a> [TOP](#jp0)
- 一般而言，样式优先级可通过权重来体现，按照 a-b-c-d 的类别及次序计算权重

        *              {}  /* a=0 b=0 c=0 d=0 -> specificity = 0,0,0,0 */
        li             {}  /* a=0 b=0 c=0 d=1 -> specificity = 0,0,0,1 */
        li::first-line {}  /* a=0 b=0 c=0 d=2 -> specificity = 0,0,0,2 */
        ul li          {}  /* a=0 b=0 c=0 d=2 -> specificity = 0,0,0,2 */
        ul ol+li       {}  /* a=0 b=0 c=0 d=3 -> specificity = 0,0,0,3 */
        h1 + *[rel=up] {}  /* a=0 b=0 c=1 d=1 -> specificity = 0,0,1,1 */
        ul ol li.red   {}  /* a=0 b=0 c=1 d=3 -> specificity = 0,0,1,3 */
        li.red.level   {}  /* a=0 b=0 c=2 d=1 -> specificity = 0,0,2,1 */
        #x34y          {}  /* a=0 b=1 c=0 d=0 -> specificity = 0,1,0,0 */
        style=""           /* a=1 b=0 c=0 d=0 -> specificity = 1,0,0,0 */

  - a：计值 n，0，0，0；指代内联样式
  - b：计值 0，n，0，0；指代`id`选择器
  - c：计值 0，0，n，0；指代其他属性（class，属性选择器）和伪类（pseudo-classes）
  - d：计值 0，0，0，n；指代标签选择器和伪元素（pseudo-elements）<br/><br/>
    ***note:***
  - 通配符`*`，子选择器，相邻选择器等，计值 0，0，0，0
  - 类别在前的拥有更高的优先级
  - 同类别中，权重更大的拥有更高的优先级
  - 同一元素中，后定义的样式规则优先于先定义的<br/><br/>
    *refer to [specified value | w3](https://www.w3.org/TR/CSS2/cascade.html#specified-value)*

- `CSS` 的继承性，指的是应用在一个标签上的那些 `CSS` 属性被传到其子标签上
  - 最近的“祖先样式”比其他“祖先样式”优先级高
    ```
    <!-- 类名为 son 的 div 的 color 为 blue -->
    <div style="color: red">
        <div style="color: blue">
            <div class="son"></div>
        </div>
    </div>
    ```
  - “直接样式”比“祖先样式”优先级高
    ```
    <!-- 类名为 son 的 div 的 color 为 blue -->
    <div style="color: red">
        <div class="son" style="color: blue"></div>
    </div>
    ```
    *refer to [CSS 样式优先级 | segmentfault](https://segmentfault.com/a/1190000003860309)*

- `!important`规则将优先于其他正常声明的规则，不推荐使用该规则，使用后会破坏正常优先级次序，不利于的debug
  - 应该使用的情况
    + 存在设定了全站样式的CSS文件，同时在元素上使用了内联样式；此时可在全局的`CSS`文件中写一些`!important`的样式来覆盖掉那些直接写在元素上的内联样式
    + 类似在外层有 `#id` ，要使 `.class` 的段落变成红色的情况
      ```
        #id p { color: blue; }

        p.class { color: red !important; }
      ```
  - 覆盖 `!important` 规则
    + 再添加一条带 `!important` 的CSS规则，给这个给选择器更高的优先级（添加一个标签，`#id`或`.class`）
      ```
        table td    { height: 50px !important; }
        .myTable td { height: 50px !important; }
        #myTable td { height: 50px !important; }
      ```
    + 使用相同的选择器，但是置于已有的样式之后
      ```
        td { height: 50px !important; }
      ```
    *refer to [Specificity - CSS | MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity)*

#### <a name="jp4">4. CSS 链接的四种状态</a> [TOP](#jp0)
- 链接的四种状态
  + `a:link` 未访问的状态
  + `a:visited` 已访问的状态
  + `a:hover` 鼠标悬停时的状态
  + `a:active` 点击时那一刻的状态

- 四个伪类具有相同的权重，因此依据先后定义的顺序来确定优先级，后定义的优先级更高
  - 按照`w3c`规定的顺序为：`a:link`/`a:visited` - `a:hover` - `a:active`；（常被助记为LoVe&HAte）
    + 未访问链接的两种属性：`a:link`和`a:hover`，若`a:link`在后，即使处于悬停状态，也会覆盖`a:hover`的定义而致其失效；
    + 已访问链接的两种属性：`a:visited`和`a:hover`,若`a:visited`在后，同样地，也会覆盖`a:hover`的定义；
    + 若`a:hover`位于点击时的状态`a:active`之后，悬停状态也会覆盖点击时的激活状态而致其失效；
    + 而`a:link`和`a:visited`的前后顺序并不影响`a:visited`后的状态
