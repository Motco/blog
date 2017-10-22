title: CSS常见样式2
---

#### 1. `text-align`的特性
- `text-align`常用于盒子里的文字、图片等内容居左、居中或局右
  - `text-align: center;`使父容器下元素居中，包括一般行内元素，行内块级元素和块级元素的内文本等
  - `text-align: justify;`可以使文本两端对齐
  - 其他属性`left`，`right`，

#### 2. 盒模型
- CSS盒模型是网页布局的基础，每一个HTML元素都可看作被矩形框所包裹，W3C标准盒模型如下：
![w3c盒模型](https://www.w3.org/TR/CSS22/images/boxdim.png)
  - IE盒模型中`width`和`height`的尺寸包含`content`、`padding`和`border`
  - w3c盒模型中`width`和`height`的尺寸仅含`content`，不包括`padding`和`border`

- `box-sizing: border-box;`的特性：使`width`和`height`的尺寸包含`content`、`padding`和`border`，即使浏览器渲染采用IE盒模型的效果



#### 3. `line-height`的特性，
- `line-height`用来控制行与行之间的垂直间距，按照值的不同，继承情况有所差别
  - 值为`<number>`，继承元素中的`line-height`会随着`font-size`作相应比例缩放
    ```
    body {
      font-size: 16px;
      line-height: 2;       /* 计算的值为16px * 2 = 32px */
    }

    h1 {font-size: 32px; }  /* 继承的值为32px * 2 = 64px */
    p {font-size: 12px; }   /* 继承的值为12px * 2 = 24px */
    ```

  - 值为`normal`，同上，桌面浏览器的值约为1.2，取决于元素的`font-family`
    ```
    body {
      font-size: 16px;
      line-height: normal;  /* 计算的值约为16px * 1.2 = 14.4px */
    }

    h1 {font-size: 32px; }  /* 继承的值约为32px * 1.2 = 38.4px */
    p {font-size: 12px; }   /* 继承的值约为16px * 1.2 = 14.4px */
    ```

  - 值为`<percentage>`，父容器中的`font-size`的值和`line-height`的百分比的计算值会被层叠下去的元素所继承，不会作出相应缩放
    ```
    body {
      font-size: 16px;
      line-height: 200%;    /* 计算的值为16px * 200% = 32px */
    }

    h1 {font-size: 32px; }  /* 继承的值为16px * 200% = 32px */
    p {font-size: 12px; }   /* 继承的值为16px * 200% = 32px */
    ```

  - 值为`<length>`，同上，长度值会被层叠下去的元素所继承，不会作出相应缩放
    ```
    body {
      font-size: 16px;
      line-height: 20px;    /* 指定值为20px */
    }

    h1 {font-size: 32px; }  /* 继承的值为20px */
    p {font-size: 12px; }   /* 继承的值为20px */
    ```

    *refer to [深入了解css的行高Line Height属性 | cnblogs](http://www.cnblogs.com/fengzheng126/archive/2012/05/18/2507632.html)*


#### 4. `inline-block`的特性
- `display：inline-block`属性和行内元素类似，不过可以设置`width`和`height`；默认情况下，`inline-block`元素间换行排列或存在空格都会导致实际呈现时出现间距

  消除间距的方法：
  - 去除`inline-block`元素间空格
    ```
      /* 无空格，代码可读性差 */
      <div class="count">
        <span>123</span><span>456</span>
      </div>

      /* 无空格 */
      <div class="count">
        <span>123</span
        ><span>456</span>
      </div>

      /* 无空格，借助HTML注释 */
      <div class="count">
        <span>123</span><!--
        --><span>456</span>
      </div>
    ```

  - 使用`font-size`，父级元素设置`font-size: 0;`，而`inline-block`设置字体所需的字体大小`font-size: 16px`
    ```
      <div class="count">
        <span>123</span>
        <span>456</span>
      </div>

      /* CSS样式 */
      .count {
        font-size: 0;
      }
      .count span {
        font-size: 16px;
      }
    ```

  - 使用`word-spacing`，父级元素设置为负值`word-spacing: -6px;`，而`inline-block`设为0，不同浏览器spacing可能不一致
    ```
      <div class="count">
        <span>123</span>
        <span>456</span>
      </div>

      /* CSS样式 */
      .count {
        word-spacing: -6px;
      }
      .count span {
        word-spacing: 0;
      }
    ```

  - 使用`letter-spacing`，用法与`word-spacing`类似

    *refer to [去除inline-block元素间间距的N种方法 | zhangxinxu](http://www.zhangxinxu.com/wordpress/2012/04/inline-block-space-remove-%E5%8E%BB%E9%99%A4%E9%97%B4%E8%B7%9D/)*

- `vertical-align`的特性，使父容器下行内元素垂直方向对齐，包括`inline`和`inline-block`元素
  - 常用的值有：`top`，`bottom`，`middle`，默认值为`baseline`
  - 使用`vertical-align: top;`可使行内元素垂直方向沿顶部对齐

    *refer to [[翻译]关于Vertical-Align你需要知道的事情 | segmentfault](https://segmentfault.com/a/1190000002668492)*

#### 5. `CSS sprites`"精灵图"
- 具有许多图像的网页需要很长时间才能加载完成并生成多个服务器请求，而"精灵图"的作用就是将一些小的图片整合到一个图片文件中，从而减少服务器请求
  - 通过`backgroud-image`属性在元素背景中插入整合后的图片
  - 通过`background-repeat`属性设置是否无限平铺
  - 通过`background-positon`属性设置图片展示的位置

#### 6. 元素隐藏的几种方式
- `display: none;`
  - 完全意义的隐藏，不生成盒模型，不占据布局空间，包括子元素也不会在页面呈现出来

- `opacity: 0;`
  - 通过设置透明度达到视觉上不呈现的效果，占据布局空间，能够响应交互操作
  - 可使用`transition`或`animate`达到淡入淡出的动画效果

- `visibility: hidden;`
  - 与`opacity: 0;`类似，但不会响应交互操作
  - 设置子元素`visibility: visible;`时可显示子元素

- `position: absolute;`属性
  - 通过绝对定位，将元素移出可见区，不占据布局空间，
  - 可设置很大的`left`负值

- 其他
  - `transform: scale(0);`缩小元素尺寸
  - `height: 0; overflow: hidden;`溢出隐藏，不占据空间

  *refer to [CSS元素隐藏 | zhangxinxu](http://www.zhangxinxu.com/wordpress/2012/02/css-overflow-hidden-visibility-hidden-disabled-use/)，[使用CSS隐藏HTML元素的4种常用方法 | htmleaf](http://www.htmleaf.com/ziliaoku/qianduanjiaocheng/201502271431.html)*

