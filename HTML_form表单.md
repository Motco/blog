## HTML `<form>`标签
#### 1. HTML 全局属性
- HTML 属性赋予元素意义和语境，全局属性可用于任何 HTML 元素

属性|Html5新添|描述|
:---|:---|:---
accesskey|- |规定激活元素的快捷键
class|- |规定元素的一个或多个类名（引用样式表中的类）
contenteditable|new |规定元素内容是否可编辑
contextmenu|new |规定元素的上下文菜单，上下文菜单在用户点击元素时显示
data-*|new |用于存储页面或应用程序的私有定制数据
dir|- |规定元素中内容的文本方向
draggable|new |规定元素是否可拖动
dropzone|new |规定在拖动被拖动数据时是否进行复制、移动或链接
hidden|new |规定元素仍未或不再相关
id|- |规定元素的唯一 id
lang|- |规定元素内容的语言
spellcheck|new |规定是否对元素进行拼写检查
style|- |规定元素的行内 CSS 样式
tabindex|- |规定元素的 tab 键次序
title|- |规定有关元素的额外信息
translate|new |规定是否应该翻译元素内容


#### 2. `<form>` 标签的定义与用法

属性|值  |描述
:---|:---|:---
accept|MIME_type|HTML5 不支持
accept-charset|charset_list|规定服务器可处理的表单数据字符集
action|URL|规定当提交表单时向何处发送表单数据
autocomplete|on/off|规定是否启用表单的自动完成功能
enctype| |规定在发送表单数据之前如何对其进行编码
method|get/post|规定用于发送 form-data 的HTTP方法
name|form_name|规定表单的名称
novalidate|novalidate|如果使用该属性，则提交表单时不进行验证
target|_blank<br/>_self<br/>_parent<br/>_top<br/>framename|规定在何处打开action URL




- `<form>` 标签用于为用户输入创建 HTML 表单
  - 表单能够包含 `input` 元素，根据不同的 `type` 属性值，输入字段拥有很多种形
式，比如文本字段、复选框、单选框、掩码后的文本控件、提交按钮等
  - 表单还可以包含 `menus`、`textarea`、`fieldset`、`legend` 和 `label` 元素
  - 表单用于向服务器传输数据


- 多数情况下被用到的表单标签是 `<input>` 标签，输入类型是由类型属性 `<type>` 定义的，常用的输入类型有
  - 文本域 Text Field：通过 `<input type="text" name=""/>` 标签设定
  - 密码字段 Password：通过 `<input type="password" name="password"/>` 标签定义
  - 提交按钮 Submit Button：通过 `<input type="submit" value="submit"/>` 标签定义
  - 重置按钮 Reset Button：通过 `<input type="reset" value="reset"/>` 标签定义
  - 单选按钮 Radio Buttons：通过 `<input type="radio" name="" value=""/>` 标签定义
  - 复选框 Checkbox：通过 `<input type="checkbox" name="" value=""/>` 标签定义<br/>
**note：**<br/>
  - `name` 属性规定 `input` 元素的名称，用于对提交到服务器后的表单数据进
行标识，或者在客户端通过 `JavaScript` 引用表单数据；只有设置了 `name` 属性的表单元素才能在提交表单时传递它们的值

- `method` 属性规定如何发送表单数据，表单数据可以作为 URL 变量 `method="get"`
或者 HTTP post `method="post"` 的方式来发送
  - 如果希望获得最佳表单传输性能，可以采用 GET 方法发送只有少数简短字段的小表单
  - 一些服务器操作系统在处理可以立即传递给应用程序的命令行参数时，会限制其数目和长度，在这种情况下，对那些有许多字段或是很长的文本域的表单来说，就应该采用 POST 方法来发送
  - 如果你在编写服务器端的表单处理应用程序方面经验不足，应该选择 GET 方法；如果采用 POST 方法，就要在读取和解码方法做些额外的工作
  - 在安全性问题上，建议选用 POST 方法。GET 方法将表单参数直接放在应用程序的 URL 中，这样网络窥探者可以很轻松地捕获它们，还可以从服务器的日志文件中进行摘录；而 POST 应用程序就没有安全方面的漏洞，在将参数作为单独的事务传输给服务器进行处理时，至少还可以采用加密的方法
  - 如果想在表单之外调用服务器端的应用程序，而且包括向其传递参数的过程，就要
  采用 GET 方法，因为该方法允许把表单这样的参数包括进来作为 URL 的一部分。而另一方面，使用 POST 样式的应用程序却希望在 URL 后还能有一个来自浏览器额外的传输过程，其中传输的内容不能作为传统 `<a>`标签的内容<br/>
**note**：<br/>
  - 如果采用 POST 方法，浏览器将会按照下面两步来发送数据：首先，浏览器将与
action属性中指定的表单处理服务器建立联系，一旦建立连接之后，浏览器就会按分段传输的方法将数据发送给服务器；
  - 如果采用 GET 方法，这时浏览器会与表单处理服务器建立连接，然后直接在一个传输
步骤中发送所有的表单数据：浏览器会将数据直接附在表单的 action URL 之后，这两者之间用问号进行分隔
    <br/>
  	 *see more at [w3c: form 标签的 method 属性](http://www.w3school.com.cn/tags/att_form_method.asp)*
     ```
      <form action="form_action" method="get" target="_blank">
        First name: <input type="text" name="firstname" /><br />
        Last name: <input type="text" name="lastname" /><br />
        <input type="submit" value="Submit" />
      </form>
     ```


- 知识扩展
  - `radio` 如何分组：多组 `radio` 可通过不同的 `name` 值来区分
       ```
        <div class="sex">
          <label for="">性别:</label>
          <input type="radio" name="sex" value="male">male
          <input type="radio" name="sex" value="female">female
          <input type="radio" name="sex1" value="male">male
          <input type="radio" name="sex1" value="female">female
        </div>
       ```

   - `placeholder` 属性的作用：`placeholder` 属性提供可描述输入字段预期值的提示信息，该提示会在输入字段为空时显示，并会在字段获得焦点时消失`placeholder` 属性适用于以下的 `<input>` 类型，`text`, `search`, `url`, `telephone`, `email` 以及`password`
       ```
        <form action="form_action" method="get">
          <input type="search" name="user_search" placeholder="Search" />
          <input type="submit" />
        </form>
       ```

  - `hidden` 属性定义隐藏字段，隐藏字段对于用户是不可见的
    - 在表单中插入隐藏域的目的在于收集或发送信息，以利于被处理表单的程序所使用浏览者单击发送按钮发送表单的时候，隐藏域的信息也被一起发送到服务器
    - 有些时候我们要给用户一信息，让他在提交表单时提交上来以确定用户身份，如sessionkey，等等．当然这些东西也能用cookie实现，但使用隐藏域就简单的多了；而且不会有浏览器不支持，用户禁用cookie的烦恼
    - 当一个`form`里有多个提交按钮，使程序能够分清楚到底用户是按那一个按钮提交
    上来的；可以写一个隐藏域，然后在每一个按钮处加上
    `onclick="document.form.command.value="xx""`然后我们接到数据后先检查`command`的值就会知道用户是按的那个按钮提交上来的
    - 有时候一个网页中有多个form，我们知道多个form是不能同时提交的，但有时这些 `form`确实相互作用，我们就可以在form中添加隐藏域来使它们联系起来<br/>
*from [kuangruike的博客](http://blog.csdn.net/kuangruike/article/details/52127450)*<br/>

         一般用法：`<input type="hidden" name="field＿name" value="value"> `
  - `label` 标签为 `input`元素定义标注，它不会向用户呈现任何特殊效果；不过在 `label` 元素内点击文本时，就会触发此控件，即当用户选择该标签时，浏览器就会自动将焦点转到和标签相关的表单控件；`for` 属性可绑定到相关元素的 `id `属性的值
      ```
        <form>
          <label for="male">Male</label>
          <input type="radio" name="sex" id="male" />
          <br />
          <label for="female">Female</label>
          <input type="radio" name="sex" id="female" />
        </form>
      ```






