# CSS从入门到放弃

CSS(Cascading Style Sheets）：层叠样式表

层叠次序：当同一个 HTML 元素被不止一个样式定义时，会使用哪个样式呢？ 

一般而言，所有的样式会根据下面的规则层叠于一个新的虚拟样式表中，其中数字 4 拥有最高的优先权。
> 1.  浏览器缺省设置
> 2.  外部样式表
> 3.  内部样式表（位于  标签内部）
> 4.  内联样式（在 HTML 元素内部）

因此，内联样式（在 HTML 元素内部）拥有最高的优先权，这意味着它将优先于以下的样式声明： 标签中的样式声明，外部样式表中的样式声明，或者浏览器中的样式声明（缺省值）。

# CSS基础教程

## CCS语法

![CSS语法图示](http://www.w3school.com.cn/i/ct_css_selector.gif)


### 1. 值的书写

*   当使用 RGB 百分比时，即使当值为 0 时也要写百分比符号。但是在其他的情况下就不需要这么做了。比如说，当尺寸为 0 像素时，0 之后不需要使用 px 单位，因为 0 就是 0，无论单位是什么。
*   如果值为若干单词，则要给值加引号：`p {font-family: "sans serif";}`
*   如果要定义不止一个声明，则需要用分号将每个声明分开。
*   CSS 对大小写不敏感。不过如果涉及到与 HTML 文档一起工作的话，class 和 id 名称对大小写是敏感的。<div class="md-section-divider"></div>

### 2. 选择器的分组

使用逗号将选择器分开，以下选择器分享相同的声明。 

 ```css
h1,h2,h3,h4,h5,h6 { 
  color: green; 
  } 
```
### 3. 元素的继承
子元素从父元素继承属性

* * *
<div class="md-section-divider"></div>

## 派生选择器和id选择器
<div class="md-section-divider"></div>

### 1.派生选择器

派生选择器是根据文档的上下文关系来确定某个标签的样式。通过合理地使用派生选择器，我们可以使HTML代码变得更加整洁。 

例如，我们希望列表中的 strong 元素变为斜体字，而不是通常的粗体字，可以这样定义一个派生选择器：

```css
li strong {
    font-style: italic;
    font-weight: normal;
  }
```


HTML：
```html
<p><strong>我是粗体字，不是斜体字，因为我不在列表当中，所以这个规则对我不起作用</strong></p>
<ol>
<li><strong>我是斜体字。这是因为 strong 元素位于 li 元素内。</strong></li>
<li>我是正常的字体。</li>
</ol>
```


在上面的例子中，只有 li 元素中的 strong 元素的样式为斜体字，无需为 strong 元素定义特别的 class 或 id，代码更加简洁。
<div class="md-section-divider"></div>

### 2.id选择器

id 属性只能在每个 HTML 文档中出现一次。 

CSS:
```css
#red {color:red;}
#green {color:green;}
```
HTML:
```html
<p id="red">这个段落是红色。</p>
<p id="green">这个段落是绿色。</p>
```


在网页布局中，id 选择器常常用于建立派生选择器。 

即使被标注为 sidebar 的元素只能在文档中出现一次，这个 id 选择器作为派生选择器也可以被使用很多次：
```css
#sidebar p {
    font-style: italic;
    }
#sidebar h2 {
    font-size: 1em;
    }
```


## CSS类选择器
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="m240">

1.  `<span class="pun">.</span><span class="pln">center </span><span class="pun">{</span><span class="pln">text</span><span class="pun">-</span><span class="pln">align</span><span class="pun">:</span><span class="pln"> center</span><span class="pun">}</span>`</pre>

在上面的例子中，所有拥有 center 类的 HTML 元素均为居中。 

在下面的 HTML 代码中，h1 和 p 元素都有 center 类。这意味着两者都将遵守 ".center" 选择器中的规则。
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="bx6d">

1.  `<span class="tag">&lt;h1</span><span class="pln"> </span><span class="atn">class</span><span class="pun">=</span><span class="atv">"center"</span><span class="tag">&gt;</span>`
2.  `<span class="pln">This heading will be center-aligned</span>`
3.  `<span class="tag">&lt;/h1&gt;</span>`
4.5.  `<span class="tag">&lt;p</span><span class="pln"> </span><span class="atn">class</span><span class="pun">=</span><span class="atv">"center"</span><span class="tag">&gt;</span>`
6.  `<span class="pln">This paragraph will also be center-aligned.</span>`
7.  `<span class="tag">&lt;/p&gt;</span>`</pre>

注意：类名的第一个字符不能使用数字！它无法在 Mozilla 或 Firefox 中起作用。 

和 id 一样，class 也可被用作派生选择器：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="t1ze">

1.  `<span class="pun">.</span><span class="pln">fancy td </span><span class="pun">{</span>`
2.  `<span class="pln">    color</span><span class="pun">:</span><span class="pln"> </span><span class="com">#f60;</span>`
3.  `<span class="pln">    background</span><span class="pun">:</span><span class="pln"> </span><span class="com">#666;</span>`
4.  `<span class="pln">    </span><span class="pun">}</span>`</pre>

* * *
<div class="md-section-divider"></div>

## CSS属性选择器
<div class="md-section-divider"></div>

### 1.属性选择器

下面的例子为带有 title 属性的所有元素设置样式：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="4mnm">

1.  `<span class="pun">[</span><span class="pln">title</span><span class="pun">]</span>`
2.  `<span class="pun">{</span>`
3.  `<span class="pln">color</span><span class="pun">:</span><span class="pln">red</span><span class="pun">;</span>`
4.  `<span class="pun">}</span>`</pre>

HTML:
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="em56">

1.  `<span class="tag">&lt;h1&gt;</span><span class="pln">以下文字链接可以应用样式：</span><span class="tag">&lt;/h1&gt;</span>`
2.  `<span class="tag">&lt;h2</span><span class="pln"> </span><span class="atn">title</span><span class="pun">=</span><span class="atv">"Hello world"</span><span class="tag">&gt;</span><span class="pln">Hello world</span><span class="tag">&lt;/h2&gt;</span>`
3.  `<span class="tag">&lt;a</span><span class="pln"> </span><span class="atn">title</span><span class="pun">=</span><span class="atv">"baidu"</span><span class="pln"> </span><span class="atn">href</span><span class="pun">=</span><span class="atv">"http://www.baidu.com"</span><span class="tag">&gt;</span><span class="pln">baidu</span><span class="tag">&lt;/a&gt;</span>`
4.5.  `<span class="tag">&lt;h1&gt;</span><span class="pln">以下文字链接无法应用样式：</span><span class="tag">&lt;/h1&gt;</span>`
6.  `<span class="tag">&lt;h2&gt;</span><span class="pln">Hello world</span><span class="tag">&lt;/h2&gt;</span>`
7.  `<span class="tag">&lt;a</span><span class="pln"> </span><span class="atn">href</span><span class="pun">=</span><span class="atv">"www.baidu.com"</span><span class="tag">&gt;</span><span class="pln">baidu</span><span class="tag">&lt;/a&gt;</span>`</pre><div class="md-section-divider"></div>

### 2.属性和值选择器
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="jq1c">

1.  `<span class="pun">[</span><span class="pln">title</span><span class="pun">=</span><span class="pln">baidu</span><span class="pun">]</span>`
2.  `<span class="pun">{</span>`
3.  `<span class="pln">color</span><span class="pun">:</span><span class="pln">red</span><span class="pun">;</span>`
4.  `<span class="pun">}</span>`</pre>

HTML:
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="53jl">

1.  `<span class="tag">&lt;h1&gt;</span><span class="pln">以下文字链接可以应用样式：</span><span class="tag">&lt;/h1&gt;</span>`
2.  `<span class="tag">&lt;a</span><span class="pln"> </span><span class="atn">title</span><span class="pun">=</span><span class="atv">"baidu"</span><span class="pln"> </span><span class="atn">href</span><span class="pun">=</span><span class="atv">"www.baidu.com"</span><span class="tag">&gt;</span><span class="pln">baidu</span><span class="tag">&lt;/a&gt;</span>`
3.4.  `<span class="tag">&lt;h1&gt;</span><span class="pln">以下文字链接无法应用样式：</span><span class="tag">&lt;/h1&gt;</span>`
5.  `<span class="tag">&lt;p</span><span class="pln"> </span><span class="atn">title</span><span class="pun">=</span><span class="atv">"greeting"</span><span class="tag">&gt;</span><span class="pln">Hi!</span><span class="tag">&lt;/p&gt;</span>`
6.  `<span class="tag">&lt;a</span><span class="pln"> </span><span class="atn">class</span><span class="pun">=</span><span class="atv">"baidu"</span><span class="pln"> </span><span class="atn">href</span><span class="pun">=</span><span class="atv">"www.baidu.com"</span><span class="tag">&gt;</span><span class="pln">baidu</span><span class="tag">&lt;/a&gt;</span>`</pre><div class="md-section-divider"></div>

### 3.属性和值选择器 - 多个值

① 以下例子中，只要title属性值包含“hello”，如“hello”、“hello world”、“hi hello”等，都会使用样式。 

适用于由空格分隔的属性值。
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="yymx">

1.  `<span class="pun">[</span><span class="pln">title</span><span class="pun">~=</span><span class="pln">hello</span><span class="pun">]</span><span class="pln"> </span><span class="pun">{</span><span class="pln"> color</span><span class="pun">:</span><span class="pln">red</span><span class="pun">;</span><span class="pln"> </span><span class="pun">}</span>`</pre>

② 以下例子中，只要title属性值包含“hello”，如“hello”、“hello-world”等，都会使用样式。 

适用于由连字符分隔的属性值。 

注意：如“hi-hello”形式的不适用下面样式。
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="2dx4">

1.  `<span class="pun">[</span><span class="pln">lang</span><span class="pun">|=</span><span class="pln">hello</span><span class="pun">]</span><span class="pln"> </span><span class="pun">{</span><span class="pln"> color</span><span class="pun">:</span><span class="pln">red</span><span class="pun">;</span><span class="pln"> </span><span class="pun">}</span>`</pre>

* * *
<div class="md-section-divider"></div>

## 创建CSS
<div class="md-section-divider"></div>

### 1.外部样式表

当样式需要应用于很多页面时，外部样式表将是理想的选择。在使用外部样式表的情况下，你可以通过改变一个文件来改变整个站点的外观。每个页面使用`&lt;link&gt;`标签链接到样式表。`&lt;link&gt;` 标签在（文档的）头部：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="veor">

1.  `<span class="tag">&lt;head&gt;</span>`
2.  `<span class="tag">&lt;link</span><span class="pln"> </span><span class="atn">rel</span><span class="pun">=</span><span class="atv">"stylesheet"</span><span class="pln"> </span><span class="atn">type</span><span class="pun">=</span><span class="atv">"text/css"</span><span class="pln"> </span><span class="atn">href</span><span class="pun">=</span><span class="atv">"mystyle.css"</span><span class="pln"> </span><span class="tag">/&gt;</span>`
3.  `<span class="tag">&lt;/head&gt;</span>`</pre>

浏览器会从文件 mystyle.css 中读到样式声明，并根据它来格式文档。 

注意：不要在属性值与单位之间留有空格。
<div class="md-section-divider"></div>

### 2.内部样式表

由于要将表现和内容混杂在一起，内联样式会损失掉样式表的许多优势。请慎用这种方法，例如当样式仅需要在一个元素上应用一次时。 

要使用内联样式，需要在相关的标签内使用样式（style）属性。Style 属性可以包含任何 CSS 属性。
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="oz8h">

1.  `<span class="tag">&lt;p</span><span class="pln"> </span><span class="atn">style</span><span class="pun">=</span><span class="atv">"</span><span class="pln">color</span><span class="pun">:</span><span class="pln"> sienna</span><span class="pun">;</span><span class="pln"> margin</span><span class="pun">-</span><span class="pln">left</span><span class="pun">:</span><span class="pln"> </span><span class="lit">20px</span><span class="atv">"</span><span class="tag">&gt;</span>`
2.  `<span class="pln">This is a paragraph</span>`
3.  `<span class="tag">&lt;/p&gt;</span>`</pre>

* * *
<div class="md-section-divider"></div>

# CSS样式
<div class="md-section-divider"></div>

## CSS背景
<div class="md-section-divider"></div>

### 1.背景色

使用 background-color 属性为元素设置背景色。这个属性接受任何合法的颜色值。
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="t3jq">

1.  `<span class="pln">p </span><span class="pun">{</span><span class="pln">background</span><span class="pun">-</span><span class="pln">color</span><span class="pun">:</span><span class="pln"> gray</span><span class="pun">;}</span>`</pre>

background-color 不能继承，其默认值是 transparent。transparent 有“透明”之意。也就是说，如果一个元素没有指定背景色，那么背景就是透明的，这样其祖先元素的背景才能可见。
<div class="md-section-divider"></div>

### 2.背景图像

要把图像放入背景，需要使用 background-image 属性。
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="d8jc">

1.  `<span class="pln">body </span><span class="pun">{</span><span class="pln">background</span><span class="pun">-</span><span class="pln">image</span><span class="pun">:</span><span class="pln"> url</span><span class="pun">(</span><span class="str">/i/</span><span class="pln">bg_01</span><span class="pun">.</span><span class="pln">gif</span><span class="pun">);}</span>`
2.  `<span class="pln">p</span><span class="pun">.</span><span class="pln">flower </span><span class="pun">{</span><span class="pln">background</span><span class="pun">-</span><span class="pln">image</span><span class="pun">:</span><span class="pln"> url</span><span class="pun">(</span><span class="str">/i/</span><span class="pln">bg_02</span><span class="pun">.</span><span class="pln">gif</span><span class="pun">);}</span>`
3.  `<span class="pln">a</span><span class="pun">.</span><span class="pln">radio </span><span class="pun">{</span><span class="pln">background</span><span class="pun">-</span><span class="pln">image</span><span class="pun">:</span><span class="pln"> url</span><span class="pun">(</span><span class="str">/i/</span><span class="pln">bg_03</span><span class="pun">.</span><span class="pln">gif</span><span class="pun">);}</span>`</pre><div class="md-section-divider"></div>

### 3.背景重复

如果需要在页面上对背景图像进行平铺，可以使用 background-repeat 属性。 

默认地，背景图像将从一个元素的左上角开始。 

repeat-x 和 repeat-y 分别导致图像只在水平或垂直方向上重复，no-repeat 则不允许图像在任何方向上平铺。
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="r6qo">

1.  `<span class="pln">body</span>`
2.  `<span class="pln">  </span><span class="pun">{</span><span class="pln"> </span>`
3.  `<span class="pln">  background</span><span class="pun">-</span><span class="pln">image</span><span class="pun">:</span><span class="pln"> url</span><span class="pun">(</span><span class="str">/i/</span><span class="pln">bg_01</span><span class="pun">.</span><span class="pln">gif</span><span class="pun">);</span>`
4.  `<span class="pln">  background</span><span class="pun">-</span><span class="pln">repeat</span><span class="pun">:</span><span class="pln"> repeat</span><span class="pun">-</span><span class="pln">y</span><span class="pun">;</span>`
5.  `<span class="pln">  </span><span class="pun">}</span>`</pre><div class="md-section-divider"></div>

### 4.背景定位

利用 background-position 属性改变图像在背景中的位置。
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="29am">

1.  `<span class="pln">body</span>`
2.  `<span class="pln">  </span><span class="pun">{</span><span class="pln"> </span>`
3.  `<span class="pln">    background</span><span class="pun">-</span><span class="pln">image</span><span class="pun">:</span><span class="pln">url</span><span class="pun">(</span><span class="str">/i/</span><span class="pln">bg_01</span><span class="pun">.</span><span class="pln">gif</span><span class="pun">);</span>`
4.  `<span class="pln">    background</span><span class="pun">-</span><span class="pln">repeat</span><span class="pun">:</span><span class="kwd">no</span><span class="pun">-</span><span class="pln">repeat</span><span class="pun">;</span>`
5.  `<span class="pln">    background</span><span class="pun">-</span><span class="pln">position</span><span class="pun">:</span><span class="pln">center</span><span class="pun">;</span>`
6.  `<span class="pln">  </span><span class="pun">}</span>`</pre>

为 background-position 属性提供值有很多方法：
> *   关键字：top、bottom、left、right 、center
> *   长度值：100px、5cm
> *   百分数值<div class="md-section-divider"></div>

#### ①关键字

关键字可以成对出现。 

根据规范，位置关键字可以按任何顺序出现，只要保证不超过两个关键字 - 一个对应水平方向，另一个对应垂直方向。 

如果只出现一个关键字，则认为另一个关键字是 center。 

例如，如果希望每个段落的中部上方出现一个图像，只需声明如下：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="ysps">

1.  `<span class="pln">p</span>`
2.  `<span class="pln">  </span><span class="pun">{</span><span class="pln"> </span>`
3.  `<span class="pln">    background</span><span class="pun">-</span><span class="pln">image</span><span class="pun">:</span><span class="pln">url</span><span class="pun">(</span><span class="str">'bgimg.gif'</span><span class="pun">);</span>`
4.  `<span class="pln">    background</span><span class="pun">-</span><span class="pln">repeat</span><span class="pun">:</span><span class="kwd">no</span><span class="pun">-</span><span class="pln">repeat</span><span class="pun">;</span>`
5.  `<span class="pln">    background</span><span class="pun">-</span><span class="pln">position</span><span class="pun">:</span><span class="pln">top</span><span class="pun">;</span>`
6.  `<span class="pln">  </span><span class="pun">}</span>`</pre>

等价的位置关键字：
<table data-anchor-id="egnk" class="table table-striped-white table-bordered">
<thead>
<tr>
 <th>单一关键字</th>
 <th>等价关键字</th>
</tr>
</thead>
<tbody><tr>
 <td>center</td>
 <td>center center</td>
</tr>
<tr>
 <td>top</td>
 <td>top center 或 center top</td>
</tr>
<tr>
 <td>bottom</td>
 <td>bottom center 或 center bottom</td>
</tr>
<tr>
 <td>right</td>
 <td>right center 或 center right</td>
</tr>
<tr>
 <td>left</td>
 <td>left center 或 center left</td>
</tr>
</tbody></table><div class="md-section-divider"></div>

#### ②百分数值

以下这个图像放在水平方向 2/3、垂直方向 1/3 处。
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="lz6e">

1.  `<span class="pln">body</span>`
2.  `<span class="pln">  </span><span class="pun">{</span><span class="pln"> </span>`
3.  `<span class="pln">    background</span><span class="pun">-</span><span class="pln">image</span><span class="pun">:</span><span class="pln">url</span><span class="pun">(</span><span class="str">'/i/bg_01.gif'</span><span class="pun">);</span>`
4.  `<span class="pln">    background</span><span class="pun">-</span><span class="pln">repeat</span><span class="pun">:</span><span class="kwd">no</span><span class="pun">-</span><span class="pln">repeat</span><span class="pun">;</span>`
5.  `<span class="pln">    background</span><span class="pun">-</span><span class="pln">position</span><span class="pun">:</span><span class="lit">66</span><span class="pun">%</span><span class="pln"> </span><span class="lit">33</span><span class="pun">%;</span>`
6.  `<span class="pln">  </span><span class="pun">}</span>`</pre>

如果只提供一个百分数值，所提供的这个值将用作水平值，垂直值将假设为 50%。这一点与关键字类似。
<div class="md-section-divider"></div>

#### ③长度值

以下图像的左上角将在元素内边距区左上角向右 50 像素、向下 100 像素的位置上。
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="yerx">

1.  `<span class="pln">body</span>`
2.  `<span class="pln">  </span><span class="pun">{</span><span class="pln"> </span>`
3.  `<span class="pln">    background</span><span class="pun">-</span><span class="pln">image</span><span class="pun">:</span><span class="pln">url</span><span class="pun">(</span><span class="str">'/i/bg_01.gif'</span><span class="pun">);</span>`
4.  `<span class="pln">    background</span><span class="pun">-</span><span class="pln">repeat</span><span class="pun">:</span><span class="kwd">no</span><span class="pun">-</span><span class="pln">repeat</span><span class="pun">;</span>`
5.  `<span class="pln">    background</span><span class="pun">-</span><span class="pln">position</span><span class="pun">:</span><span class="lit">50px</span><span class="pln"> </span><span class="lit">100px</span><span class="pun">;</span>`
6.  `<span class="pln">  </span><span class="pun">}</span>`</pre><div class="md-section-divider"></div>

### 5.背景关联

通过 background-attachment 属性可防止图片随着滚动条滚动。 

通过这个属性，可以声明图像相对于可视区是固定的（fixed），因此不会受到滚动的影响。
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="nlcq">

1.  `<span class="pln">body </span>`
2.  `<span class="pln">  </span><span class="pun">{</span>`
3.  `<span class="pln">  background</span><span class="pun">-</span><span class="pln">image</span><span class="pun">:</span><span class="pln">url</span><span class="pun">(</span><span class="str">/i/</span><span class="pln">bg_01</span><span class="pun">.</span><span class="pln">gif</span><span class="pun">);</span>`
4.  `<span class="pln">  background</span><span class="pun">-</span><span class="pln">repeat</span><span class="pun">:</span><span class="kwd">no</span><span class="pun">-</span><span class="pln">repeat</span><span class="pun">;</span>`
5.  `<span class="pln">  background</span><span class="pun">-</span><span class="pln">attachment</span><span class="pun">:</span><span class="kwd">fixed</span>`
6.  `<span class="pln">  </span><span class="pun">}</span>`</pre>

background-attachment 属性的默认值是 scroll，也就是说，在默认的情况下，背景会随文档滚动。

* * *
<div class="md-section-divider"></div>

## CSS文本
<div class="md-section-divider"></div>

### 1.缩进文本

`text-indent`实现首行缩进，该长度可以为负值。
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="bzro">

1.  `<span class="pln">p </span><span class="pun">{</span><span class="pln">text</span><span class="pun">-</span><span class="pln">indent</span><span class="pun">:</span><span class="pln"> </span><span class="lit">5em</span><span class="pun">;}</span>`</pre>

在为`text-indent`设置负值时要当心，如果对一个段落设置了负值，那么首行的某些文本可能会超出浏览器窗口的左边界。为了避免出现这种显示问题，可针对负缩进再设置一个外边距或一些内边距：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="jfux">

1.  `<span class="pln">p </span><span class="pun">{</span><span class="pln">text</span><span class="pun">-</span><span class="pln">indent</span><span class="pun">:</span><span class="pln"> </span><span class="pun">-</span><span class="lit">5em</span><span class="pun">;</span><span class="pln"> padding</span><span class="pun">-</span><span class="pln">left</span><span class="pun">:</span><span class="pln"> </span><span class="lit">5em</span><span class="pun">;}</span>`</pre>

`text-indent`可使用百分比值。百分数是相对于元素的父元素的宽度。如下例子，缩进值是父元素的20%，即100px：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="p33l">

1.  `<span class="pln">div </span><span class="pun">{</span><span class="pln">width</span><span class="pun">:</span><span class="pln"> </span><span class="lit">500px</span><span class="pun">;}</span>`
2.  `<span class="pln">p </span><span class="pun">{</span><span class="pln">text</span><span class="pun">-</span><span class="pln">indent</span><span class="pun">:</span><span class="pln"> </span><span class="lit">20</span><span class="pun">%;}</span>`
3.4.  `<span class="str">&lt;div&gt;</span>`
5.  `<span class="str">&lt;p&gt;</span><span class="kwd">this</span><span class="pln"> </span><span class="kwd">is</span><span class="pln"> a paragragh</span><span class="pun">&lt;/</span><span class="pln">p</span><span class="pun">&gt;</span>`
6.  `<span class="pun">&lt;/</span><span class="pln">div</span><span class="pun">&gt;</span>`</pre>

`text-indent`属性可以继承。
<div class="md-section-divider"></div>

### 2.水平对齐

`text-align`属性影响文本行之间的对齐方式，它的值分别为left、right、cneter、justify、inherit 

left、right、cneter分别为左对齐、右对齐、居中对齐； 

justify为两端对齐； 

inherit为从父元素继承text-align属性的值。

注意：`text-align:center` 与 `&lt;CENTER&gt;` 

text-align:center 与 `&lt;CENTER&gt;` 二者作用不相同。 

`&lt;CENTER&gt;` 不仅影响文本，还会把整个元素居中。 

`text-align` 不会控制元素的对齐，而只影响内部内容。元素本身不会从一段移到另一端，只是其中的文本受影响。
<div class="md-section-divider"></div>

### 3.字间隔

`word-spacing`改变字（单词）之间的标准间隔，其默认值为0，可接受正长度值或负长度值。
<div class="md-section-divider"></div>

### 4.字母间隔

`letter-spacing`改变字母之间的标准间隔，其默认值为0，可接受正长度值或负长度值。
<div class="md-section-divider"></div>

### 5.字符转换

`text-transform`改变文本的大小写，其值有四个：
> *   none：不做任何改动
> *   uppercase：全大写
> *   lowercase：全小写
> *   capitaliza：**每个单词**的首字母大写<div class="md-section-divider"></div>

### 6.文本装饰

`text-decoration`的值有五个：
> *   none：不做任何改动
> *   underline：加下划线
> *   overline：加上划线
> *   line-through：加贯穿线
> *   blink：文本闪烁

通常，无装饰的文本是默认外观，但也不总是这样。例如，链接默认地会有下划线。如果希望去掉超链接的下划线，可以使用以下 CSS 来做到这一点：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="nh9m">

1.  `<span class="pln">a </span><span class="pun">{</span><span class="pln">text</span><span class="pun">-</span><span class="pln">decoration</span><span class="pun">:</span><span class="pln"> none</span><span class="pun">;}</span>`</pre>

注意：如果两个不同的装饰都与同一元素匹配，胜出规则的值会完全取代另一个值。如下：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="hqj6">

1.  `<span class="pln">h2</span><span class="pun">.</span><span class="pln">stricken </span><span class="pun">{</span><span class="pln">text</span><span class="pun">-</span><span class="pln">decoration</span><span class="pun">:</span><span class="pln"> line</span><span class="pun">-</span><span class="pln">through</span><span class="pun">;}</span>`
2.  `<span class="pln">h2 </span><span class="pun">{</span><span class="pln">text</span><span class="pun">-</span><span class="pln">decoration</span><span class="pun">:</span><span class="pln"> underline overline</span><span class="pun">;}</span>`</pre>

对于给定的规则，所有 `class` 为 `stricken` 的 `h2` 元素都只有一个贯穿线装饰，而没有下划线和上划线，因为 **`text-decoration` 值会替换而不是累积起来。**
<div class="md-section-divider"></div>

### 7.处理空白符

`white-space` 属性会影响到用户代理对源文档中的空格、换行和 tab 字符的处理。
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="bnhl">

1.  `<span class="pln">p </span><span class="pun">{</span><span class="pln">white</span><span class="pun">-</span><span class="pln">space</span><span class="pun">:</span><span class="pln"> normal</span><span class="pun">;}</span>`</pre>

①值 normal 

按照平常的做法去处理，丢掉多余的空白符。换行字符（回车）会转换为空格，一行中多个空格的序列也会转换为一个空格。

②值 pre 

不合并空白符，也不忽略换行符。相当于html中`&lt;pre&gt;&lt;/pre&gt;`预文本格式。

③值 nowrap 

不合并空白符，但忽略换行符，转变成一个空格，除非使用了一个 br 元素。

④值 pre-wrap 

不仅保留空白符并保留换行符，还允许自动换行。

⑤值 pre-line 

保留换行符，并允许自动换行，但是会合并空白符。

**总结**
<table data-anchor-id="2arp" class="table table-striped-white table-bordered">
<thead>
<tr>
 <th>值</th>
 <th>空白符</th>
 <th>换行符</th>
 <th>自动换行</th>
</tr>
</thead>
<tbody><tr>
 <td>normal</td>
 <td>合并</td>
 <td>忽略</td>
 <td>允许</td>
</tr>
<tr>
 <td>pre</td>
 <td>保留</td>
 <td>保留</td>
 <td>不允许</td>
</tr>
<tr>
 <td>nowrap</td>
 <td>保留</td>
 <td>忽略</td>
 <td>不允许</td>
</tr>
<tr>
 <td>pre-wrap</td>
 <td>保留</td>
 <td>保留</td>
 <td>允许</td>
</tr>
<tr>
 <td>pre-line</td>
 <td>合并</td>
 <td>保留</td>
 <td>允许</td>
</tr>
</tbody></table><div class="md-section-divider"></div>

### 8.文本方向

`direction` 属性影响块级元素中文本的书写方向、表中列布局的方向、内容水平填充其元素框的方向、以及两端对齐元素中最后一行的位置。其属性值有两个：
> *   ltr：从左到右的文本  （left to right）
> *   rtl：从右到左的文本  （right to left）

* * *
<div class="md-section-divider"></div>

## CSS字体
<div class="md-section-divider"></div>

### 1.使用字体系列

以下，文档将会使用一种 sans-serif 字体：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="8btx">

1.  `<span class="pln">body </span><span class="pun">{</span><span class="pln">font</span><span class="pun">-</span><span class="pln">family</span><span class="pun">:</span><span class="pln"> sans</span><span class="pun">-</span><span class="pln">serif</span><span class="pun">;}</span>`</pre>

以下，如果用户代理上没有安装Georgia字体，就只能使用用户代理的默认字体来显示 h1 元素：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="0oy2">

1.  `<span class="pln">h1 </span><span class="pun">{</span><span class="pln">font</span><span class="pun">-</span><span class="pln">family</span><span class="pun">:</span><span class="pln"> </span><span class="typ">Georgia</span><span class="pun">;}</span>`</pre>

可通过结合特定字体名和通用字体系列来解决这个问题：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="dlo5">

1.  `<span class="pln">h1 </span><span class="pun">{</span><span class="pln">font</span><span class="pun">-</span><span class="pln">family</span><span class="pun">:</span><span class="pln"> </span><span class="typ">Georgia</span><span class="pun">,</span><span class="pln"> serif</span><span class="pun">;}</span>`</pre>

当字体名中有一个或多个空格（比如 New York），或者如果字体名包括 # 或 $ 之类的符号，需要在 font-family 声明的值加上引号。
<div class="md-section-divider"></div>

### 2.字体风格

`font-style` 属性最常用于规定斜体文本。其值有三个：
> *   normal：文本正常显示
> *   italic：文本斜体显示
> *   oblique：文本倾斜显示

italic 和 oblique 的区别： 

斜体（italic）是一种简单的字体风格，对每个字母的结构有一些小改动，来反映变化的外观。 

倾斜（oblique）文本则是正常竖直文本的一个倾斜版本。 

通常情况下，italic 和 oblique 文本在 web 浏览器中看上去完全一样。
<div class="md-section-divider"></div>

### 3.字体变形

`font-variant` 属性可以设定小型大写字母。 

小型大写字母不是一般的大写字母，也不是小写字母，这种字母采用不同大小的大写字母。
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="by0a">

1.  `<span class="pln">p </span><span class="pun">{</span><span class="pln">font</span><span class="pun">-</span><span class="pln">variant</span><span class="pun">:</span><span class="pln">small</span><span class="pun">-</span><span class="pln">caps</span><span class="pun">;}</span>`</pre>

实例：[http://www.w3school.com.cn/tiy/t.asp?f=csse_font-variant](http://www.w3school.com.cn/tiy/t.asp?f=csse_font-variant)
<div class="md-section-divider"></div>

### 4.字体加粗

`font-weight` 属性设置文本的粗细。 

使用 bold 关键字可以将文本设置为粗体。 

关键字 100 ~ 900 为字体指定了9级加粗度。如果一个字体内置了这些加粗级别，那么这些数字就直接映射到预定义的级别，100对应最细的字体变形，900对应最粗的字体变形。数字 400 等价于 normal，而 700 等价于 bold。
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="wvup">

1.  `<span class="pln">p</span><span class="pun">.</span><span class="pln">normal </span><span class="pun">{</span><span class="pln">font</span><span class="pun">-</span><span class="pln">weight</span><span class="pun">:</span><span class="pln">normal</span><span class="pun">;}</span>`
2.  `<span class="pln">p</span><span class="pun">.</span><span class="pln">thick </span><span class="pun">{</span><span class="pln">font</span><span class="pun">-</span><span class="pln">weight</span><span class="pun">:</span><span class="pln">bold</span><span class="pun">;}</span>`
3.  `<span class="pln">p</span><span class="pun">.</span><span class="pln">thicker </span><span class="pun">{</span><span class="pln">font</span><span class="pun">-</span><span class="pln">weight</span><span class="pun">:</span><span class="lit">900</span><span class="pun">;}</span>`</pre><div class="md-section-divider"></div>

### 5.字体大小

font-size 属性设置文本的大小。其值可以是绝对值或相对值。 

绝对值：

*   将文本设置为指定的大小
*   不允许用户在所有浏览器中改变文本大小（不利于可用性）
*   绝对大小在确定了输出的物理尺寸时很有用

相对值：

*   相对于周围的元素来设置大小
*   允许用户在浏览器改变文本大小

如您没有规定字体大小，普通文本（比如段落）的默认大小是 16 像素 (16px=1em)。

①使用像素来设置字体大小： 

通过像素设置文本大小，可以对文本大小进行完全控制：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="mcam">

1.  `<span class="pln">h1 </span><span class="pun">{</span><span class="pln">font</span><span class="pun">-</span><span class="pln">size</span><span class="pun">:</span><span class="lit">60px</span><span class="pun">;}</span>`
2.  `<span class="pln">h2 </span><span class="pun">{</span><span class="pln">font</span><span class="pun">-</span><span class="pln">size</span><span class="pun">:</span><span class="lit">40px</span><span class="pun">;}</span>`
3.  `<span class="pln">p </span><span class="pun">{</span><span class="pln">font</span><span class="pun">-</span><span class="pln">size</span><span class="pun">:</span><span class="lit">14px</span><span class="pun">;}</span>`</pre>

②使用em 来设置字体大小 

推荐使用 em 尺寸单位。 

1em 等于当前的字体尺寸。如果一个元素的 font-size 为 16 像素，那么对于该元素，1em 就等于 16 像素。在设置字体大小时，em 的值会相对于父元素的字体大小改变。 

浏览器中默认的文本大小是 16 像素。因此 1em 的默认尺寸是 16 像素。 

可以使用下面这个公式将像素转换为 em：pixels/16=em 

注：16 等于父元素的默认字体大小，假设父元素的 font-size 为 20px，那么公式需改为：pixels/20=em
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="g3w0">

1.  `<span class="pln">h1 </span><span class="pun">{</span><span class="pln">font</span><span class="pun">-</span><span class="pln">size</span><span class="pun">:</span><span class="lit">3.75em</span><span class="pun">;}</span><span class="pln"> </span><span class="com">/* 60px/16=3.75em */</span>`
2.  `<span class="pln">h2 </span><span class="pun">{</span><span class="pln">font</span><span class="pun">-</span><span class="pln">size</span><span class="pun">:</span><span class="lit">2.5em</span><span class="pun">;}</span><span class="pln">  </span><span class="com">/* 40px/16=2.5em */</span>`
3.  `<span class="pln">p </span><span class="pun">{</span><span class="pln">font</span><span class="pun">-</span><span class="pln">size</span><span class="pun">:</span><span class="lit">0.875em</span><span class="pun">;}</span><span class="pln"> </span><span class="com">/* 14px/16=0.875em */</span>`</pre>

③ 结合使用百分比和em 

在所有浏览器中均有效的方案是为 body 元素（父元素）以百分比设置默认的 font-size 值：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="s8i0">

1.  `<span class="pln">body </span><span class="pun">{</span><span class="pln">font</span><span class="pun">-</span><span class="pln">size</span><span class="pun">:</span><span class="lit">100</span><span class="pun">%;}</span>`
2.  `<span class="pln">h1 </span><span class="pun">{</span><span class="pln">font</span><span class="pun">-</span><span class="pln">size</span><span class="pun">:</span><span class="lit">3.75em</span><span class="pun">;}</span>`
3.  `<span class="pln">h2 </span><span class="pun">{</span><span class="pln">font</span><span class="pun">-</span><span class="pln">size</span><span class="pun">:</span><span class="lit">2.5em</span><span class="pun">;}</span>`
4.  `<span class="pln">p </span><span class="pun">{</span><span class="pln">font</span><span class="pun">-</span><span class="pln">size</span><span class="pun">:</span><span class="lit">0.875em</span><span class="pun">;}</span>`</pre>

* * *
<div class="md-section-divider"></div>

## CSS链接
<div class="md-section-divider"></div>

### 1.设置链接的样式

链接的四种状态：
> *   a:link - 普通的、未被访问的链接
> *   a:visited - 用户已访问的链接
> *   a:hover - 鼠标指针位于链接的上方
> *   a:active - 链接被点击的时刻<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="tpwq">

1.  `<span class="pln">a</span><span class="pun">:</span><span class="pln">link </span><span class="pun">{</span><span class="pln">color</span><span class="pun">:#</span><span class="pln">FF0000</span><span class="pun">;}</span><span class="pln">     </span><span class="com">/* 未被访问的链接 */</span>`
2.  `<span class="pln">a</span><span class="pun">:</span><span class="pln">visited </span><span class="pun">{</span><span class="pln">color</span><span class="pun">:#</span><span class="lit">00FF00</span><span class="pun">;}</span><span class="pln">  </span><span class="com">/* 已被访问的链接 */</span>`
3.  `<span class="pln">a</span><span class="pun">:</span><span class="pln">hover </span><span class="pun">{</span><span class="pln">color</span><span class="pun">:#</span><span class="pln">FF00FF</span><span class="pun">;}</span><span class="pln">    </span><span class="com">/* 鼠标指针移动到链接上 */</span>`
4.  `<span class="pln">a</span><span class="pun">:</span><span class="pln">active </span><span class="pun">{</span><span class="pln">color</span><span class="pun">:#</span><span class="lit">0000FF</span><span class="pun">;}</span><span class="pln">   </span><span class="com">/* 正在被点击的链接 */</span>`</pre>

**注意：当为链接的不同状态设置样式时，请按照以下次序规则：**
> *   a:hover 必须位于 a:link 和 a:visited 之后
> *   a:active 必须位于 a:hover 之后<div class="md-section-divider"></div>

### 2.常见的链接样式
<div class="md-section-divider"></div>

#### ①文本修饰

`text-decoration` 属性常用于去掉链接中的下划线。
<div class="md-section-divider"></div>

#### ②背景色

`background-color` 属性规定链接的背景色。

* * *
<div class="md-section-divider"></div>

## CSS列表

[http://www.w3school.com.cn/css/css_list.asp](http://www.w3school.com.cn/css/css_list.asp)

在一个无序列表中，列表项的标志 (marker) 是出现在各列表项旁边的圆点。在有序列表中，标志可能是字母、数字或另外某种计数体系中的一个符号。 

要修改用于列表项的标志类型，可以使用属性[list-style-type](http://www.w3school.com.cn/cssref/pr_list-style-type.asp)：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="ee62">

1.  `<span class="pln">ul </span><span class="pun">{</span><span class="pln">list</span><span class="pun">-</span><span class="pln">style</span><span class="pun">-</span><span class="pln">type </span><span class="pun">:</span><span class="pln"> square</span><span class="pun">}</span>`</pre>

如果想对各标志使用一个图像，可以利用属性[list-style-image](http://www.w3school.com.cn/cssref/pr_list-style-image.asp)：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="1et1">

1.  `<span class="pln">ul li </span><span class="pun">{</span><span class="pln">list</span><span class="pun">-</span><span class="pln">style</span><span class="pun">-</span><span class="pln">image </span><span class="pun">:</span><span class="pln"> url</span><span class="pun">(</span><span class="pln">xxx</span><span class="pun">.</span><span class="pln">gif</span><span class="pun">)}</span>`</pre>

确定标志出现在列表项内容之外还是内容内部，可以利用属性[list-style-position](http://www.w3school.com.cn/cssref/pr_list-style-position.asp)：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="gozn">

1.  `<span class="pln">ul </span><span class="pun">{</span><span class="pln"> list</span><span class="pun">-</span><span class="pln">style</span><span class="pun">-</span><span class="pln">position</span><span class="pun">:</span><span class="pln">inside</span><span class="pun">;}</span>`</pre>

* * *
<div class="md-section-divider"></div>

## CSS表格

[http://www.w3school.com.cn/css/css_table.asp](http://www.w3school.com.cn/css/css_table.asp)

* * *
<div class="md-section-divider"></div>

# CSS框模型
<div class="md-section-divider"></div>

## CSS框模型概述

![CCS框模型](http://www.w3school.com.cn/i/ct_boxmodel.gif)

*   element : 元素
*   padding : 内边距
*   border : 边框
*   margin : 外边距

* * *
<div class="md-section-divider"></div>

## CSS内边距
<div class="md-section-divider"></div>

### 1.CSS padding属性

padding 属性定义元素的内边距。 

padding属性接受长度值或百分比值，但不允许使用负值。
<div class="md-section-divider"></div>

### 2.单边内边距属性

以下两种写法效果是一样的：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="p87n">

1.  `<span class="pln">h1 </span><span class="pun">{</span><span class="pln">padding</span><span class="pun">:</span><span class="pln"> </span><span class="lit">10px</span><span class="pln"> </span><span class="lit">0.25em</span><span class="pln"> </span><span class="lit">2ex</span><span class="pln"> </span><span class="lit">20</span><span class="pun">%;}</span>`</pre><div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="8ven">

1.  `<span class="pln">h1 </span><span class="pun">{</span>`
2.  `<span class="pln">  padding</span><span class="pun">-</span><span class="pln">top</span><span class="pun">:</span><span class="pln"> </span><span class="lit">10px</span><span class="pun">;</span>`
3.  `<span class="pln">  padding</span><span class="pun">-</span><span class="pln">right</span><span class="pun">:</span><span class="pln"> </span><span class="lit">0.25em</span><span class="pun">;</span>`
4.  `<span class="pln">  padding</span><span class="pun">-</span><span class="pln">bottom</span><span class="pun">:</span><span class="pln"> </span><span class="lit">2ex</span><span class="pun">;</span>`
5.  `<span class="pln">  padding</span><span class="pun">-</span><span class="pln">left</span><span class="pun">:</span><span class="pln"> </span><span class="lit">20</span><span class="pun">%;</span>`
6.  `<span class="pln">  </span><span class="pun">}</span>`</pre>

所以，padding属性各边的顺序为上、右、下、左。
<div class="md-section-divider"></div>

### 3.内边距的百分比数值

百分数值是相对于其父元素的 width 计算的，如果父元素的 width 改变，它们也会改变。 

下面这条规则把段落的内边距设置为父元素 width 的 10%：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="jubq">

1.  `<span class="pln"> p </span><span class="pun">{</span><span class="pln">padding</span><span class="pun">:</span><span class="pln"> </span><span class="lit">10</span><span class="pun">%;}</span>`</pre>

**注意：上下内边距与左右内边距一致；即上下内边距的百分数会相对于父元素宽度设置，而不是相对于高度。**

* * *
<div class="md-section-divider"></div>

## CSS 边框
<div class="md-section-divider"></div>

### 1.边框与背景

边框绘制在“元素的背景之上”。如果有些边框是“间断的”（例如，点线边框或虚线框），元素的背景应当出现在边框的可见部分之间。
<div class="md-section-divider"></div>

### 2.边框的样式

CSS 的 border-style 属性定义了 10 个不同的非 inherit 样式，包括 none。 

[http://www.w3school.com.cn/cssref/pr_border-style.asp](http://www.w3school.com.cn/cssref/pr_border-style.asp)

下面这条规则定义了四种边框样式：实线上边框、点线右边框、虚线下边框和一个双线左边框。
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="oibm">

1.  `<span class="pln">p</span><span class="pun">.</span><span class="pln">aside </span><span class="pun">{</span><span class="pln">border</span><span class="pun">-</span><span class="pln">style</span><span class="pun">:</span><span class="pln"> solid dotted dashed </span><span class="kwd">double</span><span class="pun">;}</span>`</pre>

如果我们为元素框的某一边设置边框样式，而不是设置所有 4 个边的边框样式，可以使用下面的单边边框样式属性：

*   border-top-style
*   border-right-style
*   border-bottom-style
*   border-left-style<div class="md-section-divider"></div>

### 3.边框的宽度

通过 border-width 属性为边框指定宽度。 

为边框指定宽度有两种方法：可以指定长度值，比如 2px 或 0.1em；或者使用 3 个关键字之一，它们分别是 thin 、medium（默认值） 和 thick。

可以按照 top-right-bottom-left 的顺序设置元素的各边边框：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="ktz1">

1.  `<span class="pln">p </span><span class="pun">{</span><span class="pln">border</span><span class="pun">-</span><span class="pln">width</span><span class="pun">:</span><span class="pln"> </span><span class="lit">15px</span><span class="pln"> </span><span class="lit">5px</span><span class="pln"> </span><span class="lit">15px</span><span class="pln"> </span><span class="lit">5px</span><span class="pun">;}</span>`</pre>

也可以通过下列属性分别设置边框各边的宽度：

*   border-top-width
*   border-right-width
*   border-bottom-width
*   border-left-width

下面的规则与上面的例子是等价的：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="g0rw">

1.  `<span class="pln">p </span><span class="pun">{</span>`
2.  `<span class="pln">  border</span><span class="pun">-</span><span class="pln">top</span><span class="pun">-</span><span class="pln">width</span><span class="pun">:</span><span class="pln"> </span><span class="lit">15px</span><span class="pun">;</span>`
3.  `<span class="pln">  border</span><span class="pun">-</span><span class="pln">right</span><span class="pun">-</span><span class="pln">width</span><span class="pun">:</span><span class="pln"> </span><span class="lit">5px</span><span class="pun">;</span>`
4.  `<span class="pln">  border</span><span class="pun">-</span><span class="pln">bottom</span><span class="pun">-</span><span class="pln">width</span><span class="pun">:</span><span class="pln"> </span><span class="lit">15px</span><span class="pun">;</span>`
5.  `<span class="pln">  border</span><span class="pun">-</span><span class="pln">left</span><span class="pun">-</span><span class="pln">width</span><span class="pun">:</span><span class="pln"> </span><span class="lit">5px</span><span class="pun">;</span>`
6.  `<span class="pln">  </span><span class="pun">}</span>`</pre>

如果把 border-style 设置为 none，边框会没有了，尽管定义了边框的样式（如宽度），但并不会起效。
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="axpv">

1.  `<span class="pln">p </span><span class="pun">{</span><span class="pln">border</span><span class="pun">-</span><span class="pln">style</span><span class="pun">:</span><span class="pln"> none</span><span class="pun">;</span><span class="pln"> border</span><span class="pun">-</span><span class="pln">width</span><span class="pun">:</span><span class="pln"> </span><span class="lit">50px</span><span class="pun">;}</span>`</pre>

**注意：由于 border-style的默认值是none，如果没有声明样式，就相当于 border-style:none。因此，如果希望边框出现，就必须声明一个边框样式。**
<div class="md-section-divider"></div>

### 4.边框的颜色

border-color 属性设置边框的颜色，一次可以接受最多4个颜色值。
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="uz9l">

1.  `<span class="pln">p </span><span class="pun">{</span>`
2.  `<span class="pln">  border</span><span class="pun">-</span><span class="pln">style</span><span class="pun">:</span><span class="pln"> solid</span><span class="pun">;</span>`
3.  `<span class="pln">  border</span><span class="pun">-</span><span class="pln">color</span><span class="pun">:</span><span class="pln"> blue rgb</span><span class="pun">(</span><span class="lit">25</span><span class="pun">%,</span><span class="lit">35</span><span class="pun">%,</span><span class="lit">45</span><span class="pun">%)</span><span class="pln"> </span><span class="com">#909090 red;</span>`
4.  `<span class="pln">  </span><span class="pun">}</span>`</pre>

定义单边颜色：

*   border-top-color
*   border-right-color
*   border-bottom-color
*   border-left-color

* * *
<div class="md-section-divider"></div>

## CSS外边框

margin 属性设置外边框。 

margin 可以设置为 auto，常用于居中。 

如果为margin设置百分比数值，百分数是相对于父元素width计算的，与padding一样。 

margin 的默认值是0，所以如果没有为margin声明一个值，就不会出现外边距。

其他内容与padding属性基本相同。

* * *
<div class="md-section-divider"></div>

## CSS外边框合并

外边距合并指的是，当两个垂直外边距相遇时，它们将形成一个外边距。合并后的外边距的高度等于两个发生合并的外边距的高度中的较大者。

当一个元素出现在另一个元素上面时，第一个元素的下外边距与第二个元素的上外边距会发生合并。请看下图： 

![外边框合并1](http://www.w3school.com.cn/i/ct_css_margin_collapsing_example_1.gif)

当一个元素包含在另一个元素中时（假设没有内边距或边框把外边距分隔开），它们的上和/或下外边距也会发生合并。请看下图： 

![外边框合并2](http://www.w3school.com.cn/i/ct_css_margin_collapsing_example_2.gif)

假设有一个空元素，它有外边距，但是没有边框或填充。在这种情况下，上外边距与下外边距就碰到了一起，它们会发生合并： 

![外边框合并3](http://www.w3school.com.cn/i/ct_css_margin_collapsing_example_3.gif)

如果这个外边距遇到另一个元素的外边距，它还会发生合并： 

![外边框合并4](http://www.w3school.com.cn/i/ct_css_margin_collapsing_example_4.gif)

这就是一系列的段落元素占用空间非常小的原因，因为它们的所有外边距都合并到一起，形成了一个小的外边距。

外边距合并初看上去可能有点奇怪，但是实际上，它是有意义的。以由几个段落组成的典型文本页面为例。第一个段落上面的空间等于段落的上外边距。如果没有外边距合并，后续所有段落之间的外边距都将是相邻上外边距和下外边距的和。这意味着段落之间的空间是页面顶部的两倍。如果发生外边距合并，段落之间的上外边距和下外边距就合并在一起，这样各处的距离就一致了。 

![外边框合并5](http://www.w3school.com.cn/i/ct_css_margin_collapsing.gif)

**只有普通文档流中块框的垂直外边距才会发生外边距合并。行内框、浮动框或绝对定位之间的外边距不会合并。**

* * *
<div class="md-section-divider"></div>

# CSS定位
<div class="md-section-divider"></div>

## CSS定位概述
<div class="md-section-divider"></div>

### 1.块状元素与行内元素

div、h1 或 p 元素常常被称为块级元素。这意味着这些元素显示为一块内容，即“块框”。与之相反，span和strong等元素称为“行内元素”，这是因为它们的内容显示在行中，即“行内框”。

我们可以使用 display 属性改变生成的框的类型。这意味着，通过将 display 属性设置为block，可以让行内元素（比如`&lt;a&gt;`元素）表现得像块级元素一样。还可以通过把display设置为none，让生成的元素根本没有框。这样的话，该框及其所有内容就不再显示，不占用文档中的空间。
<div class="md-section-divider"></div>

### 2.CSS定位机制

CSS 有三种基本的定位机制：普通流、浮动和绝对定位。

除非专门指定，否则所有框都在普通流中定位。也就是说，普通流中的元素的位置由元素在 (X)HTML 中的位置决定。

块级框从上到下一个接一个地排列，框之间的垂直距离是由框的垂直外边距计算出来。

行内框在一行中水平布置。可以使用水平内边距、边框和外边距调整它们的间距。但是，垂直内边距、边框和外边距不影响行内框的高度。由一行形成的水平框称为行框（Line Box），行框的高度总是足以容纳它包含的所有行内框。不过，设置行高可以增加这个框的高度。
<div class="md-section-divider"></div>

### 3.CSS position 属性

通过使用position属性，4种不同类型的定位，这会影响元素框生成的方式。
> *   **static**
>       元素框正常生成。块级元素生成一个矩形框，作为文档流的一部分，行内元素则会创建一个或多个行框，置于其父元素中。
> *   **relative(相对定位)**
>       元素框偏移某个距离。元素仍保持其未定位前的形状，它原本所占的空间仍保留。
> *   **absolute(绝对定位)**
>       元素框从文档流完全删除，并相对于其包含块定位。包含块可能是文档中的另一个元素或者是初始包含块。元素原先在正常文档流中所占的空间会关闭，就好像元素原来不存在一样。元素定位后生成一个块级框，而不论原来它在正常流中生成何种类型的框。
> *   **fixed(固定定位)**
>       元素框的表现类似于将position设置为absolute，不过其包含块是视窗本身。

* * *
<div class="md-section-divider"></div>

## CSS相对定位
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="w045">

1.  `<span class="com">#box_relative {</span>`
2.  `<span class="pln">  position</span><span class="pun">:</span><span class="pln"> relative</span><span class="pun">;</span>`
3.  `<span class="pln">  left</span><span class="pun">:</span><span class="pln"> </span><span class="lit">30px</span><span class="pun">;</span>`
4.  `<span class="pln">  top</span><span class="pun">:</span><span class="pln"> </span><span class="lit">20px</span><span class="pun">;</span>`
5.  `<span class="pun">}</span>`</pre>

如下图所示： 

![相对定位](http://www.w3school.com.cn/i/ct_css_positioning_relative_example.gif)

**注意：在使用相对定位时，无论是否进行移动，元素仍然占据原来的空间。因此，移动元素会导致它覆盖其它框。**

* * *
<div class="md-section-divider"></div>

## CSS绝对定位

绝对定位使元素的位置与文档流无关，因此不占据空间。
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="xcvo">

1.  `<span class="com">#box_relative {</span>`
2.  `<span class="pln">  position</span><span class="pun">:</span><span class="pln"> absolute</span><span class="pun">;</span>`
3.  `<span class="pln">  left</span><span class="pun">:</span><span class="pln"> </span><span class="lit">30px</span><span class="pun">;</span>`
4.  `<span class="pln">  top</span><span class="pun">:</span><span class="pln"> </span><span class="lit">20px</span><span class="pun">;</span>`
5.  `<span class="pun">}</span>`</pre>

![绝对定位](http://www.w3school.com.cn/i/ct_css_positioning_absolute_example.gif)

绝对定位的元素的位置相对于最近的已定位祖先元素，如果元素没有已定位的祖先元素，那么它的位置相对于最初的包含块。

注意：因为绝对定位的框与文档流无关，所以它们可以覆盖页面上的其它元素。可以通过设置 [z-index](http://www.w3school.com.cn/cssref/pr_pos_z-index.asp) 属性来控制这些框的堆放次序。

* * *
<div class="md-section-divider"></div>

## CSS浮动
<div class="md-section-divider"></div>

### 1.CSS浮动

下图，当把框 1 向右浮动时，它脱离文档流并且向右移动，直到它的右边缘碰到包含框的右边缘： 

![向右浮动](http://www.w3school.com.cn/i/ct_css_positioning_floating_right_example.gif)

下图，当框 1 向左浮动时，它脱离文档流并且向左移动，直到它的左边缘碰到包含框的左边缘。因为它不再处于文档流中，所以它不占据空间，实际上覆盖住了框 2，使框 2 从视图中消失。 

如果把所有三个框都向左移动，那么框1向左浮动直到碰到包含框，另外两个框向左浮动直到碰到前一个浮动框。 

![向左浮动](http://www.w3school.com.cn/i/ct_css_positioning_floating_left_example.gif)

下图，如果包含框太窄，无法容纳水平排列的三个浮动元素，那么其它浮动块向下移动，直到有足够的空间。如果浮动元素的高度不同，那么当它们向下移动时可能被其它浮动元素“卡住”： 

![浮动](http://www.w3school.com.cn/i/ct_css_positioning_floating_left_example_2.gif)
<div class="md-section-divider"></div>

### 2.CSS float 属性

float默认值为none，没有继承性。 

可能的值为：
> *   left
> *   right
> *   none
> *   inhert

把图像向右浮动：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="ec9h">

1.  `<span class="pln">img</span>`
2.  `<span class="pln">  </span><span class="pun">{</span>`
3.  `<span class="pln">  </span><span class="kwd">float</span><span class="pun">:</span><span class="pln">right</span><span class="pun">;</span>`
4.  `<span class="pln">  </span><span class="pun">}</span>`</pre><div class="md-section-divider"></div>

### 3.行框和清理

浮动框旁边的行框被缩短，从而给浮动框留出空间，行框围绕浮动框。 

因此，创建浮动框可以使文本围绕图像： 

![行框1](http://www.w3school.com.cn/i/ct_css_positioning_floating_linebox.gif)

要想阻止行框围绕浮动框，需要对该框应用[ clear 属性](http://www.w3school.com.cn/cssref/pr_class_clear.asp)。clear 属性的值可以是 left、right、both 或 none，它表示框的哪些边不应该挨着浮动框。 

为了实现这种效果，在被清理的元素的上外边距上添加足够的空间，使元素的顶边缘垂直下降到浮动框下面： 

![行框2](http://www.w3school.com.cn/i/ct_css_positioning_floating_clear.gif)

假设希望让一个图片浮动到文本块的左边，并且希望这幅图片和文本包含在另一个具有背景颜色和边框的元素中。我们可能编写下面的代码：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="1k78">

1.  `<span class="pun">.</span><span class="pln">news </span><span class="pun">{</span>`
2.  `<span class="pln">  background</span><span class="pun">-</span><span class="pln">color</span><span class="pun">:</span><span class="pln"> gray</span><span class="pun">;</span>`
3.  `<span class="pln">  border</span><span class="pun">:</span><span class="pln"> solid </span><span class="lit">1px</span><span class="pln"> black</span><span class="pun">;</span>`
4.  `<span class="pln">  </span><span class="pun">}</span>`
5.6.  `<span class="pun">.</span><span class="pln">news img </span><span class="pun">{</span>`
7.  `<span class="pln">  </span><span class="kwd">float</span><span class="pun">:</span><span class="pln"> left</span><span class="pun">;</span>`
8.  `<span class="pln">  </span><span class="pun">}</span>`
9.10.  `<span class="pun">.</span><span class="pln">news p </span><span class="pun">{</span>`
11.  `<span class="pln">  </span><span class="kwd">float</span><span class="pun">:</span><span class="pln"> right</span><span class="pun">;</span>`
12.  `<span class="pln">  </span><span class="pun">}</span>`
13.14.  `<span class="pun">&lt;</span><span class="pln">div </span><span class="kwd">class</span><span class="pun">=</span><span class="str">"news"</span><span class="pun">&gt;</span>`
15.  `<span class="pun">&lt;</span><span class="pln">img src</span><span class="pun">=</span><span class="str">"news-pic.jpg"</span><span class="pln"> </span><span class="pun">/&gt;</span>`
16.  `<span class="str">&lt;p&gt;</span><span class="pln">some text</span><span class="pun">&lt;/</span><span class="pln">p</span><span class="pun">&gt;</span>`
17.  `<span class="pun">&lt;/</span><span class="pln">div</span><span class="pun">&gt;</span>`</pre>

这种情况下，出现了一个问题。因为浮动元素脱离了文档流，所以包围图片和文本的 div 不占据空间。 

如何让包围元素在视觉上包围浮动元素呢？需要在这个元素中的某个地方应用 clear： 

![浮动实例](http://www.w3school.com.cn/i/ct_css_positioning_floating_clear_div.gif)

不幸的是出现了一个新的问题，由于没有现有的元素可以应用清理，所以我们只能添加一个空元素并且清理它。
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="4syd">

1.  `<span class="pun">.</span><span class="pln">news </span><span class="pun">{</span>`
2.  `<span class="pln">  background</span><span class="pun">-</span><span class="pln">color</span><span class="pun">:</span><span class="pln"> gray</span><span class="pun">;</span>`
3.  `<span class="pln">  border</span><span class="pun">:</span><span class="pln"> solid </span><span class="lit">1px</span><span class="pln"> black</span><span class="pun">;</span>`
4.  `<span class="pln">  </span><span class="pun">}</span>`
5.6.  `<span class="pun">.</span><span class="pln">news img </span><span class="pun">{</span>`
7.  `<span class="pln">  </span><span class="kwd">float</span><span class="pun">:</span><span class="pln"> left</span><span class="pun">;</span>`
8.  `<span class="pln">  </span><span class="pun">}</span>`
9.10.  `<span class="pun">.</span><span class="pln">news p </span><span class="pun">{</span>`
11.  `<span class="pln">  </span><span class="kwd">float</span><span class="pun">:</span><span class="pln"> right</span><span class="pun">;</span>`
12.  `<span class="pln">  </span><span class="pun">}</span>`
13.14.  `<span class="pun">.</span><span class="pln">clear </span><span class="pun">{</span>`
15.  `<span class="pln">  clear</span><span class="pun">:</span><span class="pln"> both</span><span class="pun">;</span>`
16.  `<span class="pln">  </span><span class="pun">}</span>`
17.18.  `<span class="pun">&lt;</span><span class="pln">div </span><span class="kwd">class</span><span class="pun">=</span><span class="str">"news"</span><span class="pun">&gt;</span>`
19.  `<span class="pun">&lt;</span><span class="pln">img src</span><span class="pun">=</span><span class="str">"news-pic.jpg"</span><span class="pln"> </span><span class="pun">/&gt;</span>`
20.  `<span class="str">&lt;p&gt;</span><span class="pln">some text</span><span class="pun">&lt;/</span><span class="pln">p</span><span class="pun">&gt;</span>`
21.  `<span class="pun">&lt;</span><span class="pln">div </span><span class="kwd">class</span><span class="pun">=</span><span class="str">"clear"</span><span class="pun">&gt;&lt;/</span><span class="pln">div</span><span class="pun">&gt;</span>`
22.  `<span class="pun">&lt;/</span><span class="pln">div</span><span class="pun">&gt;</span>`</pre>

这样可以实现我们希望的效果，但是需要添加多余的代码。常常有元素可以应用 clear，但是有时候不得不为了进行布局而添加无意义的标记。

不过我们还有另一种办法，那就是对容器 div 进行浮动：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="pbdz">

1.  `<span class="pun">.</span><span class="pln">news </span><span class="pun">{</span>`
2.  `<span class="pln">  background</span><span class="pun">-</span><span class="pln">color</span><span class="pun">:</span><span class="pln"> gray</span><span class="pun">;</span>`
3.  `<span class="pln">  border</span><span class="pun">:</span><span class="pln"> solid </span><span class="lit">1px</span><span class="pln"> black</span><span class="pun">;</span>`
4.  `<span class="pln">  </span><span class="kwd">float</span><span class="pun">:</span><span class="pln"> left</span><span class="pun">;</span>`
5.  `<span class="pln">  </span><span class="pun">}</span>`
6.7.  `<span class="pun">.</span><span class="pln">news img </span><span class="pun">{</span>`
8.  `<span class="pln">  </span><span class="kwd">float</span><span class="pun">:</span><span class="pln"> left</span><span class="pun">;</span>`
9.  `<span class="pln">  </span><span class="pun">}</span>`
10.11.  `<span class="pun">.</span><span class="pln">news p </span><span class="pun">{</span>`
12.  `<span class="pln">  </span><span class="kwd">float</span><span class="pun">:</span><span class="pln"> right</span><span class="pun">;</span>`
13.  `<span class="pln">  </span><span class="pun">}</span>`
14.15.  `<span class="pun">&lt;</span><span class="pln">div </span><span class="kwd">class</span><span class="pun">=</span><span class="str">"news"</span><span class="pun">&gt;</span>`
16.  `<span class="pun">&lt;</span><span class="pln">img src</span><span class="pun">=</span><span class="str">"news-pic.jpg"</span><span class="pln"> </span><span class="pun">/&gt;</span>`
17.  `<span class="str">&lt;p&gt;</span><span class="pln">some text</span><span class="pun">&lt;/</span><span class="pln">p</span><span class="pun">&gt;</span>`
18.  `<span class="pun">&lt;/</span><span class="pln">div</span><span class="pun">&gt;</span>`</pre>

这样会得到我们希望的效果。不幸的是，下一个元素会受到这个浮动元素的影响。为了解决这个问题，有些人选择对布局中的所有东西进行浮动，然后使用适当的有意义的元素（常常是站点的页脚）对这些浮动进行清理。这有助于减少或消除不必要的标记。

* * *
<div class="md-section-divider"></div>

# CSS选择器
<div class="md-section-divider"></div>

## CSS元素选择器

最常见的 CSS 选择器是元素选择器,又称类型选择器。
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="idfj">

1.  `<span class="pln">html </span><span class="pun">{</span><span class="pln">color</span><span class="pun">:</span><span class="pln">black</span><span class="pun">;}</span>`
2.  `<span class="pln">h1 </span><span class="pun">{</span><span class="pln">color</span><span class="pun">:</span><span class="pln">blue</span><span class="pun">;}</span>`
3.  `<span class="pln">h2 </span><span class="pun">{</span><span class="pln">color</span><span class="pun">:</span><span class="pln">silver</span><span class="pun">;}</span>`</pre>

* * *
<div class="md-section-divider"></div>

## CSS选择器分组
<div class="md-section-divider"></div>

### 1.选择器分组
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="f1wt">

1.  `<span class="com">/* no grouping */</span>`
2.  `<span class="pln">h1 </span><span class="pun">{</span><span class="pln">color</span><span class="pun">:</span><span class="pln">blue</span><span class="pun">;}</span>`
3.  `<span class="pln">h2 </span><span class="pun">{</span><span class="pln">color</span><span class="pun">:</span><span class="pln">blue</span><span class="pun">;}</span>`
4.  `<span class="pln">h3 </span><span class="pun">{</span><span class="pln">color</span><span class="pun">:</span><span class="pln">blue</span><span class="pun">;}</span>`
5.  `<span class="pln">h4 </span><span class="pun">{</span><span class="pln">color</span><span class="pun">:</span><span class="pln">blue</span><span class="pun">;}</span>`
6.  `<span class="pln">h5 </span><span class="pun">{</span><span class="pln">color</span><span class="pun">:</span><span class="pln">blue</span><span class="pun">;}</span>`
7.  `<span class="pln">h6 </span><span class="pun">{</span><span class="pln">color</span><span class="pun">:</span><span class="pln">blue</span><span class="pun">;}</span>`
8.9.  `<span class="com">/* grouping */</span>`
10.  `<span class="pln">h1</span><span class="pun">,</span><span class="pln"> h2</span><span class="pun">,</span><span class="pln"> h3</span><span class="pun">,</span><span class="pln"> h4</span><span class="pun">,</span><span class="pln"> h5</span><span class="pun">,</span><span class="pln"> h6 </span><span class="pun">{</span><span class="pln">color</span><span class="pun">:</span><span class="pln">blue</span><span class="pun">;}</span>`</pre><div class="md-section-divider"></div>

### 2.通配符选择器

该选择器可以与任何元素匹配，就像是一个通配符。 

下面的规则可以使文档中的每个元素都为红色：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="lac3">

1.  `<span class="pun">*</span><span class="pln"> </span><span class="pun">{</span><span class="pln">color</span><span class="pun">:</span><span class="pln">red</span><span class="pun">;}</span>`</pre><div class="md-section-divider"></div>

### 3.声明分组

我们既可以对选择器进行分组，也可以对声明分组。
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="x1ke">

1.  `<span class="com">/* no grouping */</span>`
2.  `<span class="pln">h1 </span><span class="pun">{</span><span class="pln">font</span><span class="pun">:</span><span class="pln"> </span><span class="lit">28px</span><span class="pln"> </span><span class="typ">Verdana</span><span class="pun">;}</span>`
3.  `<span class="pln">h1 </span><span class="pun">{</span><span class="pln">color</span><span class="pun">:</span><span class="pln"> blue</span><span class="pun">;}</span>`
4.  `<span class="pln">h1 </span><span class="pun">{</span><span class="pln">background</span><span class="pun">:</span><span class="pln"> red</span><span class="pun">;}</span>`
5.6.  `<span class="com">/* grouping */</span>`
7.  `<span class="pln">h1 </span><span class="pun">{</span>`
8.  `<span class="pln">  font</span><span class="pun">:</span><span class="pln"> </span><span class="lit">28px</span><span class="pln"> </span><span class="typ">Verdana</span><span class="pun">;</span>`
9.  `<span class="pln">  color</span><span class="pun">:</span><span class="pln"> blue</span><span class="pun">;</span>`
10.  `<span class="pln">  background</span><span class="pun">:</span><span class="pln"> red</span><span class="pun">;</span>`
11.  `<span class="pln">  </span><span class="pun">}</span>`</pre><div class="md-section-divider"></div>

### 4.结合选择器和声明的分组
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="begc">

1.  `<span class="pln">h1</span><span class="pun">,</span><span class="pln"> h2</span><span class="pun">,</span><span class="pln"> h3</span><span class="pun">,</span><span class="pln"> h4</span><span class="pun">,</span><span class="pln"> h5</span><span class="pun">,</span><span class="pln"> h6 </span><span class="pun">{</span>`
2.  `<span class="pln">  color</span><span class="pun">:</span><span class="pln">gray</span><span class="pun">;</span>`
3.  `<span class="pln">  background</span><span class="pun">:</span><span class="pln"> white</span><span class="pun">;</span>`
4.  `<span class="pln">  padding</span><span class="pun">:</span><span class="pln"> </span><span class="lit">10px</span><span class="pun">;</span>`
5.  `<span class="pln">  border</span><span class="pun">:</span><span class="pln"> </span><span class="lit">1px</span><span class="pln"> solid black</span><span class="pun">;</span>`
6.  `<span class="pln">  font</span><span class="pun">-</span><span class="pln">family</span><span class="pun">:</span><span class="pln"> </span><span class="typ">Verdana</span><span class="pun">;</span>`
7.  `<span class="pln">  </span><span class="pun">}</span>`</pre>

* * *
<div class="md-section-divider"></div>

## CSS类选择器详解
<div class="md-section-divider"></div>

### 1.CSS类选择器

html:
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="uvo0">

1.  `<span class="tag">&lt;h1</span><span class="pln"> </span><span class="atn">class</span><span class="pun">=</span><span class="atv">"important"</span><span class="tag">&gt;</span>`
2.  `<span class="pln">This heading is very important.</span>`
3.  `<span class="tag">&lt;/h1&gt;</span>`
4.5.  `<span class="tag">&lt;p</span><span class="pln"> </span><span class="atn">class</span><span class="pun">=</span><span class="atv">"important"</span><span class="tag">&gt;</span>`
6.  `<span class="pln">This paragraph is very important.</span>`
7.  `<span class="tag">&lt;/p&gt;</span>`</pre>

css:
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="o4eo">

1.  `<span class="pun">.</span><span class="pln">important </span><span class="pun">{</span><span class="pln">color</span><span class="pun">:</span><span class="pln">red</span><span class="pun">;}</span>`</pre><div class="md-section-divider"></div>

### 2.结合元素选择器

如果我们只希望段落显示为红色文本：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="mak8">

1.  `<span class="pln">p</span><span class="pun">.</span><span class="pln">important </span><span class="pun">{</span><span class="pln">color</span><span class="pun">:</span><span class="pln">red</span><span class="pun">;}</span>`</pre>

选择器现在会匹配 class 属性包含 important 的所有 p 元素，但是其他任何类型的元素都不匹配，不论是否有此 class 属性。选择器 p.important 解释为：“其 class 属性值为 important 的所有段落”。
<div class="md-section-divider"></div>

### 3.多类选择器

在 HTML 中，一个 class 值中可能包含一个词列表，各个词之间用空格分隔。例如，如果希望将一个特定的元素同时标记为重要（important）和警告（warning），就可以写作：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="ntko">

1.  `<span class="tag">&lt;p</span><span class="pln"> </span><span class="atn">class</span><span class="pun">=</span><span class="atv">"important warning"</span><span class="tag">&gt;</span>`
2.  `<span class="pln">This paragraph is a very important warning.</span>`
3.  `<span class="tag">&lt;/p&gt;</span>`</pre>

这两个词的顺序无关紧要，写成 warning important 也可以。

我们假设 class 为 important 的所有元素都是粗体，而 class 为 warning 的所有元素为斜体，class 中同时包含 important 和 warning 的所有元素还有一个银色的背景 。就可以写作：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="tcnj">

1.  `<span class="pun">.</span><span class="pln">important </span><span class="pun">{</span><span class="pln">font</span><span class="pun">-</span><span class="pln">weight</span><span class="pun">:</span><span class="pln">bold</span><span class="pun">;}</span>`
2.  `<span class="pun">.</span><span class="pln">warning </span><span class="pun">{</span><span class="pln">font</span><span class="pun">-</span><span class="pln">style</span><span class="pun">:</span><span class="pln">italic</span><span class="pun">;}</span>`
3.  `<span class="pun">.</span><span class="pln">important</span><span class="pun">.</span><span class="pln">warning </span><span class="pun">{</span><span class="pln">background</span><span class="pun">:</span><span class="pln">silver</span><span class="pun">;}</span>`</pre>

通过把两个类选择器链接在一起，仅可以选择**同时包含这些类名**的元素（类名的顺序不限）。

如果一个多类选择器包含类名列表中没有的一个类名，匹配就会失败。请看下面的规则：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="nwkv">

1.  `<span class="pun">.</span><span class="pln">important</span><span class="pun">.</span><span class="pln">urgent </span><span class="pun">{</span><span class="pln">background</span><span class="pun">:</span><span class="pln">silver</span><span class="pun">;}</span>`</pre>

这个选择器将只匹配 class 属性中包含词 important 和 urgent 的 p 元素。因此，如果一个 p 元素的 class 属性中只有词 important 和 warning，将不能匹配。不过，它能匹配以下元素：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="8qfg">

1.  `<span class="tag">&lt;p</span><span class="pln"> </span><span class="atn">class</span><span class="pun">=</span><span class="atv">"important urgent warning"</span><span class="tag">&gt;</span>`
2.  `<span class="pln">This paragraph is a very important and urgent warning.</span>`
3.  `<span class="tag">&lt;/p&gt;</span>`</pre>

* * *
<div class="md-section-divider"></div>

## CSS ID选择器详解

ID 选择器前面有一个 # 号 - 也称为棋盘号或井号。 

html:
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="dnqo">

1.  `<span class="tag">&lt;p</span><span class="pln"> </span><span class="atn">id</span><span class="pun">=</span><span class="atv">"intro"</span><span class="tag">&gt;</span><span class="pln">This is a paragraph of introduction.</span><span class="tag">&lt;/p&gt;</span>`</pre>

css:
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="1c2u">

1.  `<span class="com">#intro {font-weight:bold;}</span>`</pre>

**注意：类选择器和 ID 选择器可能是区分大小写的，这取决于文档的语言。**

因此，对于以下的 CSS 和 HTML，由于字母 i 的大小写不同，所以选择器不会匹配下面的元素，元素不会变成粗体：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="lbw4">

1.  `<span class="com">#intro {font-weight:bold;}</span>`
2.3.  `<span class="pun">&lt;</span><span class="pln">p id</span><span class="pun">=</span><span class="str">"Intro"</span><span class="pun">&gt;</span><span class="typ">This</span><span class="pln"> </span><span class="kwd">is</span><span class="pln"> a paragraph of introduction</span><span class="pun">.&lt;/</span><span class="pln">p</span><span class="pun">&gt;</span>`</pre>

* * *
<div class="md-section-divider"></div>

## CSS 属性选择器详解

属性选择器可以根据元素的属性及属性值来选择元素。
<div class="md-section-divider"></div>

### 1.简单属性选择器

如果我们希望把包含标题（title）的所有元素变为红色，可以写作：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="ec9j">

1.  `<span class="pun">[</span><span class="pln">title</span><span class="pun">]</span><span class="pln"> </span><span class="pun">{</span><span class="pln">color</span><span class="pun">:</span><span class="pln">red</span><span class="pun">;}</span>`</pre>

还可以根据多个属性进行选择，只需将属性选择器链接在一起即可。 

例如，为了将同时有 href 和 title 属性的 HTML 超链接的文本设置为红色，可以这样写：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="xudq">

1.  `<span class="pln">a</span><span class="pun">[</span><span class="pln">href</span><span class="pun">][</span><span class="pln">title</span><span class="pun">]</span><span class="pln"> </span><span class="pun">{</span><span class="pln">color</span><span class="pun">:</span><span class="pln">red</span><span class="pun">;}</span>`</pre><div class="md-section-divider"></div>

### 2.根据具体属性值选择

除了选择拥有某些属性的元素，还可以进一步缩小选择范围，只选择有特定属性值的元素。

假设希望将指向 Web 服务器上某个指定文档的超链接变成红色，可以这样写：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="jweq">

1.  `<span class="pln">a</span><span class="pun">[</span><span class="pln">href</span><span class="pun">=</span><span class="str">"http://www.w3school.com.cn/"</span><span class="pun">][</span><span class="pln">title</span><span class="pun">=</span><span class="str">"W3School"</span><span class="pun">]</span><span class="pln"> </span><span class="pun">{</span><span class="pln">color</span><span class="pun">:</span><span class="pln"> red</span><span class="pun">;}</span>`</pre>

这会把以下标记中的第一个超链接的文本变为红色，但是第二个或第三个链接不受影响：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="ari7">

1.  `<span class="tag">&lt;a</span><span class="pln"> </span><span class="atn">href</span><span class="pun">=</span><span class="atv">"http://www.w3school.com.cn/"</span><span class="pln"> </span><span class="atn">title</span><span class="pun">=</span><span class="atv">"W3School"</span><span class="tag">&gt;</span><span class="pln">W3School</span><span class="tag">&lt;/a&gt;</span>`
2.  `<span class="tag">&lt;a</span><span class="pln"> </span><span class="atn">href</span><span class="pun">=</span><span class="atv">"http://www.w3school.com.cn/css/"</span><span class="pln"> </span><span class="atn">title</span><span class="pun">=</span><span class="atv">"CSS"</span><span class="tag">&gt;</span><span class="pln">CSS</span><span class="tag">&lt;/a&gt;</span>`
3.  `<span class="tag">&lt;a</span><span class="pln"> </span><span class="atn">href</span><span class="pun">=</span><span class="atv">"http://www.w3school.com.cn/html/"</span><span class="pln"> </span><span class="atn">title</span><span class="pun">=</span><span class="atv">"HTML"</span><span class="tag">&gt;</span><span class="pln">HTML</span><span class="tag">&lt;/a&gt;</span>`</pre>

**注意：这种格式要求属性与属性值必须完全匹配。**
<div class="md-section-divider"></div>

### 3.根据部分属性值选择

如果需要根据属性值中的词列表的某个词进行选择，则需要使用波浪号（~）。 

假设我们想选择 class 属性中包含 important 的元素，可以用下面这个选择器做到这一点：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="h7of">

1.  `<span class="pln">p</span><span class="pun">[</span><span class="kwd">class</span><span class="pun">~=</span><span class="str">"important"</span><span class="pun">]</span><span class="pln"> </span><span class="pun">{</span><span class="pln">color</span><span class="pun">:</span><span class="pln"> red</span><span class="pun">;}</span>`</pre><div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="gb8o">

1.  `<span class="tag">&lt;h1&gt;</span><span class="pln">可以应用样式：</span><span class="tag">&lt;/h1&gt;</span>`
2.  `<span class="tag">&lt;p</span><span class="pln"> </span><span class="atn">class</span><span class="pun">=</span><span class="atv">"important warning"</span><span class="tag">&gt;</span><span class="pln">This is a paragraph.</span><span class="tag">&lt;/a&gt;</span>`
3.  `<span class="tag">&lt;p</span><span class="pln"> </span><span class="atn">class</span><span class="pun">=</span><span class="atv">"important"</span><span class="tag">&gt;</span><span class="pln">This is a paragraph.</span><span class="tag">&lt;/a&gt;</span>`
4.5.  `<span class="tag">&lt;h1&gt;</span><span class="pln">无法应用样式：</span><span class="tag">&lt;/h1&gt;</span>`
6.  `<span class="tag">&lt;p</span><span class="pln"> </span><span class="atn">class</span><span class="pun">=</span><span class="atv">"warning"</span><span class="tag">&gt;</span><span class="pln">This is a paragraph.</span><span class="tag">&lt;/a&gt;</span>`</pre>

如果忽略了波浪号，则说明需要完成完全值匹配。
<div class="md-section-divider"></div>

### 4.子串匹配属性选择器

子串匹配属性选择器是一个更高级的选择器模块。 

简单总结：
<table data-anchor-id="te08" class="table table-striped-white table-bordered">
<thead>
<tr>
 <th style="text-align:left;">类型</th>
 <th style="text-align:left;">描述</th>
</tr>
</thead>
<tbody><tr>
 <td style="text-align:left;">[abc^="def"]</td>
 <td style="text-align:left;">选择 abc 属性值以 "def" 开头的所有元素</td>
</tr>
<tr>
 <td style="text-align:left;">[abc$="def"]</td>
 <td style="text-align:left;">选择 abc 属性值以 "def" 结尾的所有元素</td>
</tr>
<tr>
 <td style="text-align:left;">[abc*="def"]</td>
 <td style="text-align:left;">选择 abc 属性值中包含子串 "def" 的所有元素</td>
</tr>
</tbody></table>

css:
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="rm53">

1.  `<span class="pln">a</span><span class="pun">[</span><span class="pln">href</span><span class="pun">*=</span><span class="str">"w3school.com.cn/"</span><span class="pun">]</span>`
2.  `<span class="pun">{</span>`
3.  `<span class="pln">color</span><span class="pun">:</span><span class="pln"> red</span><span class="pun">;</span>`
4.  `<span class="pun">}</span>`</pre>

html:
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="0wks">

1.  `<span class="tag">&lt;h1&gt;</span><span class="pln">可以应用样式：</span><span class="tag">&lt;/h1&gt;</span>`
2.  `<span class="tag">&lt;a</span><span class="pln"> </span><span class="atn">href</span><span class="pun">=</span><span class="atv">"http://www.w3school.com.cn/"</span><span class="tag">&gt;</span><span class="pln">W3School</span><span class="tag">&lt;/a&gt;</span>`
3.  `<span class="tag">&lt;a</span><span class="pln"> </span><span class="atn">href</span><span class="pun">=</span><span class="atv">"http://www.w3school.com.cn/css/"</span><span class="tag">&gt;</span><span class="pln">CSS</span><span class="tag">&lt;/a&gt;</span>`
4.  `<span class="tag">&lt;a</span><span class="pln"> </span><span class="atn">href</span><span class="pun">=</span><span class="atv">"http://www.w3school.com.cn/html/"</span><span class="tag">&gt;</span><span class="pln">HTML</span><span class="tag">&lt;/a&gt;</span>`
5.6.  `<span class="tag">&lt;h1&gt;</span><span class="pln">无法应用样式：</span><span class="tag">&lt;/h1&gt;</span>`
7.  `<span class="tag">&lt;a</span><span class="pln"> </span><span class="atn">href</span><span class="pun">=</span><span class="atv">"http://www.w3c.org/"</span><span class="tag">&gt;</span><span class="pln">W3C</span><span class="tag">&lt;/a&gt;</span>`
8.  `<span class="tag">&lt;a</span><span class="pln"> </span><span class="atn">href</span><span class="pun">=</span><span class="atv">"http://www.microsoft.com"</span><span class="tag">&gt;</span><span class="pln">Microsoft</span><span class="tag">&lt;/a&gt;</span>`
9.  `<span class="tag">&lt;a</span><span class="pln"> </span><span class="atn">href</span><span class="pun">=</span><span class="atv">"http://www.apple.com.cn"</span><span class="tag">&gt;</span><span class="pln">Apple</span><span class="tag">&lt;/a&gt;</span>`</pre><div class="md-section-divider"></div>

## 5.特定属性选择类型
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="bzzt">

1.  `<span class="pun">[</span><span class="pln">lang</span><span class="pun">|=</span><span class="str">"en"</span><span class="pun">]</span><span class="pln"> </span><span class="pun">{</span><span class="pln">color</span><span class="pun">:</span><span class="pln"> red</span><span class="pun">;}</span>`</pre>

上面这个规则会选择 lang 属性等于 en 或以 en- 开头的所有元素。因此，以下示例标记中的前三个元素将被选中，而不会选择后两个元素：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="66nc">

1.  `<span class="tag">&lt;p</span><span class="pln"> </span><span class="atn">lang</span><span class="pun">=</span><span class="atv">"en"</span><span class="tag">&gt;</span><span class="pln">Hello!</span><span class="tag">&lt;/p&gt;</span>`
2.  `<span class="tag">&lt;p</span><span class="pln"> </span><span class="atn">lang</span><span class="pun">=</span><span class="atv">"en-us"</span><span class="tag">&gt;</span><span class="pln">Greetings!</span><span class="tag">&lt;/p&gt;</span>`
3.  `<span class="tag">&lt;p</span><span class="pln"> </span><span class="atn">lang</span><span class="pun">=</span><span class="atv">"en-au"</span><span class="tag">&gt;</span><span class="pln">G'day!</span><span class="tag">&lt;/p&gt;</span>`
4.  `<span class="tag">&lt;p</span><span class="pln"> </span><span class="atn">lang</span><span class="pun">=</span><span class="atv">"fr"</span><span class="tag">&gt;</span><span class="pln">Bonjour!</span><span class="tag">&lt;/p&gt;</span>`
5.  `<span class="tag">&lt;p</span><span class="pln"> </span><span class="atn">lang</span><span class="pun">=</span><span class="atv">"cy-en"</span><span class="tag">&gt;</span><span class="pln">Jrooana!</span><span class="tag">&lt;/p&gt;</span>`</pre>

一般来说，[att|="val"] 可以用于任何属性及其值。

假设一个 HTML 文档中有一系列图片，其中每个图片的文件名都形如 figure-1.jpg 和 figure-2.jpg。就可以使用以下选择器匹配所有这些图像：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="30bu">

1.  `<span class="pln">img</span><span class="pun">[</span><span class="pln">src</span><span class="pun">|=</span><span class="str">"figure"</span><span class="pun">]</span><span class="pln"> </span><span class="pun">{</span><span class="pln">border</span><span class="pun">:</span><span class="pln"> </span><span class="lit">1px</span><span class="pln"> solid gray</span><span class="pun">;}</span>`</pre>

* * *
<div class="md-section-divider"></div>

## CSS后代选择器

后代选择器（descendant selector）又称为包含选择器。

如果我们希望只对 h1 元素中的 em 元素应用样式，可以这样写：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="7yn2">

1.  `<span class="pln">h1 em </span><span class="pun">{</span><span class="pln">color</span><span class="pun">:</span><span class="pln">red</span><span class="pun">;}</span>`</pre>

上面这个规则会把作为 h1 元素后代的 em 元素的文本变为 红色。其他 em 文本（如段落或块引用中的 em）则不会被这个规则选中：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="21nl">

1.  `<span class="tag">&lt;h1&gt;</span><span class="pln">This is a </span><span class="tag">&lt;em&gt;</span><span class="pln">important</span><span class="tag">&lt;/em&gt;</span><span class="pln"> heading</span><span class="tag">&lt;/h1&gt;</span>`
2.  `<span class="tag">&lt;p&gt;</span><span class="pln">This is a </span><span class="tag">&lt;em&gt;</span><span class="pln">important</span><span class="tag">&lt;/em&gt;</span><span class="pln"> paragraph.</span><span class="tag">&lt;/p&gt;</span>`</pre>

注意：此处要注意顺序。

**有关后代选择器有一个易被忽视的方面，即两个元素之间的层次间隔可以是无限的，不管子元素嵌套层次多深，CSS规则依然会被应用。**

* * *
<div class="md-section-divider"></div>

## CSS子元素选择器

如果我们不希望选择任意的后代元素，而是希望缩小范围，只选择某个元素的子元素，请使用子元素选择器（Child selector）。

例如，如果我们希望选择只作为 h1 元素子元素的 strong 元素，可以这样写：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="dmkl">

1.  `<span class="pln">h1 </span><span class="pun">&gt;</span><span class="pln"> strong </span><span class="pun">{</span><span class="pln">color</span><span class="pun">:</span><span class="pln">red</span><span class="pun">;}</span>`</pre>

这个规则会把第一个 h1 下面的两个 strong 元素变为红色，但是第二个 h1 中的 strong 不受影响：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="09qg">

1.  `<span class="tag">&lt;h1&gt;</span><span class="pln">This is </span><span class="tag">&lt;strong&gt;</span><span class="pln">very</span><span class="tag">&lt;/strong&gt;</span><span class="pln"> </span><span class="tag">&lt;strong&gt;</span><span class="pln">very</span><span class="tag">&lt;/strong&gt;</span><span class="pln"> important.</span><span class="tag">&lt;/h1&gt;</span>`
2.  `<span class="tag">&lt;h1&gt;</span><span class="pln">This is </span><span class="tag">&lt;em&gt;</span><span class="pln">really </span><span class="tag">&lt;strong&gt;</span><span class="pln">very</span><span class="tag">&lt;/strong&gt;&lt;/em&gt;</span><span class="pln"> important.</span><span class="tag">&lt;/h1&gt;</span>`</pre><div class="md-section-divider"></div>

## CSS相邻兄弟选择器

相邻兄弟选择器（Adjacent sibling selector）可选择紧接在另一元素后的元素，且二者有相同父元素。

如果需要选择紧接在另一个元素后的元素，而且二者有相同的父元素，可以使用相邻兄弟选择器（Adjacent sibling selector）。 

例如，如果要增加紧接在 h1 元素后出现的段落的上边距，可以这样写：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="r2mo">

1.  `<span class="pln">h1 </span><span class="pun">+</span><span class="pln"> p </span><span class="pun">{</span><span class="pln">margin</span><span class="pun">-</span><span class="pln">top</span><span class="pun">:</span><span class="lit">50px</span><span class="pun">;}</span>`</pre>

这个选择器读作：“选择紧接在 h1 元素后出现的段落，h1 和 p 元素拥有共同的父元素”。

上面规则只会应用到下面html中的紧挨着h1的p标签：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="ompv">

1.  `<span class="tag">&lt;h1&gt;</span><span class="pln">This is a heading.</span><span class="tag">&lt;/h1&gt;</span>`
2.  `<span class="tag">&lt;p&gt;</span><span class="pln">这个段落被应用了样式</span><span class="tag">&lt;/p&gt;</span>`
3.  `<span class="tag">&lt;p&gt;</span><span class="pln">这个段落没有被应用样式</span><span class="tag">&lt;/p&gt;</span>`
4.  `<span class="tag">&lt;p&gt;</span><span class="pln">这个段落也没有被应用样式</span><span class="tag">&lt;/p&gt;</span>`</pre>

* * *
<div class="md-section-divider"></div>

## CSS伪类

CSS 伪类用于向某些选择器添加特殊的效果。
<div class="md-section-divider"></div>

### 1.锚伪类
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="ru82">

1.  `<span class="pln">a</span><span class="pun">:</span><span class="pln">link </span><span class="pun">{</span><span class="pln">color</span><span class="pun">:</span><span class="pln"> </span><span class="com">#FF0000}     /* 未访问的链接 */</span>`
2.  `<span class="pln">a</span><span class="pun">:</span><span class="pln">visited </span><span class="pun">{</span><span class="pln">color</span><span class="pun">:</span><span class="pln"> </span><span class="com">#00FF00}  /* 已访问的链接 */</span>`
3.  `<span class="pln">a</span><span class="pun">:</span><span class="pln">hover </span><span class="pun">{</span><span class="pln">color</span><span class="pun">:</span><span class="pln"> </span><span class="com">#FF00FF}    /* 鼠标移动到链接上 */</span>`
4.  `<span class="pln">a</span><span class="pun">:</span><span class="pln">active </span><span class="pun">{</span><span class="pln">color</span><span class="pun">:</span><span class="pln"> </span><span class="com">#0000FF}   /* 选定的链接 */</span>`</pre>

注意：
> *   在 CSS 定义中，a:hover 必须被置于 a:link 和 a:visited 之后，才是有效的。
> *   在 CSS 定义中，a:active 必须被置于 a:hover 之后，才是有效的。
> *   伪类名称对大小写不敏感。<div class="md-section-divider"></div>

### 2.CSS2 - :first-child 伪类

可以使用 :first-child伪类来选择元素的第一个子元素。
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="qxns">

1.  `<span class="pln">p</span><span class="pun">:</span><span class="pln">first</span><span class="pun">-</span><span class="pln">child </span><span class="pun">{</span><span class="pln">font</span><span class="pun">-</span><span class="pln">weight</span><span class="pun">:</span><span class="pln"> bold</span><span class="pun">;}</span>`
2.  `<span class="pln">li</span><span class="pun">:</span><span class="pln">first</span><span class="pun">-</span><span class="pln">child </span><span class="pun">{</span><span class="pln">text</span><span class="pun">-</span><span class="pln">transform</span><span class="pun">:</span><span class="pln">uppercase</span><span class="pun">;}</span>`</pre>

第一个规则将作为某元素第一个子元素的所有 p 元素设置为粗体。第二个规则将作为某个元素（在 HTML 中，这肯定是 ol 或 ul 元素）第一个子元素的所有 li 元素变成大写。 

注意：最常见的错误是认为 p:first-child 之类的选择器会选择 p 元素的第一个子元素。
<div class="md-section-divider"></div>

#### ①匹配第一个p元素

在下面的例子中，选择器匹配作为任何元素的第一个子元素的`&lt;p&gt;`元素：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="zrdr">

1.  `<span class="tag">&lt;html&gt;</span>`
2.  `<span class="tag">&lt;head&gt;</span>`
3.  `<span class="tag">&lt;style</span><span class="pln"> </span><span class="atn">type</span><span class="pun">=</span><span class="atv">"text/css"</span><span class="tag">&gt;</span>`
4.  `<span class="pln">p</span><span class="pun">:</span><span class="pln">first</span><span class="pun">-</span><span class="pln">child </span><span class="pun">{</span>`
5.  `<span class="pln">  color</span><span class="pun">:</span><span class="pln"> red</span><span class="pun">;</span>`
6.  `<span class="pln">  </span><span class="pun">}</span><span class="pln"> </span>`
7.  `<span class="tag">&lt;/style&gt;</span>`
8.  `<span class="tag">&lt;/head&gt;</span>`
9.10.  `<span class="tag">&lt;body&gt;</span>`
11.  `<span class="tag">&lt;p&gt;</span><span class="pln">some text</span><span class="tag">&lt;/p&gt;</span>`
12.  `<span class="tag">&lt;p&gt;</span><span class="pln">some text</span><span class="tag">&lt;/p&gt;</span>`
13.  `<span class="tag">&lt;/body&gt;</span>`
14.  `<span class="tag">&lt;/html&gt;</span>`</pre><div class="md-section-divider"></div>

#### ②匹配所有p元素中的第一个i元素

在下面的例子中，选择器匹配所有`&lt;p&gt;`元素中的第一个`&lt;i&gt;`元素：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="9pne">

1.  `<span class="tag">&lt;html&gt;</span>`
2.  `<span class="tag">&lt;head&gt;</span>`
3.  `<span class="tag">&lt;style</span><span class="pln"> </span><span class="atn">type</span><span class="pun">=</span><span class="atv">"text/css"</span><span class="tag">&gt;</span>`
4.  `<span class="pln">p </span><span class="pun">&gt;</span><span class="pln"> i</span><span class="pun">:</span><span class="pln">first</span><span class="pun">-</span><span class="pln">child </span><span class="pun">{</span>`
5.  `<span class="pln">  font</span><span class="pun">-</span><span class="pln">weight</span><span class="pun">:</span><span class="pln">bold</span><span class="pun">;</span>`
6.  `<span class="pln">  </span><span class="pun">}</span><span class="pln"> </span>`
7.  `<span class="tag">&lt;/style&gt;</span>`
8.  `<span class="tag">&lt;/head&gt;</span>`
9.10.  `<span class="tag">&lt;body&gt;</span>`
11.  `<span class="tag">&lt;p&gt;</span><span class="pln">some </span><span class="tag">&lt;i&gt;</span><span class="pln">text</span><span class="tag">&lt;/i&gt;</span><span class="pln">. some </span><span class="tag">&lt;i&gt;</span><span class="pln">text</span><span class="tag">&lt;/i&gt;</span><span class="pln">.</span><span class="tag">&lt;/p&gt;</span>`
12.  `<span class="tag">&lt;p&gt;</span><span class="pln">some </span><span class="tag">&lt;i&gt;</span><span class="pln">text</span><span class="tag">&lt;/i&gt;</span><span class="pln">. some </span><span class="tag">&lt;i&gt;</span><span class="pln">text</span><span class="tag">&lt;/i&gt;</span><span class="pln">.</span><span class="tag">&lt;/p&gt;</span>`
13.  `<span class="tag">&lt;/body&gt;</span>`
14.  `<span class="tag">&lt;/html&gt;</span>`</pre><div class="md-section-divider"></div>

#### ③匹配所有作为第一个子元素的p元素中的所有i元素

在下面的例子中，选择器匹配所有作为元素的第一个子元素的`&lt;p&gt;`元素中的所有`&lt;i&gt;`元素：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="dm4r">

1.  `<span class="tag">&lt;html&gt;</span>`
2.  `<span class="tag">&lt;head&gt;</span>`
3.  `<span class="tag">&lt;style</span><span class="pln"> </span><span class="atn">type</span><span class="pun">=</span><span class="atv">"text/css"</span><span class="tag">&gt;</span>`
4.  `<span class="pln">p</span><span class="pun">:</span><span class="pln">first</span><span class="pun">-</span><span class="pln">child i </span><span class="pun">{</span>`
5.  `<span class="pln">  color</span><span class="pun">:</span><span class="pln">blue</span><span class="pun">;</span>`
6.  `<span class="pln">  </span><span class="pun">}</span><span class="pln"> </span>`
7.  `<span class="tag">&lt;/style&gt;</span>`
8.  `<span class="tag">&lt;/head&gt;</span>`
9.10.  `<span class="tag">&lt;body&gt;</span>`
11.  `<span class="tag">&lt;p&gt;</span><span class="pln">some </span><span class="tag">&lt;i&gt;</span><span class="pln">text</span><span class="tag">&lt;/i&gt;</span><span class="pln">. some </span><span class="tag">&lt;i&gt;</span><span class="pln">text</span><span class="tag">&lt;/i&gt;</span><span class="pln">.</span><span class="tag">&lt;/p&gt;</span>`
12.  `<span class="tag">&lt;p&gt;</span><span class="pln">some </span><span class="tag">&lt;i&gt;</span><span class="pln">text</span><span class="tag">&lt;/i&gt;</span><span class="pln">. some </span><span class="tag">&lt;i&gt;</span><span class="pln">text</span><span class="tag">&lt;/i&gt;</span><span class="pln">.</span><span class="tag">&lt;/p&gt;</span>`
13.  `<span class="tag">&lt;/body&gt;</span>`
14.  `<span class="tag">&lt;/html&gt;</span>`</pre><div class="md-section-divider"></div>

### 3.CSS2 - :lang 伪类

:lang 伪类使你有能力为不同的语言定义特殊的规则。在下面的例子中，:lang 类为属性值为 no 的 q 元素定义引号的类型：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="9jf9">

1.  `<span class="tag">&lt;html&gt;</span>`
2.  `<span class="tag">&lt;head&gt;</span>`
3.4.  `<span class="tag">&lt;style</span><span class="pln"> </span><span class="atn">type</span><span class="pun">=</span><span class="atv">"text/css"</span><span class="tag">&gt;</span>`
5.  `<span class="pln">q</span><span class="pun">:</span><span class="pln">lang</span><span class="pun">(</span><span class="kwd">no</span><span class="pun">)</span>`
6.  `<span class="pln">   </span><span class="pun">{</span>`
7.  `<span class="pln">   quotes</span><span class="pun">:</span><span class="pln"> </span><span class="str">"~"</span><span class="pln"> </span><span class="str">"~"</span>`
8.  `<span class="pln">   </span><span class="pun">}</span>`
9.  `<span class="tag">&lt;/style&gt;</span>`
10.11.  `<span class="tag">&lt;/head&gt;</span>`
12.13.  `<span class="tag">&lt;body&gt;</span>`
14.  `<span class="tag">&lt;p&gt;</span><span class="pln">文字</span><span class="tag">&lt;q</span><span class="pln"> </span><span class="atn">lang</span><span class="pun">=</span><span class="atv">"no"</span><span class="tag">&gt;</span><span class="pln">段落中的引用的文字</span><span class="tag">&lt;/q&gt;</span><span class="pln">文字</span><span class="tag">&lt;/p&gt;</span>`
15.  `<span class="tag">&lt;/body&gt;</span>`
16.  `<span class="tag">&lt;/html&gt;</span>`</pre>

* * *
<div class="md-section-divider"></div>

## CSS伪元素
<div class="md-section-divider"></div>

### 1.:first-line 伪元素

"first-line" 伪元素用于向文本的首行设置特殊样式。 

在下面的例子中，浏览器会根据 "first-line" 伪元素中的样式对 p 元素的第一行文本设置样式：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="vben">

1.  `<span class="pln">p</span><span class="pun">:</span><span class="pln">first</span><span class="pun">-</span><span class="pln">line</span>`
2.  `<span class="pln">  </span><span class="pun">{</span>`
3.  `<span class="pln">  color</span><span class="pun">:#</span><span class="pln">ff0000</span><span class="pun">;</span>`
4.  `<span class="pln">  font</span><span class="pun">-</span><span class="pln">variant</span><span class="pun">:</span><span class="pln">small</span><span class="pun">-</span><span class="pln">caps</span><span class="pun">;</span>`
5.  `<span class="pln">  </span><span class="pun">}</span>`</pre>

注释：
> *   "first-line" 伪元素只能用于块级元素。
> *   下面的属性可应用于 "first-line" 伪元素：
> 
>         *   font
>     *   color
>     *   background
>     *   word-spacing
>     *   letter-spacing
>     *   text-decoration
>     *   vertical-align
>     *   text-transform
>     *   line-height
>     *   clear<div class="md-section-divider"></div>

### 2.:first-letter 伪元素

"first-letter"伪元素用于向文本的首字母设置特殊样式：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="ombk">

1.  `<span class="pln">p</span><span class="pun">:</span><span class="pln">first</span><span class="pun">-</span><span class="pln">letter</span>`
2.  `<span class="pln">  </span><span class="pun">{</span>`
3.  `<span class="pln">  color</span><span class="pun">:#</span><span class="pln">ff0000</span><span class="pun">;</span>`
4.  `<span class="pln">  font</span><span class="pun">-</span><span class="pln">size</span><span class="pun">:</span><span class="pln">xx</span><span class="pun">-</span><span class="pln">large</span><span class="pun">;</span>`
5.  `<span class="pln">  </span><span class="pun">}</span>`</pre>

注释：
> *   "first-line" 伪元素只能用于块级元素。
> *   下面的属性可应用于 "first-letter" 伪元素：
> 
>         *   font
>     *   color
>     *   background
>     *   margin
>     *   padding
>     *   border
>     *   text-decoration
>     *   vertical-align (仅当 float 为 none 时)
>     *   text-transform
>     *   line-height
>     *   float
>     *   clear<div class="md-section-divider"></div>

### 3.伪元素和 CSS 类

伪元素可以与 CSS 类配合使用：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="l84b">

1.  `<span class="pln">p</span><span class="pun">.</span><span class="pln">article</span><span class="pun">:</span><span class="pln">first</span><span class="pun">-</span><span class="pln">letter</span>`
2.  `<span class="pln">  </span><span class="pun">{</span>`
3.  `<span class="pln">  color</span><span class="pun">:</span><span class="pln"> </span><span class="com">#FF0000;</span>`
4.  `<span class="pln">  </span><span class="pun">}</span>`
5.6.  `<span class="pun">&lt;</span><span class="pln">p </span><span class="kwd">class</span><span class="pun">=</span><span class="str">"article"</span><span class="pun">&gt;</span><span class="typ">This</span><span class="pln"> </span><span class="kwd">is</span><span class="pln"> a paragraph </span><span class="kwd">in</span><span class="pln"> an article</span><span class="pun">。&lt;/</span><span class="pln">p</span><span class="pun">&gt;</span>`</pre><div class="md-section-divider"></div>

### 4.CSS2 - :before 伪元素

":before" 伪元素可以在元素的内容前面插入新内容。

下面的例子在每个`&lt;h1&gt;`元素前面插入一幅图片：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="cwvz">

1.  `<span class="pln">h1</span><span class="pun">:</span><span class="pln">before</span>`
2.  `<span class="pln">  </span><span class="pun">{</span>`
3.  `<span class="pln">  content</span><span class="pun">:</span><span class="pln">url</span><span class="pun">(</span><span class="pln">logo</span><span class="pun">.</span><span class="pln">gif</span><span class="pun">);</span>`
4.  `<span class="pln">  </span><span class="pun">}</span>`</pre><div class="md-section-divider"></div>

### 5.CSS2 - :after 伪元素

":after" 伪元素可以在元素的内容之后插入新内容。

下面的例子在每个`&lt;h1&gt;`元素后面插入一幅图片：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="sb9k">

1.  `<span class="pln">h1</span><span class="pun">:</span><span class="pln">after</span>`
2.  `<span class="pln">  </span><span class="pun">{</span>`
3.  `<span class="pln">  content</span><span class="pun">:</span><span class="pln">url</span><span class="pun">(</span><span class="pln">logo</span><span class="pun">.</span><span class="pln">gif</span><span class="pun">);</span>`
4.  `<span class="pln">  </span><span class="pun">}</span>`</pre>

* * *
<div class="md-section-divider"></div>

# CSS 高级
<div class="md-section-divider"></div>

## CSS对齐
<div class="md-section-divider"></div>

### 1.使用 margin 属性来水平对齐

可通过将左和右外边距设置为 "auto"，来对齐块元素。规定的是均等地分配可用的外边距，结果就是居中的元素：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="jxyd">

1.  `<span class="pun">.</span><span class="pln">center</span>`
2.  `<span class="pun">{</span>`
3.  `<span class="pln">margin</span><span class="pun">-</span><span class="pln">left</span><span class="pun">:</span><span class="kwd">auto</span><span class="pun">;</span>`
4.  `<span class="pln">margin</span><span class="pun">-</span><span class="pln">right</span><span class="pun">:</span><span class="kwd">auto</span><span class="pun">;</span>`
5.  `<span class="pln">width</span><span class="pun">:</span><span class="lit">70</span><span class="pun">%;</span>`
6.  `<span class="pun">}</span>`</pre><div class="md-section-divider"></div>

### 2.使用 position 属性进行左和右对齐

对齐元素的方法之一是使用绝对定位：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="bbql">

1.  `<span class="pun">.</span><span class="pln">right</span>`
2.  `<span class="pun">{</span>`
3.  `<span class="pln">position</span><span class="pun">:</span><span class="pln">absolute</span><span class="pun">;</span>`
4.  `<span class="pln">right</span><span class="pun">:</span><span class="lit">0px</span><span class="pun">;</span>`
5.  `<span class="pln">width</span><span class="pun">:</span><span class="lit">300px</span><span class="pun">;</span>`
6.  `<span class="pun">}</span>`</pre><div class="md-section-divider"></div>

### 3.使用 float 属性来进行左和右对齐

对齐元素的另一种方法是使用 float 属性：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="c24c">

1.  `<span class="pun">.</span><span class="pln">right</span>`
2.  `<span class="pun">{</span>`
3.  `<span class="kwd">float</span><span class="pun">:</span><span class="pln">right</span><span class="pun">;</span>`
4.  `<span class="pln">width</span><span class="pun">:</span><span class="lit">300px</span><span class="pun">;</span>`
5.  `<span class="pun">}</span>`</pre><div class="md-section-divider"></div>

## CSS尺寸

[http://www.w3school.com.cn/css/css_dimension.asp](http://www.w3school.com.cn/css/css_dimension.asp)
<div class="md-section-divider"></div>

## CSS分类

[http://www.w3school.com.cn/css/css_classification.asp](http://www.w3school.com.cn/css/css_classification.asp)
<div class="md-section-divider"></div>

## CSS导航条
<div class="md-section-divider"></div>

### 1.垂直导航条

在例子中，将用标准的 HTML 列表来构建导航栏。 

导航栏基本上是一个链接列表，因此使用`&lt;ul&gt;`和`&lt;li&gt;`元素是非常合适的：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="b5ej">

1.  `<span class="tag">&lt;ul&gt;</span>`
2.  `<span class="tag">&lt;li&gt;&lt;a</span><span class="pln"> </span><span class="atn">href</span><span class="pun">=</span><span class="atv">"default.asp"</span><span class="tag">&gt;</span><span class="pln">Home</span><span class="tag">&lt;/a&gt;&lt;/li&gt;</span>`
3.  `<span class="tag">&lt;li&gt;&lt;a</span><span class="pln"> </span><span class="atn">href</span><span class="pun">=</span><span class="atv">"news.asp"</span><span class="tag">&gt;</span><span class="pln">News</span><span class="tag">&lt;/a&gt;&lt;/li&gt;</span>`
4.  `<span class="tag">&lt;li&gt;&lt;a</span><span class="pln"> </span><span class="atn">href</span><span class="pun">=</span><span class="atv">"contact.asp"</span><span class="tag">&gt;</span><span class="pln">Contact</span><span class="tag">&lt;/a&gt;&lt;/li&gt;</span>`
5.  `<span class="tag">&lt;li&gt;&lt;a</span><span class="pln"> </span><span class="atn">href</span><span class="pun">=</span><span class="atv">"about.asp"</span><span class="tag">&gt;</span><span class="pln">About</span><span class="tag">&lt;/a&gt;&lt;/li&gt;</span>`
6.  `<span class="tag">&lt;/ul&gt;</span>`</pre>

从列表中去掉圆点和外边距：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="q3xo">

1.  `<span class="pln">ul</span>`
2.  `<span class="pun">{</span>`
3.  `<span class="pln">list</span><span class="pun">-</span><span class="pln">style</span><span class="pun">-</span><span class="pln">type</span><span class="pun">:</span><span class="pln">none</span><span class="pun">;</span>`
4.  `<span class="pln">margin</span><span class="pun">:</span><span class="lit">0</span><span class="pun">;</span>`
5.  `<span class="pln">padding</span><span class="pun">:</span><span class="lit">0</span><span class="pun">;</span>`
6.  `<span class="pun">}</span>`</pre>

如需构建垂直导航栏，我们只需要定义`&lt;a&gt;` 元素的样式，除了上面的代码之外：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="vm3k">

1.  `<span class="pln">a</span>`
2.  `<span class="pun">{</span>`
3.  `<span class="pln">display</span><span class="pun">:</span><span class="pln">block</span><span class="pun">;</span>`
4.  `<span class="pln">width</span><span class="pun">:</span><span class="lit">60px</span><span class="pun">;</span>`
5.  `<span class="pun">}</span>`</pre>

解释：display:block - 把链接显示为块元素可使整个链接区域可点击（不仅仅是文本），同时也允许我们规定宽度。
<div class="md-section-divider"></div>

### 2.水平导航栏

有两种创建水平导航栏的方法。使用行内或浮动列表项。 

两种方法都不错，但是如果希望链接拥有相同的尺寸，就必须使用浮动方法。
<div class="md-section-divider"></div>

#### ①行内列表项

除了上面的“标准”代码，构建水平导航栏的方法之一是将`&lt;li&gt;`元素规定为行内元素：
<div class="md-section-divider"></div><pre class="prettyprint linenums prettyprinted" data-anchor-id="uc76">

1.  `<span class="pln">li </span><span class="pun">{</span>`
2.  `<span class="pln">display</span><span class="pun">:</span><span class="kwd">inline</span><span class="pun">;</span>`
3.  `<span class="pun">}</span>`</pre>

解释：display:inline; - 默认地，
<li data-anchor-id="ymln"> 元素是块元素。在这里，我们去除了每个列表项前后的换行，以便让它们在一行中显示。

<div class="md-section-divider"></div>

#### ②对列表项进行浮动

在上面的例子中，链接的宽度是不同的。 

为了让所有链接拥有相等的宽度，浮动 
</li><li data-anchor-id="jqb8"> 元素并规定  元素的宽度：

<div class="md-section-divider"></div>

<pre class="prettyprint linenums prettyprinted">

1.  `<span class="pln">li </span><span class="pun">{</span>`
2.  `<span class="kwd">float</span><span class="pun">:</span><span class="pln">left</span><span class="pun">;</span>`
3.  `<span class="pun">}</span>`
4.  `<span class="pln">a </span><span class="pun">{</span>`
5.  `<span class="pln">display</span><span class="pun">:</span><span class="pln">block</span><span class="pun">;</span>`
6.  `<span class="pln">width</span><span class="pun">:</span><span class="lit">60px</span><span class="pun">;</span>`
7.  `<span class="pun">}</span>`</pre>

解释：

> *   float:left - 使用 float 来把块元素滑向彼此。
> *   display:block - 把链接显示为块元素可使整个链接区域可点击（不仅仅是文本），同时也允许我们规定宽度。