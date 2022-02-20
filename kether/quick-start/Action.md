---
description: 快速了解 Kether 相关内容
---

# 动作 Action

{% hint style="info" %}

在旧版本的 Kether 官方文档中，“**Action**” 一词翻译为 “**语句**”

而在目前新版本的 Kether 官方文档中，该词已更正为 “**动作**”

{% endhint %}

## 简介

动作是指一段可以实现一个特定功能的语句，其语句结构大致为：<br>
`动作名 {参数1} {参数2...}`

我们也可以将多条语句写在一起：<br>
`动作1 {参数1} {参数2...} 动作2 {参数3} {参数4...}`<br>
需要注意的是，如果多条语句写在同一行，不同的动作语句之间需要使用 **空格符号** 分隔，否则动作2会与前面的参数2一起被视作整个参数，导致运行出错

此外，根据查阅文档得知，动作分为 **公有动作** 以及 **私有动作**，关于这两者的区别，我会在后面 **命名空间** 章节详细介绍

这里举两个最常用的动作例子：<br>
[`print {参数1}`](https://kether.tabooproject.org/list.html#Print) 在控制台输出指定信息
> print *Hello!<br>
> 输出内容：Hello!

[`tell {参数1}`](https://kether.tabooproject.org/list.html#Tell) 向执行者发送指定信息
> tell *"Hello World!"<br>
> 输出内容：Hello World!

更多动作内容请前往官网查看

## 动作返回值

在 Kether 中，在动作执行完成后，会返回一个值，返回值可能是任意类型，也可能是空值

这些返回值都有可能会作为参数而去为其他的动作服务

> 例如动作 [`player name`](https://kether.tabooproject.org/list.html#Name) <br>
> 当执行者是玩家时，其返回值便是玩家的名字

## 动作参数 Token / Action

通过查阅官方文档发现，绝大多数动作都需要一个或多个参数，只有少数情况是没有参数的

例如前面提到的 [`print {action}`](https://kether.tabooproject.org/list.html#Print) 就是一个典型的带参数动作，而形如 [`close`](https://kether.tabooproject.org/list.html#Close) 这一种就属于无参数动作

那么问题来了，要怎么书写参数呢？

参数的写法有很多种，这里最常用的参数写法便是使用 `*` 放在参数前面，即 `*参数`<br>
例如：`*1` &nbsp; `*10086` &nbsp; `*true` `*Hello` &nbsp; `*黑哥哥牛逼`

如果参数内含有空格，则需要在参数前后加上英文双引号 `"`，即 `*"参数"`<br>
例如：`*"Hello World!"` &nbsp; `*"Hello Kether!"`

此外参数还有一种列表写法<br>
使用中括号 `[` `]` 将多个参数包裹起来，即，`[ *参数1 *参数2 *参数3 ]`<br>
例如：`[ *1 *3 *5 ]` &nbsp; `[ *Hello *Kether ]` &nbsp; `[ *Huai *Hei *Niu *Bi ]`

此类写法仅用于需要为动作提供 **列表类型的参数** 的情况<br>
例如 [`all {action list}`](https://kether.tabooproject.org/list.html#All)
[`any {action list}`](https://kether.tabooproject.org/list.html#Any)


> [**check {action} {symbol} {action}**](https://kether.tabooproject.org/list.html#Check)<br>
> [**command {action} [as (console|player|op)]**](https://kether.tabooproject.org/list.html#Command)

## 动作嵌套

有些情况下，我们可能需要用到多个动作，它们往往会构成一种嵌套的结构

下面举几个例子来说：

## 匿名动作 *

顾名思义，就是没有被命名的动作，可能有人会很好奇动作怎么会没有名字

但通过查阅官方文档以及源码后发现，我们经常看到的带 “ **\*** ” 的参数，其本质上就是一种动作，只不过它并没有被命名。准确来说，它们都有一个共同的名字 “ **\*** ”，因此我习惯性称它们为 **匿名动作** 或者 **参数**。

常见的有：`*"Hello World"` `*1` `*0` `*233` `*true` `*heigegeNB`

为了验证这种想法，我们可以前往官方文档实际运行一下这类动作便知

{% hint style="info" %}

[Kether PlayGround<br>https://kether.tabooproject.org/playground.html](https://kether.tabooproject.org/playground.html)

{% endhint %}

![对比运行演示](../../resources/quick-start/14191722.png)

从结果来看，它们确实是一种动作，一种没有确定的名字，但带有返回值的特殊动作。

## 匿名代码块 Block

代码块