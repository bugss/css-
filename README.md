# css-具现  头脑风暴

希望通过自定义一些定义来涵盖css中的一些问题.

对 bfc 层叠上下文 层叠顺序进行具现.

bfc  不是含有两个换行符的元素.  硬换行符,软换行符
换行符特性:
+ 换行
+ 元素后面的宽度充满一行

# bfc 元素流分类.  浮动层,常规流层,独自隔离层.
+ 元素都是一行一行的渲染,碰到换行符或者超过宽度会换行.
+ 浮动层会最先渲染.(注意碰到换行符号立即换行)
+ 浮动层会影响当前行中的其他行以及bfc常规流层在常规流中的位置.没有换行符号的情况都是一列一列的渲染.(浮动优先,影响常规bfc层).
+ 常规流一般都是有前后两个换行符号的.(常规流无视浮动层,独自隔离层,在常规bfc层处换行)

# margin 会受到换行符号影响
+ margin left top  跟right bottom 是两套.left 为负在上面行没有换行符的情况下,如果没有支撑,会渲染到上一层. left 负值的影响只在一行.
+ margin 上移行 对后面的元素是没有影响的.  margin-right 最多到margin box的最左边.
+ margin-left 着力点

margin 力壁.float:left+overflow:hidden  . 参考线. 位置可能会跟浮动位置取最大值. inline-box 的margin 参考线 跟常规文档流对象 不同.
