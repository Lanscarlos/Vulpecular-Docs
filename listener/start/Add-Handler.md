---
description: 配置监听模块
---

# 配置监听模块

## 配置

首先我们打开处理模块路径内的 def.yml 文件

`<服务器根目录>/plugins/Vulpecular/listener/handlers/def.yml`

可以看到以下内容

{% tabs %}
{% tab title="处理模块的 def.yml" %}
```yaml
# 处理模块的 id
# 可自定义 但请不要与其他处理模块 id 相同
example-handler:
  # 已禁用当前处理模块
  enable: false
  # 绑定的监听模块
  # 支持使用监听模块的别名
  listeners:
    - 'on-quit'
  # 使用 Kether脚本 向后台发送消息
  kether: |-
    print color *"&8[&3Vul&bpecular&8] &7检测到玩家离开了服务器！"

```
{% endtab %}
{% tab title="监听模块的 def.yml" %}
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

# 玩家进入服务器事件
player-join:
  # 启用监听模块
  enable: true
  # 监听模块的别名
  aliases: [ 'on-join', 'join' ]
  # [必填] 监听的事件
  # 这里代表玩家进入服务器事件
  class: 'org.bukkit.event.player.PlayerJoinEvent'

```
{% endtab %}
{% endtabs %}

这里我们放上前面配置好的 **监听模块 def.yml** 做比对参照


