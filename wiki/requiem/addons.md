---
title: 安魂曲附加包
breadcrumb: 附加包
layout: requiem_wiki
---

## Pandemonium

Pandemonium是安魂曲的第一方“试验场”。
它包含被认定过于粗糙而无法融入安魂曲的功能。

### 现有内容
#### 游魂
游魂是永久拥有忏悔II、再生和解放效果的新灵魂状态。
拥有这种灵魂状态的玩家可以对其他身体来去自如，但是无法自己制造人体。


### 已移除内容

以下部分描述了已从 pandemonium 中删除的内容，因为它们已
集成到主 mod 中。

{% capture summary %}<h4 id="before-v2">Before v2.0.0</h4>{% endcapture %}
{% capture content %}
##### 对安魂曲的改变

- 大多数生物都可以被附身。值得注意的是末影龙、凋灵、监守者和其他玩家是个例外。
- 正常形态的玩家可以在任何时候解离，并留下一个*玩家躯体*。

##### 玩家躯体

当一个玩家从他们的普通身体解离时，它们会创建一个玩家躯体。如果该玩家躯体被另一个玩家附身的话，那个玩家就会获得玩家躯体对应的玩家的身份——参阅[Impersonate](../impersonate)以了解更多。

呆滞的躯体上的物品可以像盔甲架一样被添加或移除。

###### 模组兼容性

- 躯体会保留起源模组的能力。如果一个玩家躯体被其他玩家附身，附身者的起源会变成附身的玩家躯体的。
- 躯体会保留Haema模组的狼人化。如果一个玩家躯体被其他玩家附身，附身者会基于附身的玩家躯体是否为狼人来得到或失去狼人化能力。

##### 特殊的物品用法

Pandemonium为新的可附身生物添加了一些特殊的物品使用方式。

###### 女巫的酿造基地

女巫可以在空中酿造药水：当它们拿着水瓶时，女巫会
自动酿造它们在某些情况下赖以生存的药水。

##### 管理员命令

- `/pandemonium shell`
  - `/pandemonium shell create [player]`: 在命令发生地创建有着目标玩家的数据的拷贝的玩家躯体。如果没有指定玩家，该命令会将命令执行者作为对象。
  - `/pandemonium shell split [players]`: 人为地解离一个或多个玩家，就好像他们按了解离按键一样。
  - `/pandemonium shell identity set <profile> [shells]`: 将一个或多个玩家躯体的身份（名字与皮肤）设置为给定的资料信息。
{% endcapture %}
{% include details.liquid summary=summary content=content%}
