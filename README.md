### <span style="color: #ff641c">Draft ECMA-262 (Ecma/TC39/2016/010)</span>
### <span style="color: #ff641c">7ᵗʰ Edition (第七版) / 2016.03.01</span>

# <span class="orange">ECMAScript® 2016 语言标准</span>

![MacDown logo](./pictures/ecma-logo.jpg)

# 版权声明

版权声明 © 2016 Ecma国际

这份文档和它可能的翻译版可以被复制并配备到别处，且对它的评论或解释或协助它实现的衍生作品也可以被完整或部分且没有任何形式的限制地编著、复制、出版、传播。这么做的前提是将版权声明和本章节包含到所有这样的复制版和衍生作品中。尽管如此，这份文档本身不能被以任何形式修改，包括移除其版权声明或其对Ecma国际的引用部分都是不允许的，除非是Ecma国际以开发任何文档或是可交付内容为目的需要(在这种情况下必须保留版权声明)，又或是根据需求将其翻译到除英语之外的其它语言。

本片翻译是 [Toxni](https://github.com/Toxni) 在业余时间翻译的，很多内容借用了  w3c 中文兴趣小组的 [这篇 ES5 中文译版](https://www.w3.org/html/ig/zh/wiki/ES5)。本翻译只做交流学习使用，遵守 [自由转载-非商用-非衍生-保持署名 (创意共享3.0许可证)](https://creativecommons.org/licenses/by-nc-nd/3.0/deed.zh)。

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

Allen Wirfs-Brock

ECMA-262 第六版本编辑者

Brian Terlson

ECMA-262 第七版本编辑者

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

*注意：内置函数包含例如 parseInt 和 Math.exp 这样的函数。标准的实现可能包含本标准中未包含的额外的内置函数。

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

TODO

### 6.1.7 对象类型

TODO

