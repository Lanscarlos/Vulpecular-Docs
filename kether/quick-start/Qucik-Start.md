---
description: 快速了解 Kether 相关内容
---

# 快速入门

## 简介

> 这是我个人对 Kether 的研究心得，并不是官方教程<br>
> 如果有写的不恰当的地方欢迎指出，还请大佬轻喷 qwq 🐾

**Kether** 是坏黑哥哥的 [TabooLib](https://github.com/TabooLib/taboolib) 中的一款 **脚本语言** 模块

{% hint style="info" %}

[Kether 官方文档<br>https://kether.tabooproject.org/](https://kether.tabooproject.org/)

{% endhint %}

下面我们简单了解一下 Kether 的几个相关概念

## 执行者 Sender

Kether 脚本运行时插件开发者指定的一个执行对象，这个对象可能是玩家 (Player)，也可能是控制台对象，一些特殊情况下执行者也可能是一个空值，即开发者并没有指定执行对象

{% hint style="warning" %}

某些动作需要执行者是特定对象才可被执行，如果强行执行可能导致一些意外情况的发生

例如，当执行者不是玩家时，如果强行执行动作 [**player name**](https://kether.tabooproject.org/list.html#Name)，会报错：java.lang.IllegalStateException: No player selected. 

{% endhint %}

## 动作 Action

{% hint style="info" %}

在旧版本的 Kether 官方文档中，“**Action**” 一词翻译为 “**语句**”

而在目前新版本的 Kether 官方文档中，该词已更正为 “**动作**”

{% endhint %}

在 Kether 中，用来实现不同功能的语句称为动作

其中，动作也被分为 **公有动作** 以及 **私有动作**，关于这两者的区别，我会在下面介绍到 **命名空间** 时讲解

这里举两个最常用的动作例子：<br>
[**print <参数1>**](https://kether.tabooproject.org/list.html#Print) 在控制台输出指定信息
> print *Hello!<br>
> 输出内容：Hello!

[**tell <参数1>**](https://kether.tabooproject.org/list.html#Tell) 向执行者发送指定信息
> tell *"Hello World!"<br>
> 输出内容：Hello World!

## 返回值

大部分动作都会有它的返回值，返回值可能是任意类型，也可能是空值

例如
动作 [**player name**](https://kether.tabooproject.org/list.html#Name) 
当执行者是玩家时，会返回的就是玩家的名字

## 参数



## 命名空间 Namespace

语句被分为 **公有语句** 以及 **私有语句**