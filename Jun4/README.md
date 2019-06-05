---
typora-root-url: asset
typora-copy-images-to: ..\asset
---

## HTML课程目标

第二天，我们希望你能够通过简单的实践，更加清楚地了解HTML是什么，HTML5是什么。学习基本的HTML标签，理解HTML语义化概念

开发工具:[codepen](https://codepen.io/)

阅读

[MDN](https://developer.mozilla.org/zh-CN/)

[W3C](https://www.w3.org/TR/2017/REC-html52-20171214/introduction.html#introduction):看下来的的人都太牛了叭

## HTML验证

来最后小验证一下，你是否能流畅地回答以下问题：

#### 1.HTML是什么，HTML5是什么

- HTML 是用来描述网页的一种语言。

  - HTML 指的是超文本标记语言 (**H**yper **T**ext **M**arkup **L**anguage)
  - HTML 不是一种编程语言，而是一种*标记语言* (markup language)
  - 标记语言是一套*标记标签* (markup tag)
  - HTML 使用*标记标签*来描述网页

- HTML5 是最新的 HTML 标准。

  HTML5 是专门为承载丰富的 web 内容而设计的，并且无需额外插件。

  HTML5 拥有新的语义、图形以及多媒体元素。

  HTML5 提供的新元素和新的 API 简化了 web 应用程序的搭建。

  HTML5 是跨平台的，被设计为在不同类型的硬件（PC、平板、手机、电视机等等）之上运行。

#### 2.HTML元素标签、属性都是什么概念？

- HTML 标记标签通常被称为 HTML 标签 (HTML tag)。

  - HTML 标签是由*尖括号*包围的关键词，比如 <html>
  - HTML 标签通常是*成对出现*的，比如 <b> 和 </b>
  - 标签对中的第一个标签是*开始标签*，第二个标签是*结束标签*
  - 开始和结束标签也被称为*开放标签*和*闭合标签*

- HTML 属性

  HTML 标签可以拥有*属性*。属性提供了有关 HTML 元素的*更多的信息*。

  属性总是以名称/值对的形式出现，比如：*name="value"*。

  属性总是在 HTML 元素的*开始标签*中规定。

#### 3.文档类型是什么概念，起什么作用？

- <!DOCTYPE> 声明

  Web 世界中存在许多不同的文档。只有了解文档的类型，浏览器才能正确地显示文档。

  HTML 也有多个不同的版本，只有完全明白页面中使用的确切 HTML 版本，浏览器才能完全正确地显示出 HTML 页面。这就是 <!DOCTYPE> 的用处。

  <!DOCTYPE> 不是 HTML 标签。它为浏览器提供一项信息（声明），即 HTML 是用什么版本编写的。

  提示：W3School 即将升级为最新的 HTML5 文档类型。

#### 4.meta标签都用来做什么的？

- 通常所说的META标签，是在HTML网页源代码中一个重要的html标签。META标签用来描述一个HTML网页文档的属性，例如作者、日期和时间、网页描述、关键词、页面刷新等。

#### 5.Web语义化是什么，是为了解决什么问题

- HTML的每个标签都有其特定含义(语义),Web语义化是指使用语义恰当的标签,使页面有良好的结构,页面元素有含义,能够让人和搜索引擎都容易理解。

- 我用DIV+CSS也能做出来一样的效果，确实单纯看效果两者并没有什么区别，但是页面不止是给人看的，机器也要看爬虫也要看。

  - ##### 常用的一些语义化标签

    - `<h1>`~`<h6>` ，作为标题使用，并且依据重要性递减，`<h1>` 是最高的等级。
    - `<p>`段落标记，知道了 `<p>` 作为段落，你就不会再使用 `<br />` 来换行了，而且不需要 `<br />` 来区分段落与段落。`<p>` 中的文字会自动换行，而且换行的效果优于 `<br />`。段落与段落之间的空隙也可以利用 CSS 来控制，很容易而且清晰的区分出段落与段落。
    - `<ul>`、`<ol>`、`<li>`，`<ul>` 无序列表，这个被大家广泛的使用，`<ol>` 有序列表不常用。在 Web 标准化过程中，`<ul>` 还被更多的用于导航条，本来导航条就是个列表，这样做是完全正确的，而且当你的浏览器不支持 CSS 的时候，导航链接仍然很好使，只是美观方面差了一点而已。
    - `<dl>`、`<dt>`、`<dd>`，`<dl>` 就是“定义列表”。比如说词典里面的词的解释、定义就可以用这种列表。**dl不单独使用，它通常与dt和dd一起使用。dl开启一个定义列表，dt表示要定义的项目名称，dd表示对dt的项目的描述。**
    - `<em>`、`<strong>`，`<em>` 是用作强调，`<strong>` 是用作重点强调。
    - `<table>`、`<thead>`、`<tbody>`、`<td>`、`<th>`、`<caption>`， 就是用来做表格不要用来布局

    ###### HTML5新增的那些

    HTML5标准更加的讲究语义化了，借用一张网上的图来说明这些新标签

    

    - `header元素`：header 元素代![html5-layout](/../../asset/html5-layout.jpg)表“网页”或“section”的页眉。

    - `footer元素`：footer元素代表“网页”或“section”的页脚，通常含有该节的一些基本信息，譬如：作者，相关文档链接，版权资料。

    - `hgroup元素`：

    - `nav元素`：nav元素代表页面的导航链接区域。用于定义页面的主要导航部分。

    - `aside元素`：aside元素被包含在article元素中作为主要内容的附属信息部分，其中的内容可以是与当前文章有关的相关资料、标签、名次解释等。（特殊的section）

    - `section元素`：section元素代表文档中的“节”或“段”，“段”可以是指一篇文章里按照主题的分段；“节”可以是指一个页面里的分组。section通常还带标题，虽然html5中section会自动给标题h1-h6降级，但是最好手动给他们降级。

    - `article元素`：article元素最容易跟section和div容易混淆，其实article代表一个在文档，页面或者网站中自成一体的内容，其目的是为了让开发者独立开发或重用。譬如论坛的帖子，博客上的文章，一篇用户的评论，一个互动的widget小工具。（特殊的section）除了它的内容，article会有一个标题（通常会在header里），会有一个footer页脚。

      

#### 6.链接是什么概念，对应什么标签？

- HTML <a> 元素  (或锚元素) 可以创建一个到其他网页、文件、同一页面内的位置、电子邮件地址或任何其他URL的超链接。

  

#### 7.常用标签都有哪些，都适合用在什么场景?

- body:在网页上要展示出来的页面内容一定要放在body标签中
- p:如果想在网页上显示文章，这时就需要p标签了，把文章的段落放到p标签中。标签的默认样式，段前段后都会有空白，如果不喜欢这个空白，可以用css样式来删除或改变它。
- span:标签是没有语义的，它的作用就是为了设置单独的样式用的。
- br:在需要加回车换行的地方加入br，br标签作用相当于word文档中的回车。在 html  代码中输入回车、空格都是没有作用的。在html文本中想输入回车换行，就必须输入br。没有HTML内容的标签就是空标签，空标签只需要写一个开始标签，这样的标签有br、hr和img。
- div:在网页制作过程过中，可以把一些独立的逻辑部分划分出来，放在一个div标签中，这个div标签的作用就相当于一个容器。什么是逻辑部分？它是页面上相互关联的一组元素。如网页中的独立的栏目版块，就是一个典型的逻辑部分。用id属性来为div提供唯一的名称，必须唯一。
- img:插入图片,img src=”图片地址” alt=”下载失败时的替换文本” title = “提示文本”  src：标识图像的位置；alt：指定图像的描述性文本，当图像不可见时（下载不成功时），可看到该属性指定的文本；title：提供在图像可见时对图像的描述(鼠标滑过图片时显示的文本)；图像可以是GIF，PNG，JPEG格式的图像文件。

  

#### 8、表单标签都有哪些，对应着什么功能，都有哪些属性

- form:可以把浏览者输入的数据传送到服务器端，这样服务器端程序就可以处理表单传过来的数据。form method=”传送方式”  action=”服务器文件” . form标签是成对出现的，以form开始，以/form结束。action  ：浏览者输入的数据被传送到的地方,比如一个PHP页面(save.php)。method ：  数据传送的方式（get/post）。所有表单控件（文本框、文本域、按钮、单选框、复选框等）都必须放在标签之间
- input:当用户要在表单中键入字母、数字等内容时，就会用到文本输入框。文本框也可以转化为密码输入框。input  type=”text/password” name=”名称” value=”文本” /  当type=”text”时，输入框为文本输入框;当type=”password”时,  输入框为密码输入框。name：为文本框命名，以备后台程序ASP 、PHP使用。value：为文本输入框设置默认值。(一般起到提示作用)
- textarea:当用户需要在表单中输入大段文字时，需要用到文本输入域。textarea rows=”行数” cols=”列数” 文本  /textarea rows ：多行输入域的行数。cols ：多行输入域的列数。在textarea /textarea 标签之间可以输入默认值。
- radio/checkbox:使用单选框、复选框，让用户选择,input type=”radio/checkbox” value=”值”  name=”名称” checked=”checked”/> 当 type=”radio” 时，控件为单选框,当  type=”checkbox” 时，控件为复选框,value：提交数据到服务器的值（后台程序PHP使用）,name：为控件命名，以备后台程序  ASP、PHP 使用,checked：当设置 checked=”checked” 时，该选项被默认选中,同一组的单选按钮，name  取值一定要一致，这样同一组的单选按钮才可以起到单选的作用。
- submit:使用提交按钮，提交数据,input type=”submit” value=”提交”> type：只有当type值设置为submit时，按钮才有提交作用,value：按钮上显示的文字

#### 9、ol, ul, li, dl, dd, dt等这些标签都适合用在什么地方，举个例子

- ol、ul、li适用无描述的列表。例如：新闻展示页面，一共N条新闻，点进去可浏览详情。
                  dl、dd、dt适用有描述的列表 例如：简历页面，介绍自己的信息、年龄、住址等。



## CSS

### 阅读

上面的阅读和练习主要是让你认真地体会一下写CSS的感觉，接下来，我们需要按部就班一些。希望你认真阅读以下几个内容：

- [MDN-CSS 介绍](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Introduction_to_CSS)
- [MDN-CSS如何工作](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Introduction_to_CSS/How_CSS_works)
- [MDN-CSS 语法](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Introduction_to_CSS/Syntax)
- [MDN-选择器](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Introduction_to_CSS/Selectors)
- [MDN-简单选择器](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Introduction_to_CSS/Simple_selectors)
- [MDN-属性选择器](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Introduction_to_CSS/Simple_selectors)

然后可以暂时跳过伪类选择器，开始重新仔细看文本相关的样式

- [MDN-基本文本和字体样式](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/为文本添加样式/Fundamentals)

当然，你也可以选择阅读其它网站，比如W3School等上面相应的内容。