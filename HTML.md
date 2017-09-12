## <a name="jp0">HTML XML XHTML features</a> *--extracted mainly from [wikipedia](https://en.wikipedia.org/wiki/)*

&emsp;[1. Differences](#jp1)<br/>
&emsp;[2. Semantic HTML](#jp2) <br/>
&emsp;[3. Separation of presentation and content](#jp3) <br/>
&emsp;[4. Meta element](#jp4) <br/>
&emsp;[5. Document type declaration](#jp5) <br/>
&emsp;[6. Mojibake](#jp6) <br/>
&emsp;[7. The common web browers](#jp7) <br/>
&emsp;[8. HTML tags](#jp8) <br/>

---



### 1. Difinition and Differences
#### HTML
 - **Hpertext Markup Language** is the standard markup language for creating web pages and web applications.
 With **Cascading Style Sheets(CSS)** and **JavaScript** it forms a traid of cornerstone technologies for the *World Wide Web*.
 Web browsers receive **HTML** documents from a web server or from local storage and render them into multimedia web pages. 

 - **HTML** elements are the building blocks of **HTML** pages, and delineated by tags,written using angle brackets.
 Tags such as `<img />` and `<input />` introduce content into the page directly. Others such as `<p>...</p>` surround and
 provide information about document text and may include other tags as sub-elements. Browsers do not display the **HTML**
 tags, but use them to interpret the content of the page.
 
#### XML
 - **Extensible Markup Language** is a simple, very flexible text format derived from **SGML**.**XML** defines a set of
 rules for encoding documents in a format that is both human-readable and machine-readable by using tags created and
 defined by users.

 - Much like natural languages,**XML** can grow when users creat new elements and agree on what they mean,which makes
 **XML** more broadly to capture intent and semantically deeper than a nonextensible markup language such as **HTML**.


#### XHTML
 - **Extensible Hypertext Markup Language** is a variant of **HTML** that uses the syntax of XML.It mirrors or extends
 versions of **HTML**,but stricter in syntax.**XHTML** documents are well-formed and could be parsed using standard
 **XML** parsers,while **HTML** requires a leninet HTML-specific parser.

#### <a name="jp1">Differences between **XHTML1.x** and **HTML4**</a>
 - Documents must be well-formed in **XHTML**，meaning that all elements must have closing tags nest properly.
   - correct nested elements:`<p>here is an emphasized <em>paragraph</em>.</p>`
   - incorrect overlapping elements:~~`<p>here is an emphasized <em>paragraph.</p></em>`~~
 - Element and attribute names must be in lower case in **XHTML** documents.
 - For non-empty elements, end tags are required.
   - correct terminated elements:`<p>here is a paragraph.</p><p>here is another paragraph.</p>`
   - incorrect unterminated elements:~~`<p>here is a paragraph.<p>here is another paragraph.`~~
 - Attribute values must always be quoted,even numeric.
   - correct quoted attribute values:`<td rowspan="3">`
   - incorrect unquoted attribute values:~~`<td rowspan=3>`~~
 - Attribute-value pairs must be written in full. Attribute names such as `compact` and `checked` cannot occur in elements 
 without their value being specified.
   - correct unminimized attributes:`<dl compact="compact">`
   - incorrect minimized attributes:~~`<dl compact>`~~
 - Empty elements must either have an end tag or the start tag must end with `/>`.
   - correct terminated empty elements:`<br/><hr/>`
   - incorrect unterminated empty elements:~~`<br><hr>`~~
 - White Space handling in attribute values.
   - Strip leading and trailing white space.
   - Map sequences of one or more white space characters (including line breaks) to a single inter-word space.
 <br/><br/>
*see [w3:xhtml1](https://www.w3.org/tr/xhtml1/#diffs),[w3:standards](https://www.w3.org/standards/webdesign/htmlcss) and
 [w3:html5-diff](https://www.w3.org/TR/html5-diff/) for more*


### 2. <a name="jp2">Semantic HTML</a>  [TOP](#jp0)
 - **Semantic HTML** is a way of writing **HTML** that emphasizes the meaning of the encoded information over its presentation.
 **HTML** has included semantic markup(new semantic elements in **HTML5**:`section`,`article`,`footer`,<br/>
 `progress`,`nav`,`aside`,`mark`,`time`,etc) from its inception,but has also included presentational markup, such
 as `font`, `i` and `center` tags.There are also the semantically neutral `span` and `div` tags.<br/>
 
 - In order for search-engine spiders to be able to rate the significance of pieces of text they find in **HTML** documents,
 and also for those creating mashups and other hybrids as well as for more automated agents as they are developed, the
 semantic structures that exist in **HTML** need to be widely and uniformly applied to bring out the meaning of published 
 text.<br/>

 - Presentational elements are deprecated in current **HTML** and **XHTML** recommendations,while some elements,like `i`and
 `b`,are still specified as their meaning has been clearly defined "as to be stylistically offset from the normal prose 
 without conveying any extra importance".


### 3. <a name="jp3">Separation of presentation and content</a>  [TOP](#jp0)
 - **Separation of presentation and content** is a design principle where visual and design aspects are kept separate from
 the material and structure.A typical analogy used to explain this principle is the purposeful distinction between the
 human skeleton (as the structural component) from human flesh (as the visual component) which makes up the body's appearance.
 <br/><br/>
 - This principle is not a rigid guideline, but serves more as best practice for keeping design and structure separate. 
 In many cases, the design and development aspects of a project are performed by different people, so keeping both aspects 
 separated ensures both readability and simplification as in the **DRY**(Don't Repeat Yourself) principle.

#### CSS
 - **Cascading Style Sheets** is a style sheet language used for describing the presentation of a document written in a markup
 language.And **CSS** is designed primarily to enable the separation of presentation and content, including aspects such as 
 the layout, colors, and fonts.This separation can improve content accessibility, provide more flexibility and control in 
 the specification of presentation characteristics, enable multiple HTML pages to share formatting by specifying the 
 relevant CSS in a separate .css file, and reduce complexity and repetition in the structural content.
 <br/><br/>
 - Separation of presentation and content makes it possible to present the same markup page in different styles for different
 rendering methods, such as on-screen, in print, by voice (via speech-based browser or screen reader), and on Braille-based
 tactile devices.


### 4. <a name="jp4">Meta element</a>  [TOP](#jp0)
 - **Meta elements** are part of a web page's `head` section,used to specify page description,keywords and any other metadata.
 Multiple Meta elements with different attributes can be used on the same page. <br/><br/>
 - The meta element has two uses: either to emulate the use of an HTTP response header field, or to embed additional metadata
 within the HTML document.

#### Examples of the meta element
 - Meta element can specify HTTP headers:<br/>
 ` <meta charset="utf-8" > `
 - Meta element can describe the contents of the page:<br/>
 ` <meta name="description" content="Examples of the meta element" > `
 - Meta element used in search engine optimization:<br/>
 ` <meta name="googlebot" content="noodp" > ` <br/>
 ` <meta name="keywords" content="HTML, CSS, XML, XHTML"> `
 - Meta element can refresh a Web page automatically after a given time interval:<br/>
 ` <meta http-equiv="Refresh" content="5;url=http://www.w3school.com.cn" /> `

*[HTML meta tags summarized from w3cschool :](http://www.w3school.com.cn/tags/tag_meta.asp)*

| attribute |value |description |
|:---|:---|:---|
| content | some-text | define meta infomation about the attribute of http-equiv or name |
| http-equiv| content-type<br/>expires<br/>refresh<br/>set-cookie | associate the content attribute with HTTP headers|
| name | author<br/>description<br/>keywords<br/>generator<br/>revised<br/>others | associate the content attribute with a name |
| scheme | some-text | define the format used to translate the value of the content attribute |


### 5. <a name="jp5">Document type declaration</a>  [TOP](#jp0)
 - A **document type declaration**, or **DOCTYPE**, is an instruction that associates a particular **SGML** or **XML** document
 (for example, a webpage) with a **Document Type Definition (DTD)** (for example, the formal definition of a particular 
 version of **HTML1.0 - HTML 4.0**)
 <br/><br/>
 **HTML** documents are required to start with a **Document Type Declaration**.The original purpose of the doctype was to
 enable parsing and validation of **HTML** documents by **SGML** tools based on the **Document Type Definition (DTD)**.
 In browsers, the doctype helps to define the rendering mode,a valid doctype activates **standards mode** as opposed 
 to **quirks mode**.
 <br/><br/>
 - Strict **DTD** doesn't allow presentational markup with the argument that **CSS** should be used instead: <br/>
   - ` $ <!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd"> `
 - HTML5 doctype declaration is simpler for its without referencing to a **DTD** in the form of a **URI(Uniform Resource 
  Identifier)** or **FPI(Formal Public Identifier)**: <br/>
   - ` $ <!DOCTYPE html> `

#### Strict Mode and Quirks Mode
 - **Quirks mode** refers to a technique used by some web browsers for the sake of maintaining backward compatibility with web
 pages designed for Internet Explorer 5 and earlier, instead of strictly complying with **W3C** and **IETF** standards 
 in **standards mode**. Many older web pages will only render as intended when handled by the old browers,for its
 unimplementing the specifications of **HTML** and **CSS** before they were formulated.
 <br/><br/> 
 Thus modern web browers are generally developed with multiple rendering models: in **standards mode** pages are rendered
 according to the **HTML** and **CSS** specifications, while in **quirks mode** attempts are made to emulate the behavior
 of older browsers.
 <br/><br/>
 - **Almost standards mode(aka strict mode)** matches **standards mode** except for one,the layout of images inside table
 cells is handled the same way **quirks mode** operates,which makes the layouts of sliced-images-in-tables stabler in browers.

#### The rendering modes are generally triggering by the presence of **DOCTYPE**.
 - The factors which will trigger **strict mode**
   - Full **DOCTYPE** is presented: <br/>
 ` $ <!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd"> <!-- in HTML4 strict DTD --> `<br/> 
 ` $ <!DOCTYPE html> <!-- in HTML5 --> `
 - The factors which will trigger **quirks mode**
   - The omission of **DOCTYPE**:<br/>
 ` $ <!DOCTYPE html PUBLIC> `
   - If anything precedes the **DOCTYPE**:<br/>
 ` $ <!-- This comment will put IE 6, 7, 8, and 9 in quirks mode -->`<br/>
 ` $ <!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">`


### 6. <a name="jp6">Mojibake</a>  [TOP](#jp0)
- **Mojibake** is the garbled text as a result of text being decoded using an unintended character encoding.

  - If the encoding isn't specified,the software will decides it mainly via configuration or charset detection heuristics,
which is error-prone in not-so-uncommon scenarios.<br/>
    - For example when transferring files between Windows and Linux.One solution is to use a byte order mark, but for source
code and other machine readable text, many parsers don't tolerate this. Another is storing the encoding as metadata in the 
filesystem.Filesystems that support extended file attributes can store this as `user.charset`.
    - There are many encodings that are hard to distinguish except for a few's,UFT-8,etc.Without the coding scheme being 
assigned explictly by HTTP headings sent along with the documents or by the HTML document's meta tags subsituted fo missing 
HTTP headings,a web browers mayn't be able to distinguish which encoding the web adopt.

  - As above, mojibake also occurs when the encoding is wrongly specified.

  - When there are layers of protocols, each trying to specify the encoding based on different information.For example, consider
a web server serving a static HTML file over HTTP. The character set may be communicated to the client in any number of 3 ways:
    - in the HTTP header. This information can be based on server configuration (for instance, when serving a file off disk) or
controlled by the application running on the server (for dynamic websites).
    - in the file, as an HTML meta tag (`http-equiv` or `charset`) or the encoding attribute of an XML declaration. This is the
encoding that the author meant to save the particular file in.
    - in the file, as a byte order mark. This is the encoding that the author's editor actually saved it in. Unless an accidental
encoding conversion has happened (by opening it in one encoding and saving it in another), this will be correct.
  - Lack of Hardware/Software support.Many older hardware are typically designed to support only one character set and the
 character set typically cannot be altered.

- The difficulty of resolving an instance of mojibake varies depending on the application within which it occurs and the causes
of it. Two of the most common applications in which mojibake may occur are web browsers and word processors.
  - In web browsers,it can be sovled by switching the rendering engine's encoding to the accordant one in HTML meta tags,
such as `<meta charset="Big5">` or `<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />`.


### 7. <a name="jp7">The common web browers</a>  [TOP](#jp0)
- Browsers are primarily intended to use the World Wide Web, they can be used to access information provided by web servers in
private networks or files in file systems as well.The most popular web browsers are `Chrome`, `IE`, `Safari`, `Opera` and `Firefox`.
- A web browser engine (aka web layout engine or web rendering engine) is a computer program that renders marked up content
(such as HTML, XML, image files, etc.) and formatting information (such as CSS, XSL, etc.).
  - **Gecko** is developed by the *Mozilla Foundation*.
  - **Goanna** is a fork of **Gecko** developed by *Moonchild Productions*.
  - **KHTML** is developed by the *KDE project*.
  - **Presto** is developed by *Opera Software* for use in Opera. Development stopped as Opera transitioned to **Blink**.
  - **Tasman** was developed by *Microsoft* for use in Internet Explorer 5 for Macintosh.
  - **Trident** is developed by *Microsoft* for use in the Windows versions of Internet Explorer 4 to Internet Explorer 11.
  - **WebKit** is a fork of **KHTML** by *Apple Inc.* used in Apple Safari, Chromium and Google Chrome.
  - **Blink** is a 2013 fork of WebKit's WebCore component by *Google* used in Chromium, Google Chrome and Opera.
  - **Servo** is an experimental web browser layout engine being developed cooperatively by *Mozilla* and *Samsung*.
  - **EdgeHTML** is the engine developed by *Microsoft* for Edge. It is a largely rewritten fork of **Trident** with all legacy code removed.

<br/>

*see more at [wiki:List of web browsers](https://en.wikipedia.org/wiki/List_of_web_browsers)*

### 8. <a name="jp8">HTML tags</a>  [TOP](#jp0)
- HTML tags are the building blocks of HTML. They are used to define the HTML elements that should appear on a web page.HTML
tags tell your browser which elements to present and how to present them. Where the element appears is determined by the order
in which the tags appear.
- The common tags

|   | 1 | 2  |  3 |  4 | 5  |  6 | 7  |
|:--:|:--|:--|:--|:--|:--|:--|:--|
| 1 | `<!--...-->`   | `<!DOCTYPE>` | `<a>`      | `<abbr>`   | `<address>` | `<area>`  | `<article>`    |
| 2 | `<aside>`      | `<audio>`    |`<b>`       | `<base>`   | `<bdi>`     | `<bdo>`   | `<blockquote>` |
| 3 | `<body>`       | `<br>`       | `<button>` | `<canvas>` | `<caption>` | `<cite>`  | `<code>` |
| 4 |  `<col>`       | `<colgroup>` | `<data>` | `<datalist>` | `<dd>`      | `<del>`   | `<details>` |
| 5 |  `<dfn>`       | `<dialog>`   | `<div>`    | `<dl>`     | `<dt>`      | `<em>`    | `<embed>` |
| 6 | `<figcaption>` | `<figure>`   | `<footer>` | `<form>`   | `<h1>`      | `<h2>`    | `<h3>` |
| 7 | `<h4>`         | `<h5>`       | `<h6>`     |`<fieldset>`   | `<head>`   | `<header>` | `<hgroup>`  |
| 8 |  `<hr>`        | `<html>`     |  `<i>`  | `<iframe>`   | `<img>`    | `<input>`  | `<ins>`   |
| 9 | `<kbd>`   | `<keygen>` | `<label>`      | `<legend>`   | `<li>`     | `<link>`   | `<main>`    |
|10 | `<map>`   | `<mark>` | `<menu>`     | `<menuitem>` | `<meta>`   | `<meter>`  | `<nav>`     |
|11 | `<noscript>` | `<object>` | `<ol>`    | `<optgroup>` | `<option>` | `<output>` | `<p>`       |
|12 | `<param>` | `<pre>` | `<progress>`   | `<q>`        |`<rb>`      | `<rp>`     | `<rt>`      |
|13 |`<rtc>`   | `<ruby>` | `<s>`          | `<samp>`     | `<script>` | `<section>`|`<select>`   |
|14 |`<small>` | `<source>` | `<span>`       | `<strong>`   | `<style>`  | `<sub>`    | `<summary>` |
|15 |`<sup>`   | `<table>` | `<tbody>`       | `<td>`   | `<template>` | `<textarea>` | `<tfoot>`   |
|16 |`<th>`    | `<thead>` | `<time>`       | `<title>`    | `<tr>`     | `<track>`  | `<u>`       |
|17 |`<ul>`    | `<var>` | `<video>`      | `<wbr>`      |
