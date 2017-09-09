## HTML XML XHTML features *--extracted from [wikipedia](https://en.wikipedia.org/wiki/)*

&emsp;[1. HTML](#jp1)，[XML](#jp2)，[XHTML](#jp3) <br/>
&emsp;[2. Semantic HTML](#jp4) <br/>
&emsp;[3. Separation of presentation and content](#jp5) <br/>
&emsp;[4. Meta element](#jp6) <br/>
&emsp;[5. Document type declaration](#jp7) <br/>


---

### 1. <a name="jp1">HTML</a> 
> **Hpertext Markup Language** is the standard markup language for creating web pages and web applications.
> With **Cascading Style Sheets(CSS)** and **JavaScript** it forms a traid of cornerstone technologies for the *World Wide Web*.
> Web browsers receive **HTML** documents from a web server or from local storage and render
> them into multimedia web pages. 
> <br/><br/>
> **HTML** elements are the building blocks of **HTML** pages, and delineated by tags,written using angle brackets.
> Tags such as `<img />` and `<input />` introduce content into the page directly. Others such as `<p>...</p>` surround and
> provide information about document text and may include other tags as sub-elements. Browsers do not display the **HTML**
> tags, but use them to interpret the content of the page.

### <a name="jp2">XML</a>
> **Extensible Markup Language** is a markup language that defines a set of rules for 
> encoding documents in a format that is both human-readable and machine-readable through
> use of tags that can be created and defined by users.Much like natural languages,**XML** can
> grow when users creat new elements and agree on what they mean,which makes **XML** more 
> broadly to capture intent and semantically deeper than a nonextensible markup language such as **HTML**.
> <br/><br/>
> In addtion,**HTML** is useful for display of content;often **HTML** is used to display **XML** content
> after transformation with **XSL**(*Extensible Stylesheet Language is used to refer to a family of language 
> used to transform and render **XML** documents*).

### <a name="jp3">XHTML</a>
> **Extensible Hypertext Markup Language** is part of the family of **XML** markup language.It mirrors or 
> extends versions of **HTML**,which was defined as an application of **Standard Generalized Markup Language(SGML)**,
> a flexible markup language framework.**XHTML** is an application of **XML**,a more restrictive subset of **SGML**, and
> **XHTML** documents are well-formed and could be parsed using standard **XML** parsers,while **HTML** requires a 
> leninet HTML-specific parser.

---
### 2. <a name="jp4">Semantic HTML</a>
> **Semantic HTML** is a way of writing **HTML** that emphasizes the meaning of the encoded information over its presentation.
> **HTML** has included semantic markup(new semantic elements in **HTML5**:`section`,`article`,`footer`,<br/>
> `progress`,`nav`,`aside`,`mark`,`time`,etc) from its inception,but has also included presentational markup, such
> as `font`, `i` and `center` tags.There are also the semantically neutral `span` and `div` tags.
> <br/><br/>
> In order for search-engine spiders to be able to rate the significance of pieces of text they find in **HTML** documents,
> and also for those creating mashups and other hybrids as well as for more automated agents as they are developed, the
> semantic structures that exist in **HTML** need to be widely and uniformly applied to bring out the meaning of published 
> text.
> <br/><br/>
> Presentational elements are deprecated in current **HTML** and **XHTML** recommendations,while some elements,like `i`and
> `b`,are still specified as their meaning has been clearly defined "as to be stylistically offset from the normal prose 
> without conveying any extra importance".

---
### 3. <a name="jp5">Separation of presentation and content</a>
> **Separation of presentation and content** is a design principle where visual and design aspects are kept separate from
> the material and structure.A typical analogy used to explain this principle is the purposeful distinction between the
> human skeleton (as the structural component) from human flesh (as the visual component) which makes up the body's appearance.
> <br/><br/>
> This principle is not a rigid guideline, but serves more as best practice for keeping design and structure separate. 
> In many cases, the design and development aspects of a project are performed by different people, so keeping both aspects 
> separated ensures both readability and simplification as in the **DRY***(Don't Repeat Yourself)* principle.

#### CSS
> **Cascading Style Sheets** is a style sheet language used for describing the presentation of a document written in a markup
> language.And **CSS** is designed primarily to enable the separation of presentation and content, including aspects such as 
> the layout, colors, and fonts.This separation can improve content accessibility, provide more flexibility and control in 
> the specification of presentation characteristics, enable multiple HTML pages to share formatting by specifying the 
> relevant CSS in a separate .css file, and reduce complexity and repetition in the structural content.
> <br/><br/>
> Separation of presentation and content makes it possible to present the same markup page in different styles for different
> rendering methods, such as on-screen, in print, by voice (via speech-based browser or screen reader), and on Braille-based
> tactile devices.
---
### 4. <a name="jp6">Meta element</a>
> **Meta elements** are part of a web page's `head` section,used to specify page description,keywords and any other metadata.
> Multiple Meta elements with different attributes can be used on the same page. <br/><br/>
> The meta element has two uses: either to emulate the use of an HTTP response header field, or to embed additional metadata
> within the HTML document.
#### Examples of the meta element
> - Meta element can specify HTTP headers:<br/>
> ` <meta charset="utf-8" > `
> - Meta element can describe the contents of the page:<br/>
> ` <meta name="description" content="Examples of the meta element" > `
> - Meta element used in search engine optimization:<br/>
> ` <meta name="googlebot" content="noodp" > ` <br/>
> ` <meta name="keywords" content="HTML, CSS, XML, XHTML"> `
> - Meta element can refresh a Web page automatically after a given time interval:<br/>
> ` <meta http-equiv="Refresh" content="5;url=http://www.w3school.com.cn" /> `

*[HTML meta tags from w3cschool:](http://www.w3school.com.cn/tags/tag_meta.asp)*

| attribute |value |description |
|:---|:---|:---|
| content | some-text | define meta infomation about the attribute of http-equiv or name |
| http-equiv| content-type<br/>expires<br/>refresh<br/>set-cookie | associate the content attribute with HTTP headers|
| name | author<br/>description<br/>keywords<br/>generator<br/>revised<br/>others | associate the content attribute with a name |
| scheme | some-text | define the format used to translate the value of the content attribute |

<br/>

---

### 5. <a name="jp7">Document type declaration</a>
> A **document type declaration**, or **DOCTYPE**, is an instruction that associates a particular **SGML** or **XML** document
> (for example, a webpage) with a **document type definition (DTD)** (for example, the formal definition of a particular 
> version of **HTML1.0 - HTML 4.0**)
> <br/><br/>
> **HTML** documents are required to start with a **Document Type Declaration**.The original purpose of the doctype was to
> enable parsing and validation of HTML documents by SGML tools based on the Document Type Definition (DTD).In browsers, 
> the doctype helps to define the rendering mode,a valid doctype activates **standards mode** as opposed to **quirks mode**.
> <br/><br/>
> - Strict **DTD** doesn't allow presentational markup with the argument that **CSS** should be used instead: <br/>
> ` $ <!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd"> `
> - HTML5 doctype declaration is simpler for its without referencing to a **DTD** in the form of a **URI(Uniform Resource 
>  Identifier)** or **FPI(Formal Public Identifier)**: <br/>
> ` $ <!DOCTYPE html> `

#### Strict Mode and Quirks Mode
> **Quirks mode** refers to a technique used by some web browsers for the sake of maintaining backward compatibility with web
> pages designed for Internet Explorer 5 and earlier, instead of strictly complying with **W3C** and **IETF** standards 
> in **standards mode**. Many older web pages will only render as intended when handled by the old browers,for its
> unimplementing the specifications of **HTML** and **CSS** before they were formulated. Thus modern web browers are generally
> developed with multiple rendering models: in **standards mode** pages are rendered according to the **HTML** and **CSS**
> specifications, while in **quirks mode** attempts are made to emulate the behavior of older browsers.
> <br/><br/>
> **Almost standards mode(aka strict mode)** matches **standards mode** except for one,the layout of images inside table
> cells is handled the same way **quirks mode** operates,which makes the layouts of sliced-images-in-tables stabler in browers.

#### The rendering modes are generally triggering by the presence of **DOCTYPE**.
> - The factors which will trigger **strict mode**
>   - Full **DOCTYPE** is presented:<br/>
> ` $ <!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd"> `
<br/>
> ` /* in HTML4 strict DTD */ `
<br/>
> ` $ <!DOCTYPE html>   /* in HTML5 */ `
> - The factors which will trigger **quirks mode**
>   - The omission of **DOCTYPE**:<br/>
> ` $ <!DOCTYPE html PUBLIC> `
>   - If anything precedes the **DOCTYPE**:<br/>
> ` $ <!-- This comment will put IE 6, 7, 8, and 9 in quirks mode -->` 
<br/>
> ` $ <!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd"> `
 

