---
description: 快速创建一个自定义事件处理系统
---

# 快速入门

## 基础

### 什么是监听模块

> 监听事件的发生的模块

当某些事件发生时，我们希望对这些事件进行处理，这时候我们就需要使用监听模块去监听这些事件的发生，监听器会将整个事件内容传递到处理模块，以便让处理模块去做出相应的处理

例如我们希望在玩家加入游戏时向玩家发送一句问候语，这时我们便需要去监听**玩家加入游戏**这个事件，从而让处理模块向玩家发送问候语

### 什么是处理模块

> 使用脚本语言处理相应事件的模块

当监听模块将事件内容传递过来时，可以对事件作出相应的处理

例如上面提到的例子，我们希望在玩家加入游戏时向玩家发送一句问候语，当监听器将**玩家加入游戏**事件传递过来时，我们便可以通过编写**脚本**语句去向玩家发送问候语

## 文件格式

所有的监听和处理模块都是是以 **YAML (.yml)** 文件格式配置、读取加载的

一个 YAML 文件内可以配置多个监听模块

## 存储路径

监听模块的路径为 **`<服务器根目录>/plugins/Vulpecular/listener/registrators/`**

处理模块的路径为 **`<服务器根目录>/plugins/Vulpecular/listener/handlers/`**

插件会自动加载相应路径下的所有 YAML 文件（包括文件夹在内）

{% hint style="info" %}

如果你不想加载某个 YAML 或 文件夹<br>
可以在文件名最前面加上 “ **#** ”，插件会自动跳过带有“ **#** ”的文件或文件夹，例如：
- #example.yml
- #directory

{% endhint %}

如果你是第一次使用插件，可以在路径内发现 #example.yml 以及 def.yml 文件

#example.yml 是示例模板，里面配置的内容仅用来做说明，并不会被加载

def.yml 是一个简单的案例，但里面的配置内容并未被启用

## 配置监听模块

首先我们打开监听模块路径内的 `./listener/registrators/def.yml`

我们仿照文件内已有的 **player-quit** 监听模块，来写一个 **player-join** 模块，监听玩家加入服务器的事件

首先我们在 Bukkit 官方文档找到 **玩家加入服务器的事件** 的全名

{% embed title="ABC" url="https://bukkit.windit.net/javadoc/org/bukkit/event/player/package-summary.html" %}
Bukkit 官方文档 - 玩家事件大全
{% endembed %}


写完之后应该像下面这样

{% tabs %}
{% tab title="def.yml" %}
```yaml
# 监听模块的 id
# 可自定义 但请不要与其他监听模块 id 相同
player-quit:
  # 禁用当前监听模块，默认为 true
  enable: false
  # 监听模块的别名
  aliases: [ 'on-quit', 'quit' ]
  # 定义事件监听优先级
  priority: 'NORMAL'
  # 监听的事件
  # 这里代表玩家离开服务器事件
  class: 'org.bukkit.event.player.PlayerQuitEvent'

player-join:
  # 启用
  enable: true
  # 监听模块的别名
  aliases: [ 'on-join', 'join' ]
  # 定义事件监听优先级
  priority: 'NORMAL'
  # 监听的事件
  # 这里代表玩家进入服务器事件
  class: 'org.bukkit.event.player.PlayerJoinEvent'
```
{% endtab %}
{% endtabs %}




https://bukkit.windit.net/javadoc/org/bukkit/event/player/package-summary.html

{% tabs %}

{% tab title="First Tab" %}
Tabavxcsa
{% endtab %}

{% tab title="Second Tab" %}
example
{% endtab %}

{% endtabs %}