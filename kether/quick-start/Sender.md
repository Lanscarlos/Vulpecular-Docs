---
description: 执行者
---

# 执行者 Sender

## 简介

Kether 脚本运行时插件开发者指定的一个执行对象，这个对象可能是玩家 (Player)，也可能是控制台对象，一些特殊情况下执行者也可能是一个空值，即开发者并没有指定执行对象

{% hint style="warning" %}

某些动作要求执行者是特定对象才可被执行，如果强行执行可能导致一些意外情况的发生

例如，当执行者不是玩家时，如果强行执行动作 [**player name**](https://kether.tabooproject.org/list.html#Name)，会报错：java.lang.IllegalStateException: No player selected. 

{% endhint %}