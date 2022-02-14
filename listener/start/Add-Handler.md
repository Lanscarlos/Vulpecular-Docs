---
description: 添加处理模块
---

# 添加处理模块

## 基础

与监听模块类似

所有的处理模块都是是以 **YAML (.yml)** 文件格式配置、读取加载的

一个 YAML 文件内可以配置多个处理模块

## 路径

处理模块的存储路径为 **`<服务器根目录>/plugins/Vulpecular/listener/handlers/`**

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
# ./plugins/Vulpecular/listener/handlers/def.yml

# 向进入服务器的欢迎玩家发送一条问候语
welcome-player:
  # 已禁用当前处理模块
  enable: false
  # 绑定的监听模块
  listeners:
    - 'on-join'
  # 使用 Kether脚本 向玩家发送问候语
  kether: |-
    tell color *"&8[&3Vul&bpecular&8] &7欢迎加入服务器！祝您游戏愉快！"
```

这里我们启动一下处理模块，将 **enable** 设置为 **true** 后保存文件

## 重载配置

配置完成后，我们需要重新加载一下刚才的配置文件

在服务器后台输入以下命令来重载处理模块的配置文件

`
/rl reload handler
`

等待插件重载完毕，即可进入游戏查看效果