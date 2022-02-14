---
description: 欢迎来到 Vulpecular 的公开文档
---

# 概览

## 简介

本插件内部有一套可以自定义处理大多数事件的系统，其中也包括其他插件定义的事件

这使得我们可以更加方便的处理这些事件内容以及定义一些简单的小功能

例如
1. 玩家第一次进服给予奖励
2. 死亡惩罚 [ 扣除经验/金币 ]
3. 登录后传送到指定地点 [ 需要安装 Authme 插件 ]

## 特点

- 支持监听所有 Bukkit 事件，包括其他插件定义的事件<br>（如 Authme、MythicMobs、PlayerPoints 等）
- 支持用户对事件预处理
- 内置大量脚本参数，处理脚本时能更加便捷的访问事件的属性
- 支持用户自定义脚本参数
- 支持 JavaScript、Kether 脚本

## 缺点

- 事件处理需要用户至少掌握 JavaScript 或 Kether 其中一种脚本语法知识
    > 这里推荐使用更为简单的 [**Kether**](https://kether.tabooproject.org/) 脚本语言