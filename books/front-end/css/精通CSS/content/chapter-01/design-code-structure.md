## 设计代码结构
#### 标记简史
* 使用有意义的标签
* 类应该用于相似的元素，这些元素可以出现在同一个页面的多个位置，而ID应该用于位唯一的元素
* 只要你发现类名出现重复的单词，比如news-head和news-foote，用过考虑是否可以把这些元素分解成他们的组成部分。这会让代码更加“组件化”。
* div实际上代表部分，他可以将文档分割成几个有意义的区域。所以要给div分配有意义的类。
* div可以用来对块级元素进行分组，而span可以用来对行内元素进行分组标识。

  | 下一节 [常用选择器](../chapter-02/selector.md) |
  | ---------- |