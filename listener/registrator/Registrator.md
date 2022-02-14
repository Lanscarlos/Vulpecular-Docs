---
description: 用于监听事件的发生并将其传递给处理器
---

# 监听器

## 简介

## 基础

所有的监听模块都是是以 **YAML (.yml)** 文件格式配置、读取加载的

一个 YAML 文件内可以配置多个监听模块

## 路径

监听模块的存储路径为 **`<服务器根目录>/plugins/Vulpecular/listener/registrators/`**

插件会自动加载该路径下的所有 YAML 文件（包括文件夹在内）

{% hint style="info" %}

如果你不想加载某个 YAML 或 文件夹<br>
可以在文件名最前面加上 “ **#** ”，插件会自动跳过带有“ **#** ”的文件或文件夹，例如：
- #example.yml
- #directory

{% endhint %}

如果你是第一次使用插件，可以在路径内发现 #example.yml 以及 def.yml 文件

其中 #example.yml 是示例模板，里面配置的内容仅用来做说明，并不会被加载