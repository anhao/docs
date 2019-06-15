## XML 树结构

XML 文档形成了一种树结构，它从"根部"开始，然后扩展到"枝叶"。

## 一个 XML 文档实例

```xml
<?xml version="1.0" encoding="UTF-8"?>
<note>
<to>Tove</to>
<from>Jani</from>
<heading>Reminder</heading>
<body>Don't forget me this weekend!</body>
</note>
```

第一行是 XML 声明。它定义 XML 的版本（1.0）和所使用的编码（UTF-8 : 万国码, 可显示各种语言）。

下一行描述文档的**根元素**（像在说："本文档是一个便签"）：

`note`

接下来 4 行描述根的 4 个**子元素**（to, from, heading 以及 body）：

```xml
<to>Tove</to>
<from>Jani</from>
<heading>Reminder</heading>
<body>Don't forget me this weekend!</body>
```

最后一行定义根元素的结尾：

`</note>`



`xml` 的标签必须要闭合