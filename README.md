### <span style="color: #ff641c">Draft ECMA-262 (Ecma/TC39/2016/010)</span>
### <span style="color: #ff641c">7ᵗʰ Edition (第七版) / 2016.03.01</span>

# <span class="orange">ECMAScript® 2016 语言标准</span>

![MacDown logo](./pictures/ecma-logo.jpg)

# 版权声明

版权声明 © 2016 Ecma国际

这份文档和它可能的翻译版可以被复制并配备到别处，且对它的评论或解释或协助它实现的衍生作品也可以被完整或部分且没有任何形式的限制地编著、复制、出版、传播。这么做的前提是将版权声明和本章节包含到所有这样的复制版和衍生作品中。尽管如此，这份文档本身不能被以任何形式修改，包括移除其版权声明或其对Ecma国际的引用部分都是不允许的，除非是Ecma国际以开发任何文档或是可交付内容为目的需要(在这种情况下必须保留版权声明)，又或是根据需求将其翻译到除英语之外的其它语言。

本篇翻译内容是 [Toxni](https://github.com/Toxni) 在业余时间翻译整理的，很多内容借用了  w3c 中文兴趣小组的 [这篇 ES5 中文译版](https://www.w3.org/html/ig/zh/wiki/ES5)，第 20 章的内容是 [众成翻译](http://zcfy.cc/article/ecma-262-7-edition-1401.html) 的 [QAQMiao](http://zcfy.cc/@QAQMiao) 同学翻译的。本翻译只做交流学习使用，遵守 [自由转载-非商用-非衍生-保持署名 (创意共享3.0许可证)](https://creativecommons.org/licenses/by-nc-nd/3.0/deed.zh)。



译者水平欠佳，错误之处必定很多，希望您能 [在这里](https://github.com/Toxni/es7/issues) 提出您的宝贵意见和建议，感激不尽。 

# 介绍
本篇 Ecam 标准规定了 ECMAScript 2016 语言特性，它是 ECMAScript 语言的第七版。自 2017 年发布第一版开始，ECMAScript 已经成长为世界最广泛使用的通用编程语言之一。
它作为浏览器内置脚本被大家熟知，现如今也以脚本语言的身份广泛应用于服务端和其它应用。

ECMAScript 标准建立在一些原有的技术上，最为著名的是 JavaScript (网景) 和 JScript (微软)。它最初由网景的 Brendan Eich 发明，第一次出现是在网景的 Navigator 2.0 浏览器上。Netscape 2.0 以及微软 Internet Explorer 3.0 后序的所有浏览器上都有它的身影。

ECMAScript 标准的编写从 1996年11月 开始。ECMAScript 第一版于 1997年6月 被 Ecma委员会 采纳。

上述标准被快速提交至 ISO/IEC 联合技术委员会，并于 1998年4月 以国际标准 ISO/IEC 16262 通过。1998年6月 Ecma委员会 通过了 ECMA-262 第二版并且保持它与 ISO/IEC 16262 完全一致。第二版的变更仅仅是编辑性质的。

ECMAScript 第三版标准引入了强大的正则表达式，优化了字符串处理方法，加入了 try/catch 异常处理，定义了更严密的错误类型，格式化了数字输出，并且还做了其它一些为了国际化和语言成长的小变更。ECMAScript 标准第三版于 1999年12月 被 Ecma委员会 采纳并于 2002年6月 作为国际标准 ISO/IEC 16262:2002 发布。

自第三版标准发布以来，ECMAScript 已经与万维网的紧密关联，它也已经成为所有浏览器都支持的语言。ECMAScript第四版制定了很多有重要意义的内容，然而它却半路夭折了。尽管如此，它的一部分内容还是被继承在了第六版中。

ECMAScript 第五版标准（发布为ECMA-262 5th edition）规范化了很多已经在浏览器形成共识的语言规范，并且增加了自第三版后的一些新功能。包括存取器属性、反射创建以及对象检测、属性特性的程序控制、数组操作完善、JSON格式支持、并且新增了 严格模式 以检查语法以及程序安全性。第五版于 2009年12月 被 Ecma委员会 采纳。

第五版标准被快速提交至 ISO/IEC 联合技术委员会，并以国际标准 ISO/IEC 16262:2011 通过。5.1 版本对其做了微小改动，并继续以国际标准 ISO/IEC 16262:2011 命名。2011年6月 Ecma委员会 通过了 5.1 版本。

ECMAScript 第六版标准于 2009 年开始制定，此时也正是第五版标准准备提交的时候。其实第六版标准的不少特性都是从第三版发布后，也就是 1999 年后就开始了实验 (大部分在夭折了的第四版中)。所以某种意义上来说，第六版标准已经积累了十五年。本次更新的目标是增加对大型项目和库文件的支持，并且让 ECMAScript 作为其它语言编译的目标。最主要的增强部分有模块化、类 (class) 声明、块级作用域、迭代器 (iterator) 和生成器 (generator)、promise 异步语法、解构模式以及合理的尾调用。除此之外，第六版标准新增了数据结构操作，包括 map、sets、二进制数组等；新增了一些额外补充的 Unicode 字符并允许用在表达式或字符串中；还通过子类化增强其扩展性。第六版标准大大增强类 ECMAScript 语言本身能力以及它对库文件、大工程支持度。该标准于 2015年6月 被 Ecma委员会 通过。

本篇所描述的标准是 Ecma TC39 团队年度更新计划于今年 (2016) 的第一版更新。该纯文本的文档是基于 ECMAScript 2015 标准在 Github 上经过这一年的发展而来。这一年内，ECMAScript 2015 标准收到了数以千计的 issues 和 pull request，包括各类 bug 修复和编辑错误修复。此外，很多软件工具对本文档的编辑提供了便利，譬如  Ecmarkup、Ecmarkdown、Grammarkdown 等。本标准说明还包含了新的幂值运算，以及 `Array. prototype` 的一个新方法 —— `includes`。

许多个人及团体都对 Ecma TC39 团队年度更新本标准作出了贡献。现在已经形成了一个充满活力的社区，大家一起测试标准、报告 bug、提出可行建议、并向全世界的 ECMAScript 开发者提供教程。但是很可惜我们不可能在这里列出作出贡献的每个团体、每个人的名字。

Allen Wirfs-Brock - ECMA-262 第六版本编辑者

Brian Terlson - ECMA-262 第七版本编辑者

# 1. 范围

本标准制定目标为 ECMAScript 2016 语言。

# 2. 一致性

符合标准的 ECMAScript 实现，必须提供并支持本规范描述的所有类型、值、对象、属性、函数、程序语法和语义。

符合标准的 ECMAScript 实现，应当能解释符合 Unicode 8.0。0 或更高版本标准并符合 ISO/IEC 10646 国际标准。

符合标准的 ECMAScript 实现，应当能提供不同国家区域，不同文化，不同语言都适用的用户界面，并且接口定义需符合最新版的 ecma-402 且与本规范兼容。

符合标准的 ECMAScript 实现，允许提供超出本规范描述的额外类型、值、对象、属性、函数。尤其是本规范中描述的对象，允许提供未在本规范中描述的属性和属性值。

符合标准的 ECMAScript 实现，允许支持本规范未描述的程序语法和正则表达式语法。尤其是本规范 11.6.2.2 列出的 “未来保留字”，是允许作为程序语法的。

符合标准的 ECMAScript 实现，严禁包含任何在 16.2 中列出的禁止扩展的程序。

# 3. 参考文献

为了实现符合本规范的应用程序，下列引用文档是不可或缺的。对于标注了日期的文档，仅适用标注的版本。对于未标注日期的文档，以文档的最新版为准 (包括任何修订版)。

ISO/IEC 10646:2003: Information Technology – Universal Multiple-Octet Coded Character Set (UCS) plus Amendment 1:2005, Amendment 2:2006, Amendment 3:2008, and Amendment 4:2008, plus additional amendments and corrigenda, or successor

ECMA-402, ECMAScript 2015 Internationalization API Specification. 

[http://www.ecma-international.org/publications/standards/Ecma-402.htm](http://www.ecma-international.org/publications/standards/Ecma-402.htm)

ECMA-404, The JSON Data Interchange Format. 

[http://www.ecma-international.org/publications/standards/Ecma-404.htm](http://www.ecma-international.org/publications/standards/Ecma-404.htm)

# 4. 概述

本节包含对 ECMAScript 语言非规范性的概述。

ECMAScript 是在宿主环境中执行计算，处理对象的面向对象编程语言。这里定义的 ECMAScript 并未打算要计算性自足。事实上，本规范没有任何针对输入外部数据或输出计算结果的条文。相反，我们期望 ECMAScript 程序的计算环境可提供本规范中描述的对象和其它设施之外的、某些特定环境下的 宿主 (host) 对象，除了说明宿主对象应该提供可被 ECMAScript 程序访问的某些属性，调用的某些方法外，关于它的其他描述和行为超出了本规范涉及的范围。

ECMAScript 是脚本语言。脚本语言又被称为扩建的语言，或者动态语言，是一种编程语言，用来控制软件应用程序，脚本通常以文本（如ASCII) 保存，只在被调用时进行解释或编译。现有系统给了脚本语言需要的宿主环境，脚本语言来完善现有的系统。脚本语言更加简单，专业或非专业的程序员都可以使用。

ECMAScript 最初被设计为 Web 脚本语言，它提供了一种机制，使浏览器里的网页更加活跃。ECMAScript 可以为各种宿主环境提供核心的脚本功能，因此本文档为不依赖特定宿主环境的核心脚本语言作出规范。

ECMAScript 的一些机能和其他编程语言的类似；特别是 Java™，Self，和 Scheme。以下文献描述了他们：

ISO/IEC 9899:1996, Programming Languages – C.

Gosling, James, Bill Joy and Guy Steele. The Java™ Language Specification. Addison Wesley Publishing Co., 1996.

Ungar, David, and Smith, Randall B. Self: The Power of Simplicity. OOPSLA '87 Conference Proceedings, pp. 227-241, Orlando, FL, October 1987.

IEEE Standard for the Scheme Programming Language. IEEE Std 1178-1990.


## 4.1 Web 脚本语言

WEB 浏览器为引入客户端计算能力而提供 ECMAScript 宿主环境，例如，它提供的对象有：windows，menus，pop-ups，dialog boxes，text areas，anchors，frames，history，cookies 及 输入/输出 等等。进一步来说，Web浏览器 提供了一种方式，使得脚本代码可以去处理诸如改变焦点、页面和图片的加载卸载、错误和放弃、选择、表单提交和鼠标交互等等事件。脚本代码出现在 HTML 中，显示出来的页面是一个用户接口元素与固定的和计算出来的文本和图片的集合。脚本代码根据用户的交互而做出反应，并不需要存在一个主程序。

WEB 服务器为了服务端的计算则提供了一个完全不一样的宿主环境，包括的对象有：requests，clients，files 以及数据锁定和分享的机制。通过浏览器端脚本及服务端脚本的配合使用，在为基于 WEB 方式的应用程序提供定制的用户接口时，可以将计算分布到客户端和服务端进行。

每一种支持 ECMAScript 的 WEB 浏览器和服务器都将它们自身作为宿主环境，将 ECMAScript 作为补充，以使得 ECMAScript 的执行环境变得完整。

## 4.2 语言概述

下面是非正式的 ECMAScript 概述，并未描述语言的所有部分。此概述并非标准的一部分。

ECMAScript 是基于对象的：基本语言和宿主设施都由对象提供，ECMAScript 程序是一组可通信的对象。ECMAScript 对象 (objects) 是 属性 (properties) 的集合，每个属性有零个或多个 特性 (attributes)，它确定怎样使用此属性。例如，当设置一个属性的 Writable 特性为 false 时，任何试图更改此属性值的 ECMAScript 代码的都会运行失败。属性是持有其他 对象 (objects)， 原始值 (primitive values)， 函数 (functions) 的容器。原始值是以下内置类型之一的成员：Undefined，Null，Boolean，Number，String；对象是剩下的内置类型 Object 的成员；函数是可调用对象 (callable object)。方法 (method) 是通过属性与对象关联的函数。

ECMAScript 定义一组内置对象，勾勒出 ECMAScript 实体的定义。这些内置对象包括一些全局对象 (global object)。其中有基础对象包括 Object、Function、Boolean、Symbol以及各种 Error (EvalError、RangeError、ReferenceError、SyntaxError、TypeError、URIError)；数值相关的对象包括 Math、Number、Date；文本处理对象包括 String、RegExp；对象还是包括数列及其它九种有特定值的数据结构的基础索引；键的合集包括 Map 和 Set 都是对象；对象支持的数据结构包括 JSON 对象、ArrarBuffer 和 Dataview；对象支持的抽象方法包括 generator 和 Promise 对象；最后还有反射对象比如说 Proxy 和 Reflect。

ECMAScript 中还定义一组内置运算符 (operators)。ECMAScript 运算符包括 一元运算符，乘法运算符，加法运算符，按位移位运算符，关系运算符，相等运算符，二进制位运算符，二进制逻辑运算符，赋值运算符，逗号运算符。

大型的 ECMAScript 也支持模块化，它允许程序被分为若干小的语句和声明。每一个模块都要有一个明确的声明来显示它调用了其它的哪个模块以及它可以被那一个模块调用。

ECMAScript 语法有意设计成与 Java 语法类似。ECMAScript 的语法是松散的，使其能够作为一个易于使用的脚本语言。例如，一个变量不需要有类型声明，属性也不需要与类型关联，定义的函数也不需要声明在函数调用词句的前面。

### 4.2.1 对象

ECMAScript 不使用诸如 C++，Smalltalk，Java 中的类(class)。相反，对象可以通过各种方式创建，包括字面符号，或通过 构造器 创建对象然后运行代码初始化其全部或部分属性值，为这些属性分配初始值。每个构造器是一个拥有名为 prototype 的属性的函数。此属性用于实现 基于原型的继承 和 共享属性 。构造器通过 new 表达式创建对象：例如，new Date(2016, 10) 创建一个新 Date 对象。不使用 new 调用一个构造器的结果，依赖构造器本身。例如，Date() 产生一个表示当前日期时间的字符串，而不是一个对象。

每个由构造器创建的对象，都有一个隐式引用 (叫做对象的原型) 链接到构造器的 prototype 属性值。再者，原型可能有一个 非空(non-null) 隐式引用链接到它自己的原型，以此类推，这叫做 原型链 。当向对象的一个属性提出引用，引用会指向原型链中包含此属性名的第一个对象的此属性。换句话说，首先检查直接提及的对象的同名属性，如果对象包含同名的属性，引用即指向此属性，如果该对象不包含同名的属性，则下一步检查对象的原型；以此类推。


一般情况下基于类的面向对象语言的实例拥有状态，类拥有方法，并且只能继承结构和行为。在 ECMAScript 中，对象拥有状态和方法，并且结构，行为，状态全都可继承。

不直接包含原型中包含的特定属性的所有对象会共享此属性及属性值。图1 说明了这一点：


![MacDown logo](./pictures/pic01.png)



CF 是一个构造器 (也是一个对象)。五个对象已用 new 表达式创建：cf1, cf2, cf3, cf4, cf5。每个对象都有名为 q1 和 q2 的属性。虚线表示隐式原型关系；例如：cf3 的原型是 CFp。构造器 CF 自己有名为 P1 和 P2 的两个属性, 这对 CFp, cf1, cf2, cf3, cf4, cf5 是不可见的。CFp 的名为 CFP1 的属性共享给 cf1, cf2, cf3, cf4, cf5 (没有 CF), 以及在 CFp 的隐式原型链中找不到任何名为 q1, q2, 或 CFP1 的属性。请注意，CF 和 CFp 之间没有隐式原型链接。

不同于基于类的对象语言，属性可以通过赋值的方式动态添加给对象。也就是说，构造器并不是非要对构造的对象的全部或任何属性命名或赋值。上图中，可以用给 CFp 添加新属性值的方式为 cf1, cf2, cf3, cf4, cf5 添加一个新的共享属性。

虽然 ECMAScript 之前并未定义 类(class) 这一概念，但是在构造函数，原型对象，属性方法这些部分如果有 类(class) 这一概念的话会方便很多。因此从 ECMAScript 2015 
开始便新增了 类(class) 的语法，允许程序员使用它简洁地写出 类(class) 这样的结构。

### 4.2.2 ECMAScript 的严格模式变体

ECMAScript 语言认可有些用户希望限制使用语言中某些功能的可能性。他们这样做可能是为了安全考虑，避免他们认为是容易出错的功能，获得增强的错误检查，或其他原因。为了支持这种可能性，ECMAScript 中定义了语言的严格变体。语言的严格变体，排除了 ECMAScript 语言的某些特定的语法和语义特征，还修改了某些功能的详细语义。严格变体还指定了必须抛出错误异常报告的额外错误条件，即使在非严格的语言形式下这些条件不属于错误。

ECMAScript 的严格变体通常被称为语言的 严格模式 (strict mode)。严格模式选择使用的 ECMAScript 严格模式的语法和语义，明确地适用于个别 ECMAScript 代码单元级别。由于严格模式适用于选择的语法代码单元级别，严格模式仅在这个代码单元内施加有局部效果的限制。严格模式不限制或修改任何必须运行在多个代码单元的 ECMAScript 语义层面。一个 ECMAScript 程序可由严格模式和非严格模式的代码单元组成。在这种情况下，严格的模式只适用于严格模式代码单元内实际执行的代码。

要符合这一规范，ECMAScript的实现必须同时实现未限制的ECMAScript语言和按照这个规范定义的ECMAScript的严格模式变体。此外，实现还必须支持未限制的和严格模式代码单元的在同一个程序中混用。

## 4.3 术语定义

本文档将使用下列术语和定义。

### 4.3.1 数据类型 (type)

本规范第 6 章定义数据的集合。

### 4.3.2 原始值 (primitive value)

本规范第六章定义的 Undefined, Null, Boolean, Number, Symbol, String 这些值之一。

*注意：原始值代表语言实现的最底层的数据。*

### 4.3.3 对象 (object)

对象类型的成员。

*注意：对象是属性的集合，并有一个原型对象。原型可以是为 null。*

### 4.3.4 构造器 (constructor)

创建和初始化对象的函数对象。

*注意：构造器的 prototype 属性值是一个原型对象，它用来实现继承和共享属性。*

### 4.3.5 原型 (prototype)

为其他对象提供共享属性的对象。

*注意：当构造器创建一个对象，为了解决对象的属性引用，该对象会隐式引用构造器的 prototype 属性。通过程序表达式 constructor.prototype 可以引用到构造器的 prototype 属性，并且添加到对象原型里的属性，会通过继承与所有共享此原型的对象共享。另外，可使用 Object.create 内置函数，通过明确指定原型来创建一个新对象。*

### 4.3.6 普通对象 (ordinary object)

有 默认行为 和 所有对象都支持的基本方法 的对象。

### 4.3.7 异常对象 (exotic object)

不含或少含 所有对象都支持的基本方法 的对象。

*注意：任何对象只要不是普通对象就是异常对象。*

### 4.3.8 标准对象 (standard object)

任何语义符合本标准的对象。


### 4.3.9 内置对象 (built-in object)

由 ECMAScript 标准规定并提供的对象。

*注意：本标准制定了标准的内置对象。一个 ECMAScript 可能会包含其它更多内置对象。内置构造器是构造器，同样也是内置对象。*

### 4.3.10 未定义值 (undefined value)

原始值，一个变量未被赋值时的默认值。

### 4.3.11 未定义类型 (Undefined type)

仅有 undefined 一个值的数据的类型。

### 4.3.12 空值 (null value)

原始值，任何有意使其为空的对象的值。

### 4.3.13 空类型 (Null type)

仅有 null 一个值的数据的类型。

### 4.3.14 布尔值 (Boolean value)

布尔类型中的一个。

*注意：布尔类型只有 true 和 false 两个值。*

### 4.3.15 布尔类型 (Boolean type)

由 true 和 false 两个值构成的类型。

### 4.3.16 布尔对象 (Boolean object)

本标准内置的布尔构造器生成的实例。

*注意：布尔对象是内置的布尔构造器用 new 关键字生成的示例，提供布尔值作为参数，得到的对象会内部会有一个布尔值。布尔对象可以被强制转换为布尔值。*

### 4.3.17 字符串值 (String value)

原始值，一个有限序列或是零个或多个 16 位无符号整数。

*注意：字符串值是字符串类型的成员。序列中的每个整型值通常代表一个 16位 utf-16 单元的文本。然而，除了必须是 16位 无符号整数以外，ECMAScript 没有其它任何限制或要求。*

### 4.3.18 字符串类型 (String type)

所有可能的字符串的集合。

### 4.3.19 字符串对象 (String object)

本标准内置的字符串构造器生成的实例。

*注意：字符串对象是内置的字符串构造器用 new 关键字生成的示例，提供字符串作为参数，得到的对象内部会有一个字符串。通过调用字符串构造器 [(21.1.1.1)]()，字符串对象可以被强制转换为字符串值。*

### 4.3.20 数值 (Number value)

原始值，是一个 64 位双精度二进制值，符合 IEEE754 规定。

*注意：数值是数值类型的成员，直接表现为一个数字。*

### 4.3.21 数值类型 (Number type)

所有数值的集合，包括 “Not-a-Number” (NaN) 值，正无穷和负无穷。

### 4.3.22 数值对象 (Number object)

本标准内置的数值构造器生成的实例。

*注意：数值对象是内置的数值构造器用 new 关键字生成的示例，提供数值作为参数，得到的对象内部会有一个数值。通过调用数值构造器 [(21.1.1.1)]()，数值对象可以被强制转换为数值。*

### 4.3.23 无穷大 (Infinity)

数值，指正无穷。

### 4.3.24 非数值类型 (NaN)

数值，是 IEEE 754-2008 规定的 “Not-a-Number” 值。

### 4.3.25 符号值 (Symbol value)

原始值，代表一个独一无二的，非字符串对象的属性值。

### 4.3.26 符号类型 (Symbol type)

所有可能的符号值的集合。

### 4.3.27 符号对象 (Symbol object)

内置符号构造器生成的示例。

### 4.3.28 函数 (function)

对象类型中可被当作子程序调用的一类。

*注意：函数除了拥有属性，还包含可执行代码、状态，用以确定被调用时的行为。函数的代码不限于只用 ECMAScript 书写。*

### 4.3.29 内置函数 (built-in function)

是函数的内置对象。

*注意：内置函数包含例如 parseInt 和 Math.exp 这样的函数。标准的实现可能包含本标准中未包含的额外的内置函数。*

### 4.3.30 属性 (property)

对象的一部分，是键值对的键 (字符串类型或者符号类型)。

*注意：属性可能根据属性值的不同表现为直接的数据值（原始值，对象，或一个函数对象）或间接的一对访问器函数。*

### 4.3.31 方法 (method)

是函数的属性值。

*注意：当一个函数被叫做某对象的方法，该对象将作为 this 关键字传给该函数。*

### 4.3.32 内置方法 (built-in method)

是内置函数的方法。

*注意：标准内置方法由本规范定义，一个 ECMAScript 实现可指定，提供其他额外的内置方法。*

### 4.3.33 特性 (attribute)

属性内部定义的一些的特定值。

### 4.3.34 自身属性 (own property)

对象直接拥有的属性。

### 4.3.35 继承属性 (inherited property)

不是对象的自身属性，是对象原型的属性 (原型的自身属性或继承属性)。

## 4.4 本规范的结构

本规范剩余篇幅将会以以下结构展示：

第 4 部分将会介绍贯穿本规定始终的记法约定。

第 6 部分至第 9 部分介绍 ECMAScript 在何种环境下执行。

第 10 部分至第 16 部分介绍 ECMAScript 语言的所有语义及语法特性。

第 17 部分至 26 部分记录了 ECMAScript 标准库。它包括当 ECMAScript 标准执行时所有的标准对象。

# 5 记法约定

## 5.1 语法和词法的文法

### 5.1.1 上下文无关文法

一个 上下文无关文法 由一定数量的 产生式 (productions) 组成。每个产生式的左边 (left-hand side) 是一个被称为非终结符 (nonterminal) 的抽象符号，右边 (right-hand side) 是零或多个非终结符和终结符 (terminal symbols) 的有序排列。任何文法，它的终结符都来自指定的字母集。

当从一个叫做 目标符 (goal symbol) 的特殊非终端符组成的句子起始，那么给出的上下文无关文法就表示 语言 (language)，也就是将产生式右边序列的非终结符当作左边，进行反复替换的结果就成为可能的终结符序列集合 (可能无限)。

### 5.1.2 词法和正则的文法

第 11 部分给出了 ECMAScript 的 词法文法 (lexical grammar)。作为此文法的终结符字符 (Unicode代码单元) 符合 10.1 中定义的 SourceCharacter 的规则。它定义了一套产生式，从目标符 InputElementDiv 或 InputElementRegExp 起始，描述了如何将这样的字符序列翻译成一个输入元素序列。

空白和注释之外的输入元素构成 ECMAScript 语法文法的终结符，它们被称为 ECMAScript 的 tokens。这些 tokens 是 ECMAScript 语言的保留字，标识符，字面量，标点符号。此外，行结束符虽然不被视为 tokens，但会成为输入元素流的一部分，用于引导处理自动插入分号 (11.9)。空白和单行注释会被简单的丢弃，不会出现在语法文法的输入元素的流中。如果一个多行注释 (MultiLineComment)（即形式为 “/* ... */” 的注释，不管是否跨越多行）不包含行结束符也会简单地丢弃，但如果一个多行注释包含一个或多个结束符，那么，注释会被替换为一个行结束符，成为语法文法输入元素流的一部分。

本标准在 21.2.1 中给出了 ECMAScript 的 正则文法 (RegExp grammar)。此文法的终结符字符也由 SourceCharacter 定义。它定义了一套产生式，从目标符 Pattern 起始，描述了如何将这样的字符序列翻译成一个正则表达式模式。

两个冒号“::”作为分隔符分割词法和正则的文法产生式。词法和正则的文法共享某些产生式。

### 5.1.3 数字字符串文法

用于转换字符串为数字值的一种文法。此文法与词法文法的一部分 (与数字字面量有关的) 类似，并且有终结符 SourceCharacter。此文法出现在 (7.1.3.1)。

三个冒号“:::”作为分隔符分割数字字符串文法的产生式。

### 5.1.4 语法文法

第 11 12 13 14 15 章给出了 ECMAScript 的 语法文法。词法文法定义的 ECMAScript tokens 是此文法的终结符（5.1.2）。它定义了一组起始于 Program 目标符的产生式，描述了语法正确的 ECMAScript 程序应该怎样排列 tokens。

当一个字符流被解析为 ECMAScript 程序，它首先通过词法文法应用程序反复转换为一个输入元素流；然后再用一个语法文法应用程序解析这个输入元素流。当输入元素流没有更多 tokens 时，如果 tokens 不能解析为 Program 目标非终结符的单一实例，那么程序在语法上存在错误。

只用一个冒号“:”作为分隔符分割语法词法的产生式。

事实上第 12 13 14 15 章给出的语法语法，并不能完全说明一个正确的 ECMAScript 程序能接受的 token 序列。一些额外的 token 序列也被接受，即某些特殊位置 (如行结束符前) 加入分号可以被文法接受。此外，文法描述的某些 token 序列不被文法接受，如一个行结束符出现在 “尴尬” 的位置。

### 5.1.5 文法标记法

TODO: Change some differences

词法、正则表达式文法、字符串数字文法，以及一些其它文法，每当这些文法的终结符被文本直接涉及到时，使用等宽字符来显示，它们都在文法产生式 Note.png 中，并且贯穿这份文档。他们表示程序书写正确。所有以这种方式指定的终结符，都可以理解为 Unicode 字符的完整的 ASCII 范围，不是任何其他乌焉成马的 Unicode 范围字符。

非终结符以斜体显示。一个非终结符的定义由非终结符名称和其后定义的一个或多个冒号给出。(冒号的数量表示产生式所属的文法) 非终结符的右侧有一个或多个替代子紧跟在下一行。例如，句法定义：

```js
 WhileStatement :
   while ( Expression ) Statement
```

表示这个非终结符 WhileStatement 代表 while Token，其后跟左括号 Token，其后跟 Expression，其后跟右括号 Token，其后跟 Statement。这里出现的 Expression 和 Statement 本身是非终结符。另一个例子，句法定义：

```js
 ArgumentList :
   AssignmentExpression
   ArgumentList , AssignmentExpression
```

表示这个 ArgumentList 可以代表一个 AssignmentExpression，或 ArgumentList，其后跟一个逗号，其后跟一个 AssignmentExpression。这个 ArgumentList 的定义是递归的，也就是说，它定义它自身。其结果是，一个 ArgumentList 可能包含用逗号隔开的任意正数个参数，每个参数表达式是一个 AssignmentExpression。这样，非终结符共用了递归的定义。

终结符或非终结符可能会出现后缀下标 “opt”，表示它是可选符号。实际上包含可选符号的替代子包含两个右边部分，一个是省略可选元素的，另一个是包含可选元素的。这意味着：

```js
 VariableDeclaration :
   Identifier Initialiser(opt)
```
是以下的一种缩写：

```js
 VariableDeclaration :
   Identifier
   Identifier Initialiser
```
并且：

```js
 IterationStatement :
   for ( ExpressionNoIn(opt) ; Expression(opt) ; Expression(opt) ) Statement
```
是以下的一种缩写：

```js
 IterationStatement :
   for ( ; Expression(opt) ; Expression(opt) ) Statement
   for ( ExpressionNoIn ; Expression(opt) ; Expression(opt) ) Statement
```
是以下的一种缩写 :

```js
 IterationStatement :
   for ( ; ; Expression(opt) ) Statement
   for ( ; Expression ; Expression(opt) ) Statement
   for ( ExpressionNoIn ; ; Expression(opt) ) Statement
   for ( ExpressionNoIn ; Expression ; Expression(opt) ^) Statement
```
是以下的一种缩写：

```js
 IterationStatement :
   for ( ; ; ) Statement
   for ( ; ; Expression ) Statement
   for ( ; Expression ; ) Statement
   for ( ; Expression ; Expression ) Statement
   for ( ExpressionNoIn ; ; ) Statement
   for ( ExpressionNoIn ; ; Expression ) Statement
   for ( ExpressionNoIn ; Expression ; ) Statement
   for ( ExpressionNoIn ; Expression ; Expression ) Statement
```
因此，非终结 IterationStatement 实际上有 8 个右侧替代子。

如果文法定义的冒号后面出现文字 “one of”，那么其后一行或多行出现的每个终结符都是一个选择定义。例如，ECMAScript 包含的词法生产器：

```js
 NonZeroDigit :: one of
   1 2 3 4 5 6 7 8 9
```

这仅仅下面写法的一种缩写：

```js
 NonZeroDigit ::
   1
   2
   3
   4
   5
   6
   7
   8
   9
```

TODO

## 5.2 TODO

TODO

## 5.3 TODO

TODO

# 6 ECMAScript 数据类型和值

这个规范里处理的每个值都有一个关联的类型。可能的值和类型都将在本章中予以说明。类型将被进一步归入 ECMAScript 语言类型和特定类型。

## 6.1 ECMAScript 语言类型

ECMAScript 语言类型表示直接被程序员使用的几种类型，包括 Undefined、Null、Bollean、String、Symbol、Number 和 Object 这七种。ECMAScript 语言值就是符合这七种类型的值。

### 6.1.1 未定义类型 (Undefined Type)

未定义类型只有一个确定值，也就是 undefined 任何未声明的变量值都为 undefined。

### 6.1.2 空类型 (Null Type)

未定义类型只有一个确定值，也就是 null。

### 6.1.3 布尔类型 (Boolean Type)

未定义类型只有两个确定值，也就是逻辑上的 true 和 false。


### 6.1.4 字符串类型 (String Type)

字符串类型是所有有限的零个或多个16位无符号整数值 (“元素”) 的有序序列，其最大长度为 2^53 -1。在运行的 ECMAScript 程序中，字符串类型常被用于表示文本数据，此时字符串中的每个元素都被视为一个 UTF-16 代码单元。每个元素都被认为占有此序列中的一个位置，用非负整数索引这些位置。任何时候，第一个元素(若存在)在位置 0，下一个元素 (若存在) 在位置 1，依此类推。字符串的长度即其中元素 (即16位的值) 的个数。空字符串长度为零，因而不包含任何元素。

若一个字符串包含实际的文本数据，每个元素都被认为是一个单独的 UTF-16 代码单元。然而 ECMAScript 并不设条件或是强制规定字符串值的代码单元序列，所以它们可能不是规范的 UTF-16 代码单元序列。无论这是不是 String 实际的存储格式，String 中的字符都被当作表示为 UTF-16 来计数。`String.prototype.normalize` 可以将字符串值标准化，`String.prototype.normalize` 会隐式地将字符串值标准化，除此之外，没有其它操作会将其隐式标准化。除非特别声明，作用在字符串上的所有操作都视它们为无差别的 16 位无符号整数；这些操作不保证结果字符串仍为正规形式，也不保证语言敏感结果。

*注意：这些决议背后的原理是尽可能地保持字符串的实现简单而高效。因此，建议 ECMAScript 程序源代码若为正规形式 C，应保证字符串常量是正规化的 (如果保证源代码文本是正规化的话)，即便它们不包含任何 Unicode 转义序列。*

有些操作会将字符串值当作 UTF-16 编码代码点，对此解释如下：

* 在 0 到 0xD7FF 范围内的代码单元或在 0xE000 至 0xFFFF 内的代码单元会被解释为相同代码点。
* 两个字符的字符串序列，前者 c1 在 0xD800 至 0xDBFF 范围内，后者 c2 在 0xDC00 至 0xDFFF范围内，这是一个代理对，它们代码点值为 (c1 - 0xD800) × 0x400 + (c2 - 0xDC00) + 0x10000。
* 在  0xD800 至 0xDFFF 范围内，但又不是代理对，那么将它的代码点理解为同一个值。

### 6.1.5 符号类型

符号类型是一组非字符串类型的，可用于对象键名的特殊符号。

每个符号类型值都是唯一的，不可变更的。

每个符号类型都有一个不可改变的，相互独立的，被叫做 [[描述(Description)]] 的值，它只能是字符串或 undefined。

#### 6.1.5.1 著名符号 (Well-Known Symbols)

著名符号是本篇规范中描述的一些明确的内置符号。他们通常用作键的属性值。除非另行声明，著名符号可用在所有领域使用。

本说明中，著名符号会以 @@name 形式表示，name 是下表中的某个值。

 规定名 | [[ 描述 (Description) ]] | 值和目的 |
-------------------|------------------|--------------------|
@@hasInstance | "Symbol.hasIntance" | 方法，判断对象是否为某构造器的示例，被 instanceof 操作调用。 |
@@isConcatSpreadble | "Symbol.isConcatSpreadable" | 布尔值，若为 true 则表明该对象内部的数组应该用 `Array.prototype.concat` 合并起来。 |
@@iterator | "Symbol. iterator" | 方法，返回一个对象的迭代器，被 for-of 语句调用。 |
@@match | "Symbol.match" | 正则方法，在字符串中匹配正则表达式。被 `String.prototype.match` 调用。 |
@@repalce | "Symbol.replace" | 正则方法，在字符串中替换匹配正则表达式的字符。被 `String.prototype.replace` 调用。 |
@@search | "Symbol.search" | 正则方法，在字符串中返回匹配正则表达式的字符序号。被 `String.prototype.search` 调用。 |
@@species | "Symbol.species" |  值为函数的属性，用于创建导出对象的构造器函数。 |
@@split | "Symbol.split" | 正则方法，在字符串中分割正则表达式匹配的字符。被 `String.prototype.split` 调用。 |
@@toPrimitive | "Symbol.toPrimitive" | 方法，将一个对象转换为对应的原始值，被 [ToPrimitive]() 概念调用。  |
@@toStringTag | "Symbol.toStringTag" | 值为字符串的属性，用以创建一个对象的默认字符串描述，被内置方法 Object.prototype.toString 调用。 |
@@unscopable | "Symbol.unscopable" | 值为对象的属性，该对象自身的以及继承的属性名就是同其绑定的相关对象的属性名，除 with 语句条件以外。 |

### 6.1.6 数值类型

精确地描述，数值类型拥有 18437736874454810627 (2^64 - 2^53 + 3) 个值，表示为 IEEE-754 格式 64 位双精度数值 (IEEE 二进制浮点数算术中描述了它)，除了 IEEE 标准中的 9007199254740990 (即，2^53 - 2) 个明显的 “非数字” 值。在 ECMAScript 中，它们被表示为一个单独的特殊值 NaN。(请注意，NaN 值由程序表达式 NaN 产生，并假设执行程序不能调整定义的全局变量 NaN ) 在某些实现中，外部代码也许有能力探测出众多非数字值之间的不同，但此类行为依赖于具体实现。对于 ECMAScript 代码而言，NaN 值相互之间无法区别。

还有另外两个特殊值，称为正无穷和负无穷。为简洁起见，在说明目的时，用符号 +∞ 和 -∞ 分别代表它们。(请注意，两个无限数值由程序表达式 +Infinity (简作 Infinity) 和 -Infinity 产生，并假设执行程序不能调整定义的全局变量 Infinity。)

另外 18437736874454810624 (即，2^64 - 2^53) 个值被称为有限数值。其中的一半是正数，另一半是负数，对于每个正数而言，都有一个与之对应的、相同规模的负数。

请注意，还有一个正零和一个负零。为简洁起见，类似地，在说明目的时，分别用用符号 +0 和 -0 代表这些值。(请注意，这两个数字零由程序表达式 +0（简作 0） 和 -0 产生。)

这 18437736874454810622 (2^64 - 2^53 - 2)个有限非零值分为两种：

其中 18428729675200069632（即，2^64 - 2^54） 个是常规值，形如

```js
 s×m×2^e
```

这里的 s 是 +1 或 -1，m 是一个小于 253 但不小于 252 的正整数，e 是一个闭区间 -1074 到 971 中的整数。

剩下的 9007199254740990（即，2^53 - 2）个值是非常规的，形如

```js
 s×m×2e
```

这里的 m 是 +1 或 -1，m 是一个小于 252 的 正整数，e 为 -1074。

请注意，所有规模不超过 253 的正整数和负整数都可被数值类型表示 (整数 0 有两个呈现形式 +0 和 0)。

如果一个有限的数值非零且用来表达它 (上文两种形式之一) 的整数 m 是奇数，则该数值有 奇数标记。否则，它有 偶数标记。


在本规范中，当 x 表示一个精确的非零实数数学量 (甚至可以是无理数，比如 π) 时，短语 "x 的 Number 值" 意为，以下面的方式选择一个 Number 值。考虑数值类型的所有有限值的集合 (不包括 -0 和两个被加入在数值类型中但不可呈现的值，即 21024 (+1 × 2^53 × 2971) 和 -21024 (-1 × 2^53 × 2971)。选择此集合 中值最接近 x 的一员，若集合中的两值近似相等，那么选择有偶数标记的那个；为此，21024 和 -21024 这两个超额值被认为有偶数标记。最终，若选择 21024 ，用 +∞ 替换它；若选择 -21024 ，用 -∞ 替换它；若选择 +0，有且只有 x 小于零时，用 -0 替换它；其它任何被选取的值都不用改变。结果就是 x 的 Number 值。(此过程正是 IEEE-754 的四舍五入模式对应的行为。)

某些 ECMAScript 运算符仅涉及闭区间 -2^31 到 2^31 - 1 的整数，或闭区间 0 到 2^32 - 1。这些运算符接受任何数值类型的值，不过，数值首先被转换为 232 个整数值中的一个。参见 (7.1 章)[] 中的数值转换描述。

### 6.1.7 对象类型

本规范中的特性用于定义和解释命名属性的状态。命名的数据属性由一个名字关联到一个下表中列出的特性。

TODO

TODO

TODO

TODO



# 19 基本对象

## 19.1 对象对象

### 19.1.1 对象构造器

对象构造器是固有对象 %Object% 的初始值，它是全局对象的一个属性。当它作为构造器被调用的时候可以产生一个新的普通对象。当它作为函数而不是构造器被调用的时候，它会执行类型转换。

对象构造器被设计为可子类化的，当定义类的时侯，它可以作为 extends 语句的值。

#### 19.1.1.1 Object([value])

当 Object 被当作函数调用，且包含可选参数参数 [value]，那么执行以下步骤：

1. 如果 NewTarget 非空也非有效函数，那么返回  OrdinaryCreateFromConstructor(NewTarget, "%ObjectPrototype%") 的值。

2. 如果 [value] 为 null, undefined 或者为未提供的值，那么返回 ?ObjectCreate(%ObjectPrototype%) 的值。

3. 返回 ToObject(value) 的值。


### 19.1.2 对象构造器的属性 

对象构造器的内部固有属性 [[Prototype]] 的值为标准对象 %FunctionPrototype%。 

除了 length 属性以外，对象构造器还有以下属性：

#### 19.1.2.1 Object.assign ( target, ...sources )

assign 方法可以复制原对象中的所有可枚举属性到新的对象中去，当 assign 方法调用时，执行以下步骤：

1. Let to be ? ToObject(target).
2. If only one argument was passed, return to.
3. Let sources be the List of argument values starting with the second argument.
4. For each element nextSource of sources, in ascending index order,
	1. If nextSource is undefined or null, let keys be a new empty List.
	2. Else,
		i. Let from be ToObject(nextSource).
		ii. Let keys be ? from.[[OwnPropertyKeys]]&nbsp;().
	3. Repeat for each element nextKey of keys in List order,
		i. Let desc be ? from.[[GetOwnProperty]]&nbsp;(nextKey).
		ii. If desc is not undefined and desc.[[Enumerable]] is true, then
		1. Let propValue be ? Get(from, nextKey).
		2. Perform ? Set(to, nextKey, propValue, true).
5. Return to.

assign 的 length 属性为 2。

#### 19.1.2.2 Object.create ( target, ...sources )

create 方法创建一个包含特定原型属性的全新对象，create 方法调用时，执行以下步骤：

1. If Type(O) is neither Object nor Null, throw a TypeError exception.
2. Let obj be ObjectCreate(O).
3. If Properties is not undefined, then
	1. Return ? ObjectDefineProperties(obj, Properties).
4. Return obj.

#### 19.1.2.3 Object.defineProperties ( O, Properties )

defineProperties 函数用于给对象添加新的属性或者更新已存在的属性。当 defineProperties 方法调用的时候，执行以下步骤：

1. Return ? ObjectDefineProperties(O, Properties).

##### 19.1.2.3.1 执行中语义 ObjectDefineProperties ( O, Properties )

有 O 和 Properties 两个参数的抽象方法 ObjectDefineProperties 调用时，执行以下步骤：

1. If Type(O) is not Object, throw a TypeError exception.
2. Let props be ? ToObject(Properties).
3. Let keys be ? props.[[OwnPropertyKeys]]&nbsp;().
4. Let descriptors be a new empty List.
5. Repeat for each element nextKey of keys in List order,
	1. Let propDesc be ? props.[[GetOwnProperty]]&nbsp;(nextKey).
	2. If propDesc is not undefined and propDesc.[[Enumerable]] is true, then
		1. Let descObj be ? Get(props, nextKey).
		2. Let desc be ? ToPropertyDescriptor(descObj).
		3. Append the pair (a two element List) consisting of nextKey and desc to the end of descriptors.
6. For each pair from descriptors in list order,
	1. Let P be the first element of pair.
	2. Let desc be the second element of pair.
	3. Perform ? DefinePropertyOrThrow(O, P, desc).
7. Return O.

#### 19.1.2.4 Object.defineProperty ( O, P, Attributes )

defineProperties 函数用于给对象添加一个新的属性或者更新一个已存在的属性。当 defineProperties 方法调用的时候，执行以下步骤：

1. If Type(O) is not Object, throw a TypeError exception.
2. Let key be ? ToPropertyKey(P).
3. Let desc be ? ToPropertyDescriptor(Attributes).
4. Perform ? DefinePropertyOrThrow(O, key, desc).
5. Return O.

#### 19.1.2.5 Object.freeze ( O )

freeze 方法调用时，执行以下步骤：

1. If Type(O) is not Object, return O.
2. Let status be ? SetIntegrityLevel(O, "frozen").
3. If status is false, throw a TypeError exception.
4. Return O.

#### 19.1.2.6 Object.getOwnPropertyDescriptor ( O, P )
getOwnPropertyDescriptor 方法调用时，执行以下步骤：

1. Let obj be ? ToObject(O).
2. Let key be ? ToPropertyKey(P).
3. Let desc be ? obj.[[GetOwnProperty]]&nbsp;(key).
4. Return FromPropertyDescriptor(desc).

#### 19.1.2.7 Object.getOwnPropertyNames ( O )
getOwnPropertyNames 方法调用时，执行以下步骤
1. Return ? GetOwnPropertyKeys(O, String).

#### 19.1.2.8 Object.getOwnPropertySymbols ( O )
getOwnPropertySymbols 方法调用且有参数 O 时，执行以下步骤：

1. Return ? GetOwnPropertyKeys(O, Symbol).

##### 19.1.2.8.1 执行中语义: GetOwnPropertyKeys ( O, Type )
抽象方法 GetOwnPropertyKeys 被调用，且参数为对象类型的 O 和字符串或是符号类型的 Type 时，执行以下步骤：

1. Let obj be ? ToObject(O).
2. Let keys be ? obj.[[OwnPropertyKeys]]&nbsp;().
3. Let nameList be a new empty List.
4. Repeat for each element nextKey of keys in List order,
	1. If Type(nextKey) is Type, then
		1. Append nextKey as the last element of nameList.
5. Return CreateArrayFromList(nameList).

#### 19.1.2.9 Object.getPrototypeOf ( O )
getPrototypeOf 方法调用且有参数 O 时，执行以下步骤：

1. Let obj be ? ToObject(O).
2. Return ? obj.[[GetPrototypeOf]]&nbsp;().

#### 19.1.2.10 Object.is ( value1, value2 )
is 方法调用且有参数 value1 和 value2 时，执行以下步骤：

1. Return SameValue(value1, value2).

#### 19.1.2.11 Object.isExtensible ( O )
isExtensibl 方法调用且有参数 O 时，执行以下步骤：

1. If Type(O) is not Object, return false.
2. Return ? IsExtensible(O).

#### 19.1.2.12 Object.isFrozen ( O )
isFrozen 方法调用且有参数 O 时，执行以下步骤：

1. If Type(O) is not Object, return true.
2. Return ? TestIntegrityLevel(O, "frozen").

#### 19.1.2.13 Object.isSealed ( O )
isSealed 方法调用且有参数 O 时，执行以下步骤：

1. If Type(O) is not Object, return true.
2. Return ? TestIntegrityLevel(O, "sealed").

#### 19.1.2.14 Object.keys ( O )
keys 方法调用且有参数 O 时，执行以下步骤：

1. Let obj be ? ToObject(O).
2. Let nameList be ? EnumerableOwnNames(obj).
3. Return CreateArrayFromList(nameList).

If an implementation defines a specific order of enumeration for the for-in statement, the same order must be used for the elements of the array returned in step 3.

#### 19.1.2.15 Object.preventExtensions ( O )
preventExtensions 方法调用时，执行以下步骤：
1. If Type(O) is not Object, return O.
2. Let status be ? O.[[PreventExtensions]]&nbsp;().
3. If status is false, throw a TypeError exception.
4. Return O.

#### 19.1.2.16 Object.prototype
Object.prototype 的初始值是内置对象 %ObjectPrototype%.

该原型的特性如下 { [[Writable]]: false, [[Enumerable]]: false, [[Configurable]]: false }.

#### 19.1.2.17 Object.seal ( O )
seal 方法调用时，执行以下步骤：

1. If Type(O) is not Object, return O.
2. Let status be ? SetIntegrityLevel(O, "sealed").
3. If status is false, throw a TypeError exception.
4. Return O.

#### 19.1.2.18 Object.setPrototypeOf ( O, proto )
When the setPrototypeOf 方法调用且有参数 O 和 proto 时，执行以下步骤：

1. Let O be ? RequireObjectCoercible(O).
2. If Type(proto) is neither Object nor Null, throw a TypeError  exception.
3. If Type(O) is not Object, return O.
4. Let status be ? O.[[SetPrototypeOf]]&nbsp;(proto).
5. If status is false, throw a TypeError exception.
6. Return O.

### 19.1.3 标准对象的原型属性

标准对象的原型是 %ObjectPrototype% 固有对象，它是一个不可变更的异常对象。它的 [[prototype]] 为 null 且初始的 [[Extensible]] 内置值为 true。

#### 19.1.3.1 Object.prototype.constructor
Object.prototype.constructor 也就是内置对象 %Object%。

#### 19.1.3.2 Object.prototype.hasOwnProperty ( V )
hasOwnProperty 方法调用且有参数 V 时，执行以下步骤：

1. Let P be ? ToPropertyKey(V).
2. Let O be ? ToObject(this value).
3. Return ? HasOwnProperty(O, P).

* 注意，步骤 1 2 的顺序是为了确保任何步骤 1 抛出的异常情况都不影响步骤执行，比如说 this 值为 undefined 或 null，兼容了以前版本中的内容。

#### 19.1.3.3 Object.prototype.isPrototypeOf ( V )
isPrototypeOf 方法调用且有参数 V 时，执行以下步骤：

1. If Type(V) is not Object, return false.
2. Let O be ? ToObject(this value).
3. Repeat
	1. Let V be ? V.[[GetPrototypeOf]]&nbsp;().
	2. If V is null, return false.
	3. If SameValue(O, V) is true, return true.

* 注意，步骤 1 2 的顺序是为了保证即使 V 不是对象且其 this 值为 undefined or null，步骤也可以照常运行，兼容了以前版本规范中的内容。

#### 19.1.3.4 Object.prototype.propertyIsEnumerable ( V )
propertyIsEnumerable 方法调用且有参数 V 时，执行以下步骤：

1. Let P be ? ToPropertyKey(V).
2. Let O be ? ToObject(this value).
3. Let desc be ? O.[[GetOwnProperty]]&nbsp;(P).
4. If desc is undefined, return false.
5. Return the value of desc.[[Enumerable]].

* 注意，本方法不考虑原型链。

* 注意，步骤 1 2 的顺序是为了确保任何步骤 1 抛出的异常情况都不影响步骤执行，比如说 this 值为 undefined 或 null，兼容了以前版本中的内容。

#### 19.1.3.5 Object.prototype.toLocaleString ( [ reserved1 [ , reserved2 ] ] )
toLocaleString 方法调用时，执行以下步骤：

1. Let O be the this value.
2. Return ? Invoke(O, "toString").

可选参数暂时未使用，打算用它来与 ECMA-402 中的 toLocalString 保持一致。本特性的实现若不依赖 ECMA-402 的支持，就不得使用这些可选参数作为其他用途。

The optional parameters to this function are not used but are intended to correspond to the parameter pattern used by ECMA-402 toLocalString functions. Implementations that do not include ECMA-402 support must not use those parameter positions for other purposes.

* 注意，本方法提供一个个通用的 toLocaleString 实现，用以给 toString 添加本地化行为。Array Number Date 和  Typed Arrays 会提供它们自己的一些 toLocaleString 方法。

* 注意，ECMA-402 有意不为本规范的实现提供可选项。

#### 19.1.3.6Object.prototype.toString ( )

toString 方法调用时，执行以下步骤：

1. If the this value is undefined, return "[object Undefined]".
2. If the this value is null, return "[object Null]".
3. Let O be ToObject(this value).
4. Let isArray be ? IsArray(O).
5. If isArray is true, let builtinTag be "Array".
6. Else, if O is an exotic String object, let builtinTag be "String".
7. Else, if O has an [[ParameterMap]] internal slot, let builtinTag be "Arguments".
8. Else, if O has a [[Call]] internal method, let builtinTag be "Function".
9. Else, if O has an [[ErrorData]] internal slot, let builtinTag be "Error".
10. Else, if O has a [[BooleanData]] internal slot, let builtinTag be "Boolean".
11. Else, if O has a [[NumberData]] internal slot, let builtinTag be "Number".
12. Else, if O has a [[DateValue]] internal slot, let builtinTag be "Date".
13. Else, if O has a [[RegExpMatcher]] internal slot, let builtinTag be "RegExp".
14. Else, let builtinTag be "Object".
15. Let tag be ? Get(O, @@toStringTag).
16. If Type(tag) is not String, let tag be builtinTag.
17. Return the String that is the result of concatenating "[object ", tag, and "]".

该方法是 %ObjProto_toString% 固有对象。

* 注意，在之前的版本中，该方法有时会用来访问 [[class]] 内部特性的字符串值。在有些内置对象中，有时它只是形如虚设。上面的定义保留了用 toString 来测试一些特定的内置对象。它并不提供一个可靠的测试特定对象的方法，所以它不能测试其它的内置对象抑或是程序生成的对象的类型。除此之外，程序可以利用 @@toStringTag 使得测试特定内置对象的类型无效。

#### 19.1.3.7 Object.prototype.valueOf ( )

valueOf 方法调用时，执行以下步骤：

1. Return ? ToObject(this value).

该方法是 %ObjProto_valueOf% 固有对象。

### 19.1.4 对象实例的属性

除了对象原型外，对象实例不包含任何特定属性。



# ECMA-262 7ᵗʰ Edition 第 20 章

> 本文转载自：[众成翻译](http://www.zcfy.cc)
> 译者：[QAQMiao](http://www.zcfy.cc/@QAQMiao)
> 链接：[http://www.zcfy.cc/article/1401](http://www.zcfy.cc/article/1401)
> 原文：[http://www.ecma-international.org/ecma-262/7.0/#sec-numbers-and-dates](http://www.ecma-international.org/ecma-262/7.0/#sec-numbers-and-dates)

# 20 Number 和 Date
---
## 20.1 Number 对象

### 20.1.1 Number 构造函数

Number 构造函数是 %Number% 的内部对象也是[全局对象](http://www.ecma-international.org/ecma-262/7.0/#global-object)中 `Number` 属性的初始值。当作为构造函数被调用时，它会创建并初始化一个新的 Number 对象。当作为函数被调用时，它会执行类型转换。

`Number` 构造函数被设计成可继承的，可以将其复制给继承类。想要继承 `Number` 行为的子类构造函数为了创建和初始化带有内置 [[NumberData]] 的子类实例中必须包含一个 `super` 调用 `Number` 构造函数。

#### 20.1.1.1 Number( <var>value</var> )

当调用 `Number` 传递了一个 *number* 参数时，会执行以下步骤：

1. 如果函数调用没有传参，则设置 n 为 +0。
2. 否则令 n 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/#sec-tonumber)(*value*)。
3. 如果结果为 undefined，返回 n。
4. 初始化 O = [OrdinaryCreateFromConstructor](http://www.ecma-international.org/ecma-262/7.0/#sec-ordinarycreatefromconstructor)(n, `"%NumberPrototype%"`, « [[NumberData]] »)。
5. 设置 O 的内置 [[NumberData]] 的值为 n。
6. 返回 O。

### 20.1.2 Number构造函数的属性

Number 构造函数的内部 [[Prototype]] 的值为内部对象 [%FunctionPrototype%](http://www.ecma-international.org/ecma-262/7.0/#sec-properties-of-the-function-prototype-object)。

Number 构造函数有以下属性：

#### 20.1.2.1 Number.EPSILON

Number.EPSILON 表示的是比 1 大的最小的数与 1 的差的数值，大约为 2.2204460492503130808472633361816 x 10<sup>-16</sup>。

这个属性的特性为 { [[Writable]]: false, [[Enumerable]]:false, [[Configurable]]:false }。

#### 20.1.2.2 Number.isFinite ( <var>number</var> )

当调用 `Number.isFinite` 传递了一个 *number* 参数时，会执行以下步骤：

1. 如果 [Type](http://www.ecma-international.org/ecma-262/7.0/#sec-ecmascript-data-types-and-values)(number) 的结果不是 Number 类型，返回 false。
2. 如果 number 的值为 NaN，+∞，或是 -∞，返回 false。
3. 其他情况返回 true。

#### 20.1.2.3 Number.isInteger ( <var>number</var> )

当调用 `Number.isFinite` 传递了一个 *number* 参数时，会执行以下步骤：

1. 如果 [Type](http://www.ecma-international.org/ecma-262/7.0/#sec-ecmascript-data-types-and-values)(number) 的结果不是 Number 类型，返回 false。
2. 如果 number 的值为 NaN，+∞，或是 -∞，返回 false。
3. 初始化 integer 为 [ToInteger](http://www.ecma-international.org/ecma-262/7.0/#sec-tointeger)(number)。
4. 如果 integer 不等于 number，返回 false。
5. 其他情况返回 true。

#### 20.1.2.4 Number.isNaN ( <var>number</var> )

当调用 `Number.isNaN` 传递了一个 *number* 参数时，会执行以下步骤：

1. 如果 [Type](http://www.ecma-international.org/ecma-262/7.0/#sec-ecmascript-data-types-and-values)(number) 的结果不是 Number 类型，返回 false。
2. 如果 number 的值为 NaN，返回 true。
3. 其他情况返回 false。

注
这个函数与全局函数 isNaN [18.2.3](http://www.ecma-international.org/ecma-262/7.0/#sec-isnan-number) 是不同的。isNaN 在确定当前参数是否是 NaN 之前不会对其进行转换。

#### 20.1.2.5 Number.isSafeInteger ( <var>number</var> )

当调用 `Number.isSafeInteger` 传递了一个 *number* 参数时，会执行以下步骤：

1.  如果 [Type](http://www.ecma-international.org/ecma-262/7.0/#sec-ecmascript-data-types-and-values)(number) 的结果不是 Number 类型，返回 false。
2. 如果 number 的值为 NaN，+∞，或是 -∞，返回 false。
3. 初始化 integer 为 [ToInteger](http://www.ecma-international.org/ecma-262/7.0/#sec-tointeger)(number)。
4. 如果 integer 不等于 number，返回 false。
5. 如果 [abs](http://www.ecma-international.org/ecma-262/7.0/#sec-algorithm-conventions)(integer) ≤ 2<sup>53</sup> - 1，返回 true。
6. 其他情况返回 false。

#### 20.1.2.6 Number.MAX_SAFE_INTEGER

注
`Number.MAX_SAFE_INTEGER` 的值是 Number 类型最大值 - 1。

Number.MAX_SAFE_INTEGER 的值等于 9007199254740991 (2<sup>53</sup> - 1)。

这个属性的特性为 { [[Writable]]: false, [[Enumerable]]: false, [[Configurable]]: false }。

#### 20.1.2.7 Number.MAX_VALUE

`Number.MAX_VALUE` 的值代表最大的正数，约为 1.7976931348623157 × 10<sup>308</sup>。

这个属性的特性为 { [[Writable]]: false, [[Enumerable]]: false, [[Configurable]]: false }。

#### 20.1.2.8 Number.MIN_SAFE_INTEGER

注
`Number.MIN_SAFE_INTEGER` 的值是 Number 类型最小值 + 1。

Number.MIN_SAFE_INTEGER 的值等于 -9007199254740991 (-(2<sup>53</sup>-1))。

这个属性的特性为 { [[Writable]]: false, [[Enumerable]]: false, [[Configurable]]: false }。

#### 20.1.2.9 Number.MIN_VALUE

`Number.MIN_VALUE` 代表最小的正数，约为5 × 10<sup>-324</sup>。

在 IEEE 754-2008 双精度二进制表示法中，最小的可取值为非规格化数。如果一个实现中不支持非规格化值，那 `Number.MIN_VALUE` 的值应为最小的非零正数，实际以实现为准。

这个属性的特性为 { [[Writable]]: false, [[Enumerable]]: false, [[Configurable]]: false }。

#### 20.1.2.10 Number.NaN

`Number.NaN` 的值为 NaN。

这个属性的特性为 { [[Writable]]: false, [[Enumerable]]: false, [[Configurable]]: false }。

#### 20.1.2.11 Number.NEGATIVE_INFINITY

Number.NEGATIVE_INFINITY 的值为 -∞。

这个属性的特性为 { [[Writable]]: false, [[Enumerable]]: false, [[Configurable]]: false }。

#### 20.1.2.12 Number.parseFloat ( <var>string</var> )

`Number.parseFloat` 数据属性的值与[全局对象](http://www.ecma-international.org/ecma-262/7.0/index.html#global-object)的内置函数 `parseFloat` 属性的值是相同的，其定义位于 18.2.4。

#### 20.1.2.13 Number.parseInt ( <var>string</var>, <var>radix</var> )

`Number.parseInt` 数据属性的值与[全局对象](http://www.ecma-international.org/ecma-262/7.0/index.html#global-object)的内置函数 `parseInt` 属性的值是相同的，其定义位于 18.2.5。

#### 20.1.2.14 Number.POSITIVE_INFINITY

Number.POSITIVE_INFINITY 的值为 +∞。

这个属性的特性为 { [[Writable]]: false, [[Enumerable]]: false, [[Configurable]]: false }。

#### 20.1.2.15 Number.prototype

`Number.prototype` 的初始值为内部对象 [%NumberPrototype%](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-number-prototype-object)

这个属性的特性为 { [[Writable]]: false, [[Enumerable]]: false, [[Configurable]]: false }。

### 20.1.3 Number 原型对象的属性

Number 原型对象就是内部对象 %NumberPrototype%。Number 原型对象是一个普通对象。Number 原型本身是一个 Number 对象；它有一个值为 +0 的内置 [[NumberData]]。

Number 原型对象的内置 [[Prototype]] 的值为内部对象 [%ObjectPrototype%](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-object-prototype-object)。

除非另有明确说明，以下定义的 Number 原型对象均为非通用的，传递给它们的 this 值必须为一个 Number 值或者一个内置 [[NumberData]] 已经初始化为 Number 值的对象。

抽象操作 thisNumberValue(value) 执行以下步骤：

1. 如果 [Type](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-ecmascript-data-types-and-values)(value) 为 Number，返回 value。
2. 如果 [Type](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-ecmascript-data-types-and-values)(value) 为对象，并且 value 有内置 [[NumberData]]，则
    1. 断言： value 的内置 [[NumberData]] 是 Number 类型值。
    2. 返回： value 的内置 [[NumberData]]。
3. 抛出 TypeError 异常。


在规范的方法中，短语 "this Number value"指的是通过将 this 的值作为参数传递来调用抽象操作 thisNumberValue 返回相应的值。

#### 20.1.3.1 Number.prototype.constructor

`Number.prototype.constructor` 的初始值为内部对象 [%Number%](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-number-constructor)。

#### 20.1.3.2 Number.prototype.toExponential ( <var>fractionDigits</var> )

返回一个科学计数法表示的代表 this 数字值的字符串，它的有效数字的小数点前有一个数字，有效数字的小数点后有 fractionDigits 个数字。如果 fractionDigits 是 undefined，包括指定唯一数字值需要的尽可能多的有效数字（就像 [ToString](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tostring)，但在这里总是以科学计数法输出）。具体来说执行以下步骤：

1. 令 x 等于 thisNumberValue(this value)。
2. 令 f 等于 [ToInteger](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tointeger)(fractionDigits)。
3. 断言： 当 fractionDigits 为 undefined 时，f 为 0。
4. 如果 x 是 NaN, 返回字符串 `"NaN"`。
5. 令 s 为空字符串。
6. 如果 x < 0,则
    1. 令 s 为 `"-"`。
    2. 令 x 为 -x。
7. 如果 x = +∞，则
    1. 返回拼接字符串 s 和 "Infinity" 后的结果。
8. 如果 f < 0 或者 f > 20，抛出一个 RangeError 的异常。然而实现被允许扩展 `toExponential` 对于 f 的值小于0或者大于20时的行为。在这种情况下，`toExponential` 不再必须抛出 RangeError 的异常。
9. 如果 x = 0，则
    1. 令 m 为由 f + 1 个码元 0x0030（数字0）所组成的字符串。
    2. 令 e 等于 0。
10. 如果 x ≠ 0，
    1. 如果 fractionDigits 不是 undefined，则
        1. 令 e 和 n 为整数，使得满足 10<sup>f</sup> ≤ n < 10<sup>f+1</sup> 且 n × 10<sup>e–f</sup> – x 的准确数值尽可能接近零。如果 e 和 n 有两个这样的组合，选择使 n × 10<sup>e–f</sup> 更大的组合。
    2. 如果  fractionDigits 是 undefined
        1. 令 e, n, 和 f 为整数，使得满足 f ≥ 0 且 10<sup>f</sup>≤ n < 10<sup>f+1</sup>, n × 10<sup>e–f</sup> 的数值等于 x, 且 f 的值尽可能小。需要注意的是，n 的十进制表示有 f + 1 个数字，n 不能被 10 整除，并且 n 的最少有效位数未必由这些条件唯一确定。
    3. 令 m 等于 n 的十进制表示的字符串（没有前导零）。
11.  如果 f ≠ 0，则
    1. 另 a 为 m 中的第一个元素，b 为 m 中剩下的 f 个元素。
    2. 令 m 等于 a，`"."`，b 三个字符串的拼接。
12. 如果 e = 0，则
    1. 令 c = `"+"`。
    2. 令 d = `"0"`。
13. 否则，
    1. 如果 e > 0，令 c 等于 `"+"`。
    2. 如果 e ≤ 0，
        1.  令 c 等于 `"-"`。
        2.  令 e 等于 -e。
    3. 令 d 等于 e 的十进制表示的字符串（没有前导零）。
14. 令 m 等于 m，`"e"`，c，d 四个字符串的拼接。

如果调用 `toExponential` 方法时多于一个参数，则该行为未定义（详见规范[17](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-ecmascript-standard-built-in-objects)）。

注
对于需要提供比上述规则更准确转换的实现，建议用以下算法作为指引替代步骤 10.2.1：

1. 令 e, n, 和 f 为整数，使得满足 f ≥ 0, 10<sup>f</sup>≤ n < 10<sup>f+1</sup>, n × 10<sup>e–f</sup> 的数值等于 x，且 f 的值尽可能小。如果这样的 n 值可能多个，选择使 n × 10<sup>e–f</sup> 的值尽可能接近 x 的 n 值。如果有两个这样的 n 值，则选择偶数。

#### 20.1.3.3 Number.prototype.toFixed ( <var>fractionDigits</var> )

注 1
`tiFixed` 返回一个包含了 -- 代表 this 数字值的留有小数点后 fractionDigits 个数字的十进制固定小数点记法 -- 的字符串。如果 fractionDigits 是 undefined，就认为是 0。

执行以下步骤：

1. 令 x 等于 thisNumberValue(this value)。
2. 令 f 等于 [ToInteger](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tointeger)(fractionDigits)。（如果 fractionDigits 是 undefined，这步产生的值为 0）。
3. 如果 f < 0 或 f > 20, 抛出一个 RangeError 异常。不过允许实现去扩展 `toFixed` 的值使 f 小于 0 或者是大于 20。在这种情况下，`toFixed` 不必在此时抛出 RangeError 异常。
4. 如果 x 是 NaN，返回字符串 `"NaN"`。
5. 令 s 为空字符串。
6. 如果 x < 0，则
    1. 令 s 为 "-"。
    2. 令 x = –x。
7. 如果 x ≥ 10<sup>21</sup>，则
    1. 令 m = [ToString](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tostring)(x)。
8. 如果 x < 10<sup>21</sup>，
    1. 令 n 为一个整数，让 n ÷ 10<sup>f</sup> – x 准确的数学值尽可能接近零。如果有两个这样 n 值，选择较大的 n。
    2. 如果 n = 0，令 m 为字符串 "0"。否则，令 m 等于 n 的十进制表示的字符串（为了没有前导零）。
    3. 如果 f ≠ 0，则
        1. 令 k 等于 m 里的字符个数。
        2. 如果 k ≤ f，则
            1. 令 z 等于 f+1–k 个码元 0x0030（数字0）组成的字符串。
            2. 令 m 等于字符串 z 和 m 的拼接。
            3. 令 k 等于 f + 1。
        3. 令 a 等于 m 的前 k–f 个字符，令 b 为其余 f 个字符。
        4. 令 m 等于 a，`"."`，b 三个字符串的拼接。
9. 返回字符串 s 和 m 的拼接。


如果调用 `toFixed` 方法时传递了多于一个参数，这种行为是未定义的（详见规范[17](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-ecmascript-standard-built-in-objects)）

注 2
对于某些值，toFixed 的输出可比 toString 的更精确，因为 toString 只打印区分相邻数字值的足够的有效数字。例如，

 `(1000000000000000128).toString()` 返回 `"1000000000000000100"`，

 而 `(1000000000000000128).toFixed(0)` 返回 `"1000000000000000128"`。

#### 20.1.3.4 Number.prototype.toLocaleString ( [ <var>reserved1</var> [, <var>reserved2</var> ] ])

一个包含 ECMA-402 国际化 API 的 ECMAScript 实现必须要按照 ECMA-402 规范中的定义进行实现 `Number.prototype.toLocaleString`，如果这个 ECMAScript 实现没有包含 ECMA-402 API，那么接下来的规范适用于 `toLocaleString`。

根据宿主环境的当前语言环境惯例来格式化当前 Number 值，生成代表这个值的字符串。此函数是依赖于实现的，允许但不鼓励它的返回值与 toString 相同。

这个方法可选参数的意义被定义在 ECMA-402 规范中。实现如果没有包含 ECMA-402 支持，应当不使用此参数做任何用途。

#### 20.1.3.5 Number.prototype.toPrecision ( <var>precision</var> )

返回一个包含当前 Number 值的科学计数法（有效数字的小数点前有一个数字，有效数字的小数点后有 precision-1 个数字）或十进制固定计数法（precision 个有效数字）的字符串。如果 precision 是 undefined，调用 [ToString](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tostring) 代替。具体执行以下步骤:

1. 令 x 等于 thisNumberValue(this value)。
2. 如果 precision 为 undefined，返回 [ToString](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tostring)(x)。
3. 令 p 等于 [ToInteger](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tointeger)(precision)。
4. 如果 x 为 NaN，返回字符串 `"NaN"`。
5. 令 s 为空字符串。
6. 如果 x < 0，则
    1. 令 s 等于 码元 0x002D（连字符暨减号）
    2. 令 x 等于 -x。
7. 如果 x = +∞，则
    1. 返回 s 和 `"Infinity"` 拼接的字符串。
8. 如果 p < 1 或者 p > 21，抛出 RangeError 异常。不过允许实现扩展 `toPrecision` 的行为使 p 小于1或是大于21。在这种情况下，`toPrecision` 不必抛出 RangeError 异常。
9. 如果 x = 0，则
    1. 令 m 等于 p 个 码元 0x0030（数字 0）拼接的字符串。
    2. 令 e 等于 0。
10 如果 x ≠ 0，
    1. 令 e 和 n 为整数，并且满足 10<sup>p–1</sup> ≤ n < 10<sup>p</sup> 且 n × 10<sup>e–p+1</sup> – x 的值尽可能的接近0。如果有两个这样 e 和 n 的集合，选择 n × 10<sup>e–p+1</sup> 的值更大的那组。
    2. 令 m 等于 n 的十进制表示的字符串（没有前导零）
    3. 如果 e < -6 或者 e ≥ p，则
        1. 断言： e ≠ 0。
        2. 令 a 等于 m 的第一个字符，令 b 等于剩下的 p - 1 个字符。
        3. 令 m 等于 a，`"."`，b 三个字符串的拼接。
        4. 如果 e > 0，则
            1. 令 c 等于码元 0x002B（加号）。
        5. 如果 e < 0，
            1. 令 c 等于码元 0x002D（连字符暨减号）。
            2. 令 e 等于 -e。
        6. 令 d 等于 e 的十进制表示的字符串（没有前导零）。
        7. 返回 s，m，码元0x0065（小写拉丁字母 E），c，d五个字符串的拼接。
11. 如果 e = p - 1，返回字符串 s 和 m 的拼接。
12. 如果 e ≥ 0，则
    1. 令 m 等于 m 的前 e+1 个字符， 码元0x002E（字符 ‘.’）, m 的其余 p– (e+1) 个字符拼接的结果。
13. 如果 e ＜ 0，
    1. 令 m 等于码元 0x0030（数字 0），码元0x002E（字符 ‘.’）,-(e + 1)个码元 0x0030（数字 0），字符串 m 的拼接。
14. 返回字符串 s 和 m 的拼接。

`toPrecision` 方法调用时传递多于一个参数，这种行为是未定义的（详见规范[17](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-ecmascript-standard-built-in-objects)）

#### 20.1.3.6 Number.prototype.toString ( [ <var>radix</var> ] )

注
可选参数 radix 应当为 2 - 36 之间的一个整数值。如果没有给出 radix 或者其为 undefined，则使用数字 10 作为默认值。

将会执行以下步骤：

1. 令 x 等于 thisNumberValue（this value）。
2. 如果 radix 不存在，令 radixNumber 等于 10。
3. 否则如果 radix 为 undefined，令 radixNumber 等于 10。
4. 否则令 radixNumber 等于 [ToInteger](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tointeger)(radix)。
5. 如果 radixNumber < 2 或者 radixNumber > 36，抛出 RangeError 异常。
6. 如果 radixNumber = 10，返回 [ToString](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tostring)(x)。
7. 根据 radixNumber 的值返回当前数值特定进制的字符串表示。字母 'a'-'z' 用来代表 10 到 35。算法的精确度依赖于实现，算法应当是[7.1.12.1](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tostring-applied-to-the-number-type)中指定的实现。

`toString` 函数是不通用的，如果 this 值不是 Number 或者 Number 对象，他就会抛出 TypeError 异常。因此，它不能作为一个转移到其他对象上的方法。

`toString` 方法的 `length` 属性等于 1。

#### 20.1.3.7Number.prototype.valueOf( )

1. 返回 thisNumberValue（this value）。

### 20.1.4 Number 实例的属性

Number 实例从 Number 原型对象继承属性，Number 实例还有一个 [[NumberData]] 内部属性。[[NumberData]] 存储着当前 Number 对象的 Number 值。

## 20.2 Math 对象

Math 对象是 %Math% 的内部对象以及[全局对象](http://www.ecma-international.org/ecma-262/7.0/index.html#global-object)的 `Math` 属性的初始值。Math 对象是一个独立普通对象。

Math 对象内置 [[Prototype]] 的值是内部对象 [%ObjectPrototype%](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-object-prototype-object)。

Math 对象不是一个函数对象。它没有 [[Construct]] 内置函数。在 `new` 操作符后使用 Math 对象作为构造器是不可以的。同时 Math 对象也没有内置的 [[Call]] 方法。没办法作为一个函数调用 Math 对象。

注
在本规范中，“x 的数值”在 [6.1.6](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-ecmascript-language-types-number-type)中有技术含义。

### 20.2.1 Math 对象的值属性

#### 20.2.1.1 Math.E

自然对数的底数 e 的数值，约为 2.7182818284590452354。

这个属性的特性为 { [[Writable]]: false, [[Enumerable]]: false, [[Configurable]]: false }。

#### 20.2.1.2 Math.LN10

10 的自然对数的数字值，约为 2.302585092994046。

这个属性的特性为 { [[Writable]]: false, [[Enumerable]]: false, [[Configurable]]: false }。

#### 20.2.1.3 Math.LN2

2 的自然对数的数字值，约为 0.6931471805599453。

这个属性的特性为 { [[Writable]]: false, [[Enumerable]]: false, [[Configurable]]: false }。

#### 20.2.1.4 Math.LOG10E

自然对数的底数 e 的以 10 为底数的对数的数字值；约为 0.4342944819032518。

这个属性的特性为 { [[Writable]]: false, [[Enumerable]]: false, [[Configurable]]: false }。

注
`Math.LOG10E` 的值约为 `Math.LN10` 值的倒数。

#### 20.2.1.5 Math.LOG2E

自然对数的底数 e 的以 2 为底数的对数的数字值；约为 1.4426950408889634。

这个属性的特性为 { [[Writable]]: false, [[Enumerable]]: false, [[Configurable]]: false }。

注
`Math.LOG2E` 的值约为 `Math.LN2` 值的倒数。

#### 20.2.1.6 Math.PI

圆的周长与直径之比π的数字值，约为 3.1415926535897932。

这个属性的特性为 { [[Writable]]: false, [[Enumerable]]: false, [[Configurable]]: false }。

#### 20.2.1.7 Math.SQRT1_2

½ 的平方根的数字值，约为 0.7071067811865476。

这个属性的特性为 { [[Writable]]: false, [[Enumerable]]: false, [[Configurable]]: false }。

注
`Math.SQRT1_2` 的值约为 `Math.SQRT2` 值的倒数。

#### 20.2.1.8 Math.SQRT2

2 的平方根的数字值，约为 1.4142135623730951。

这个属性的特性为 { [[Writable]]: false, [[Enumerable]]: false, [[Configurable]]: false }。

#### 20.2.1.9 Math [ @@toStringTag ]

@@toStringTag 属性的初始值为字符串 `"Math"`。

这个属性的特性为 { [[Writable]]: false, [[Enumerable]]: false, [[Configurable]]: true }。

### 20.2.2 Math 对象的函数属性

对以下 `Math` 对象函数的每个参数（如果有多个，以左到右的顺序）应用 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber) 抽象操作，然后对结果数字值执行计算。如果 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)返回[突然中止](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-completion-record-specification-type)，那么[中止记录](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-completion-record-specification-type)将被马上返回。否则，函数对结果数值执行计算。每个函数返回的值都是一个 Number。

在下面的函数描述中，符号 NaN，-0，+0，-∞，以及 +∞ 都指的是 [6.1.6](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-ecmascript-language-types-number-type) 中描述的数值。

注
这里没有精确规定函数 acos，asin，atan，atan2，cos，exp，logpow，sin，sqrt 的行为，除了需要特别说明对边界情况某些参数值的结果之外。对其他参数值，这些函数旨在计算计算常见数学函数的结果，但选择的近似算法中的某些范围是被允许的。这样做的目的是为了实现人员可以在给定的硬件平台上为 ECMAScript 与 C 语言程序员使用相同的数学库。

尽管实现拥有算法的选择权，但是推荐（不是本标准中指定）实现使用 `fdlibm` 中包含的 IEEE 754-2008 算法来作为近似算法，由 Sun Microsystems([http://www.netlib.org/fdlibm](http://www.netlib.org/fdlibm))免费提供。

#### 20.2.2.1 Math.abs ( <var>x</var> )

返回 x 的绝对值，返回结果大小与 x 相同，但是有正数标记。

* 如果 x 是 NaN，返回结果是 NaN。
* 如果 x 是 -0，返回结果是 +0。
* 如果 x 是 -∞，返回结果是 +∞。

#### 20.2.2.2 Math.acos ( <var>x</var> )

返回 x 的反余弦的依赖实现的近似值。结果以弧度形式表示，范围是 +0 到 +π。

*   如果 x 是 NaN，返回结果是 NaN。
*   如果 x 大于 1，返回结果是 NaN。
*   如果 x 小于 −1，返回结果是 NaN。
*   如果 x 是 1，返回结果是 +0。

#### 20.2.2.3Math.acosh ( <var>x</var> )

返回 x 的反双曲余弦的依赖实现的近似值。

* 如果 x 是 NaN，返回结果是 NaN。
* 如果 x 小于 1，返回结果是 NaN。
* 如果 x 是 1，返回结果是 +0。
* 如果 x 是 +∞，返回结果是 +∞。

#### 20.2.2.4 Math.asin ( <var>x</var> )

返回 x 的反正弦的依赖实现的近似值。结果以弧度形式表示，范围是−π/2 到 +π/2。

*   如果 x 是 NaN，返回结果是 NaN。
*   如果 x 大于 1，返回结果是 NaN。
*   如果 x 小于 –1，返回结果是 NaN。
*   如果 x 是 +0，返回结果是 +0。
*   如果 x 是 −0，返回结果是 −0。

#### 20.2.2.5 Math.asinh ( <var>x</var> )

返回 x 的反双曲正弦的依赖实现近似值。

* 如果 x 是 NaN，返回结果是 NaN。
* 如果 x 是 +0，返回结果是 +0。
* 如果 x 是 -0，返回结果是 -0。
* 如果 x 是 +∞，返回结果是 +∞。
* 如果 x 是 -∞，返回结果是 -∞。

### 20.2.2.6 Math.atan ( <var>x</var> )

返回 x 的反正切的依赖实现的近似值。结果以弧度形式表示，范围是−π/2 到 +π/2。

*   如果 x 是 NaN，返回结果是 NaN。
*   如果 x 是 +0，返回结果是 +0。
*   如果 x 是 −0，返回结果是 −0。
*   如果 x 是 +∞，返回结果是 一个依赖于实现的近似值 +π/2。
*   如果 x 是 −∞，返回结果是 一个依赖于实现的近似值 −π/2。

#### 20.2.2.7 Math.atanh ( <var>x</var> )

返回 x 的反双曲正切的依赖实现的近似值。

* 如果 x 是 NaN，返回结果是 NaN。
* 如果 x 小于 -1，返回结果是 NaN。
* 如果 x 大于 1，返回结果是 NaN。
* 如果 x 是 -1，返回结果是 -∞。
* 如果 x 是 +1，返回结果是 +∞。
* 如果 x 是 +0，返回结果是 +0。
* 如果 x 是 -0，返回结果是 -0。

#### 20.2.2.8 Math.atan2 ( <var>y</var>, <var>x</var> )

返回 -- 参数 y 和 x 的商 y/x-- 的反正切的依赖实现的近似值，y 和 x 的符号用于确定返回值的象限。注：命名为 y 的参数为第一个，命名为 x 的参数为第二个，这是有意，是反正切函数俩参数的惯例。结果以弧度形式表示，范围是−π到 +π。

*   如果 x 和 y 至少一个是 NaN，返回结果是 NaN。
*   如果 y>0 且 x 是 +0，返回结果是一个依赖于实现的近似值 +π/2。
*   如果 y>0 且 x 是 −0，返回结果是一个依赖于实现的近似值 +π/2。
*   如果 y 是 +0 且 x>0，返回结果是 +0。
*   如果 y 是 +0 且 x 是 +0，返回结果是 +0。
*   如果 y 是 +0 且 x 是 −0，返回结果是一个依赖于实现的近似值 +π。
*   如果 y 是 +0 且 x < 0，返回结果是 一个依赖于实现的近似值 +π。
*   如果 y 是 −0 且 x > 0，返回结果是 −0。
*   如果 y 是 −0 且 x 是 +0，返回结果是 −0。
*   如果 y 是 −0 且 x 是 −0，返回结果是一个依赖于实现的近似值 −π。
*   如果 y 是 −0 且 x < 0，返回结果是一个依赖于实现的近似值 −π。
*   如果 y < 0 且 x 是 +0，返回结果是一个依赖于实现的近似值 −π/2。
*   如果 y < 0 且 x 是 −0，返回结果是一个依赖于实现的近似值 −π/2。
*   如果 y > 0 且 y 是有限的且 x 是 +∞，返回结果是 +0。
*   如果 y > 0 且 y 是有限的且 x 是 −∞，返回结果是一个依赖于实现的近似值 +π。
*   如果 y < 0 且 y 是有限的且 x 是 +∞，返回结果是 −0。
*   如果 y < 0 且 y 是有限的且 x 是 −∞，返回结果是一个依赖于实现的近似值 −π。
*   如果 y 是 +∞ 且 x 是有限的，返回结果是 返回结果是一个依赖于实现的近似值 +π/2。
*   如果 y 是 −∞ 且 x 是有限的，返回结果是 返回结果是一个依赖于实现的近似值 −π/2。
*   如果 y 是 +∞ 且 x 是 +∞，返回结果是一个依赖于实现的近似值 +π/4。
*   如果 y 是 +∞ 且 x 是 −∞，返回结果是一个依赖于实现的近似值 +3π/4。
*   如果 y 是 −∞ 且 x 是 +∞，返回结果是一个依赖于实现的近似值 −π/4。
*   如果 y 是 −∞ 且 x 是 −∞，返回结果是一个依赖于实现的近似值 −3π/4。


#### 20.2.2.9 Math.cbrt ( <var>x</var> )

返回 x 的立方根的依赖实现的近似值。

* 如果 x 是 NaN，返回结果是 NaN。
* 如果 x 是 +0，返回结果是 +0。
* 如果 x 是 -0，返回结果是 -0。
* 如果 x 是 +∞，返回结果是 +∞。
* 如果 x 是 -∞，返回结果是 -∞。

#### 20.2.2.10 Math.ceil ( <var>x</var> )

返回不小于 x 的且为数学整数的最小(接近 −∞)数字值。如果 x 已是整数，则返回 x。

*   如果 x 是 NaN，返回结果是 NaN。
*   如果 x 是 +0，返回结果是 +0。
*   如果 x 是 −0，返回结果是 −0。
*   如果 x 是 +∞，返回结果是 +∞。
*   如果 x 是 −∞，返回结果是 −∞。
*   如果 x 小于 0 但大于 -1，返回结果是 −0。

注
Math.ceil(x) 的值与 -Math.floor(-x) 的值相同。

#### 20.2.2.11 Math.clz32 ( <var>x</var> )

当调用 `Math.clz32` 传递了一个参数 x 时，执行以下步骤：

1. 令 n 等于 [ToUint32](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-touint32)(x)。
2. 令 p 等于 n 的 32 位二进制表示中前导 0 的位数。
3. 返回 p。

注
如果 n 等于 0，p 等于 32。如果 n 的 32 位二进制编码的最高位为 1，则 p 等于 0。

#### 20.2.2.12 Math.cos ( <var>x</var> )

返回 x 的余弦的依赖实现的近似值。参数被当做是弧度值。

*   如果 x 是 NaN，返回结果是 NaN。
*   如果 x 是 +0，返回结果是 1。
*   如果 x 是 −0，返回结果是 1。
*   如果 x 是 +∞，返回结果是 NaN。
*   如果 x 是 −∞，返回结果是 NaN。

#### 20.2.2.13 Math.cosh ( <var>x</var> )

返回 x 的双曲余弦的依赖实现的近似值。

* 如果 x 等于 NaN，返回结果是 NaN。
* 如果 x 等于 +0，返回结果是 1。
* 如果 x 等于 -0，返回结果是 1。
* 如果 x 等于 +∞，返回结果是 +∞。
* 如果 x 等于 -∞，返回结果是 +∞。

注
cosh(x) 的值等同于 *(exp(x) + exp(-x))/2*。

#### 20.2.2.14 Math.exp ( <var>x</var> )

返回 x 的指数的依赖实现的近似值（返回 e 的 x 次幂，e 代表自然对数的底数）。

*   如果 x 是 NaN，返回结果是 NaN。
*   如果 x 是 +0，返回结果是 1。
*   如果 x 是 −0，返回结果是 1。
*   如果 x 是 +∞，返回结果是 +∞。
*   如果 x 是 −∞，返回结果是 +0。

#### 20.2.2.15 Math.expm1 ( <var>x</var> )

返回 x 的指数减 1 的依赖实现的近似值（返回 e 的 x 次幂，e 代表自然对数的底数）。即使当 x 的值接近 0 的时候，计算的结果也是准确的。

* 如果 x 是 NaN，返回结果是 NaN。
* 如果 x 是 +0，返回结果是 +0。
* 如果 x 是 -0，返回结果是 -0。
* 如果 x 是 +∞，返回结果是 +∞。
* 如果 x 是 -∞，返回结果是 -1。

#### 20.2.2.16 Math.floor ( <var>x</var> )

返回不大于 x 的且为数学整数的最大(接近 +∞)数值。如果 x 已是整数，则返回 x。

*   如果 x 是 NaN，返回结果是 NaN。
*   如果 x 是 +0，返回结果是 +0。
*   如果 x 是 −0，返回结果是 −0。
*   如果 x 是 +∞，返回结果是 +∞。
*   如果 x 是 −∞，返回结果是 −∞。
*   如果 x 大于 0 但小于 1，返回结果是 +0。

注
Math.floor(x) 的值与 -Math.ceil(-x) 的值相同。

#### 20.2.2.17 Math.fround ( <var>x</var> )

当调用 `Math.fround` 传递了一个参数时，将执行以下步骤：

1. 如果 x 等于 NaN，返回 NaN。
2. 如果 x 等于 +0，-0，+∞，-∞ 其中之一时，返回 x。
3. 令 x32 等于用 roundTiesToEven 将 x 转换为 IEEE 754-2008 单精度形式的值。
4. 令 x64 等于将 x32 转换为 IEEE 754-2008 双精度形式的值。
5. 返回 ECMAScript 数值相应的 x64。

#### 20.2.2.18 Math.hypot ( <var>value1</var>, <var>value2</var>, ...<var>values</var> )

* 如果没有参数传递，返回结果是 +0。
* 如果其中某个参数为 +∞，返回结果是 +∞。
* 如果其中某个参数为 -∞，返回结果是 -∞。
* 如果没有参数为 +∞ 或 -∞，并且某个参数为 NaN，返回结果是 NaN。
* 如果所有的参数都是 +0 或者 -0，返回结果是 +0。

注
实现应当注意避免上溢出和下溢出所带来的精度损失，当函数调用时传递了两个及以上参数时，不成熟的实现很容易出现这种问题。

#### 20.2.2.19 Math.imul ( <var>x</var>, <var>y</var> )

当调用 `Math.imul` 传递了两个参数 x 和 y 时，将执行以下步骤：

1. 令 a 等于 [ToUint32](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-touint32)(x)。
2. 令 b 等于 [ToUint32](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-touint32)(y)。
3. 令 product 等于 (a × b) [模](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-algorithm-conventions) 2<sup>32</sup>。
4. 如果 product ≥ 2<sup>31</sup>，返回 product - 2<sup>32</sup>。否则返回 product。

#### 20.2.2.20 Math.log ( <var>x</var> )

返回 x 的自然对数的依赖于实现的近似值 .

*   如果 x 是 NaN，返回结果是 NaN。
*   如果 x 小于 0，返回结果是 NaN。
*   如果 x 是 +0 或 −0，返回结果是 −∞。
*   如果 x 是 1，返回结果是 +0。
*   如果 x 是 +∞，返回结果是 +∞。

#### 20.2.2.21 Math.log1p ( <var>x</var> )

返回 x + 1 的自然对数的依赖于实现的近似值。即使 x 接近 0，计算出的结果也是准确的。

* 如果 x NaN，返回结果是 NaN。
* 如果 x 小于 -1，返回结果是 NaN。
* 如果 x 等于 -1，返回结果是 -∞。
* 如果 x 等于 +0，返回结果是 +0。
* 如果 x 等于 -0，返回结果是 -0。
* 如果 x 等于 +∞，返回结果是 +∞。

#### 20.2.2.22 Math.log10 ( <var>x</var> )

返回 x 以 10 为底的对数的依赖于实现的近似值。

* 如果 x 是 NaN，返回结果是 NaN。
* 如果 x 小于 0，返回结果是 NaN。
* 如果 x 是 +0，返回结果是 -∞。
* 如果 x 是 -0，返回结果是 -∞。
* 如果 x 是 1，返回结果是 +0。
* 如果 x 是 +∞，返回结果是 +∞。

#### 20.2.2.23 Math.log2 ( <var>x</var> )

返回 x 以 2 为底的对数的依赖于实现的近似值。

* 如果 x 是 NaN，返回结果是 NaN。
* 如果 x 小于 0，返回结果是 NaN。
* 如果 x 是 +0，返回结果是 -∞。
* 如果 x 是 -0，返回结果是 -∞。
* 如果 x 是 1，返回结果是 +0。
* 如果 x 是 +∞，返回结果是 +∞。

#### 20.2.2.24 Math.max ( <var>value1</var>, <var>value2</var>, ...<var>values</var> )

给定零或多个参数，对每个参数调用 ToNumber 并返回调用结果里的最大值。

*   如果没有给定参数，返回结果是 −∞。
*   如果某个值是 NaN，返回结果是 NaN。
*   比较以确定最大值是使用了[抽象关系比较](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-abstract-relational-comparison)算法，除了 +0 被认为大于 -0 这一特殊情况。

#### 20.2.2.25 Math.min ( <var>value1</var>, <var>value2</var>, ...<var>values</var> )

给定零或多个参数，对每个参数调用 ToNumber 并返回调用结果里的最小值。

*   如果没有给定参数，返回结果是 −∞。
*   如果某个值是 NaN，返回结果是 NaN。
*   比较以确定最小值是使用了[抽象关系比较](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-abstract-relational-comparison)算法，除了 +0 被认为大于 -0 这一特殊情况。

#### 20.2.2.26 Math.pow ( <var>base</var>, <var>exponent</var> )

1. 返回如规范[12.7.3.4](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-applying-the-exp-operator)中所定义的对 base 和 exponent [应用 ** 操作符](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-applying-the-exp-operator)的结果。

#### 20.2.2.27 Math.random ( )

返回一个大于或等于 0 但小于 1 的符号为正的数字值，选择随机或在该范围内近似均匀分布的伪随机，用一个依赖与实现的算法或策略。此函数不需要参数。

不同领域创建的每个 `Math.random` 函数都必须在连续调用的情况下返回不同的序列。

#### 20.2.2.28 Math.round ( <var>x</var> )

 返回最接近 x 且为数学整数的数值。如果两个整数同等接近 x，则选择接近 +∞的数值 。如果 x 已是整数，则返回 x。

*   如果 x 是 NaN，返回结果是 NaN。
*   如果 x 是 +0，返回结果是 +0。
*   如果 x 是 −0，返回结果是 −0。
*   如果 x 是 +∞，返回结果是 +∞。
*   如果 x 是 −∞，返回结果是 −∞。
*   如果 x 大于 0 但小于 0.5，返回结果是 +0。
*   如果 x 小于 0 但大于或等于 -0.5，返回结果是 −0。

注 1
Math.round(3.5) 返回 4，但 Math.round(–3.5) 返回 –3.

注 2
当 x 为 −0 或 x 小于 0 当大于大于等于 -0.5 时，Math.round(x) 返回 −0, 但 Math.floor(x+0.5) 返回 +0，除了这种情况之外 Math.round(x) 的返回值与 Math.floor(x+0.5) 的返回值相同。

#### 20.2.2.29 Math.sign (<var>x</var>)

返回 x 的标识位，标识 x 是正数，负数，或者 0。

* 如果 x 是 NaN，返回结果是 NaN。
* 如果 x 是 -0，返回结果是 -0。
* 如果 x 是 +0，返回结果是 +0。
* 如果 x 是负数并且不为 -0，返回结果是 -1。
* 如果 x 是正数并且不为 +0，返回结果是 +1。

# 20.2.2.30Math.sin ( <var>x</var> )

返回 x 的正弦的依赖实现的近似值。参数被当做是弧度值。

*   如果 x 是 NaN，返回结果是 NaN。
*   如果 x 是 +0，返回结果是 +0。
*   如果 x 是 −0，返回结果是 −0。
*   如果 x 是 +∞ 或 −∞，返回结果是 NaN。

#### 20.2.2.31 Math.sinh ( <var>x</var> )

返回 x 的双曲正弦的依赖实现的近似值。

*   如果 x 是 NaN，返回结果是 NaN。
*   如果 x 是 +0，返回结果是 +0。
*   如果 x 是 −0，返回结果是 −0。
*   如果 x 是 +∞，返回结果是 +∞。
*   如果 x 是 -∞，返回结果是 -∞。

注
sinh(x) 的值与 *(exp(x) - exp(-x))/2* 相同。

#### 20.2.2.32 Math.sqrt ( <var>x</var> )

返回 x 的平方根的依赖实现的近似值。

*   如果 x 是 NaN，返回结果是 NaN。
*   如果 x 小于 0，返回结果是 NaN。
*   如果 x 是 +0，返回结果是 +0。
*   如果 x 是 −0，返回结果是 −0。
*   如果 x 是 +∞，返回结果是 +∞。

#### 20.2.2.33 Math.tan ( <var>x</var> )

返回 x 的正切的依赖实现的近似值。参数被当做是弧度值。

*   如果 x 是 NaN，返回结果是 NaN。
*   如果 x 是 +0，返回结果是 +0。
*   如果 x 是 −0，返回结果是 −0。
*   如果 x 是 +∞ 或 −∞，返回结果是 NaN。

#### 20.2.2.34 Math.tanh ( <var>x</var> )

返回 x 的双曲正切的依赖实现的近似值。

*   如果 x 是 NaN，返回结果是 NaN。
*   如果 x 是 +0，返回结果是 +0。
*   如果 x 是 −0，返回结果是 −0。
*   如果 x 是 +∞，返回结果是 +1。
*   如果 x 是 -∞，返回结果是 -1。

注
tanh(x)的值与 *(exp(x) - exp(-x))/(exp(x) + exp(-x))*相同。

#### 20.2.2.35 Math.trunc ( <var>x</var> )

返回 x 的整数部分，删除所有小数部分。如果 x 已经是整数，则返回 x。

* 如果 x 是 NaN，返回结果是 NaN。
* 如果 x 是 -0，返回结果是 -0。
* 如果 x 是 +0，返回结果是 +0。
* 如果 x 是 +∞，返回结果是 +∞。
* 如果 x 是 -∞，返回结果是 -∞。
* 如果 x 大于 0 小于 1，返回结果是 +0。
* 如果 x 小于 0 大于 -1，返回结果是 -0。

## 20.3 Date 对象

### 20.3.1O Date 对象的概述和抽象操作的定义

下面的函数是操作时间值的抽象操作（在规范[20.3.1.1](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-time-values-and-time-range)中定义）。需要注意的是，在任何情况下，如果以下这些函数某个参数是 NaN，返回结果则为 NaN。

#### 20.3.1.1 时间值和时间范围

一个 Date 对象包含一个表示特定时间瞬间的毫秒的数字值。这样的 Number 叫做时间值 。一个时间值也可以是 NaN，说明这个 Date 对象不表示特定时间瞬间。

ECMAScript 中测量时间以毫秒为单位自 1970 年 1 月 1 日开始的。在时间值中闰秒是被忽略的，假设每天正好有 86,400,000 毫秒。ECMAScript 数字值可表示的所有从–9,007,199,254,740,991 到 9,007,199,254,740,991 的整数；这个范围足以衡量在约 1970 年 1 月 1 日前后约 285,616 年内时间精确到毫秒的任何时刻。

ECMAScript Date 对象支持的实际时间范围是略小一些的：相对 1970 年 1 月 1 日午夜 0 点的精确的 –100,000,000 天到 100,000,000 天。这给出了 1970 年 1 月 1 日前后 8,640,000,000,000,000 毫秒的范围。

精确的协调世界时 1970 年 1 月 1 日午夜 0 点用 +0 表示。

#### 20.3.1.2 天数和天内时间

一个给定[时间值](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-time-values-and-time-range) t 所属的天数是

[Day](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-day-number-and-time-within-day)(t) = [floor](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-algorithm-conventions)(t / [msPerDay](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-day-number-and-time-within-day))

其中每天的毫秒数是

[msPerDay](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-day-number-and-time-within-day) = 86400000

余数叫做天内时间

[TimeWithinDay](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-day-number-and-time-within-day)(t) = t [%](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-algorithm-conventions)[msPerDay](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-day-number-and-time-within-day)。

#### 20.3.1.3 年数

ECMAScript 使用一个推算公历系统，来将一个天数映射到一个年数，并确定在那年的月份的日期。在这个系统中，闰年是且仅是（可被 4 整除）且（（不可被 100 整除）或（可被 400 整除））的年份。因此，y 年的天的数目定义为

[DaysInYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(y)

= 365 if (y [%](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-algorithm-conventions) 4) ≠ 0

= 366 if (y [%](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-algorithm-conventions) 4) = 0 and (y [modulo](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-algorithm-conventions) 100) ≠ 0

= 365 if (y [%](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-algorithm-conventions) 100) = 0 and (y [modulo](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-algorithm-conventions) 400) ≠ 0

= 366 if (y [%](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-algorithm-conventions) 400) = 0


所有非闰年有 365 天，其中每月的天的数目是常规的。闰年的二月里有个多出来的一天。 y 年第一天的天数是：

[DayFromYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(y) = 365 × (y-1970) + [floor](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-algorithm-conventions)((y-1969)/4) - [floor](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-algorithm-conventions)((y-1901)/100) + [floor](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-algorithm-conventions)((y-1601)/400)


 y 年的起始[时间值](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-time-values-and-time-range)是：

[TimeFromYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(y) = [msPerDay](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-day-number-and-time-within-day) × [DayFromYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(y)

 一个[时间值](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-time-values-and-time-range)决定的年数是：

[YearFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t) = 最大整数 y (距离正无穷最近) 这样 [TimeFromYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(y) ≤ t

若时间值在闰年内，闰年函数返回 1，否则返回 0：

[InLeapYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t)

= 0 if [DaysInYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)([YearFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t)) = 365

= 1 if [DaysInYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)([YearFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t)) = 366

#### 20.3.1.4 月数

月份是由闭区间 0 到 11 内的一个整数确定。一个[时间值](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-time-values-and-time-range) t 到一个月数的映射 MonthFromTime(t) 的定义为：

[MonthFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t)

= 0 if 0 ≤ [DayWithinYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t) < 31

= 1 if 31 ≤ [DayWithinYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t) < 59+[InLeapYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t)

= 2 if 59+[InLeapYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t) ≤ [DayWithinYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t) < 90+[InLeapYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t)

= 3 if 90+[InLeapYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t) ≤ [DayWithinYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t) < 120+[InLeapYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t)

= 4 if 120+[InLeapYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t) ≤ [DayWithinYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t) < 151+[InLeapYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t)

= 5 if 151+[InLeapYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t) ≤ [DayWithinYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t) < 181+[InLeapYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t)

= 6 if 181+[InLeapYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t) ≤ [DayWithinYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t) < 212+[InLeapYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t)

= 7 if 212+[InLeapYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t) ≤ [DayWithinYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t) < 243+[InLeapYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t)

= 8 if 243+[InLeapYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t) ≤ [DayWithinYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t) < 273+[InLeapYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t)

= 9 if 273+[InLeapYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t) ≤ [DayWithinYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t) < 304+[InLeapYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t)

= 10 if 304+[InLeapYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t) ≤ [DayWithinYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t) < 334+[InLeapYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t)

= 11 if 334+[InLeapYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t) ≤ [DayWithinYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t) < 365+[InLeapYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t)

[DayWithinYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t) = [Day](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-day-number-and-time-within-day)(t)-[DayFromYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)([YearFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t))

月数值 0 指一月；1 指二月；2 指三月；3 指四月；4 指五月；5 指六月；6 指七月；7 指八月；8 指九月；9 指十月；10 指十一月；11 指十二月。注：[MonthFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(0) = 0，对应 1970 年 1 月 1 日，星期四。

#### 20.3.1.5 日期数

一个日期数用闭区间 1 到 31 内的一个整数标识。从一个[时间值](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-time-values-and-time-range) t 到一个日期数的映射 DateFromTime(t) 的定义为：

[DateFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-date-number)(t)

= [DayWithinYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t)+1 if [MonthFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t)=0

= [DayWithinYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t)-30 if [MonthFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t)=1

= [DayWithinYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t)-58-[InLeapYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t) if [MonthFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t)=2

= [DayWithinYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t)-89-[InLeapYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t) if [MonthFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t)=3

= [DayWithinYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t)-119-[InLeapYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t) if [MonthFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t)=4

= [DayWithinYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t)-150-[InLeapYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t) if [MonthFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t)=5

= [DayWithinYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t)-180-[InLeapYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t) if [MonthFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t)=6

= [DayWithinYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t)-211-[InLeapYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t) if [MonthFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t)=7

= [DayWithinYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t)-242-[InLeapYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t) if [MonthFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t)=8

= [DayWithinYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t)-272-[InLeapYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t) if [MonthFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t)=9

= [DayWithinYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t)-303-[InLeapYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t) if [MonthFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t)=10

= [DayWithinYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t)-333-[InLeapYear](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t) if [MonthFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t)=11

#### 20.3.1.6 星期数

特定[时间值](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-time-values-and-time-range) t 对应的星期数的定义为：


[WeekDay](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-1.  `YYYY-MM-DD`1.  `YYYY-MM-DD`****week-day)(t) = ([Day](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-day-number-and-time-within-day)(t) + 4) [%](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-algorithm-conventions) 7

星期数的值 0 指星期日；1 指星期一；2 指星期二；3 指星期三；4 指星期四；5 指星期五；6 指星期六。注：[WeekDay](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-week-day)(0) = 4, 对应 1970 年 1 月 01 日 星期四。

#### 20.3.1.7 本地时区校准

一个 ECMAScript 的实现预期可以进行确定本地时区校准。本地时区校准是一个毫秒为单位的值 LocalTZA，它加上 UTC 代表本地标准时间。LocalTZA 不体现夏令时。LocalTZA 值不随时间改变，只取决于地理位置。

注
推荐实现使用 IANA 时区数据库[http://www.iana.org/time-zones/](http://www.iana.org/time-zones/)提供的信息。

#### 20.3.1.8 夏时令校准

实现依赖算法来使用关于时区最佳可得的信息来确定本地的夏时令校准 DaylightSavingTA(t)，以毫秒计。一个 ECMAScript 实现预期应尽最大努力来确定本地的夏时令校准。

注
推荐实现使用 IANA 时区数据库[http://www.iana.org/time-zones/](http://www.iana.org/time-zones/)提供的信息。

#### 20.3.1.9 LocalTime (<var> t </var>)

带有参数 t 的抽象操作 LocalTime 将 t 从国际协调时间（UTC）转换为本地时间，具体执行以下步骤：

1. 返回 t + [LocalTZA](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-local-time-zone-adjustment) + DaylightSavingTA(t)。

#### 20.3.1.10 UTC (<var> t </var>)

The abstract operation UTC with argument t converts t from local time to UTC is defined by performing the following steps:
带有参数 t 的抽象操作 UTC 将 t 从本地时间转换为 UTC，具体执行以下步骤：

1. 返回 t - [LocalTZA](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-local-time-zone-adjustment) - DaylightSavingTA(t - [LocalTZA](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-local-time-zone-adjustment))。

注
[UTC](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-utc-t)([LocalTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-localtime)(t))不必恒等于 t。

#### 20.3.1.11 时，分，秒，毫秒

以下函数用于分解时间值：

[HourFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)(t) = [floor](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-algorithm-conventions)(t / [msPerHour](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)) [%](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-algorithm-conventions) [HoursPerDay](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)

[MinFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)(t) = [floor](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-algorithm-conventions)(t / [msPerMinute](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)) [%](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-algorithm-conventions) [MinutesPerHour](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)

[SecFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)(t) = [floor](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-algorithm-conventions)(t / [msPerSecond](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)) [%](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-algorithm-conventions) [SecondsPerMinute](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)

[msFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)(t) = t [%](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-algorithm-conventions) [msPerSecond](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)

此时

[HoursPerDay](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds) = 24

[MinutesPerHour](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds) = 60

[SecondsPerMinute](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds) = 60

[msPerSecond](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds) = 1000

[msPerMinute](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds) = 60000 = [msPerSecond](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds) × [SecondsPerMinute](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)

[msPerHour](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds) = 3600000 = [msPerMinute](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds) × [MinutesPerHour](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)

#### 20.3.1.12 MakeTime (<var>hour, min, sec, ms</var>)

MakeTime 抽象操作用它的四个参数算出一个毫秒数，参数必须是 ECMAScript 数值。此抽象操作运行以下：

1.  如果 hour 不是有限的或 min 不是有限的或 sec 不是有限的或 ms 不是有限的，返回 NaN。
2.  令 h 为 [ToInteger](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tointeger)(hour)。
3.  令 m 为 [ToInteger](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tointeger)(min)。
4.  令 s 为 [ToInteger](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tointeger)(sec)。
5.  令 milli 为 [ToInteger](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tointeger)(ms)。
6.  令 t 为 h * msPerHour + m * msPerMinute + s * msPerSecond + milli，执行的四则运算根据 IEEE 754 规则（这就像使用 ECMAScript 运算符 * 和 + 一样）。
7.  返回 t。

#### 20.3.1.13 MakeDay (<var>year, month, date</var>)

MakeDay 抽象操作用它的三个参数算出一个天数，参数必须是 ECMAScript 数值。此抽象操作运行以下：

1.  如果 year 不是有限的或 month 不是有限的或 date 不是有限的，返回 NaN。
2.  令 y 为 ToInteger(year)。
3.  令 m 为 ToInteger(month)。
4.  令 dt 为 ToInteger(date)。
5.  令 ym 为 y + floor(m /12)。
6.  令 mn 为 m % 12。
7.  找一个满足 YearFromTime(t) == ym 且 MonthFromTime(t) == mn 且 DateFromTime(t) == 1 的 t 值 ； 但如果这些条件是不可能的（因为有些参数超出了范围），返回 NaN。
8.  返回 Day(t) + dt − 1。

#### 20.3.1.14 MakeDate (<var>day, time</var>)

MakeDate 抽象操作用它的两个参数算出一个毫秒数，参数必须是 ECMAScript 数字值。此抽象操作运行以下：

1.  如果 day 不是有限的或 time 不是有限的， 返回 NaN.
2.  返回 day × [msPerDay](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-day-number-and-time-within-day) + time.

#### 20.3.1.15 TimeClip (<var>time</var>)

TimeClip 抽象操作用它的参数算出一个毫秒数，参数必须是 ECMAScript 数字值。此抽象操作运行以下：

1. 如果 time 不是有限的，返回 NaN。
2. 如果 [abs](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-algorithm-conventions)(time) > 8.64 x 1015，返回 NaN。
3. 令 clippedTime 等于 [ToInteger](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tointeger)(time)。
4. 如果 clippedTime 等于 -0，令 clippedTime 等于 +0。
5. 返回 clippedTime。

 第 4 步的重点是说允许实现自行选择时间值的内部表示形式，如 64 位有符号整数或 64 位浮点数。根据不同的实现，这个内部表示可能区分也可能无法区分 −0 和 +0。

#### 20.3.1.16 日期时间字符串格式

ECMAScript 定义了一个基于简化的 ISO 8601 扩展格式的日期时间的字符串互换格式，格式为：`YYYY-MM-DDTHH:mm:ss.sssZ`

其中字段为：

|||
|:----|:----|
| `YYYY` | 公历中 0000 年到 9999 年的十进制表示。 |
| `-` | 在字符串中直接以`"-"` (连字符)出现两次。 |
| `MM` | 一年中的月份，从 01 （一月） 到 12 （十二月）。 |
| `DD` | 一月中的日期，从 01 到 31。 |
| `T` | `"T"` 直接出现在字符串中表示时间元素的起点。 |
| `HH` | 自午夜开始经过的小时数，从 00 到 24 以两位十进制形式表示。 |
| `:` | 在字符串中直接以 `":"` (冒号)出现两次。 |
| `mm` | 自小时开始经过的分钟数，从 00 到 59 以两位十进制形式表示。 |
| `ss` | 自分钟开始经过的秒数，从 00 到 59 以两位十进制形式表示。 |
| `.` | `"."` (点) 直接出现在字符串中。 |
| `sss` | 自秒开始经过的毫秒数，以三位十进制形式表示。 |
| `Z` | 时区偏移量，由 `"Z"` (指 UTC) 或 `"+"` / `"-"` 和后面跟着的时间表示 `HH:mm` 组成。 |

格式包含了只表示日期的形式：

```
YYYY
YYYY-MM
YYYY-MM-DD
```

其中也包含了“日期-时间” 的格式，包括上述提到的只有日期的形式然后马上跟着一个时间格式与一个可选的附加时区偏移：

```
THH:mm
THH:mm:ss
THH:mm:ss.sss
```

所有数字必须是 10 进制的。如果缺少 `MM` 或 `DD` 字段，用 `"01"` 作为它们的值。如果缺少 `mm` 或 `ss` 字段，用 `"00"` 作为它们的值，对于缺少的 `sss` 用 `"000"` 作为它的值。如果时区偏移量缺失，只有日期的形式会被理解为 UTC 事件，日期-时间格式会被理解为本地时间。

个格式字符串里有非法值（越界以及语法错误），意味着这个格式字符串不是有效的本节描述格式的实例。

注 1
由于每天的开始和结束都在午夜，使用两个记号 00:00 和 24:00 可以区分这样同一日期的两个午夜。这意味着两个记号 1995-02-04T24:00 和 1995-02-05T00:00 精准的指向同一时刻。

注 2
不存在用来规范像 CET，EST 这样的民间时区缩写的国际标准。有时相同的缩写甚至使用不同的时区。出于这个原因，ISO 8601 和这里的格式指定数字来表示时区。

#### 20.3.1.16.1 延长的年份

ECMAScript 需要有表示 6 位数年份（延长的时间）的能力；UTC 1970 年 1 月 1 日前后分别约 285,616 年。对于表示 0 年之前或 9999 年之后的年份，ISO 8601 允许对年的表示法进行扩展，但只能在发送和接受信息的双方有事先共同约定的情况下才能扩展。在已经简化的 ECMAScript 的格式中这样扩展的年份表示法有 2 个额外的数字和始终存在的前缀符号 + 或 - 。0 年被认为是正的，因此用 + 符号作为前缀。

注
年份扩展示例：

|||
|---|---|
| -283457-03-21T15:00:59.008Z | 283458 B.C. |
| -000001-01-01T00:00:00Z | 2 B.C. |
| +000000-01-01T00:00:00Z | 1 B.C. |
| +000001-01-01T00:00:00Z | 1 A.D. |
| +001970-01-01T00:00:00Z | 1970 A.D. |
| +002009-12-15T00:00:00Z | 2009 A.D. |
| +287396-10-12T08:59:00.992Z | 287396 A.D. |

#### 20.3.2 Date 构造器

Date 构造器是 %Date% 的内部对象以及[全局对象](http://www.ecma-international.org/ecma-262/7.0/index.html#global-object) `Date` 属性的初始值。当其作为一个构造器被调用时，它会创建并初始化一个新的 Date 对象。当 `Date` 作为一个函数而不是构造器被调用的时候，它返回一个代表当前时间的字符串（UTC）。

`Date` 构造器是一个单一功能的函数，其行为是根据它的参数数值及类型进行重载操作。

`Date` 构造器被设计为可继承的，可以将其赋值给继承类。想要继承 `Date` 行为的子类构造函数为了创建和初始化带有内置 [[DateValue]] 的子类实例中必须包含一个 `super` 调用 `Date` 构造函数。

`Date` 构造器函数的 `length` 属性的值为 7。

#### 20.3.2.1 Date (<var> year, month [, date [, hours [, minutes [, seconds [, ms ] ] ] ] ] </var>)

此描述仅适用于当 Date 构造器被调用时至少传递了两个参数的情况。

当 `Date` 函数被调用时，会执行以下步骤：

1. 令 numberOfArgs 等于函数调用时传递的参数数目。
2. 断言： numberOfArgs ≥ 2。
3. 如果 NewTarget 不是未定义的，则
    1. 令 y 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(year)。
    2. 令 m 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(month)。
    3. 如果提供了 date，令 dt 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(date)；否则令 dt 等于 1。
    4. 如果提供了 hours，令 h 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(hours)；否则令 h 等于 0。
    5. 如果提供了 minutes，令 min 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(minutes)；否则令 min 等于 0。
    6. 如果提供了 seconds，令 s 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(seconds)；否则令 s 等于 0。
    7. 如果提供了 ms，令 milli 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(ms)；否则令 milli 等于 0。
    8. 如果 y 不是 NaN，并且 0 ≤ [ToInteger](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tointeger)(y) ≤ 99，令 yr 等于 1900+[ToInteger](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tointeger)(y)；否则，令 yr 等于 y。
    9. 令 finalDate 等于 [MakeDate](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-makedate)([MakeDay](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-makeday)(yr, m, dt), [MakeTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-maketime)(h, min, s, milli))。
    10. 令 O 等于 [OrdinaryCreateFromConstructor](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-ordinarycreatefromconstructor)(NewTarget, `"%DatePrototype%"`, « [[DateValue]] »)。
    11. 设置 O 的内置 [[DateValue]] 为 [TimeClip](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-timeclip)([UTC](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-utc-t)(finalDate))。
    12.  返回 O。
4. 否则,
    1. 令 now 等于 [time value](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-time-values-and-time-range) (UTC) 的数值，指定了当前时间。
    2. 返回 [ToDateString](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-todatestring)(now).

#### 20.3.2.2 Date (<var> value </var>)

此描述仅适用于当 Date 构造器被调用时只传递了一个参数的情况。

当 `Date` 函数被调用时，会执行以下步骤：

1. 令 numberOfArgs 等于函数调用时传递的参数数目。
2. 断言： numberOfArgs = 1。
3. 如果 NewTarget 不是未定义的，则
    1. 如果 [Type](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-ecmascript-data-types-and-values)(value) 为 Object 并且 value 内部有 [[DateValue]] 的值，则
        1. 令 tv 等于 [thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(value)。
    2.  否则，
        1. 令 v 等于 [ToPrimitive](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-toprimitive)(value)。
        2. 如果 [Type](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-ecmascript-data-types-and-values)(v) 为字符串，则
            1. 令 tv 等于按日期解析 v 的结果，解析方式与 `parse` 方法完全相同（[20.3.3.2](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-date.parse)）。如果解析结果导致了一个[突然终止](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-completion-record-specification-type)，tv 则为[终止记录](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-completion-record-specification-type)。
            2.  [ReturnIfAbrupt](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-returnifabrupt)(tv).
        3. 否则
            1. 令 tv 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(v)。
    3. 令 O 等于 [OrdinaryCreateFromConstructor](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-ordinarycreatefromconstructor)(NewTarget, `"%DatePrototype%"`, « [[DateValue]] »)。
    4. 设置 O 内部的 [[DataValue]] 为 [TimeClip](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-timeclip)(tv)。
    5. 返回 O。
4. 否则，
    1. 令 now 为 [time value](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-time-values-and-time-range) (UTC) 的一个表示当前时间的 Number。
    2.  返回 [ToDateString](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-todatestring)(now)。

#### 20.3.2.3 Date ( )

此描述仅适用于没有函数传递的 Date 构造器调用。

当 `Date` 函数被调用时，将执行以下步骤：

1. 令 numberOfArgs 等于函数调用时传递的参数数目。
2. 断言： numberOfArgs = 0。
3. 如果 NewTarget 不是未定义的，则
    1. 令 O 等于 [OrdinaryCreateFromConstructor](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-ordinarycreatefromconstructor)(NewTarget, `"%DatePrototype%"`, « [[DateValue]] »)。
    2. 令 O 的内置 [[DateValue]] 等于 [time value](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-time-values-and-time-range) (UTC)，表示当前时间。
    3. 返回 O。
4. 否则，
    1. 令 now 为 [time value](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-time-values-and-time-range) (UTC) 的一个表示当前时间的 Number。
    2.  返回 [ToDateString](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-todatestring)(now)。

### 20.3.3 Date 构造器的属性

Date 构造器的内置 [[Prototype]] 的值是函数原型对象 [%FunctionPrototype%](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-function-prototype-object)。

Date 构造器有以下属性：

#### 20.3.3.1 Date.now ( )

函数 `now` 返回一个数字值，它表示调用 now 时的 UTC 日期时间的数值。
#### 20.3.3.2 Date.parse (<var> string </var>)

parse 函数对它的参数应用 [ToString](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tostring) 操作。如果 [ToString](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tostring) 的结果是一个[突然终止](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-completion-record-specification-type)，[终止记录](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-completion-record-specification-type)将被立即返回。

否则，`parse` 将结果字符串解释为一个日期和时间；返回一个数字值，是对应这个日期时间的 UTC [时间值](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-time-values-and-time-range)。字符串可解释为本地时间，UTC 时间，或某个其他时区的时间，这取决于字符串里的内容。此函数首先尝试根据日期时间字符串格式（[20.3.1.16](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-date-time-string-format))里的规则来解析字符串的格式。如果字符串不符合这个格式此函数可回退，用任意实现定义的试探方式或日期格式。无法识别的字符串或日期时间包含非法元素值，将导致 `Date.parse` 返回 NaN。

在所有属性都指向它们的初始值的情况下，如果 x 是一个在特定 ECMAScript 的实现里的毫秒数为零的任意 Date 对象，则在这个实现中以下所有表达式应产生相同数字值：

```
x.valueOf()
Date.parse(x.toString())
Date.parse(x.toUTCString())
Date.parse(x.toISOString())
```

然而，表达式

```
 `Date.parse(x.toLocaleString())`
```

是不需要产生与前面三个表达参数相同的数字值。通常，在给定的字符串不符合日期时间字符串格式（[20.3.1.16](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-date-time-string-format)）时，`Date.parse` 的产生值是依赖于实现，并且在同一实现中 `toString` 或 `toUTCString` 方法不能产生不符合日期时间字符串格式的字符串。

#### 20.3.3.3 Date.prototype

Date.prototype 的初始值是内置的 Date 原型对象 [%DatePrototype%](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)。

这个属性的特性为 { [[Writable]]: false, [[Enumerable]]: false, [[Configurable]]: false }。

#### 20.3.3.4 Date.UTC (<var> year, month [, date [, hours [, minutes [, seconds [, ms ] ] ] ] ] </var>)

当用少于两个的参数调用 `UTC` 函数时，它的行为是依赖于实现的。当用二到七个参数调用 `UTC` 函数，它从 year，month 和 (可选的) date，hours，minutes，seconds，ms 计算出日期时间。采用以下步骤：

1.  令 y 为 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(year)。
2.  令 m 为 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(month)。
3.  如果提供了 date，则令 dt 为 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(date)； 否则令 dt 为 1。
4.  如果提供了 hours则令 h 为 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(hours)； 否则令 h 为 0。
5.  如果提供了 minutes，则令 min 为 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(minutes)； 否则令 min 为 0。
6.  如果提供了 seconds，则令 s 为 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(seconds)； 否则令 s 为 0。
7.  如果提供了 ms，则令 milli 为 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(ms)； 否则令 milli 为 0。
8.  如果 y 不是 NaN 且 0 ≤ [ToInteger](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tointeger)(y) ≤ 99，则令 yr 为 1900+[ToInteger](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tointeger)(y)； 否则令 yr 为 y。
9.  返回 [TimeClip](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-timeclip)([MakeDate](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-makedate)([MakeDay](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-makeday)(yr, m, dt), [MakeTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-maketime)(h, min, s, milli)))。

`UTC` 函数的 `length` 属性是 7。

注
UTC 函数与 Date 构造器的不同点有：它返回一个时间值，而不是创建 Date 对象，还有它将参数解释为 UTC，而不是本地时间。

### 20.3.4 Date 原型对象的属性

Date 原型对象是内部对象 %DatePrototype%。Date 原型对象是本身一个普通对象。没有 Date 实例并且没有 [[DateValue]] 的值。

Date 原型对象的内置 [[Prototype]] 的值为内部对象 [%ObjectPrototype%](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-object-prototype-object)。

除非有明确定义，否则，下列定义 Date 原型对象方法均为不通用的而且传递给它们的值必须是一个其 [[DateValue]] 的初始值为[时间值](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-time-values-and-time-range)的对象。
The abstract operation thisTimeValue(value) performs the following steps:
抽象操作 thisTimeValue(value) 执行以下步骤：

1. 如果 [Type](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-ecmascript-data-types-and-values)(value) 是一个对象并且 value 有内置 [[DateValue]]，则
    1. 返回 value 的内置 [[DateValue]]。
2. 抛出 TypeError 异常。

在以下对 Date 原型对象的函数属性的描述中，短语“当前 Date 对象”指调用函数时的 this 对象。如果当前值不是一个对象，则抛出一个 TypeError 异常。在规范中的一种方法中短语“当前时间值”指的是通过传递当前函数调用的参数给抽象操作 thisTimeValue 所返回的结果。

#### 20.3.4.1 Date.prototype.constructor

Date.prototype.constructor 的初始值是内置函数 [%Date%](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-date-constructor)。

#### 20.3.4.2 Date.prototype.getDate ( )

执行以下步骤：

1.  令 t 等于 [thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value)。
2.  如果 t 是 NaN，返回 NaN。
3.  返回 [DateFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-date-number)([LocalTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-localtime)(LocalTime(t))。

#### 20.3.4.3 Date.prototype.getDay ( )

执行以下步骤：

1.  令 t 等于 [thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value)。
2.  如果 t 是 NaN，返回 NaN。
3.  返回 [WeekDay](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-week-day)([LocalTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-localtime)(LocalTime(t))。

#### 20.3.4.4 Date.prototype.getFullYear ( )

执行以下步骤：

1.  令 t 等于 [thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value)。
2.  如果 t 是 NaN，返回 NaN。
3.  返回 [YearFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)([LocalTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-localtime)(t))。

#### 20.3.4.5 Date.prototype.getHours ( )

执行以下步骤：

1.  令 t 等于 [thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value)。
2.  如果 t 是 NaN，返回 NaN。
3.  返回 [HourFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)([LocalTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-localtime)(t))。

#### 20.3.4.6 Date.prototype.getMilliseconds ( )

执行以下步骤：

1.  令 t 等于 [thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value)。
2.  如果 t 是 NaN，返回 NaN。
3.  返回 [msFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)([LocalTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-localtime)(t))。

#### 20.3.4.7 Date.prototype.getMinutes ( )

执行以下步骤：

1.  令 t 等于 [thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value)。
2.  如果 t 是 NaN，返回 NaN。
3.  返回 [MinFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)([LocalTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-localtime)(t))。

#### 20.3.4.8 Date.prototype.getMonth ( )

执行以下步骤：

1.  令 t 等于 [thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value)。
2.  如果 t 是 NaN，返回 NaN。
3.  返回 [MonthFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)([LocalTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-localtime)(t))。

#### 20.3.4.9 Date.prototype.getSeconds ( )

执行以下步骤：

1.  令 t 等于 [thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value)。
2.  如果 t 是 NaN，返回 NaN。
3.  返回 [SecFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)([LocalTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-localtime)(t))。

#### 20.3.4.10 Date.prototype.getTime ( )

执行以下步骤：

1.  返回 [thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value)。

#### 20.3.4.11 Date.prototype.getTimezoneOffset ( )

执行以下步骤：

1.  令 t 等于 [thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value)。
2.  如果 t 是 NaN，返回 NaN。
3.  返回 (t - [LocalTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-localtime)(t)) / [msPerMinute](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)。

#### 20.3.4.12 Date.prototype.getUTCDate ( )

执行以下步骤：

1.  令 t 等于 [thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value)。
2.  如果 t 是 NaN，返回 NaN。
3.  返回 [DateFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-date-number)(t)。

#### 20.3.4.13 Date.prototype.getUTCDay ( )

执行以下步骤：

1.  令 t 等于 [thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value)。
2.  如果 t 是 NaN，返回 NaN。
3.  返回 [WeekDay](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-week-day)(t)。

#### 20.3.4.14 Date.prototype.getUTCFullYear ( )

执行以下步骤：

1.  令 t 等于 [thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value)。
2.  如果 t 是 NaN，返回 NaN。
3.  返回 [YearFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t)。

#### 20.3.4.15 Date.prototype.getUTCHours ( )

执行以下步骤：

1.  令 t 等于 [thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value)。
2.  如果 t 是 NaN，返回 NaN。
3.  返回 [HourFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)(t)。

#### 20.3.4.16 Date.prototype.getUTCMilliseconds ( )

执行以下步骤：

1.  令 t 等于 [thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value)。
2.  如果 t 是 NaN，返回 NaN。
3.  返回 [msFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)(t)。

#### 20.3.4.17 Date.prototype.getUTCMinutes ( )

执行以下步骤：

1.  令 t 等于 [thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value)。
2.  如果 t 是 NaN，返回 NaN。
3.  返回 [MinFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)(t)。

#### 20.3.4.18 Date.prototype.getUTCMonth ( )

执行以下步骤：

1.  令 t 等于 [thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value)。
2.  如果 t 是 NaN，返回 NaN。
3.  返回 [MonthFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t)。

#### 20.3.4.19 Date.prototype.getUTCSeconds ( )

执行以下步骤：

1.  令 t 等于 [thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value)。
2.  如果 t 是 NaN，返回 NaN。
3.  返回 [SecFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)(t)。

# 20.3.4.20Date.prototype.setDate (<var> date </var>)

执行以下步骤：

1.  令 t 等于 [LocalTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-localtime)([thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value))。
2.  令 dt 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(date)。
3.  令 newDate 等于 [MakeDate](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-makedate)([MakeDay](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-makeday)([YearFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t), [MonthFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t), dt), [TimeWithinDay](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-day-number-and-time-within-day)(t))。
4.  令 u 为 [TimeClip](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-timeclip)([UTC](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-utc-t)(newDate))。
5.  设定当前 Date 对象的内置 [[DateValue]] 的值为 u。
6.  返回 u。

#### 20.3.4.21 Date.prototype.setFullYear (<var> year [, month [, date ] ] </var>)

执行以下步骤：

1. 令 t 等于[thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value)。
2. 如果 t 是 NaN，令 t 等于 +0，否则，令 t 等于 [LocalTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-localtime)(t)。
3.  令 y 为 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(year)。
4.  如果没指定 month，则令 m 等于 [MonthFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t)； 否则，令 m 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(month)。
5.  如果没指定 date，则令 dt 等于 [DateFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-date-number)(t)； 否则，令 dt 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(date)。
6.  令 newDate 等于 [MakeDate](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-makedate)([MakeDay](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-makeday)(y, m, dt), [TimeWithinDay](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-day-number-and-time-within-day)(t))。
7.  令 u 为 [TimeClip](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-timeclip)([UTC](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-utc-t)(newDate))。
8.  设定当前 Date 对象的内置 [[DateValue]] 为 u。
9.  返回 u。

`setFullYear` 方法的 length 属性是 3。

注
没指定 month 参数时的行为，与 ms 被指定为调用 `getMonth()` 的结果一样。没指定 date 参数时的行为，与 ms 被指定为调用 `getDate()` 的结果一样。


#### 20.3.4.22 Date.prototype.setHours (<var> hour [, min [, sec [, ms ] ] ] </var>)

执行以下步骤：

1.  令 t 等于 [LocalTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-localtime)([thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value))。
2.  令 h 为 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(hour)。
3.  如果没指定 min，则令 m 为 [MinFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)(t)； 否则，令 m 为 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber(min)。
4.  如果没指定 sec，则令 s 为 [SecFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)(t)； 否则，令 s 为 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber(sec)。
5.  如果没指定 ms，则令 milli 为 [msFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)(t)； 否则，令 milli 为 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber(ms)。
6.  令 date 为 [MakeDate](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-makedate)([Day](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-day-number-and-time-within-day)(t), [MakeTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-maketime)(h, m, s, milli))。
7.  令 u 为 [TimeClip](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-timeclip)([UTC](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-utc-t)(date))。
8.  设定当前 Date 对象的内置 [[DateValue]] 的值为 u。
9.  返回 u。

`setHours` 方法的 `length` 属性是 4。

注
没指定 min 参数时的行为，与 min 被指定为调用 `getMinutes()` 的结果一样。没指定 sec 参数时的行为，与 ms 被指定为调用 `getSeconds() `的结果一样。没指定 ms 参数时的行为，与 ms 被指定为调用 `getMilliseconds()` 的结果一样。

#### 20.3.4.23 Date.prototype.setMilliseconds (<var> ms </var>)

执行以下步骤：

1.  令 t 等于 [LocalTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-localtime)([thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value))。
2. 令 ms 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(ms)。
3. 令 time 等于 [MakeTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-maketime)([HourFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)(t), [MinFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)(t), [SecFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)(t), ms)。
4. 令 u 等于 [TimeClip](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-timeclip)([UTC](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-utc-t)([MakeDate](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-makedate)([Day](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-day-number-and-time-within-day)(t), time)))。
5. 设定当前 Date 对象的内置 [[DateValue]] 的值为 u。
6. 返回 u。

#### 20.3.4.24 Date.prototype.setMinutes (<var> min [, sec [, ms ] ] </var>)

执行以下步骤：

1.  令 t 等于 [LocalTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-localtime)([thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value))。
2. 令 m 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(min)。
3.  如果没指定 sec，则令 s 等于 [SecFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)(t)； 否则，令 s 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(sec)。
4.  如果没指定 ms，则令 milli 等于 [msFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)(t)； 否则，令 milli 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(ms)。
5.  令 date 等于 [MakeDate](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-makedate)([Day](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-day-number-and-time-within-day)(t), [MakeTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-maketime)([HourFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)(t), m, s, milli))。
6.  令 u 等于 [TimeClip](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-timeclip)([UTC](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-utc-t)(date))。
7.  设定当前 Date 对象的内置 [[DateValue]] 为 u。
8.  返回 u。

`setMinutes` 方法的 `length` 属性是 3。

注
没指定 sec 参数时的行为，与 ms 被指定为调用 `getSeconds()` 的结果一样。没指定 ms 参数时的行为，与 ms 被指定为调用 `getMilliseconds()` 的结果一样。

#### 20.3.4.25 Date.prototype.setMonth (<var> month [, date ] </var>)

执行以下步骤：

1.  令 t 等于 [LocalTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-localtime)([thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value))。
2. 令 m 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(month)。
3. 如果没指定 date，则令 dt 为 [DateFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-date-number)(t)； 否则，令 dt 为 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(date)。
4. 令 newDate 为 [MakeDate](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-makedate)([MakeDay](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-makeday)([YearFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t), m, dt), [TimeWithinDay](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-day-number-and-time-within-day)(t))。
5. 令 u 为 [TimeClip](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-timeclip)([UTC](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-utc-t)(newDate))。
6. 设定当前 Date 对象的内置 [[DateValue]] 为 u。
7. 返回 u。

`setMonth` 方法的 `length` 属性是 2。

注
没指定 date 参数时的行为，与 ms 被指定为调用 `getDate()` 的结果一样。

#### 20.3.4.26 Date.prototype.setSeconds (<var> sec [, ms ] </var>)

执行以下步骤：

1.  令 t 等于 [LocalTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-localtime)([thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value))。
2.  令 s 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(sec)。
3. 如果没指定 ms，令 milli 等于 [msFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)(t)；否则，令 milli 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(ms)。
4.  令 date 等于 [MakeDate](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-makedate)([Day](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-day-number-and-time-within-day)(t), [MakeTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-maketime)([HourFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)(t), [MinFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)(t), s, milli))。
5.  令 u 等于 [TimeClip](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-timeclip)([UTC](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-utc-t)(date))。
6. 设定当前 Date 对象的内置 [[DateValue]] 为 u。
7. 返回 u。

setSeconds 方法的 length 属性是 2。

注
没指定 ms 参数时的行为，与 ms 被指定为调用 `getMilliseconds()` 的结果一样。

#### 20.3.4.27 Date.prototype.setTime (<var> time </var>)

执行以下步骤：

1.  执行 [thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value)。
2.  令 t 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(time)。
3.  令 v 等于 [TimeClip](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-timeclip)(t)。
4.  设定当前 Date 对象的内置 [[DateValue]] 为 v。
5.  返回 v。

#### 20.3.4.28 Date.prototype.setUTCDate (<var> date </var>)

执行以下步骤：

1.  令 t 等于 [thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value)。
2.  令 dt 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(date)。
3.  令 newDate 等于 [MakeDate](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-makedate)([MakeDay](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-makeday)([YearFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t), [MonthFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t), dt), [TimeWithinDay](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-day-number-and-time-within-day)(t))。
4.  令 v 等于 [TimeClip](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-timeclip)(newDate)。
5.  设定当前 Date 对象的内置 [[DateValue]] 为 v。
6.  返回 v。

#### 20.3.4.29 Date.prototype.setUTCFullYear (<var> year [， month [， date ] ] </var>)

执行以下步骤：

1.  令 t 等于 [thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value)。
2.  如果 t 是 NaN，令 t 等于 +0。
3.  令 y 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(year)。
4.  如果没指定 month，令 m 等于 [MonthFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-month-number)(t)；否则，令 m 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(month)。
5.  如果没指定 date，令 dt 等于 [DateFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-date-number)(t)；否则，令 dt 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(date)。
6.  令 newDate 等于 [MakeDate](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-makedate)([MakeDay](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-makeday)(y, m, dt), [TimeWithinDay](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-day-number-and-time-within-day)(t))。
7.  令 v 等于 [TimeClip](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-timeclip)(newDate)。
8.  设定当前 Date 对象的内置 [[DateValue]] 为 v。
9.  返回 v。

`setUTCFullYear` 方法的 `length` 属性是 3。

注
没指定 month 参数时的行为，与 ms 被指定为调用 `getUTCMonth()` 的结果一样。没指定 date 参数时的行为，与 ms 被指定为调用 `getUTCDate()` 的结果一样。

#### 20.3.4.30 Date.prototype.setUTCHours (<var> hour [， min [， sec [， ms ] ] ] </var>)

执行以下步骤：

1.  令 t 等于 [thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value)。
2.  令 h 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(hour).
3. 如果没指定 min，令 m 等于 [MinFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)(t)；否则，令 m 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(min)。
4.  如果没指定 sec，令 s 等于 [SecFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)(t)； 否则，令 s 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(sec)。
5.  如果没指定 ms, 令 milli 等于 [msFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)(t)； 否则，令 milli 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(ms)。
6.  令 newDate 等于 [MakeDate](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-makedate)([Day](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-day-number-and-time-within-day)(t), [MakeTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-maketime)(h, m, s, milli))。
7.  令 v 等于 [TimeClip](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-timeclip)(newDate)。
8.  设定当前 Date 对象的内置 [[DateValue]] 为 v。
9.  返回 v。

`setUTCHours` 方法的 `length` 属性是 4。

注
没指定 min 参数时的行为，与 min 被指定为调用 getUTCMinutes() 的结果一样。没指定 sec 参数时的行为，与 ms 被指定为调用 `getUTCSeconds()` 的结果一样。没指定 ms 参数时的行为，与 ms 被指定为调用 `getUTCMilliseconds()` 的结果一样。

#### 20.3.4.31 Date.prototype.setUTCMilliseconds (<var> ms </var>)

执行以下步骤：

1.  令 t 等于 [thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value)。
2.  令 milli 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(ms)。
3.  令 time 等于 [MakeTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-maketime)([HourFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)(t), [MinFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)(t), [SecFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)(t), milli)。
4.  令 v 等于 [TimeClip](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-timeclip)([MakeDate](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-makedate)([Day](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-day-number-and-time-within-day)(t), time))。
5.  设定当前 Date 对象的内置 [[DateValue]] 为 v。
6.  返回 v。

#### 20.3.4.32 Date.prototype.setUTCMinutes (<var> min [, sec [, ms ] ] </var>)

执行以下步骤：

1.  令 t 等于 [thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value)。
2.  令 m 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(min).
3.  如果没指定 sec，令 s 等于 [SecFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)(t)。
4.  否则，
    1.  令 s 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(sec)。
5.  如果没指定 ms，令 milli 等于 [msFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)(t)。
6.  否则，
    1.  令 milli 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(ms)。
7.  令 date 等于 [MakeDate](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-makedate)([Day](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-day-number-and-time-within-day)(t), [MakeTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-maketime)([HourFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)(t), m, s, milli))。
8.  令 v 等于 [TimeClip](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-timeclip)(date)。
9.  设定当前 Date 对象的内置 [[DateValue]] 为 v。
10. 返回 v。

`setUTCMinutes` 方法的 `length` 属性是 3。

注
没指定 sec 参数时的行为，与 ms 被指定为调用 `getUTCSeconds()` 的结果一样。没指定 ms 参数时的行为，与 ms 被指定为调用 `getUTCMilliseconds()` 的结果一样。

#### 20.3.4.33 Date.prototype.setUTCMonth (<var> month [, date ]</var> )

执行以下步骤：

1.  令 t 等于 [thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value)。
2.  令 m 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(month)。
3.  如果没指定 date，令 dt 等于 [DateFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-date-number)(t)。
4.  否则，
    1.  令 dt 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(date)。
5.  令 newDate 等于 [MakeDate](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-makedate)([MakeDay](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-makeday)([YearFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-year-number)(t), m, dt), [TimeWithinDay](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-day-number-and-time-within-day)(t))。
6.  令 v 等于 [TimeClip](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-timeclip)(newDate)。
7.  设定当前 Date 对象的内置 [[DateValue]] 为 v。
8.  返回 v。



`setUTCMonth` 方法的 `length` 属性是 2。

注
没指定 date 参数时的行为，与 ms 被指定为调用 `getUTCDate()` 的结果一样。

#### 20.3.4.34 Date.prototype.setUTCSeconds (<var> sec [, ms ]</var> )

执行以下步骤：

1.  令 t 等于 [thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value)。
2.  令 s 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(sec).
3.  如果没指定 ms，令 milli 等于 [msFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)(t)。
4.  否则，
    1.  令 milli 等于 [ToNumber](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-tonumber)(ms)。
5.  令 date 等于 [MakeDate](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-makedate)([Day](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-day-number-and-time-within-day)(t), [MakeTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-maketime)([HourFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)(t), [MinFromTime](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-hours-minutes-second-and-milliseconds)(t), s, milli))。
6.  令 v 等于 [TimeClip](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-timeclip)(date)。
7.  设定当前 Date 对象的内置 [[DateValue]] 为 v。
8.  返回 v。

`setUTCSeconds` 方法的 `length` 属性是 2。

注
没指定 ms 参数时的行为，与 ms 被指定为调用 `getUTCMilliseconds()` 的结果一样。

#### 20.3.4.35 Date.prototype.toDateString ( )

此函数返回一个字符串值。字符串中内容是依赖于实现的，但目的是用一种方便的，可读的形式表示当前时区时间的“日期”部分。

#### 20.3.4.36 Date.prototype.toISOString ( )

此函数返回一个代表[当前时间值](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)的实例的字符串。字符串的格式是 [20.3.1.16](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-date-time-string-format) 定义的日期时间字符串格式。字符串中包含所有的字段。时区 UTC 用后缀 Z 标记。如果当前对象的时间值不是有限的数字值，抛出一个 RangeError 异常。

#### 20.3.4.37 Date.prototype.toJSON ( key )

这个函数通过使用 `JSON.stringify` ([24.3.2](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-json.stringify)) 为 Date 对象提供了一个字符串表示。

当用参数 key 调用 toJSON 方法，执行以下步骤：

1.  令 O 等于 [ToObject](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-toobject)(this value)。
2.  令 tv 等于 [ToPrimitive](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-toprimitive)(O, hint Number)。
3.  如果 [Type](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-ecmascript-data-types-and-values)(tv) 为 Number 并且 tv 是无限的，返回 null。
4.  返回 [Invoke](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-invoke)(O, `"toISOString"`)。

注 1
参数是被忽略的。

注 2
`toJSON` 函数是特意设计为通用的；它不需要其 this 值必须是一个 Date 对象。因此，这个方法可以转换到其他类型的对象上。但转换到的对象必须有 toISOString 方法。对象可自由使用参数 key 来过滤字符串化的方式。

#### 20.3.4.38 Date.prototype.toLocaleDateString (<var> [ reserved1 [， reserved2 ] ] </var>)

一个包含 ECMA-402 国际化 API 的 ECMAScript 实现必须按照规范 ECMA-402 中所定义的来实现 `Date.prototype.tolocaleDateString`。如果一个 ECMAScript 实现没有包含 ECMA-402 API，接下来的定义则应用于 `toLocaleDateString` 方法中。

这个函数返回一个 String。String 的内容是依赖于实现的，但其目的是根据宿主环境当前的约定，来方便的、可读的表示当前时区 Date 的日期部分。

这个方法可选参数的意义定义在 ECMA-402 APPI规范中；没有包含 ECMA-402 的实现不应使用这些参数做其他用途。

#### 20.3.4.39 Date.prototype.toLocaleString (<var> [ reserved1 [， reserved2 ] ] </var>)

一个包含 ECMA-402 国际化 API 的 ECMAScript 实现必须按照规范 ECMA-402 中所定义的来实现 `Date.prototype.toLocaleString`。如果一个 ECMAScript 实现没有包含 ECMA-402 API，接下来的定义则应用于 `toLocaleString` 方法中。

这个函数返回一个 String。String 的内容是依赖于实现的，但其目的是根据宿主环境当前的约定，来方便的、可读的表示当前时区 Date。

这个方法可选参数的意义定义在 ECMA-402 APPI规范中；没有包含 ECMA-402 的实现不应使用这些参数做其他用途。

#### 20.3.4.40 Date.prototype.toLocaleTimeString (<var> [ reserved1 [， reserved2 ] ]</var> )

一个包含 ECMA-402 国际化 API 的 ECMAScript 实现必须按照规范 ECMA-402 中所定义的来实现 `Date.prototype.toLocaleTimeString`。如果一个 ECMAScript 实现没有包含 ECMA-402 API，接下来的定义则应用于 `toLocaleTimeString` 方法中。

这个函数返回一个 String。String 的内容是依赖于实现的，但其目的是根据宿主环境当前的约定，来方便的、可读的表示当前时区 Date 的时间部分。

这个方法可选参数的意义定义在 ECMA-402 APPI规范中；没有包含 ECMA-402 的实现不应使用这些参数做其他用途。

#### 20.3.4.41 Date.prototype.toString ( )

执行以下步骤：

1.  令 O 等于当前 Date 对象。
2.  如果 O 没有内置 [[DateValue]]，则
    1.  令 tv 等于 NaN。
3.  否则，
    1.  令 tv 等于 [thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(O)。
4.  返回 [ToDateString](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-todatestring)(tv)。

注 1
对毫秒数为零的任意 Date 值 d，`Date.parse(d.toString())` 和 `d.valueOf()` 的结果相同。参见 [20.3.3.2](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-date.parse)。

注 2
`toString` 函数是特意设计为通用的；它不需要其 this 值必须为一个 Date 对象。因此，这个方法可以转换到其他类型的对象上。

#### 20.3.4.41.1 Runtime Semantics: ToDateString(<var>tv</var>)

执行以下步骤：

1.  断言: [Type](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-ecmascript-data-types-and-values)(tv) 为 Number。
2.  如果 tv 是 NaN，返回 `"Invalid Date"`。
3.  返回一个依赖于实现的字符串，根据当前时区以方便的、可读的形式将 tv 表示为日期和时间的组合。

#### 20.3.4.42 Date.prototype.toTimeString ( )

这个函数返回一个 String。String 的内容是依赖于实现的，但其目的是根据宿主环境当前的约定，来方便的、可读的表示当前时区 Date 的时间部分。

#### 20.3.4.43 Date.prototype.toUTCString ( )

这个函数返回一个 String。String 的内容是依赖于实现的，但其目的是根据宿主环境当前的约定，来方便的、可读的表示 UTC 的 [当前时间值](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)。

注
此函数的目的是为日期时间产生一个比 [20.3.1.16](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-date-time-string-format) 指定的格式更易读的字符串表示。而不用选择清楚的或易于机器解析的格式。如果一个实现没有一个首选的可读格式，建议使用 [20.3.1.16](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-date-time-string-format) 定义的格式，但用空格而不是“T”分割日期和时间元素。

#### 20.3.4.44Date.prototype.valueOf ( )

执行以下步骤：

1.  返回 [thisTimeValue](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-properties-of-the-date-prototype-object)(this value)。

#### 20.3.4.45Date.prototype [ @@toPrimitive ] ( <var>hint</var> )

这个函数是由 ECMAScript 语言操作符调用来将一个 Date 对象转换为一个原始值。hint 的合法值有 `"default"`，`"number"`，以及 `"string"`。Date 对象是 ECMAScript 中唯一一个将 `"default"` 与 `"string"` 看作等效的内置对象。其余 ECMAScript 内置对象都将 `"default"` 看作与 `"number"` 等效。

当 `@@toPrimitive` 被调用时传递了一个 hint 参数时，执行以下步骤：

1.  令 O 等于当前 value。
2.  如果 [Type](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-ecmascript-data-types-and-values)(O) 不是 Object，抛出一个 TypeError 异常。
3.  如果 hint 是字符串 `"string"` 或者是字符串 `"default"`，则
    1.  令 tryFirst 等于 `"string"`。
4.  否则如果 hint 是字符串 `"number"`，则
    1.  令 tryFirst 等于 `"number"`。
5.  否则，抛出一个 TypeError 异常。
6.  返回 OrdinaryToPrimitive(O, tryFirst)。

这个函数的 `name` 属性的值为 `"[Symbol.toPrimitive]"`。

这个属性的特性有 { [[Writable]]: false, [[Enumerable]]: false, [[Configurable]]: true }。

### 20.3.5 Date 实例的属性

Date 实例从 Date 原型对象继承属性。Date 实例同样有一个内置 [[DateValue]]。内置 [[DateValue]] 的值设置为当前 Date 对象的[时间值](http://www.ecma-international.org/ecma-262/7.0/index.html#sec-time-values-and-time-range)。

