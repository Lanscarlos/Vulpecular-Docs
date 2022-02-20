[postbg]bg9.png[/postbg]
[index]

[#1]首页

[#2]入门篇
*[#3]数据表示
*[#3]执行者 Sender
*[#6]命名空间 Namespace
*[#4]动作 Action
*[#5]变量 Namespace

[#11]进阶篇
*[#]选择结构
*[#]循环结构

[#]拓展篇
*[#]匿名动作 *
*[#]匿名代码块 Block

[/index]

[align=center][table]
[tr=#BA55D3][td][align=center][table]
[tr=#FF69B4][td][align=center][table]
[tr=#FFC0CB][td][align=center][table]
[tr=#E5EDF2][td][align=center][size=5][b]数据类型[/b][/size][/align][/td][/tr]
[/table][/align][/td][/tr]
[/table][/align][/td][/tr]
[/table][/align][/td][/tr]
[/table][/align]
[size=3]
在 Kether 中，我们通常使用 [b]*[/b] 来定义数据
例如 *true、*0、*1、*12138、*minecraft、*"Hello World!" 等等...

你可能会认为 *true 是布尔型中的 true 而 *0、*1、*12138 是整数型数据，分别代表了数字0，1和12138

但仔细研究会发现，这样定义的数据在 Kether 里都表示为 String 字符串型数据

PS: 如果有小伙伴还不是很了解 [b]基本数据类型[/b] 的话
有兴趣可以去看看菜鸟教程这篇关于基本数据类型的讲解
[url=https://www.runoob.com/java/java-basic-datatypes.html]https://www.runoob.com/java/java-basic-datatypes.html[/url]
[color=black][backcolor=black]当然不看也没有关系，只是理解起来可能会有点点难♂[/backcolor][/color]

我认为基本数据类型可以分为 布尔型、数值型、字符串型以及数组型 四种

具体可以查看下表
[/size]
[table]
[tr=#d3dfed]
[td][size=3][b] 类型 [/b][/size][/td]
[td][size=3][b] 在 Kether 中表示 [/b][/size][/td]
[td][size=3][b] 说明 [/b][/size][/td]
[/tr]

[tr=#f1f3f4]
[td][size=3] Boolean 布尔型 [/size][/td]
[td][size=3]  *true 或 *false [/size][/td]
[td][size=3]  true 表示为"真"
  false 表示为"假"
[/size][/td]
[/tr]

[tr=#d3dfed]
[td][size=3] Integer 整数型 [/size][/td]
[td][size=3]  *0、*1、*233、*12138 等... [/size][/td]
[td][size=3]  代表数字 [/size][/td]
[/tr]

[tr=#f1f3f4]
[td][size=3] String 字符串型 [/size][/td]
[td][size=3]  *minecraft
  *"Hello World!"、*牛蛙 等...
[/size][/td]
[td][size=3]  代表一段文本
  字符串前后可以选择加上 [b]英文引号[/b]
  ❗ [color=red]如果包含空格，则引号不可省略[/color]
[/size][/td]
[/tr]

[tr=#d3dfed]
[td][size=3] Array 数组型 [/size][/td]
[td][size=3]  [ *1, *3, *5, *7, *9 ]
  [ *农夫, *手艺人, *猎手 ]
  [ *你爱我, *我爱你, *mxbc甜蜜蜜 ]
  等...
[/size][/td]
[td][size=3]  一组有序的数据序列
  数据之间需要使用 [b]英文逗号[/b] 隔开
[/size][/td]
[/tr]

[/table]