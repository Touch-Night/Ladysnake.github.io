---
title: 安魂曲命令
breadcrumb: 命令
layout: requiem_wiki
---

安魂曲添加了一些管理员命令，以便更轻松地测试模组或帮助无知的玩家。
所有安魂曲的命令均以`/requiem`开头。它们大都需要一个可选的玩家参数。如果没有给出该参数，则命令的目标将是命令执行者。

- `/requiem remnant`
    - `/requiem remnant set <true|false> [player]`: 设置玩家的残魂（传说中残魂也被称为恶魔，它们死后会变成鬼魂）状态。
      此命令本身不会阻止选择菜单在下一次死亡时出现。
    - `/requiem remnant query [player]`: 查询一个玩家的残魂状态
- `/requiem vagrant` <span class="badge badge-secondary">&gt; 2.0.0</span>
    - `/requiem vagrant set <true|false> [player]`: 设置残魂玩家的游荡状态。如果为`true`，则该玩家会变成一个虚无缥缈的鬼魂。
    - `/requiem vagrant query [player]`: 查询一个玩家的游魂状态
- `/requiem possession`
    - `/requiem possession start <mob> [player]`: 如果玩家已经是一个灵魂，则使他开始附身一个生物。
    - `/requiem possession stop [player]`: 停止对指定玩家的正在进行的附身。
- `/requiem shell` <span class="badge badge-secondary">&gt; 2.0.0</span>
    - `/requiem shell create [player]`: 在命令发生地创建有着目标玩家的数据的拷贝的玩家躯体。如果没有指定玩家，该命令会将命令执行者作为对象。
    - `/requiem shell split [players]`: 人为地解离一个或多个玩家，就好像他们按了*解离*按键一样。
    - `/requiem shell identity set <profile> <shells>`: 将一个或多个玩家躯体的身份（名字与皮肤）设置为给定的资料信息。
    - `/requiem shell merge <shell> [player]`: 人为地将一个游魂玩家与一个躯壳结合，就好像他们尝试附身它一样。如果没有指定玩家，该命令会将躯体与命令执行者结合。
- `/requiem soul` <span class="badge badge-secondary">&gt; 2.0.0</span>
    - `/requiem soul remove <entities>`: 移除一个或多个实体的灵魂，就好像对它们使用了灵魂容器一样。
    - `/requiem soul restore <entities>`: 恢复一个或多个实体的灵魂,就好像它们从灵魂容器中被释放了一样。
- `/requiem soul` <span class="badge badge-danger">&lt; 2.0.0</span>
    - `/requiem soul set <true|false> [player]`: 设置一个残魂玩家的灵魂状态。
    - `/requiem soul query [player]`: 查询一个玩家的灵魂状态。

### 残魂选择界面
残魂选择界面是基于[Blabber](../blabber)制作的，而且可以用该模组的指令来与之交互。
正常情况下，它在没有获得`requiem:adventure/the_choice`成就的玩家死亡后，且
[`requiem:startingRemnantType`](configuration#requiem-startingremnanttype) 游戏规则设为`选择`时出现。

### 目标选择器参数
安魂曲也添加了一个新的[目标选择器参数](https://minecraft.fandom.com/zh/wiki/%E7%9B%AE%E6%A0%87%E9%80%89%E6%8B%A9%E5%99%A8#%E7%9B%AE%E6%A0%87%E9%80%89%E6%8B%A9%E5%99%A8%E5%8F%82%E6%95%B0)————`"requiem:possessor"`.
任何可以针对实体的命令都可以使用此参数根据其附身者选择实体。
该参数使用附身者的名字或空字符串来匹配未被附身的实体。
可以通过在前面加上`'!'`字符来取反。

_例子:_
```bash
# 使所有被附身的实体说“你好，世界！”
execute as @e["requiem:possessor"=!] run say 你好，世界！
```
