# Java 解析 xml



## XML 的解析方式  `dom` 和 `sax`

### DOM 解析方式

 - 根据xml 的层级结构在内存分配一个树形结构，把xml 的标签，属性，文本都封装成对象
 - 缺点 : 如果文件过大，容易造成内存溢出
 - 优点：很方便实现增删改查

### SAX 解析方式
 - 采用事件驱动，边读边解析
 	- 从上到下一行一行的解析，标签->文本
 - 缺点：不能增删改查
 - 优点：不会造成内存溢出