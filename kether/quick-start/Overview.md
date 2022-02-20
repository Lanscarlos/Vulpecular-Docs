[postbg]bg9.png[/postbg]
[index]

[#1]首页
[#]入门篇
[#3]Kether 初体验
[#4]数据类型与表示
[#5]动作 Action
[#6]变量 Variable
[#7]命名空间* Namespace

[#]拓展篇
[#]应用篇

[/index]

[quote]本教程是我用个人的研究心得总结出来的，可能有些地方讲的不是很好，欢迎各位指出！[/quote]

[align=center][table]
[tr=#E5EDF2][td][align=center][size=5][b] Kether [/b][/size][/align][/td][/tr]
[tr=#00a3d9][td][/td][/tr]
[/table][/align]
[size=3]
Kether 是黑哥哥的 TabooLib 内一款功能及其强大的脚本语言，由海螺等众多大佬开发，可以轻松实现诸多功能（如：发送动作栏或标题信息、改变玩家游戏模式、获取PAPI变量等等），它还拥有良好的拓展API，能让其他开发者更加轻松地开发出自己的动作语句。

目前，随着越来越多的插件开始使用 TabooLib 开发，很多插件也开始支持 Ketehr，由各类插件开发拓展的 Kether 语句也渐渐多了起来。

其中比较广为人知的可能当属 TrMenu，如果你曾使用过A神大佬的这款 TrMenu 菜单插件并查阅过这款插件文档的话，应该对 Kether 并不陌生。

我相信很多人都是从 TrMenu 开始接触到 Kether 的吧，但由于 Kether 目前并没有详细的教程，官方文档里也只有动作语句的示例，导致有些人刚开始接触 Kether 的时候无从下手，用 Kether 编写 TrMehu 菜单的时候频频报错（没错是我自己...），于是无奈放弃了这款神器，所以这里我想用我自己的研究心得，写一篇详细教程，让各位能在学习的同时不迷路！

[b]官方文档首页[/b] 🌐 https://kether.tabooproject.org/
[b]动作语句大全[/b] 🌐 https://kether.tabooproject.org/list.html
[b]在线运行环境[/b] 🌐 https://kether.tabooproject.org/playground.html
[/size]

[align=center][table]
[tr=#E5EDF2][td][align=center][size=5][b] 更新记录 [/b][/size][/align][/td][/tr]
[tr=#00a3d9][td][/td][/tr]
[/table][/align]
[size=3] [align=center] [spoiler] 由于文档还在编写，所以这里贴个更新记录~
[color=black][backcolor=black]其实是因为保存草稿的时候不小心点到发表了qwq~[/backcolor][/color]
[/spoiler] [/align]
[/size]

[page]

[page]

[align=center][table]
[tr=#E5EDF2][td][align=center][size=5][b] Kether 初体验 [/b][/size][/align][/td][/tr]
[tr=#00a3d9][td][/td][/tr]
[/table][/align]
[size=3]
在我们开始学习 Kether 之前，我们不妨先来玩一玩 Kether。熟悉一下大概内容。

接下来我会列举一些常用的 Kether 语句，你可以前往官方文档在线运行这些语句并查看结果
🌐 https://kether.tabooproject.org/playground.html
PS：这里建议最好不要复制粘贴语句过去，自己打出来的才是认真学习的好孩子呐~

准备好了吗？要来咯♂

[b]向控制台输出信息[/b]
[code] print *"Hello World!" [/code] [spoiler] [code] Hello World!
---
运行结果: null
[/code] [/spoiler]

[b] 判断两个数的大小 [/b]
[code] check *16 > *12 [/code] [spoiler] [code]
---
运行结果: true
[/code] [/spoiler]

[b] 简单的加法 1 + 2 [/b]
[code] math add [ *1 *2 ] [/code] [spoiler] [code]
---
运行结果: 3
[/code] [/spoiler]

[b] 生成 0~10 以内的随机有理数，可以多运行几次看看结果 [/b]
[code] random 10 [/code] [spoiler] [code]
---
运行结果: 8.492791270517468
[/code] [code]
---
运行结果: 7.065020256386402
[/code] [code]
---
运行结果: 2.002535878403112
[/code] [code]
---
运行结果: 4.217747232415446
[/code] [code]
---
运行结果: 1.6381617418678152
[/code] [/spoiler]

[b] 判断大小并提示 [/b]
[code] if check *1.18 > *1.16 then *"1.18比1.16大！" else *"怎么可能？" [/code] [spoiler] [code]
---
运行结果: 1.18比1.16大！
[/code] [/spoiler]

[b] 将有理数数转变成整数 [/b]
[code] type int *12.34 [/code] [spoiler] [code]
---
运行结果: 12
[/code] [/spoiler]

[b] 将整数转变成有理数 [/b]
[code] type double *12 [/code] [spoiler] [code]
---
运行结果: 12
[/code] [/spoiler]

怎么样，是不是感觉[s]很好玩？[/s]很费脑？
不用担心，不妨接着往下看~我会慢慢给你讲解~
[/size]

[page]

[quote] 这一章节我们讲解一下 [b] 数据的类型 [/b] 以及 [b] 数据的表示 [/b][color=black][backcolor=black]赶时间的可以直接跳到最后看总结[/backcolor][/color][/quote]

[align=center][table]
[tr=#E5EDF2][td][align=center][size=5][b] 数据的类型 [/b][/size][/align][/td][/tr]
[tr=#00a3d9][td][/td][/tr]
[/table][/align]
[size=3]
先来给大伙介绍一下在 Kether 中可能会用到的数据类型。
不必紧张，我会尽量说的通俗一点

[size=4] [b] 一、布尔型 Boolean [/b] [/size]
    一种经常用要用在判断语句中的数据类型。
    只有两个取值：true 与 false ，分别代表“真”和“假”

[size=4] [b] 二、整数型 Integer [/b] [/size]
    可以理解为整数，包括正整数，负整数和零。
    整数型 Integer 可简写为：Int，简称：整型
    例如： 0,、1、-233、12138
    💡 拓展小知识：
    除了 [b]整型 Int[/b] 外还有 [b]短整型 Short[/b] 和 [b]长整型 Long[/b]，它们的区别在于它们表示的范围不同 [align=center][table=95%]
    [tr][td][b]类型[/b][/td][td][b]最小值[/b][/td][td][b]最大值[/b][/td][/tr]
    [tr][td]短整型 Short[/td][td]-32768（-2^15）[/td][td]32767（2^15 - 1）[/td][/tr]
    [tr][td]整型 Int[/td][td]-2,147,483,648（-2^31）[/td][td]2,147,483,647（2^31 - 1）[/td][/tr]
    [tr][td]长整型 Long[/td][td]-9,223,372,036,854,775,808（-2^63）[/td][td]9,223,372,036,854,775,807（2^63 -1）[/td][/tr] [/table][/align]
[size=4] [b] 三、浮点数 Float/Double [/b] [/size]
    可以理解为有理数，带有有限位小数的有理数。
    例如： 1.0、1.28、2.7、-5.3、1.18
    Float 表示单精度浮点数
    Double 表示双精度浮点数

[size=4] [b] 四、字符串型 String [/b] [/size]
    可以简单理解为是文本类型，主要用于表示一段文字内容。
    如： " Hello World！ "、" 黑哥哥nb "
    请注意，形如 "123"、"12.34" 这些并不是整数型和浮点型数据，是不能直接进行数字大小判断的
    但可以先转换成整数型和浮点型再判断大小

[size=4] [b] 五、数组型 Array [/b] [/size]
    有序的元素序列，可以理解为 同类型的数据序列
    如：[ 1, 3, 0, 5, 4, 6, 4 ]
    [ 1.18, 1.0, 2.5, 2.6  ]
    [ 矿工, 农夫, 手艺人, 猎手 ]
    [ 你爱我, 我爱你, mxbc甜蜜蜜 ]

💡 如果对数据类型感兴趣的读者不妨去看看菜鸟教程这篇关于 [b]Java 基本数据类型[/b] 的讲解，可能会对你有些帮助 🌐 [url=https://www.runoob.com/java/java-basic-datatypes.html]https://www.runoob.com/java/java-basic-datatypes.html[/url]
[/size]

[align=center][table]
[tr=#E5EDF2][td][align=center][size=5][b] 数据的表示 [/b][/size][/align][/td][/tr]
[tr=#00a3d9][td][/td][/tr]
[/table][/align]
[size=3]
上面介绍了几种常见用的数据类型，那这些数据在 Kether 中应该如何表示呢？
如果有玩过前面[b] Kether 初体验 [/b] 章节的小伙伴应该马上就知道
只需要在数据前面加上[b] * [/b]号就可以了，例如：
[b] *2 [/b]、[b] *12.34 [/b]、[b] *true [/b]、[b] *"Hello World!" [/b]、[b] *手艺人 [/b]
PS: ❗ 如果字符串内含有空格，则需要在前后加上引号！
这样表示虽然没错，但这里有一个小细节可能容易被忽视

先来问一个问题：你认为 [b] *2 [/b] 在 Kether 中是什么类型的数据呢？整型？浮点型？还是字符串型？
如果你仔细查阅过官方文档，应该马上能想到答案
[spoiler] [size=3] 答案揭晓：[b] 字符串型 [/b] [/size] [/spoiler]
其实官方文档有写到一个原生动作：
[quote] literal {token} | *{token}
创建并返回一个字符串。
🌐 [url=https://kether.tabooproject.org/list.html#Literal]https://kether.tabooproject.org/list.html#Literal[/url][/quote] 这里 literal {token} 与 *{token} 只是写法上不同，本质是同一个动作
所以 *2 也就等同于 literal 2
而这个动作会将你在参数 {token} 处写的东西，转化为字符串返回
因此无论你写的是 *2 或是 *12.34 还是其他什么都会被视为字符串

这里你可能会有疑惑：那为何 [b] check *16 > *12 [/b] 两边都是字符串却又可以得到正确结果而不报错
这是因为在 TabooLib 内有一个很强的工具类 [url=https://github.com/TabooLib/taboolib/blob/master/common/common-util/src/main/java/taboolib/common5/Coerce.java]taboolib.common5.Coerce[/url]
Check 动作会将左右两边的字符串用这个工具类转化为 Double 类型的浮点数后再来做大小判断
不仅仅是 Check 如此，很多 TabooLib 提供的动作都会进行类型转换（例如：math）

咳咳，扯远了，拓展这些知识主要是想提醒各位
以后用到 check 作判断的时候需要多留心一下左右两边的数据类型问题
当然一般情况下是不会出什么问题的[color=black][backcolor=black]只是怕万一碰到一些奇奇♂怪怪的情况也不好说对吧[/backcolor][/color]

话说回来，如果我想将 *2 转换为整数型该怎么做呢？
查阅一下官方文档，你会找到这样一条动作：
[quote] type {token} | type {type} {action}
创建并返回一个最接近的字符串、整型、长整型、浮点数 或 布尔值。
🌐 [url=https://kether.tabooproject.org/list.html#Type]https://kether.tabooproject.org/list.html#Type[/url]
[/quote] 其中参数 {type} 可以填入 int, long, float, double, boolean 这些值
那么将 *2 转化成整数类型我们就可以这样写：type int *2
当然第一个参数 {type} 是可以省略的：type *2

除此之外我们也可以将浮点数转化成整数，例如：type int *12.34
此时第一个参数 {type} 就不可省略了，否则会自动将 *12.34 转化成浮点数

噢对了，应该没有人会这样写吧？ (～￣▽￣)～
type int *"Hello World!"
至于会发生什么，你们可以自己去试试

接下来我猜你会想问，如果想表示数组型的数据那应该怎么写呢？
这里先卖个关子~ 下一章节会回答你的噢~

好了，接下来我们稍微总结一下
[/size]

[align=center][table]
[tr=#E5EDF2][td][align=center][size=5][b] 总结 [/b][/size][/align][/td][/tr]
[tr=#00a3d9][td][/td][/tr]
[/table][/align]
[size=3]
[size=4][b]数据的类型[/b][/size]
[list]
[*] 布尔型 Boolean
[*] 整数型 Integer
[*] 浮点型 Float / Double
[*] 字符串型 String
[*] 数组型 Array
[/list]
[size=4][b]数据的表示[/b][/size]
[list]
[*]使用 [b]literal {token}[/b] 动作可以创建字符串数据，并且还可以简写成 [b]*{token}[/b]
[*]使用 [b]type {type} {action}[/b] 动作可以对数据进行类型转换
[/list]
[/size]

[page]

[quote] 在旧版本的 Kether 官方文档中，“[b]Action[/b]” 一词翻译为 “[b]语句[/b]”
而在目前新版本的 Kether 官方文档中，该词已更正为 “[b]动作[/b]” [/quote]

[align=center][table]
[tr=#E5EDF2][td][align=center][size=5][b] 动作 Action [/b][/size][/align][/td][/tr]
[tr=#00a3d9][td][/td][/tr]
[/table][/align]
[size=3]
动作是指一段可以实现一个特定功能的语句，其语句结构大致为：
[code] 动作名 {参数1} {参数2...} [/code]
我们也可以将多条语句写在一起：
[code] 动作1 {参数1} {参数2...} 动作2 {参数3} {参数4...} [/code]
需要注意的是，如果多条语句写在同一行，不同的动作语句之间需要使用 空格符号 分隔，否则动作2会与前面的参数2一起被视作整个参数，导致运行出错

此外，根据查阅文档得知，动作分为 [b]公有动作[/b] 以及 [b]私有动作[/b]，关于这两者的区别，我会在后面 [b]命名空间[/b] 章节具体分析
[/size]

[align=center][table]
[tr=#E5EDF2][td][align=center][size=5][b] 动作返回值 [/b][/size][/align][/td][/tr]
[tr=#00a3d9][td][/td][/tr]
[/table][/align]
[size=3]
我们知道，当一个动作执行完成后，会返回一个值
这个返回值可能是任意类型的数据，当然也有可能是空值（即 null）
我们上一节讲过的 [b]literal {token}[/b] 返回值就是字符串类型的，

像 初体验 那一节里提到的 [url=https://kether.tabooproject.org/list.html#Print]Print[/url] 动作，它的返回值则是 空值null
而 [url=https://kether.tabooproject.org/list.html#Check]Check[/url] 动作，返回的是布尔型，常用在判断语句当中

不同的动作，返回值类型也不同，具体可以直接查阅官方文档

有些时候，我们可能需要留意这些会返回空值的动作，因为如果将这些动作的返回值用在参数当中，可能会产生一些不可预料的事情 [s]（例如：让大伙都喜闻乐见的报错）[/s]
[/size]

[align=center][table]
[tr=#E5EDF2][td][align=center][size=5][b] 动作的参数 [/b][/size][/align][/td][/tr]
[tr=#00a3d9][td][/td][/tr]
[/table][/align]
[size=3]
动作的参数目前主要分为三类：[b]{token}[/b]、[b]{action}[/b]、[b]{action list}[/b]

[size=4] [b]一、{token} 参数[/b] [/size]
看到这个，相信你第一反应就想起前面讲过的 literal {token} 动作了吧
这里举几个例子，你可能就能看懂了
[quote] call {token}
call [b]function_0[/b]
🌐 [url=https://kether.tabooproject.org/list.html#Call]https://kether.tabooproject.org/list.html#Call[/url]
[/quote]
[quote] goto {token}
goto [b]function_0[/b]
🌐 [url=https://kether.tabooproject.org/list.html#Goto]https://kether.tabooproject.org/list.html#Goto[/url]
[/quote]
下面这个例子可能比较复杂，实在看不懂的同学可以先跳过
[quote] sound {token} [by {double} {double}]
将文本作为音效播放，默认音量与音调均为 1.0。
sound [b]AMBIENT_CAVE[/b]
sound [b]AMBIENT_CAVE[/b] by 1 1
sound [b]resource:custom.sound[/b] by 1 1
🌐 [url=https://kether.tabooproject.org/list.html#Sound]https://kether.tabooproject.org/list.html#Sound[/url]
[/quote]
token 参数其实很简单，只需要填入相应的字符串即可，当然，也不能乱填的啦，如果不知道填什么不妨先看看官方文档~
 ❗ 如果你填入的内容里包含空格的话，请一定要记得在前后加上[b]英文引号[/b]
[code] goto 'function 0'
literal "Hello World!"
*"有 空格 记得加上 英文引号！"
[/code]

[size=4] [b]二、{action} 参数[/b] [/size]
首先我们看到里面 “[b]action[/b]” 这个词，翻译过来不就是 “[b]动作[/b]” 吗？
言外之意就是让我们填入动作，而且必须是一个完整的动作！

我们在上面讲过，每一个动作都有返回值，那么很显然，将动作填入参数位置当中，本质上是在使用这个动作的返回值

还记得 初体验 中的第一个例子吗？

[b]向控制台输出信息[/b]
[code] print *"Hello World!" [/code] [spoiler] [code] Hello World!
---
运行结果: null
[/code] [/spoiler]
这里面其实包含有两个动作
第一个是 [b]print {action}[/b] [url=https://kether.tabooproject.org/list.html#Print]🌐[/url] 向控制台输出信息，返回值是 空值null
第二个是 [b]literal {token}[/b] [url=https://kether.tabooproject.org/list.html#Literal]🌐[/url] 的简写版 [b]*{token}[/b]，返回的是字符串
我们实际上是先等待 literal 动作执行完成后给我们返回 “Hello World！” 字符串，然后 print 动作再去获取 literal 的返回值 “Hello World！” 作为参数，最后向控制台输出这段字符串

[size=4] [b]二、{action list} 参数[/b] [/size]
首先看到 action，就知道填的东西肯定少不了动作，这个毫无疑问
那这个 list 是什么东东？这里可以译为 [b]列表[/b]
那应该大致清晰了，填入[b]动作列表[/b]
老规矩，还是先来看一个例子：
[quote] array {action list}
将动作列表的所有返回值作为集合返回。
array [b][ *1 *2 *3 ][/b]
array [b][ *1 *1 *2 *3 *4 ][/b]
🌐 [url=https://kether.tabooproject.org/list.html#Array]https://kether.tabooproject.org/list.html#Array[/url]
[/quote]
通过比对一下就知道，[ *1 *2 *3 ] 就是 {action list} 的写法之一
不难发现，{action list} 其实就是将多个动作写到一起，并且前后用中括号括住，使之变成动作列表

这时候就会有小伙伴问了：诶这个跟我们前面讲数组型时的举例 [ 1, 3, 5 ] 好像啊
那数组型数据可不可以都写成这种 {action list} 形式呀？
可以是可以，但是需要注意的是
别看它俩长得很像，实际上它俩还是有一定区别的

先来看个例子
[code] print [ *1 *2 *3 ]
运行结果: Isolate literal "1" is not end of block, maybe a misspelled action? [/code]
[code] print array [ *1 *2 *3 ]

[1, 2, 3]
---
运行结果: null[/code]
前面我们探讨过了 [b]*2[/b] 与 [b]整数2[/b] 的区别
前者是字符串，后者是整数
想要得到 整数2 就需要使用 [b]type int *2[/b] 进行转换

这里也是一样 [b][ *1 *2 *3 ][/b] 与 [b][ 1, 2, 3 ][/b] 之间存在本质上的区别
前者是[b]动作列表[/b]（List<ParsedAction>），后者是[b]数组[/b]（也可以说是集合）
想要得到 [b][ 1, 2, 3 ][/b] 就需要借助上面这个动作将 [b]{action list}[/b] 转化为真正的数组型数据，即
[code] array [ *1 *2 *3 ] [/code]

至此，三种类型都已经讲解完了
噢这里顺便提一下
[quote] random {double} [to {double}] | random {action}
将动作列表的所有返回值作为集合返回。
random [b]10[/b]
random 1 to 10
random array [ *1 *2 *3 *4 *5 ]
🌐 [url=https://kether.tabooproject.org/list.html#Random]https://kether.tabooproject.org/list.html#Random[/url]
[/quote]
这里我们看到 random 其中一种写法 [b]random {double}[/b]，其中参数 [b]{double}[/b] 是我们前面讲过的浮点型数据 Double，所以这里我们可以像 [b]{token}[/b] 那样，直接填入数据就可以了，当然像这样 [b]random 10[/b] 填入整数也是可以的
除了 {double} 这种还有 {int}、{float} 等，但这些其实都可以归类为 [b]{token}[/b]
不过这些只能填入数字，不能填什么奇奇怪怪的符号噢~

最后我们来思考一个问题：
[quote] math {symbol} {action list}
math [b]add[/b] [ *1 *2 *3 ]
math [b]mul[/b] [ *1 *2 *3 ]
🌐 [url=https://kether.tabooproject.org/list.html#Math]https://kether.tabooproject.org/list.html#Math[/url]
[/quote]
这里的 [b] {symbol} [/b] 是什么类型呢？
[spoiler] [size=3] 答案是 [b] {token} 类型 [/b] [/size] [/spoiler]

[/size]

[align=center][table]
[tr=#E5EDF2][td][align=center][size=5][b] 总结 [/b][/size][/align][/td][/tr]
[tr=#00a3d9][td][/td][/tr]
[/table][/align]
[size=3]
[list]
[*] 动作的结构：[b]动作名 {参数1} {参数2...}[/b]
    [*] 动作的连用：[b]动作1 {参数1} {参数2...} 动作2 {参数3} {参数4...}[/b]
    [*] 动作返回值：可能是任意类型的值，也可能是空值
    [*] 动作的参数类型：
[list]
[*][b]{token}[/b] —— 填入相应的字符串
[*][b]{action}[/b] —— 填入一个完整的动作
[*][b]{action list}[/b] —— 填入多个完整的动作组成动作列表
[/list]
[/list]
[/size]

[page]

[align=center][table]
[tr=#E5EDF2][td][align=center][size=5][b] 变量 Variable [/b][/size][/align][/td][/tr]
[tr=#00a3d9][td][/td][/tr]
[/table][/align]
[size=3]
在 Kether 中，任何动作的返回值都是可以被我们临时储存起来，方便再次使用的，我们一般将其称为变量

需要注意的是，储存起来的变量只能在当前正在运行的 Kether 中使用，当 Kether 语句全部执行完毕后，储存起来的变量将会被释放。你无法在下一次运行 Kether 时去使用上一次运行储存的变量，这是不允许的。（除非你去改插件内部的代码）

当然，在一些插件提供的 Kether 运行环境中（例如 TrMenu 提供的 Kether 运行环境），可能在 Kether 运行前就已经给我们提供了一些变量，可以直接使用
[/size]

[align=center][table]
[tr=#E5EDF2][td][align=center][size=5][b] 定义变量 Variable Set [/b][/size][/align][/td][/tr]
[tr=#00a3d9][td][/td][/tr]
[/table][/align]
[size=3]
这里讲解一下如何储存变量
[quote] set {token} {token} | set {token} to {action}
将变量设置为基本类型或一个动作的返回值。
set [b]test[/b] yes
set [b]test[/b] to *yes
🌐 [url=https://kether.tabooproject.org/list.html#Variable_Set]https://kether.tabooproject.org/list.html#Variable_Set[/url]
[/quote]我们可以看到，这里 Set 动作有两种写法
写法一是将第二个参数 {token} 作为字符串储存起来
写法二是将动作返回值 {action} 储存起来，储存的数据类型取决于动作返回值
无论哪种写法，变量名都是第一个 {token} 参数
以上写法都是将 “yes” 储存到名为 “test” 的变量当中
 ❗ 注意，在使用第二种写法时，请不要漏掉关键词 “to”

一般第二种写法我们会用的比较多
[code] set sum to math add [ *2 *3 *4 ]
将 2+3+4 得到的结果储存在变量 sum 中

set num to random 10
将 random 动作产生的 0~10 以内的随机数储存在变量 num 中
[/code]
如果你重复使用[b]同一个变量名[/b]来储存数据，那么会将覆盖上一次存储的数据
[code] set str to *Hello
将 Hello 储存在变量 str 中

set str to *World
将 World 储存在变量 str 中
此时会覆盖掉前面储存的 Hello 这个值
[/code]
这里稍微提一下，Kether 里的变量名并没有像 Java、Kotlin 编程语言那样有那么多那么严格的规定
事实上，变量名写什么都是可以的，包括空格、中文以及特殊符号都是允许的（原理其实不复杂，Kether 是通过类似键值对这种类型来储存变量的，键的类型恰好是 String，所以理论上你填什么都可以）
但跟代码打了这么久交道，这里我还是建议你尽量使用符合规则的变量名吧（例如：[b]数字、字母和下划线[/b]）
实在不行中文变量名也可以（你看着舒服就行）
[color=black][backcolor=black]你硬是要用奇奇♂怪怪的变量名我也拦不住你对吧 awa[/backcolor][/color]
 ❗ 注意，变量名含有空格请不要忘记加上[b]英文引号[/b]
[/size]

[align=center][table]
[tr=#E5EDF2][td][align=center][size=5][b] 获取变量 Variable Get [/b][/size][/align][/td][/tr]
[tr=#00a3d9][td][/td][/tr]
[/table][/align]
[size=3]
接下来我们看看如何获取变量
[quote] get {token} | &{token}
获取变量。
get [b]test[/b]
[b]&test[/b]
🌐 [url=https://kether.tabooproject.org/list.html#Variable_Get]https://kether.tabooproject.org/list.html#Variable_Get[/url]
[/quote]
我们可以看到，这里 Get 动作也有两种写法，都是在获取变量 test 储存的值
显然第二种更加简洁，而且从形式上看是不是很像 literal 的 *{token} 写法
所以，如果你的变量名内含有空格时，请不要忘记加上[b]英文引号[/b]

这里举几个变量定义与获取的例子
[code] set random to type int random 10
将 random 动作获取的随机数转化成 Int 并储存在变量 random 中

print math mul [ *2 &random *3 ]
将 2、变量random、3 的值相乘后输出到控制台
[/code]
[/size]

[align=center][table]
[tr=#E5EDF2][td][align=center][size=5][b] 总结 [/b][/size][/align][/td][/tr]
[tr=#00a3d9][td][/td][/tr]
[/table][/align]
[size=3]
[size=4][b]一、定义变量[/b][/size]
    1. set {token} {token}
    2. set {token} to {action}

[size=4][b]二、获取变量[/b][/size]
    1. get {token}
    2. &{token}
[/size]

[page]

[quote] 这一节的内容可能会有一点点难，实在看不懂的话可以先跳过 [/quote]

[align=center][table]
[tr=#E5EDF2][td][align=center][size=5][b] 命名空间* Namespace [/b][/size][/align][/td][/tr]
[tr=#00a3d9][td][/td][/tr]
[/table][/align]
[size=3]
命名空间是 Kether 代码内部的概念，这里简单介绍一下

首先命名空间可能需要分开为两个概念来讲：[b]运行环境的命名空间[/b] 和 [b]动作所属的命名空间[/b]


[size=4] [b] 一、运行环境的命名空间 [/b] [/size]

先来解释一下运行环境是什么，担心有些小伙伴不理解

我们都知道，Kether 语句无论你怎么写它都是一串文本，并不能直接执行
要执行它们，你还必须先解析 Kether 语句，然后通过 Kether 运行环境才能真正执行这些语句，并看到最终效果
那解析要怎么解析呢？运行环境又要如何配置呢？
这些问题，都不需要你来操心，因为插件开发者都已经帮你写好了
就好比你在 TrMenu 里使用 Kether 语句
你只需要提供写好的 Kether 语句文本
剩下解析语句以及提供运行环境的工作都是由 TrMenu 来完成的

好了，说回正题
在运行环境内有一个叫命名空间的东西，它是列表类型(List<String>)的数据，你也可以通俗的理解成是数组，一般由插件开发者来指定内容。它定义了当前运行环境的命名空间范围，而这可能会影响到一些动作的正常执行


[size=4] [b] 二、动作所属的命名空间 [/b] [/size]

每一个动作在插件内部被定义的时候有几个参数需要由插件开发者来指定
这里我们挑其中两个参数来讲解：namespace 与 share

参数 [b]namespace[/b] 就是动作所属的命名空间，指明了该动作所属于哪个命名空间之下
一般情况下为插件名的小写。例如：
插件 Adyeshach 提供的大多数动作的命名空间都是 “adyeshach”
而插件 Chemdah 提供的大多数动作的命名空间都是 “chemdah”
当然也有一些例外情况：
例如插件 Zaphkiel 提供的部分动作命名空间是 “zaphkiel”，而另一部分动作则是 “zaphkiel-internal”

参数 [b]share[/b] 的类型是布尔型，定义了这个动作是否允许共享，你也可以理解为是公有还是私有
当 share 的值是 true 时，则为公有，值是 false 时则为私有
因此动作在官方文档里也被分为 [b]公有动作[/b] 和 [b]私有动作[/b]
（原生动作是定义在 Kether 最底层的，不存在上述说的两个属性）

[b]share[/b] 这个参数决定了该动作能否跨命名空间使用
简单来说：
如果该动作所属的命名空间并不在当前运行环境的命名空间之内
那么私有动作将无法在当前允许环境被正常执行
而公有动作不受任何影响

举例：
假如当前运行环境的命名空间为 [ adyeshach, zaphkiel ]
那么由 Chemdah 提供的私有动作 [url=https://kether.tabooproject.org/list.html#Cancel]cancel[/url] 将无法正常执行
因为 cancel 动作的命名空间是 “chemdah”，但运行环境的命名空间里并没有 “chemdah”，因此后台可能会报错：
[code] [14:56:14 WARN]:  taboolib.library.kether.LocalizedException$Concat: Line 1 of block "main": cancel
[14:56:14 WARN]: Unknown action cancel
意思未知的动作 cancel，系统认为 cancel 这个动作没有被定义，所以找不到~ [/code]
但假如 cancel 是公有动作，则不会受影响
[/size]

[align=center][table]
[tr=#E5EDF2][td][align=center][size=5][b] 命名空间的意义 [/b][/size][/align][/td][/tr]
[tr=#00a3d9][td][/td][/tr]
[/table][/align]
[size=3]
看到这里，你可能会开始疑惑，为什么要弄命名空间还有公有私有这些东西呢？
我认为，一方面是用来隔离同名的动作
比如：Chemdah 与 TrMenu 都各自有一个同名的动作 [url=https://kether.tabooproject.org/list.html#Variable]Variable[/url]
当你的运行环境命名空间内两者都有时：[ chemdah, trmenu ]，问题来了，动作 Variable 应该解析成哪一个呢？
它有可能被解析成 Chemdah 的动作，也有可能被解析成 TrMenu 的动作，这不就冲突了吗？

另一方面，Kether 语句的解析完全是由相关插件来完成的，其运行环境也是由相关插件提供的
你在 TrMenu 里使用 Kether，那么语句解析以及提供运行环境的工作都是由 TrMenu 来完成的
而一些特殊的动作可能必须依赖于原生插件提供的运行环境
比如：
Chemdah 提供的大多数动作都是用来处理对话以及任务的
而你将这些动作放到 TrMenu 中去执行时，由于 TrMenu 没法提供 Chemdah 的对话和任务相关数据
这不但起不到任何作用，反而还会引来一堆报错~
只有 Chemdah 提供的运行环境才能为这些动作提供相关数据

所以，命名空间在一定程度上避免了不同插件动作之间产生冲突，以及动作的不合理使用等等问题
[color=black][backcolor=black]我只能说，这设计简直太强了好吧！膜拜大佬！！[/backcolor][/color]
[/size]

[align=center][table]
[tr=#E5EDF2][td][align=center][size=5][b] 命名空间的导入与释放 [/b][/size][/align][/td][/tr]
[tr=#00a3d9][td][/td][/tr]
[/table][/align]
[size=3]
目前来说，动作的命名空间是没有办法更改的，因为它已经在插件代码里写死了
但我们可以去修改运行环境的命名空间，具体怎么操作呢？
这里就需要用到两个动作：Import 和 Release
这两个动作目前只能通过查看源码得知，并不能在官方文档里找到相关信息

这里还是提个醒，如果没什么必要还请不要随便改动命名空间

[quote] import {token}
导入新命名空间。
import trmenu
import adyeshach
[/quote]

[quote] release {token}
释放命名空间。
release trmenu
release adyeshach
[/quote]
这两个动作的使用并不复杂，这里我就不多说了~
[/size]

[align=center][table]
[tr=#E5EDF2][td][align=center][size=5][b] 总结 [/b][/size][/align][/td][/tr]
[tr=#00a3d9][td][/td][/tr]
[/table][/align]
[size=3]
[size=4][b]一、运行环境的命名空间[/b][/size]
    定义了当前运行环境的命名空间范围，其内容可能会影响到一些动作的正常执行

[size=4][b]二、动作所属的命名空间[/b][/size]
    指明了该动作所属于哪个命名空间之下，一般情况下为插件名的小写。
    此外，share 参数决定了该动作是 私有动作 还是 公有动作

[size=4][b]三、命名空间的意义[/b][/size]
    一定程度上避免了不同插件动作之间产生冲突，以及动作的不合理使用等等问题

[size=4][b]四、命名空间的导入与释放[/b][/size]
    1. import {token}
    2. release {token}



[/size]