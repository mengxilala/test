# test
just a try
前端试题
HTML&&CSS
1. 常用那几种浏览器测试？有哪些内核(Layout Engine)?
(Q1) 浏览器：IE，Chrome，FireFox，Safari，Opera。
(Q2) 内核：Trident，Gecko，Presto，Webkit。

2. 说下行内元素和块级元素的区别？行内块元素的兼容性使用？（IE8 以下）
(Q1) 行内元素：会在水平方向排列，不能包含块级元素，设置width无效，height无效(可以设置line-height)，margin上下无效，padding上下无效。
块级元素：各占据一行，垂直方向排列。从新行开始结束接着一个断行。
(Q2) 兼容性：display:inline-block;*display:inline;*zoom:1;

3. 清除浮动有哪些方式？比较好的方式是哪一种？
(Q1)
（1）父级div定义height。
（2）结尾处加空div标签clear:both。
（3）父级div定义伪类:after和zoom。
（4）父级div定义overflow:hidden。
（5）父级div定义overflow:auto。
（6）父级div也浮动，需要定义宽度。
（7）父级div定义display:table。
（8）结尾处加br标签clear:both。

(Q2) 比较好的是第3种方式，好多网站都这么用。

4. box-sizing常用的属性有哪些？分别有什么作用？
(Q1)box-sizing: content-box|border-box|inherit;
(Q2)content-box:宽度和高度分别应用到元素的内容框。在宽度和高度之外绘制元素的内边距和边框(元素默认效果)。
border-box:元素指定的任何内边距和边框都将在已设定的宽度和高度内进行绘制。通过从已设定的宽度和高度分别减去边框和内边距才能得到内容的宽度和高度。

5. Doctype作用？标准模式与兼容模式各有什么区别?
(Q1) <!DOCTYPE>告知浏览器的解析器用什么文档标准解析这个文档。DOCTYPE不存在或格式不正确会导致文档以兼容模式呈现。
(Q2) 标准模式的排版和JS运作模式都是以该浏览器支持的最高标准运行。在兼容模式中，页面以宽松的向后兼容的方式显示,模拟老式浏览器的行为以防止站点无法工作。

6. HTML5 为什么只需要写 <!DOCTYPE HTML>？
HTML5不基于 SGML，因此不需要对DTD进行引用，但是需要doctype来规范浏览器的行为（让浏览器按照它们应该的方式来运行）。
而HTML4.01基于SGML,所以需要对DTD进行引用，才能告知浏览器文档所使用的文档类型。

7. 页面导入样式时，使用link和@import有什么区别？

（1）link属于XHTML标签，除了加载CSS外，还能用于定义RSS, 定义rel连接属性等作用；而@import是CSS提供的，只能用于加载CSS;
（2）页面被加载的时，link会同时被加载，而@import引用的CSS会等到页面被加载完再加载;
（3）import是CSS2.1 提出的，只在IE5以上才能被识别，而link是XHTML标签，无兼容问题。

8. 介绍一下你对浏览器内核的理解？

主要分成两部分：渲染引擎(layout engineer或Rendering Engine)和JS引擎。

渲染引擎：负责取得网页的内容（HTML、XML、图像等等）、整理讯息（例如加入CSS等），以及计算网页的显示方式，然后会输出至显示器或打印机。浏览器的内核的不同对于网页的语法解释会有不同，所以渲染的效果也不相同。所有网页浏览器、电子邮件客户端以及其它需要编辑、显示网络内容的应用程序都需要内核。

JS引擎则：解析和执行javascript来实现网页的动态效果。

最开始渲染引擎和JS引擎并没有区分的很明确，后来JS引擎越来越独立，内核就倾向于只指渲染引擎。

9. html5有哪些新特性？如何处理HTML5新标签的浏览器兼容问题？如何区分 HTML 和 HTML5？
(Q1)
HTML5 现在已经不是 SGML 的子集，主要是关于图像，位置，存储，多任务等功能的增加。
(1)绘画 Canvas;
(2)用于媒介回放的 video 和 audio 元素;
(3)本地离线存储 localStorage 长期存储数据，浏览器关闭后数据不丢失;
(4)sessionStorage 的数据在浏览器关闭后自动删除;
(5)语意化更好的内容元素，比如 article、footer、header、nav、section;
(6)表单控件，calendar、date、time、email、url、search;
(7)新的技术webworker, websocket, Geolocation;

(Q2)
IE8/IE7/IE6支持通过document.createElement方法产生的标签，
可以利用这一特性让这些浏览器支持HTML5新标签，
浏览器支持新标签后，还需要添加标签默认的样式。
当然也可以直接使用成熟的框架、比如html5shim，
<!--[if lt IE 9]>
<![endif]-->

10. 简述一下你对HTML语义化的理解？
用正确的标签做正确的事情。
html语义化让页面的内容结构化，结构更清晰，便于对浏览器、搜索引擎解析;
即使在没有样式CSS情况下也以一种文档格式显示，并且是容易阅读的;
搜索引擎的爬虫也依赖于HTML标记来确定上下文和各个关键字的权重，利于seo;
使阅读源代码的人对网站更容易将网站分块，便于阅读维护理解。

JS

1. 介绍js的基本数据类型
Undefined、Null、Boolean、Number、String

2. js有哪些内置对象？
数据封装类对象：Object、Array、Boolean、Number 和 String
其他对象：Function、Arguments、Math、Date、RegExp、Error

3. this对象的理解
this总是指向函数的直接调用者（而非间接调用者）；
如果有new关键字，this指向new出来的那个对象；
在事件中，this指向触发这个事件的对象，特殊的是，IE中的attachEvent中的this总是指向全局对象Window。

4. eval是做什么的？
它的功能是把对应的字符串解析成JS代码并运行；
应该避免使用eval，不安全，非常耗性能（2次，一次解析成js语句，一次执行）。
由JSON字符串转换为JSON对象的时候可以用eval，var obj =eval('('+ str +')')。

5. DOM怎样添加、移除、移动、复制、创建和查找节点
// 创建新节点
createDocumentFragment() //创建一个DOM片段
createElement() //创建一个具体的元素
createTextNode() //创建一个文本节点
// 添加、移除、替换、插入
appendChild()
removeChild()
replaceChild()
insertBefore() //在已有的子节点前插入一个新的子节点
// 查找
getElementsByTagName() //通过标签名称
getElementsByName() //通过元素的Name属性的值(IE容错能力较强，会得到一个数组，其中包括id等于name值的)
getElementById() //通过元素Id，唯一性

6. null和undefined的区别？
null是一个表示"无"的对象，转为数值时为0；undefined是一个表示"无"的原始值，转为数值时为NaN。
undefined：
（1）变量被声明了，但没有赋值时，就等于undefined。
（2) 调用函数时，应该提供的参数没有提供，该参数等于undefined。
（3）对象没有赋值的属性，该属性的值为undefined。
（4）函数没有返回值时，默认返回undefined。
null：
（1） 作为函数的参数，表示该函数的参数不是对象。
（2） 作为对象原型链的终点。

7. new操作符具体干了什么呢?
（1）创建一个空对象，并且 this 变量引用该对象，同时还继承了该函数的原型。
（2）属性和方法被加入到 this 引用的对象中。
（3）新创建的对象由 this 所引用，并且最后隐式的返回 this 。

8. JSON 的了解？
JSON(JavaScript Object Notation) 是一种轻量级的数据交换格式。它是基于JavaScript的一个子集。数据格式简单, 易于读写, 占用带宽小。
格式：采用键值对，例如：{'age':'12', 'name':'back'}

9. call() 和 apply() 的区别和作用？
apply()函数有两个参数：第一个参数是上下文，第二个参数是参数组成的数组。如果上下文是null，则使用全局对象代替。
如：function.apply(this,[1,2,3]);
call()的第一个参数是上下文，后续是实例传入的参数序列。
如：function.call(this,1,2,3);

10. 如何获取UA？
function whatBrowser() {
document.Browser.Name.value=navigator.appName;
document.Browser.Version.value=navigator.appVersion;
document.Browser.Code.value=navigator.appCodeName;
document.Browser.Agent.value=navigator.userAgent;
}

其他

1. HTTP状态码知道哪些？
100 Continue 继续，一般在发送post请求时，已发送了http header之后服务端将返回此信息，表示确认，之后发送具体参数信息
200 OK 正常返回信息
201 Created 请求成功并且服务器创建了新的资源
202 Accepted 服务器已接受请求，但尚未处理
301 Moved Permanently 请求的网页已永久移动到新位置。
302 Found 临时性重定向。
303 See Other 临时性重定向，且总是使用 GET 请求新的 URI。
304 Not Modified 自从上次请求后，请求的网页未修改过。
400 Bad Request 服务器无法理解请求的格式，客户端不应当尝试再次使用相同的内容发起请求。
401 Unauthorized 请求未授权。
403 Forbidden 禁止访问。
404 Not Found 找不到如何与 URI 相匹配的资源。
500 Internal Server Error 最常见的服务器端错误。
503 Service Unavailable 服务器端暂时无法处理请求（可能是过载或维护）。

2. 你有哪些性能优化的方法？
（1） 减少http请求次数：CSS Sprites, JS、CSS源码压缩、图片大小控制合适；网页Gzip，CDN托管，data缓存 ，图片服务器。
（2） 前端模板 JS+数据，减少由于HTML标签导致的带宽浪费，前端用变量保存ajax请求结果，每次操作本地变量，不用请求，减少请求次数
（3） 用innerHTML代替DOM操作，减少DOM操作次数，优化javascript性能。
（4） 当需要设置的样式很多时设置className而不是直接操作style。
（5） 少用全局变量、缓存DOM节点查找的结果。减少IO读取操作。
（6） 避免使用CSS Expression（css表达式)又称Dynamic properties(动态属性)。
（7） 图片预加载，将样式表放在顶部，将脚本放在底部 加上时间戳。

3. 什么叫优雅降级和渐进增强？
优雅降级：web站点在所有新式浏览器中都能正常工作，如果用户使用的是老式浏览器，则代码会检查以确认它们是否能正常工作。由于IE独特的盒模型布局问题，针对不同版本的IE的hack实践过优雅降级了,为那些无法支持功能的浏览器增加候选方案，使之在旧式浏览器上以某种形式降级体验却不至于完全失效。

渐进增强：从被所有浏览器支持的基本功能开始，逐步地添加那些只有新式浏览器才支持的功能,向页面增加无害于基础浏览器的额外样式和功能的。当浏览器支持时，它们会自动地呈现出来并发挥作用。

4. 哪些常见操作会造成内存泄漏？
内存泄漏指任何对象在您不再拥有或需要它之后仍然存在。
垃圾回收器定期扫描对象，并计算引用了每个对象的其他对象的数量。如果一个对象的引用数量为 0（没有其他对象引用过该对象），或对该对象的惟一引用是循环的，那么该对象的内存即可回收。
setTimeout 的第一个参数使用字符串而非函数的话，会引发内存泄漏。
闭包、控制台日志、循环（在两个对象彼此引用且彼此保留时，就会产生一个循环）。

5. 线程与进程的区别
一个程序至少有一个进程,一个进程至少有一个线程。
线程的划分尺度小于进程，使得多线程程序的并发性高。
另外，进程在执行过程中拥有独立的内存单元，而多个线程共享内存，从而极大地提高了程序的运行效率。
线程在执行过程中与进程还是有区别的。每个独立的线程有一个程序运行的入口、顺序执行序列和程序的出口。但是线程不能够独立执行，必须依存在应用程序中，由应用程序提供多个线程执行控制。
从逻辑角度来看，多线程的意义在于一个应用程序中，有多个执行部分可以同时执行。但操作系统并没有将多个线程看做多个独立的应用，来实现进程的调度和管理以及资源分配。这就是进程和线程的重要区别。

HTML
1.Doctype作用？严格模式与混杂模式如何区分？它们有何意义?
<!DOCTYPE> 声明位于文档中的最前面的位置，处于 <html> 标签之前。此标签可告知浏览器文档使用哪种 HTML 或 XHTML 规范。
所谓的标准模式是指，浏览器按 W3C 标准解析执行代码；怪异模式则是使用浏览器自己的方式解析执行代码，因为不同浏览器解析执行的方式不一样，所以我们称之为怪异模式。
浏览器解析时到底使用标准模式还是怪异模式，与你网页中的 DTD 声明直接相关， DTD 声明定义了标准文档的类型（标准模式解析）文档类型，会使浏览器使用相应的方式加载网页并显示，忽略 DTD 声明 , 将使网页进入怪异模式。
  
2.HTML5 为什么只需要写 <!DOCTYPE HTML>？
html5不基于SGML,因此不需要对DTD进行引用，但是需要doctype来规范浏览器的行为（让浏览器按照他们应该的方式来运行）而HTML4.01基于SGML，所以需要对DTD进行引用，才能告知浏览器文档所使用的文档类型。

3.行内元素有哪些？块级元素有哪些？ 空(void)元素有那些？
CSS规范规定，每个元素都有display属性，确定该元素的类型，每个元素都有默认的display值，
比如div默认display属性值为“block”，成为“块级”元素；
span默认display属性值为“inline”，是“行内”元素。

行内元素有：a b span img input select strong（强调的语气） 
块级元素有：div ul ol li dl dt dd h1 h2 h3 h4…p  

知名的空元素： 
<br> <hr> <img> <input> <link> <meta> 
鲜为人知的是： 
<area> <base> <col> <command> <embed> <keygen> <param> <source> <track> <wbr>

4.页面导入样式时，使用link和@import有什么区别？
本质上，这两种方式都是为了加载CSS文件，但还是存在着细微的差别
link属于XHTML标签，而@import完全是CSS提供的一种方式。
link标签除了可以加载CSS外，还可以做很多其它的事情，比如定义RSS，定义rel连接属性等，@import就只能加载CSS了。

加载顺序的差别。当一个页面被加载的时候（就是被浏览者浏览的时候），link引用的CSS会同时被加载，而@import引用的CSS会等到页面全部被下载完再被加载。所以有时候浏览@import加载CSS的页面时开始会没有样式（就是闪烁），网速慢的时候还挺明显.

兼容性的差别。由于@import是CSS2.1提出的所以老的浏览器不支持，@import只有在IE5以上的才能识别，而link标签无此问题。

使用dom控制样式时的差别。当使用javascript控制dom去改变样式的时候，只能使用link标签，因为@import不是dom可以控制的。

5.介绍一下你对浏览器内核的理解？
主要分成两部分：渲染引擎(layout engineer或 Rendering Engine) 和 JS 引擎。
渲染引擎：负责取得网页的内容（HTML、 XML 、图像等等）、整理讯息（例如加入 CSS 等），以及计算网页的显示方式，然后会输出至显示器或打印机。浏览器的内核的不同对于网页的语法解释会有不同，所以渲染的效果也不相同。所有网页浏览器、电子邮件客户端以及其它需要编辑、显示网络内容的应用程序都需要内核。
JS引擎则：解析和执行 javascript 来实现网页的动态效果。
最开始渲染引擎和JS引擎并没有区分的很明确，后来 JS 引擎越来越独立，内核就倾向于只指渲染引擎。

6.常见的浏览器内核有哪些？
Trident(IE) Gecko(Firefox) Presto(Opera前内核) (已废弃) Opera现已改用Google Chrome的Blink内核。 Webkit(Safari内核,Chrome内核原型,开源) Blink(Google)

7.html5有哪些新特性、移除了那些元素？如何处理HTML5新标签的浏览器兼容问题？如何区分 HTML 和 HTML5？
HTML5已形成了最终的标准，概括来讲，它主要是关于图像，位置，存储，多任务等功能的增加。
新增的元素有绘画 canvas ，用于媒介回放的 video 和 audio 元素，本地离线存储 localStorage 长期存储数据，浏览器关闭后数据不丢失，而sessionStorage的数据在浏览器关闭后自动删除，此外，还新增了以下的几大类元素。
内容元素，article、footer、header、nav、section。
表单控件，calendar、date、time、email、url、search。
控件元素，webworker, websockt, Geolocation。
移出的元素有下列这些：
显现层元素：basefont，big，center，font, s，strike，tt，u。
性能较差元素：frame，frameset，noframes。
如何处理HTML5新标签的浏览器兼容问题？如何区分HTML和HTML5？
处理兼容问题有两种方式：
1.IE8/IE7/IE6支持通过document.createElement方法产生的标签，利用这一特性让这些浏览器支持HTML5新标签。
2.使用是html5shim框架
另外，DOCTYPE声明的方式是区分HTML和HTML5标志的一个重要因素，此外，还可以根据新增的结构、功能元素来加以区分。

(Q3)1.在文档类型声明上
html:<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
html5:<!doctype html>
在文档声明上，html有很长的一段代码，并且很难记住这段代码，而html5却不同，只有简简单单的声明，这也方便人们的记忆。
2.在结构语义上
html:没有体现结构语义化的标签，通常都是这样来命名的<div id="header"></div>，这样表示网站的头部。
html5:在语义上却有很大的优势。提供了一些新的标签，比如:<header><article><footer>。
  
8.简述一下你对HTML语义化的理解？
简答：用正确的标签做正确的事情。
html语义化让页面的内容结构化，结构更清晰，便于对浏览器、搜索引擎解析;
即使在没有样式CSS情况下也以一种文档格式显示，并且是容易阅读的;
搜索引擎的爬虫也依赖于HTML标记来确定上下文和各个关键字的权重，利于SEO;
使阅读源代码的人对网站更容易将网站分块，便于阅读维护理解。

9.HTML5的离线储存怎么使用，工作原理能不能解释一下？
在用户没有连接英特网时，可以正常访问站点和应用；在用户连接英特网时，更新用户机器上的缓存文件。

原理：HTML5的离线存储是基于一个新建的 `.appcache` 文件的缓存机制（并非存储技术），通过这个文件上的解析清单离线存储资源，这些资源就会像cookie一样被存储下来。之后当网络处于离线状态下时，浏览器会通过被离线存储的数据进行页面展示。

使用方法：
1. 在页面头部像下面一样加入一个 manifest 的属性；
2. 在 cache.manifest 文件里编写离线存储资源；
       CACHE MANIFEST
       #v0.11
       CACHE：
           js/app.js
           css/style.css
       NETWORK:
           resource/logo.png
       FALLBACK：
           / /offline.html
3. 在离线状态时，操作 window.applicationCache 进行需求实现

10.浏览器是怎么对HTML5的离线储存资源进行管理和加载的呢？
在线的情况下，浏览器发现html头部有manifest属性，它会请求manifest文件，

如果是第一次访问app，那么浏览器就会根据manifest文件的内容下载相应的资源并且进行离线存储。

如果已经访问过app并且资源已经离线存储了，那么浏览器就会使用离线的资源加载页面，然后浏览器会根据HTTP的缓存策略去探测manifest清单是否最新版本，如果最新，就不做任何操作，如果不是最新，那么就会重新下载文件中的资源并进行离线存储。

离线的情况下，浏览器就直接使用离线存储的资源。

注意：

如果服务器对离线的资源进行了更新，那么必须更新manifest文件版本之后这些资源才能被浏览器重新下载，如果只是更新了资源而没有更新manifest文件的话，浏览器并不会重新下载资源，也就是说还是使用原来离线存储的资源。

由于判断manifest清单是否最新是利用了HTTP的缓存策略的，所以可能出现你对manifest文件进行了更新，但浏览器还是使用原来的manifest文件的情况，这是因为http的缓存策略告诉浏览器本地缓存的manifest文件还没过期，所以对于manifest文件进行的缓存要十分小心。

浏览器在下载manifest文件中的资源的时候，它会一次性下载所有资源，如果某个资源由于某种原因下载失败，那么这次的所有更新就算是失败的，浏览器还是会使用原来的资源。

在更新了资源之后，新的资源需要到下次再打开app才会生效，如果需要资源马上就能生效，那么可以使用window.applicationCache.swapCache()方法来使之生效，出现这种现象的原因是浏览器会先使用离线资源加载页面，然后再去检查manifest是否有更新，所以需要到下次打开页面才能生效。

11.请描述一下 cookies，sessionStorage 和 localStorage 的区别？
`cookie`是网站为了标识用户身份而储存在用户本地终端（Client Side）上的数据（通常已经过加密）。cookie数据始终在同源的http请求中携带（即使不需要），也会在浏览器和服务器间来回传递。
`sessionStorage`和`localStorage`不会自动把数据发给服务器，仅在本地保存。

存储大小：
    cookie数据大小不能超过4K。
    sessionStorage和localStorage虽然也有存储大小的限制，但比cookie大得多，可以达到5M或更大。

有效时间：
    cookie          设置的cookie过期时间之前一直有效，即使窗口或浏览器关闭
    sessionStorage  数据在当前浏览器窗口关闭后自动删除
    localStorage    存储持久数据，浏览器关闭后数据不丢失除非主动删除数据
    
12.iframe有那些缺点？
iframe会阻塞主页面的Onload事件；
搜索引擎的检索程序无法解读这种页面，不利于SEO；
iframe和主页面共享连接池，而浏览器对相同域的连接有限制，所以会影响页面的并行加载。

使用iframe之前需要考虑这两个缺点。如果需要使用iframe，最好通过JavaScript动态给iframe添加src属性值，这样可以绕开以上两个问题。

13.Label的作用是什么？是怎么用的？（加 for 或 包裹）
label标签来定义表单控制间的关系，当用户选择该标签时，浏览器会自动将焦点转到和标签相关的表单控件上。

<label for="Name">Number:</label>
<input type="text" name="Name" id="Name" />

<label>Date:<input type="text" name="B" /></label>

14.HTML5的form如何关闭自动完成功能？
给不想要提示的 form 或下面某个 input 设置为 `autocomplete = off`。

15.如何实现浏览器内多个标签页之间的通信? (阿里)
这个功能可以通过 WebSocket API 来实现，不过这就有些小题大做了。毕竟杀鸡焉用牛刀，于是我开始寻找一些其它的跨标签页通信方式

我首先想到的就是使用 cookies 或者 localStorage ，来周期性地通过 setInterval 检查用户是否登录。对这个方案我并不满意，因为这样会把许多 CPU 周期耗费在检查一个可能自始至终都不会满足的条件上。

你知道 localStorage 会触发一个事件吗？具体地说，不论其中的哪一项在另一个浏览上下文里被添加、修改或删除时，它都会触发一个事件。实际上，这就意味着不论在哪个浏览器的标签页里访问了 localStorage

window.addEventListener('storage', function (event) {

  console.log(event.key, event.newValue);

});

不论某个标签页在何时修改了 localStorage，都会对其余的所有标签触发事件。这就意味着我们只要为 localStorage 赋值，就能够跨浏览器标签通信了

16.webSocket如何兼容低浏览器？(阿里)
Adobe Flash Socket
ActiveX HTMLFile（IE）
基于 multipart 编码发送 XHR
基于长轮询的 XHR

17.页面可见性（Page Visibility）API 可以有哪些用途？
该API可以用来检测页面对于用户的可见性，即返回用户当前浏览的页面或标签的状态变化
提高用户体验

18.如何在页面上实现一个圆形的可点击区域？
1. map + area 或者 svg
2. border-radius
3. 纯js实现，需要求一个点在不在圆上的简单算法、获取鼠标坐标等等
4.canvas

19.实现不使用 border 画出1px高的线，在不同浏览器的Quirksmode和CSSCompat模式下都能保持同一效果。
<div style="height:1px;overflow:hidden;background:#ccc"></div>

20.网页验证码是干嘛的，是为了解决什么安全问题？
区分用户是计算机还是人的公共全自动程序。可以防止：恶意破解密码、刷票、论坛灌水；
有效防止黑客对某一个特定注册用户用特定程序通过暴力破解的方式进行不断的登录尝试。

21.tite与h1的区别、b与strong的区别、i与em的区别？
从网站角度看，title网站标题能直接告诉搜索引擎和用户这个页面是关于什么主题和内容的网站。从文章的角度上看，用户进到内容页里，想看到的当然就是文章的内容，H1文章标题则是最重要的、最应该突出的。 一篇文章只能有一个标题，一个页面最好采用一个H1;多个H1会造成搜索引擎不知道这个页面哪个标题内容最重要，导致淡化这个页面标题和关键词，起不到突出主题的效果。从网站角度而言，title则重于网站信息标题;从文章角度而言，H1则概括的是文章主题。title与h1都归为代码优化，同为权重标签，要从范围来讲title传递给搜索引擎信号更强些，言外之意就是title要表达的权重在一定意义上高于h1。可以一起使用，在列表页时候两个权重标签就可以使用了，列表页使用title标签去诠释，列表页的每条信息就可以使用h1了。

<b> 标签呈现粗体文本效果。<b> 标签是基于内容的样式标签 <strong> 的物理版本，但它没有后者的扩展意义。<b> 标签明确地将包括在它和其结束标签之间的字符或者文本变成粗体。如果某种加粗的字体不可用，浏览器将使用一些其他的表现方法，例如反相显示或者加下划线等。举一个例子，经常访问 W3school 的用户可以注意到了，许多教程页面的第一句摘要都是以粗体显示的，而实际上，我们对这一句摘要使用了 <strong> 标签。使用这个标签的理由是，我们认为教程摘要不仅概括了其所在页面的内容，而且位于页面的最重要的位置，其内容自然是非常重要的且值得强调的。

<i>标签：显示斜体文本效果<i>标签告诉浏览器将包含其中的文本以斜体字（italic）或者倾斜（oblique）字体显示；<em>标签：
<em>标签中的文本表示为强调的内容，对于所有浏览器的显示效果来说，是把这段文字用斜体来显示；简单的说一个是物理标记，一个逻辑标记


CSS
1.介绍一下标准的CSS的盒子模型？与低版本IE的盒子模型有什么不同的？
CSS盒子模型：由四个属性组成的外边距(margin)、内边距(padding)、边界(border)、内容区(width和height);
标准的CSS盒子模型和低端IE CSS盒子模型不同：宽高不一样
标准的css盒子模型宽高就是内容区宽高；
低端IE css盒子模型宽高 内边距﹢边界﹢内容区；

标准的CSS盒子模型与低版本的盒子模型有什么不同的？
标准的CSS盒子模型的宽度指的是内容区（content）的宽度。 
低版本的IECSS盒子模型的宽度指的是：内容区宽+填充区宽+边界。

2.CSS选择符有哪些？哪些属性可以继承？
   1.id选择器（ # myid）
   2.类选择器（.myclassname）
   3.标签选择器（div, h1, p）
   4.相邻选择器（h1 + p）
   5.子选择器（ul > li）
   6.后代选择器（li a）
   7.通配符选择器（ * ）
   8.属性选择器（a[rel = "external"]）
   9.伪类选择器（a:hover, li:nth-child）
可继承的样式： font-size font-family color, UL LI DL DD DT;
不可继承的样式：border padding margin width height ;

3.CSS优先级算法如何计算？
优先级就近原则，同权重情况下样式定义最近者为准;
载入样式以最后载入的定位为准;
优先级为:
同权重: 内联样式表（标签内部）> 嵌入样式表（当前文件中）> 外部样式表（外部文件中）。
!important > id > class > tag
important 比 内联优先级高

4.css3新增伪类有那些？
p:first-of-type 选择属于其父元素的首个 <p> 元素的每个 <p> 元素。
p:last-of-type 选择属于其父元素的最后 <p> 元素的每个 <p> 元素。
p:only-of-type 选择属于其父元素唯一的 <p> 元素的每个 <p> 元素。
p:only-child 选择属于其父元素的唯一子元素的每个 <p> 元素。
p:nth-child(2) 选择属于其父元素的第二个子元素的每个 <p> 元素。

 :after          在元素之前添加内容,也可以用来做清除浮动。
 :before         在元素之后添加内容
 :enabled        
 :disabled       控制表单控件的禁用状态。
 :checked        单选框或复选框被选中。
 
 5.如何居中div？如何居中一个浮动元素？如何让绝对定位的div居中？
 1.水平居中：给div设置一个宽度，然后添加margin:0 auto属性
div{
width:200px;
margin:0 auto;
}

2.让绝对定位的div居中
    div {
      position: absolute;
      width: 300px;
      height: 300px;
      margin: auto;
      top: 0;
      left: 0;
      bottom: 0;
      right: 0;
      background-color: pink; /* 方便看效果 */
    }

3.水平垂直居中一
  确定容器的宽高 宽500 高 300 的层
  设置层的外边距
    div {
      position: relative;     /* 相对定位或绝对定位均可 */
      width:500px; 
      height:300px;
      top: 50%;
      left: 50%;
      margin: -150px 0 0 -250px;      /* 外边距为自身宽高的一半 */
      background-color: pink;     /* 方便看效果 */
   }

4.水平垂直居中二
  未知容器的宽高，利用 `transform` 属性
    div {
      position: absolute;     /* 相对定位或绝对定位均可 */
      width:500px; 
      height:300px;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      background-color: pink;     /* 方便看效果 */
  }

5.水平垂直居中三
  利用 flex 布局
  实际使用时应考虑兼容性
    .container {
       display: flex; 
       align-items: center;        /* 垂直居中 */
       justify-content: center;    /* 水平居中 */
    }
    .container div {
       width: 100px;
       height: 100px;
       background-color: pink;     /* 方便看效果 */
    }
    
居中浮动元素
<div class="box">
        <div class="item">123</div>
 </div>
        .box {
            position: relative;
            left: 50%;
            float: left;
        }

        .item {
            position: relative;
            left: -50%;
            float: left;
            background: red;
        }
        
  6.display有哪些值？说明他们的作用
block 块类型。默认宽度为父元素宽度，可设置宽高，换行显示。
none 缺省值。象行内元素类型一样显示。
inline 行内元素类型。默认宽度为内容宽度，不可设置宽高，同行显示。
inline-block 默认宽度为内容宽度，可以设置宽高，同行显示。
list-item 象块类型元素一样显示，并添加样式列表标记。
table 此元素会作为块级表格来显示。
inherit 规定应该从父元素继承 display 属性的值。

7.position的值relative和absolute定位原点是？
absolute
生成绝对定位的元素，相对于值不为 static的第一个父元素进行定位。
fixed （老IE不支持）
生成绝对定位的元素，相对于浏览器窗口进行定位。
relative
生成相对定位的元素，相对于其正常位置进行定位。
static
默认值。没有定位，元素出现在正常的流中（忽略 top, bottom, left, right,
z-index 声明）。
inherit
规定从父元素继承 position 属性的值。

8.CSS3有哪些新特性？
新增各种CSS选择器 （: not(.input)：所有 class 不是“input”的节点）
圆角 （border-radius:8px）
多列布局 （multi-column layout）
阴影和反射 （Shadow\Reflect）
文字特效 （text-shadow、）
文字渲染 （Text-decoration）
线性渐变 （gradient）
旋转 （transform）
缩放,定位,倾斜,动画,多背景
例如:transform:\scale(0.85,0.90)\ translate(0px,-30px)\ skew(-9deg,0deg)
Animation:

9.请解释一下CSS3的Flexbox（弹性盒布局模型）,以及适用场景？
一个用于页面布局的全新CSS3功能，Flexbox可以把列表放在同一个方向（从上到下排列，从左到右），并让列表能延伸到占用可用的空间。
较为复杂的布局还可以通过嵌套一个伸缩容器（flex container）来实现。
采用Flex布局的元素，称为Flex容器（flex container），简称"容器"。
它的所有子元素自动成为容器成员，称为Flex项目（flex item），简称"项目"。
常规布局是基于块和内联流方向，而Flex布局是基于flex-flow流可以很方便的用来做局中，能对不同屏幕大小自适应。
在布局上有了比以前更加灵活的空间。
具体：http://www.w3cplus.com/css3/flexbox-basics.html


2018/3/13

1.如何html中开启和关闭DNS预读取？
参考网页：https://developer.mozilla.org/zh-CN/docs/Controlling_DNS_prefetching
通过X-DNS-Prefetch-Control: on/off来设置。

X-DNS-Prefetch-Control的功能是:
X-DNS-Prefetch-Control控制着浏览器的预读取功能，它可以使得浏览器主动去执行域名解析的功能，包括文档中所有的链接。预读取会在后台执行，所以DNS很可能在链接对应的东西出现之前就已经解析完毕。这样能够减少用户点击链接时的延迟。

为什么要预读取:
DNS请求带宽很小，但一旦涉及到多级解析，或者很少访问到的网站，需要从服务器硬盘中查找域名时，这时延迟就会比较高。这点在手机网络上特别明显。因此预读取可以使得解析提早完成，减少延迟。

打开和关闭DNS预读取：

<meta http-equiv="x-dns-prefetch-control" content="off">
强制查询特定主机名：

<link rel="dns-prefetch" href="http://www.spreadfirefox.com/">
<link rel="dns-prefetch" href="//www.spreadfirefox.com">


2.<script>标签defer和async属性的作用，以及二者的区别？
若没有defer和async，浏览器遇到<script>标签会立即加载并执行该脚本，且停止加载和渲染文档元素。有了defer和async时，浏览器就可以异步加载脚本，不影响文档的加载和渲染。但defer和async有一定区别，在于async会使得脚本加载完则立即执行，而defer会延迟到页面元素解析完毕后再执行。

