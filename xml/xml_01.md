# XML

ML 指可扩展标记语言（**eXtensible** **Markup** **Language**）。

XML 被设计用来传输和存储数据。

XML 很重要，也很容易学习。

```
<?xml version="1.0" encoding="UTF-8"?>
<note>
  <to>Tove</to>
  <from>Jani</from>
  <heading>Reminder</heading>
  <body>Don't forget me this weekend!</body>
</note>
```



## 什么是XMl?

- XML 指可扩展标记语言（EXtensible Markup Language）。
- XML 是一种很像HTML的标记语言。
- XML 的设计宗旨是传输数据，而不是显示数据。
- XML 标签没有被预定义。您需要自行定义标签。
- XML 被设计为具有自我描述性。
- XML 是 W3C 的推荐标准。

## XML 和 HTML 之间的差异

XML 不是 HTML 的替代。

XML 和 HTML 为不同的目的而设计：

- XML 被设计用来传输和存储数据，其焦点是数据的内容。
- HTML 被设计用来显示数据，其焦点是数据的外观。

HTML 旨在显示信息，而 XML 旨在传输信息。

## XML 不会做任何事情

也许这有点难以理解，但是 XML 不会做任何事情。XML 被设计用来结构化、存储以及传输信息。

下面实例是 Jani 写给 Tove 的便签，存储为 XML：

```xml
<note>
<to>Tove</to>
<from>Jani</from>
<heading>Reminder</heading>
<body>Don't forget me this weekend!</body>
</note>
```

上面的这条便签具有自我描述性。它包含了发送者和接受者的信息，同时拥有标题以及消息主体。

但是，这个 XML 文档仍然没有做任何事情。它仅仅是包装在 XML 标签中的纯粹的信息。我们需要编写软件或者程序，才能传送、接收和显示出这个文档。


## 通过 XML 您可以发明自己的标签
上面实例中的标签没有在任何 XML 标准中定义过（比如 <to> 和 <from>）。这些标签是由 XML 文档的创作者发明的。

这是因为 XML 语言没有预定义的标签。

HTML 中使用的标签都是预定义的。HTML 文档只能使用在 HTML 标准中定义过的标签（如 <p>、<h1> 等等）。

XML 允许创作者定义自己的标签和自己的文档结构。

## XML 不是对 HTML 的替代

**XML 是对 HTML 的补充。**

XML 不会替代 HTML，理解这一点很重要。在大多数 Web 应用程序中，XML 用于传输数据，而 HTML 用于格式化并显示数据。

对 XML 最好的描述是：

**XML 是独立于软件和硬件的信息传输工具。**

------

## XML 是 W3C 的推荐标准

XML 于 1998 年 2 月 10 日成为 W3C 的推荐标准。

如需了解有关 W3C XML 活动的更多信息，请访问我们的 [W3C 教程](https://www.runoob.com/)。

------

## XML 无所不在

目前，XML 在 Web 中起到的作用不会亚于一直作为 Web 基石的 HTML。

XML 是各种应用程序之间进行数据传输的最常用的工具。



