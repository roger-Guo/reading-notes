## 常用选择器
#### 组合器
* __`相邻兄弟选择器 +`__
* __`通用兄弟选择器 ~`__
#### 存在和值（Presence and value）属性选择器
* __`[attr]`__ 该选择器选择包含 attr 属性的所有元素，不论 attr 的值为何。
* __`[attr=val]`__ 该选择器仅选择 attr 属性被赋值为 val 的所有元素。
* __`[attr~=val]`__ 该选择器仅选择 attr 属性的值（以空格间隔出多个值）中有包含 val 值的所有元素，比如位于被空格分隔的多个类（class）中的一个类。
#### 子串值（Substring value）属性选择器
* __`[attr^=val]`__ 选择attr属性的值以val开头（包括val）的元素。
* __`[attr$=val]`__ 选择attr属性的值以val结尾（包括val）的元素。
* __`[attr*=val]`__ 选择attr属性的值中包含字符串val的元素。
#### 伪类
###### 当你希望样式在特定状态下才被呈现到指定的元素时
* __`:link`__ 所有尚未访问的链接
* __`:visited`__ 所有已经访问的链接
* __`:active`__ 它代表的是用户按下按键和松开按键之间的时间。需要把 :active的样式放在所有链接相关的样式后，这种链接伪类先后顺序被称为LVHA顺序: :link — :visited — :hover — :active。
* __`:checked`__ 任何处于选中状态的radio、checkbox、select元素中的option HTML元素。
* __`:disabled`__ 被禁用的元素
* __`:enabled`__ 不被禁用的元素
* __`:required`__  任意 <input> 元素表示任意拥有required属性在提交前的外观
* __`:optional`__  表示任意没有required属性的 <input> 或 <textarea> 元素使用它
* __`:read-only`__ 表示元素不可被用户编辑的状态
* __`:first-child`__ 一组兄弟元素中的第一个
* __`:last-child`__ 一组兄弟元素中的最后一个
* __`:first-of-type`__ 一组兄弟元素中其类型的第一个元素 作用应该和 __`:first-child`__ 相同
* __`:last-of-type`__ 一组兄弟元素中其类型的最后一个元素 作用应该和 __`:last-child`__ 相同
* __`:focus`__ 获取焦点的元素
* __`:invalid`__ 表示任何 <input> 或 <form> 元素的内容无法通过输入的类型设置的验证。
* __`:not(X)`__ 匹配不符合参数选择器X描述的元素
* __`:nth-child(n)`__ 匹配一组兄弟元素中第n个元素 n为正值
  * __`span:nth-child(-n+3)`__  匹配前三个子元素中的span元素。
* __`:nth-of-type(n)`__ 匹配一组兄弟元素中第n个元素 n为正值 作用与 __`:nth-child(n)`__ 相同
#### 伪元素
###### 伪元素前缀是两个冒号:: 
* __`::before`__ 行内元素 作为已选元素的第一个元素
* __`::after`__ 行内元素 作为已选元素的最后一个元素
* __`::first-letter`__ 一整块文字第一行的第一个字母
* __`::first-line`__ 一整块文字第一行
* __`::selection`__ 被用户高亮的部分(用鼠标选中等)


