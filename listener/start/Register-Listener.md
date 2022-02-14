---
description: 注册监听模块
---

# 注册监听模块

## 基础

所有的监听模块都是是以 **YAML (.yml)** 文件格式配置、读取加载的

一个 YAML 文件内可以配置多个监听模块

## 路径

监听模块的路径为 **<服务器根目录>/plugins/Vulpecular/listener/registrators/**

插件会自动加载该路径下的所有 YAML 文件（包括文件夹在内）

{% hint style="warning" %}

如果你不想加载某个 YAML 或 文件夹，可以在文件名最前面加上 “#”，插件会自动跳过带有“#”的文件，例如：
- #example.yml
- #directory

{% endhint %}

如果你是第一次使用插件，可以在路径内发现 #example.yml 以及 #def 文件夹

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
[**PlayerJoinEvent**](https://bukkit.windit.net/javadoc/org/bukkit/event/player/PlayerJoinEvent.html)
<br>
当玩家进入服务器时便会触发这个监听模块

但此时这个监听器并没有被注册，我们需要将 **enable** 设置为 **true** 启用当前监听器
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

```cmd
/rl reload registrator
```

等待插件重载完毕，至此监听模块已经成功注册了