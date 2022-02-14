---
description: 注册监听模块
---

# 配置监听模块

## 配置

首先我们打开监听模块路径内的 def.yml 文件
`<服务器根目录>/plugins/Vulpecular/listener/registrators/def.yml`

可以看到以下内容

{% tabs %}
{% tab title="def.yml" %}
```yaml
# 监听模块的 id
# 可自定义 但请不要与其他监听模块 id 相同
player-quit:
  # 禁用当前监听模块，[ 默认为 true ]
  enable: false
  # 监听模块的别名
  aliases: [ 'on-quit', 'quit' ]
  # 定义事件监听优先级 [ 默认为 NORMAL ]
  priority: 'NORMAL'
  # [必填] 监听的事件
  # 这里代表玩家离开服务器事件
  class: 'org.bukkit.event.player.PlayerQuitEvent'
```
{% endtab %}
{% endtabs %}

接下来我们仿照上面已有的 **player-quit** 监听模块

自己写一个 **player-join** 模块，用来监听 **玩家进入服务器事件**

{% tabs %}
{% tab title="def.yml" %}
```yaml
# 监听模块的 id
# 可自定义 但请不要与其他监听模块 id 相同
player-quit:
  # 禁用当前监听模块，[ 默认为 true ]
  enable: false
  # 监听模块的别名
  aliases: [ 'on-quit', 'quit' ]
  # 定义事件监听优先级 [ 默认为 NORMAL ]
  priority: 'NORMAL'
  # [必填] 监听的事件的全类名
  # 这里代表玩家离开服务器事件
  class: 'org.bukkit.event.player.PlayerQuitEvent'

# 玩家进入服务器事件
player-join:
  # 启用
  enable: true
  # 监听模块的别名
  aliases: [ 'on-join', 'join' ]
  # [必填] 监听的事件
  # 这里代表玩家进入服务器事件
  class: '? ? ?'
```
{% endtab %}
{% endtabs %}

由于 **priority** 选项默认为 **NORMAL** 这里我们可以不写

但我们还缺少了一个必填的选项 **class**

这里我们需要填入的是<mark style="color:purple;">玩家进入服务器事件</mark> 的 **全类名**

下面将详细介绍如何确定一个事件的**全类名**

## 事件全类名

首先我们在 Bukkit 官方文档找到 **玩家进入服务器事件** 的类名全名

{% hint style="info" %}

[Bukkit 官方文档 - 玩家事件大全](https://bukkit.windit.net/javadoc/org/bukkit/event/player/package-summary.html)
<https://bukkit.windit.net/javadoc/org/bukkit/event/player/package-summary.html>

{% endhint %}

通过简单检索后，我们找到了 **玩家进入服务器事件** 对应着 **PlayerJoinEvent**

![检索相应事件](../../resources/quick-start/14152432.png)

我们点击进入 [**PlayerJoinEvent**](https://bukkit.windit.net/javadoc/org/bukkit/event/player/PlayerJoinEvent.html) 的介绍页面

从文档最上方可以找到关于 PlayerJoinEvent 的以下信息

![检索相应事件](../../resources/quick-start/14153209.png)

| 程序包 | 类名 |
| :-- | :-- |
| org.bukkit.event.player | PlayerJoinEvent  |









玩家进入服务器事件

[Bukkit 官方文档 - 玩家进入服务器事件](https://bukkit.windit.net/javadoc/org/bukkit/event/player/package-summary.html)
<https://bukkit.windit.net/javadoc/org/bukkit/event/player/package-summary.html>

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



















## 基础

所有的监听模块都是是以 **YAML (.yml)** 文件格式配置、读取加载的

一个 YAML 文件内可以配置多个监听模块

## 路径

监听模块的路径为 **`<服务器根目录>/plugins/Vulpecular/listener/registrators/`**

插件会自动加载该路径下的所有 YAML 文件（包括文件夹在内）

{% hint style="info" %}

如果你不想加载某个 YAML 或 文件夹<br>
可以在文件名最前面加上 “ **#** ”，插件会自动跳过带有“ **#** ”的文件或文件夹，例如：
- #example.yml
- #directory

{% endhint %}

如果你是第一次使用插件，可以在路径内发现 #example.yml 以及 def.yml 文件

其中 #example.yml 是示例模板，里面配置的内容仅用来做说明，并不会被加载

## 配置

现在让我们打开 **def.yml** 你会看到如下内容：
```yaml
# ./plugins/Vulpecular/listener/registrators/def.yml
player-join-event:
  # 禁用当前监听模块
  enable: false
  # 监听模块的别名
  aliases: [ 'on-join', 'join' ]
  # 定义事件监听优先级
  priority: 'NORMAL'
  # 监听的事件
  # 这里代表玩家进入服务器事件
  class: 'org.bukkit.event.player.PlayerJoinEvent'
```

可以看到这个监听模块监听的是
<mark style="color:purple;">
[**PlayerJoinEvent**](https://bukkit.windit.net/javadoc/org/bukkit/event/player/PlayerJoinEvent.html)
</mark>
<br>
当玩家进入服务器时便会触发这个监听模块

但此时这个监听器并没有被注册，我们需要将 **enable** 设置为 **true** 后保存文件

```yaml
# ./plugins/Vulpecular/listener/registrators/def.yml
player-join-event:
  # 启用当前监听模块
  enable: true
  # 监听模块的别名
  aliases: [ 'on-join', 'join' ]
  # 定义事件监听优先级
  priority: 'NORMAL'
  # 监听的事件
  # 这里代表玩家进入服务器事件
  class: 'org.bukkit.event.player.PlayerJoinEvent'
```

## 重载配置

配置完成后，我们需要重新加载一下刚才的配置文件

在服务器后台输入以下命令来重载监听模块的配置文件

`
/rl reload registrator
`

等待插件重载完毕，至此监听模块已经成功注册了