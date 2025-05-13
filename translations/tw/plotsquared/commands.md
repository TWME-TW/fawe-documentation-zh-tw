<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "7f1c134355838cdfc4d1f15b4eda7847",
  "translation_date": "2025-05-13T03:42:55+00:00",
  "source_file": "plotsquared/commands.md",
  "language_code": "tw"
}
-->
# Commands

## Introduction

所有指令若未設定，皆以 `/plot` 開頭。

作為替代或簡短指令，你可以使用以下別名：
`plots, p, plotsquared, p2, ps, 2, plotme`

## Command Overview

PlotSquared 有許多不同用途的指令。在這裡你可以找到完整的指令列表、語法與權限。

command-categories:

* [Basics](../../../plotsquared)
* [Info](../../../plotsquared)
* [Teleport](../../../plotsquared)
* [Chat](../../../plotsquared)
* [Claiming](../../../plotsquared)
* [Settings](../../../plotsquared)
* [Schematic](../../../plotsquared)
* [Rating](../../../plotsquared)
* [Administration](../../../plotsquared)
* [Debug](../../../plotsquared)
* [Other_permissions](../../../plotsquared)

{% hint style="info" %}
若指令或權限包含 `Secondary`，表示該指令支援多個子指令或有多重用途。此外，帶有 `.admin` 的權限包含管理員覆寫功能。
{% endhint %}

{% hint style="info" %}
你可以查看我們的[permission-packs](permission/permission-packs.md)以避免重複的權限設定。
{% endhint %}

---

## Basics

### HELP

取得 PlotSquared 的幫助選單。

**使用方法：**
`/plot help [category|#]`

**別名：**
`[ ? ]`

**權限：**
`plots.use` - 可使用 `/plot help` 指令

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/Help.java)

### CONFIRM

用於確認你最後輸入的指令，當 PlotSquared 要求時使用。這是為了防止誤執行或粗心操作某些指令的安全措施。

**使用方法：**
`/plot confirm`

**權限：**
`plots.confirm` - 可使用 `/plot confirm` 指令

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/Confirm.java)

---

## Info

### INFO

顯示地塊資訊。

第一個地塊位置參數為選填。若未填，則指的是使用者目前所在的地塊。

擁有 `-f` 權限可使用管理員覆寫來繞過 `hide-info` 標誌。

**使用方法：**

_主要用法：_

* `/plot [[world;]X;Z] info [-f]`
* `/plot info [[world;]X;Z] [-f]`

_次要用法：_

* `/plot [[world;]X;Z] info [-f] <category: members, alias, biome, seen, denied, flags, id, size, trusted, owner, rating>`
* `/plot info [[world;]X;Z] [-f] <category: members, alias, biome, seen, denied, flags, id, size, trusted, owner, rating>`

**別名：**
`[ i ]`

**權限：**

_主要用法：_

* `plots.info` - 可使用 `/plot info` 指令

_次要用法：_

* `plots.admin.info.force` - 可使用包含 `-f` 標誌的指令

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/Info.java)

### LIST

顯示伺服器上現有地塊的清單。

此輸出可透過更多參數進行指定或篩選。

**使用方法：**

_主要用法：_

* `+/plot list <forsale | mine | shared | world | top | all | unowned | unknown | player | world | done |fuzzy <search...>> [#]+`

_次要用法：_

* `+/plot list fuzzy <search...> [#]+`

**別名：**
`[ l, find, search ]`

**權限：**

_主要用法：_

* `plots.list` - 可使用 `/plot list` 指令

_次要用法：_

* `plots.list.world.<arg>`
* `plots.list.top` - 可使用 `/plot list top` 指令
* `plots.list.mine` - 可使用 `/plot list mine` 指令
* `plots.list.world` - 可使用 `/plot list world` 指令
* `plots.list.done` - 可使用 `/plot list done` 指令
* `plots.list.all` - 可使用 `/plot list all` 指令
* `plots.list.shared` - 可使用 `/plot list shared` 指令
* `plots.list.expired` - 可使用 `/plot list expired` 指令
* `plots.list.unowned` - 可使用 `/plot list unowned` 指令
* `plots.list.world.<world>"` - 可使用 `/plot list world <world>` 指令
* `plots.list.player` - 可使用 `/plot list player <player>` 指令
* `plots.list.forsale` - 可使用 `/plot list forsale` 指令
* `plots.list.unknown` - 可使用 `/plot list unknown` 指令
* `plots.list.area` - 可使用 `/plot list area` 指令
* `plots.list.fuzzy` - 可使用 `/plot list fuzzy #` 指令

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/ListCmd.java)

### TARGET

用你的指南針標記一個地塊。

**使用方法：**
`/plot target <<X;Z> | nearest>`

**權限：**
`plots.target` - 可使用 `/plot target` 指令

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/Target.java)

### CAPS

顯示地塊的生物與實體上限。

第一個地塊位置參數為選填。若未填，則指的是使用者目前所在的地塊。

**使用方法：**
`/plot [[world;]X;Z] caps`

**權限：**

_主要用法：_

* `plots.caps` - 可使用 `/plot caps` 指令

_次要用法：_

* `plots.admin.caps.other` - 管理其他地塊上限的管理員覆寫權限

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/Caps.java)

---

## Teleport

### HOME

傳送到你自己的地塊。

**使用方法：**

一般：

* `/plot home`
* `/plot home <#>`
* `/plot home <area/world> <#>`

別名：

* `/plot home <alias>`

座標：

* `/plot home <X>;<Z>`
* `/plot home <area/world> <X>;<Z>`
* `/plot home <area/world>;<X>;<Z>`

**別名：**
`[ h ]`

**權限：**

_主要用法：_

* `plots.home` - 可使用 `/plot home` 指令

_次要用法：_

* `plots.visit.owned` - 可造訪自己擁有的地塊

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/HomeCommand.java)

### Visit

使用此指令前往特定玩家的地塊。

若未指定 **地塊編號**，將前往該玩家的第一個（最舊）地塊。透過輸入數字可向前或向後切換地塊，第一個地塊編號為 "1"。輸入關鍵字 "last"（或 "n"）則會前往該玩家最新（最新）地塊，對應地塊編號為 "-1"。

一般：

* `/plot visit <player>`
* `/plot visit <player> <plot number|negative plot number|'last' or 'n'>`
* `/plot visit <player> <area/world>`
* `/plot visit <player> <area/world> <plot number|negative plot number|'last' or 'n'>`

別名：

* `/plot visit <alias>`

座標：

* `/plot visit <X>;<Z>`
* `/plot visit <area/world>;<X>;<Z>`

**別名：**
`[ v, tp, teleport, goto, warp ]`

**權限：**

_主要用法：_

* `plots.visit` - 可使用 `/plot visit` 指令
* `plots.visit.other` - 可造訪其他玩家的地塊

_次要用法：_

* `plots.visit.unowned` - 可造訪無主地塊
* `plots.visit.owned` - 可造訪擁有的地塊
* `plots.visit.shared` - 可造訪共享地塊
* `plots.admin.visit.untrusted` - 可造訪玩家未被信任的地塊

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/Visit.java)

### MIDDLE

傳送到地塊中心。

第一個地塊位置參數為選填。若未填，則指的是使用者目前所在的地塊。

**使用方法：**
`/plot [[world;]X;Z] middle`

**別名：**
`[ center, centre ]`

**權限：**
`plots.middle` - 可使用 `/plot middle` 指令

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/Middle.java)

---

## Chat

### COMMENT

對地塊留言。

第一個地塊位置參數為選填。若未填，則指的是使用者目前所在的地塊。

**使用方法：**
`/plot [[world;]X;Z] comment <message-type: owner | public | report (= for staff)> <comment>`

**別名：**
`[ msg ]`

**權限：**
`plots.comment` - 可使用 `/plots comment` 指令

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/Comment.java)

### INBOX

列出地塊留言 / 刪除留言或清空留言清單。

第一個地塊位置參數為選填。若未填，則指的是使用者目前所在的地塊。

**使用方法：**

_主要用法：_

* `/plot [[world;]X;Z] inbox`

_次要用法：_

* `/plot [[world;]X;Z] inbox <message-type: owner | public | report> [delete <index> | clear | page]`

**權限：**
`plots.inbox` - 可使用 `/plots inbox` 指令

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/Inbox.java)

---

## Claiming

### BUY

購買地塊。

第一個地塊位置參數為選填。若未填，則指的是使用者目前所在的地塊。

此指令需在 `worlds.yml` 啟用經濟功能。你也可以在該設定中調整「合併」、「販售」和「申請」的價格。

**使用方法：**
`/plot [[world;]X;Z] buy`

**權限：**
`plots.buy` - 可使用 `/plot buy`

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/Buy.java)

### CLAIM

申請目前所在地塊。

第一個地塊位置參數為選填。若未填，則指的是使用者目前所在的地塊。

若你未在 `worlds.yml` 啟用經濟功能，且啟用了 "specify_on_claim" 選項，則可以指定地塊結構圖。

**使用方法：**

_主要用法：_

* `/plot [[world;]X;Z] claim`

_次要用法：_

* `/plot [[world;]X;Z] claim <schematic>`

**別名：**
`[ c ]`

**權限：**

_主要用法：_

* `plots.claim` - 可使用 `/plot claim`
* `plots.plot.<max plot amount>` - 限制玩家可申請的地塊數量

_次要用法：_

* `plots.claim.<schem>` - 與所用結構圖相關的動態權限
* `plots.admin.command.schematic` - 管理員使用結構圖申請的權限

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/Claim.java)

### AUTO

在你所在世界中自動申請最近的地塊，前提是你未在 `worlds.yml` 啟用經濟功能。

**使用方法：**
`/plot auto [length, width]`

**別名：**
`[ a ]`

**權限：**

_主要用法：_

* `plots.auto` - 可使用 `/plot auto` 指令
* `plots.plot.<max plot amount>` - 限制玩家可申請的地塊數量

_次要用法：_

* `plots.claim.<schem>` - 與所用結構圖相關的動態權限
* `plots.auto.mega` - 可使用長度和寬度參數
* `plots.admin.command.schematic` - 管理員使用結構圖申請的權限

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/Auto.java)

---

## Settings

### SETOWNER

設定地塊擁有者。

第一個地塊位置參數為選填。若未填，則指的是使用者目前所在的地塊。

**使用方法：**
`/plot [[world;]X;Z] setowner <player>`

**別名：**
`[ owner, so, seto ]`

**權限：**

_主要用法：_

* `plots.admin.command.setowner`

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/Owner.java)

### ADD

將一名或多名玩家加入地塊。

「已加入」的玩家在地塊擁有者在線時可以建造（參見[Plot Membership Tiers](plot-membership-tiers.md)）。

第一個地塊位置參數為選填。若未填，則指的是使用者目前所在的地塊。

**使用方法：**
`/plot [[world;]X;Z] add <player | *>`

**權限：**

_主要用法：_

* `plots.add` - 可使用 `/plot add` 指令
* `plots.add.<amount>` - 限制地塊擁有者可加入的人數

_次要用法：_

* `plots.admin.command.add` - 管理員覆寫權限
* `plots.add.everyone` - 可加入所有人

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/Add.java)

### TRUST

將一名或多名玩家加入地塊。
"Trusted" 玩家比一般的 [/plot add](../../../plotsquared) 指令給予該使用者更多權限：Trusted 使用者可以隨時在該地塊建造，並且能使用 WorldEdit（詳見 [Plot Membership Tiers](plot-membership-tiers.md)）。

第一個地塊位置參數是可選的。若未指定，則代表目前使用者所在的地塊。

**用法：**
`/plot [[world;]X;Z] trust <player | *>`

**別名：**
`[ t ]`

**權限：**

_主要：_

* `plots.trust` - 使用 `/plot trust` 指令的權限
* `plots.trust.<amount>` - 指定地塊擁有者可以信任的人數

_次要：_

* `plots.admin.command.trust` - 管理員覆寫權限
* `plots.trust.everyone` - 可信任所有人的權限

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/Trust.java)

### REMOVE

從地塊中移除玩家。包含地塊的「白名單」玩家（[ADD](../../../plotsquared)、[TRUST](../../../plotsquared)）以及「黑名單」玩家（[DENY](../../../plotsquared)）。

第一個地塊位置參數是可選的。若未指定，則代表目前使用者所在的地塊。

**用法：**
`/plot [[world;]X;Z] remove <player | *>`

**別名：**
`[ r, untrust, ut, undeny, ud, unban ]`

**權限：**

_主要：_

* `plots.remove` - 使用 `/plot remove` 指令的權限

_次要：_

* `plots.admin.command.remove` 管理員覆寫權限

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/Remove.java)

### DENY

拒絕使用者進入地塊。使用此指令會將該使用者加入地塊的「黑名單」（詳見 [Plot Membership Tiers](plot-membership-tiers.md)）。

第一個地塊位置參數是可選的。若未指定，則代表目前使用者所在的地塊。

**用法：**
`/plot [[world;]X;Z] deny <player | *>`

**別名：**
`[ d, ban ]`

**權限：**

_主要：_

* `plots.deny` - 使用 `/plot deny` 指令的權限
* `plots.deny.<amount>` - 指定地塊擁有者可拒絕的人數

_次要：_

* `plots.admin.command.deny` - 管理員覆寫權限
* `plots.admin.entry.denied` - 管理員覆寫權限以繞過地塊拒絕
* `plots.deny.everyone` - 可拒絕所有人的權限

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/Deny.java)

### GRANT

管理地塊授權。

**用法：**
`/plot grant <check | add> [player]`

**權限：**

* `plots.grant` - 使用 `/plot grant` 指令的權限
* `plots.grant.add` - 使用 `/plot grant add` 指令的權限
* `plots.grant.check` - 使用 `/plot grant check` 指令的權限

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/Grant.java)

### KICK

將玩家從你的地塊踢出。

第一個地塊位置參數是可選的。若未指定，則代表目前使用者所在的地塊。

**用法：**
`/plot [[world;]X;Z] kick <player | *>`

**別名：**
`[ k ]`

**權限：**

_主要：_

* `plots.kick` - 使用 `/plot kick` 指令的權限

_次要：_

* `plots.admin.command.kick` - 管理員覆寫權限

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/Kick.java)

### MERGE

將地塊與其他地塊合併。

第一個地塊位置參數是可選的。若未指定，則代表目前使用者所在的地塊。

**用法：**
`/plot [[world;]X;Z] merge <all | n | e | s | w> [removeroads]`

**別名：**
`[ m ]`

**權限：**

_主要：_

* `plots.merge` - 使用 `/plot claim` 指令的權限

_次要：_

* `plots.merge.<amount>` - 限制玩家可合併成 mega 地塊的地塊數量
* `plots.admin.command.merge` - 管理員覆寫權限
* `plots.merge.other` - 可與其他玩家合併地塊的權限
* `plots.merge.keeproad` - 使用 keeproad 參數的權限

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/Merge.java)

### UNLINK

解除 mega 地塊（合併地塊）的連結。

第一個地塊位置參數是可選的。若未指定，則代表目前使用者所在的地塊。

**用法：**
`/plot [[world;]X;Z] unlink [createroads]`

**別名：**
`[ u, unmerge ]`

**權限：**

_主要：_

* `plots.unlink` - 使用 `/plot unlink` 指令的權限

_次要：_

* `plots.admin.command.unlink` - 管理員覆寫權限

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/Unlink.java)

### SETHOME

設定地塊家。

地塊家是玩家使用 `/plot home` 或 `/plot visit` 指令時會傳送到的位置。使用 `none` 參數可以將位置重設為該地塊世界的預設家。

第一個地塊位置參數是可選的。若未指定，則代表目前使用者所在的地塊。

**用法：**
`/plot [[world;]X;Z] set home [none]`

**別名：**
`[ sh, seth, sethome ]`

**權限：**

* `plots.set.home` - 使用 `/plot set home` 指令的權限

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/SetHome.java)

### ALIAS

設定「地塊名稱」。

第一個地塊位置參數是可選的。若未指定，則代表目前使用者所在的地塊。

**用法：**

* `/plot [[world;]X;Z] alias set <alias>`
* `/plot [[world;]X;Z] alias remove <alias>`

**別名：**
`[ setalias, sa, name, rename, setname, seta, nameplot ]`

**權限：**

_主要：_

* `plots.alias.set` - 使用 `/plot alias set` 指令的權限
* `plots.alias.remove` - 使用 `/plot alias remove` 指令的權限

_次要：_

* `plots.admin.alias.set` - 管理員覆寫權限以設定別名
* `plots.admin.alias.remove` - 管理員覆寫權限以移除別名

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/Alias.java)

### SETDESCRIPTION

設定地塊描述。

第一個地塊位置參數是可選的。若未指定，則代表目前使用者所在的地塊。

**用法：**
`/plot [[world;]X;Z] desc <description>`

**別名：**
`[ setdescription, setdesc, setd, description ]`

**權限：**
`plots.set.desc` - 使用 `/plot set description` 指令的權限

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/Desc.java)

### MUSIC

在地塊中播放音樂。

第一個地塊位置參數是可選的。若未指定，則代表目前使用者所在的地塊。

**用法：**
`/plot [[world;]X;Z] music`

**權限：**
`plots.music` - 使用 `/plot music` 指令的權限

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/Music.java)

### SETBIOME

列出所有可用的生物群系或更改地塊生物群系。（你也可以用 WorldEdit / FAWE 更改生物群系。）若清除或刪除地塊，也會重設生物群系設定，會使用預設生物群系（可在 `worlds.yml` 中更改）。

第一個地塊位置參數是可選的。若未指定，則代表目前使用者所在的地塊。

**用法：**
`/plot [[world;]X;Z] biome [biome]`

**別名：**
`[ biome, sb, setb, b ]`

**權限：**
`plots.set.biome` - 使用 `/plot set biome` 指令的權限

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/Biome.java)

### SETFLAG

管理地塊的旗標（詳見 [Plot Flags](plot-flags.md)）。

第一個地塊位置參數是可選的。若未指定，則代表目前使用者所在的地塊。

**用法：**

_主要：_

* `/plot [[world;]X;Z] flag`

_次要：_

* `/plot [[world;]X;Z] flag info <flag>`
* `/plot [[world;]X;Z] flag set <flag> <value>`
* `/plot [[world;]X;Z] flag add <flag> <values>`
* `/plot [[world;]X;Z] flag remove <flag> [values]`

**別名：**
`[ f, flag ]`

**權限：**

_主要：_

* `plots.flag` - 使用 `/plot flag` 指令的權限

_次要：_

* `plots.set.flag` - 使用 `/plot set flag` 指令的權限
* `plots.flag.remove` - 使用 `/plot flag remove` 指令的權限
* `plots.flag.add` - 使用 `/plot flag add` 指令的權限
* `plots.set.flag.other` - 在他人地塊設定旗標的權限
* `plots.set.flag.<arg>` - 使用 `/plot set flag <arg>` 指令的權限
* `plots.flag.list` - 使用 `/plot flag list` 指令的權限

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/FlagCommand.java)

### DONE

標記地塊為「完成」。

第一個地塊位置參數是可選的。若未指定，則代表目前使用者所在的地塊。

**用法：**
`/plot [[world;]X;Z] done`

**別名：**
`[ submit ]`

**權限：**

_主要：_

* `plots.done` - 使用 `/plot done` 指令的權限

_次要：_

* `plots.admin.command.done` - 管理員覆寫權限

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/Done.java)

### CONTINUE

繼續之前標記為「完成」的地塊。

第一個地塊位置參數是可選的。若未指定，則代表目前使用者所在的地塊。

**用法：**
`/plot [[world;]X;Z] continue`

**權限：**

_主要：_

* `plots.continue` - 使用 `/plot continue` 指令的權限

_次要：_

* `plots.admin.command.continue` - 管理員覆寫權限

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/Continue.java)

### TOGGLE

切換每位使用者的設定。

第一個地塊位置參數是可選的。若未指定，則代表目前使用者所在的地塊。

**用法：**
`/plot [[world;]X;Z] toggle <chat | chatspy | clear-confirmation | time | titles | worldedit>`

**權限：**

_主要：_

* `plots.use` - 使用 `/plot toggle` 指令的權限

_次要：_

* `plots.admin.command.chat` - 使用 `/plot toggle chat-spy` 指令的權限
* `plots.worldedit.bypass` - 使用 `/plot wea` 指令的權限
* `plots.toggle.chat` - 使用 `/plot chat` 指令的權限
* `plots.admin.command.autoclear` - 使用 `/plot toggle clear-confirmation` 指令的權限
* `plots.toggle.titles` - 使用 `/plot toggle titles` 指令的權限
* `plots.toggle.time` - 使用 `/plots toggle time` 指令的權限
* `plots.toggle.debug` - 使用 `/plots toggle debug` 指令的權限
* `plots.admin.debug.other` - 管理員覆寫權限以切換其他玩家的除錯模式

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/Toggle.java)

### SET

設定地塊的數值。

第一個地塊位置參數是可選的。若未指定，則代表目前使用者所在的地塊。

**用法：**
`/plot [[world;]X;Z] set <biome | alias | home | floor | wall | all | air | main | middle | outline | border> <value...>+`

**別名：**
`[ s ]`

**權限：**

_主要：_

* `plots.set` - 使用 `/plot set` 指令的權限

_次要：_

* `plots.set." + <component>`

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/Set.java)

### COPY

複製地塊。

第一個地塊位置參數是可選的。若未指定，則代表目前使用者所在的地塊，並代表複製的原始地塊。

第二個地塊位置參數則是定義複製後的目標地塊。

**用法：**
`/plot [[world;]X;Z] copy <X;Z>`

**別名：**
`[ copypaste ]`

**權限：**

_主要：_

* `plots.copy` - 使用 `/plot copy` 指令的權限

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/Copy.java)

### MOVE

移動地塊。

第一個地塊位置參數是可選的。若未指定，則代表目前使用者所在的地塊，並代表移動的原始地塊。

第二個地塊位置參數定義移動後的目標地塊。（移動後原始地塊會被重設。）

**用法：**
`/plot [[world;]X;Z] move <X;Z>`

**權限：**

_主要：_

* `plots.move` - 使用 `/plot move` 指令的權限

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/Move.java)

### SWAP

交換兩個地塊。

第一個地塊位置參數是可選的。若未指定，則代表目前使用者所在的地塊。

第二個地塊位置參數定義交換的另一個地塊。

**用法：**
`/plot [[world;]X;Z] swap <X;Z>`

**別名：**
`[ switch ]`

**權限：**

_主要：_

* `plots.swap` - 使用 `/plot swap` 指令的權限

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/Swap.java)

### BACKUP

管理地塊備份。

第一個地塊位置參數是可選的。若未指定，則代表目前使用者所在的地塊。

**用法：**
`/plot [[world;]X;Z] backup <save | list | load>`

**權限：**

_主要：_

* `plots.backup` - 使用 `/plot backup` 指令的權限

_次要：_

* `plots.backup.save` - 使用 `/plot backup save` 指令的權限
* `plots.backup.load` - 使用 `/plot backup load` 指令的權限
* `plots.backup.list` - 使用 `/plot backup list` 指令的權限
* `plots.admin.backup.other` - 管理員覆寫權限以管理其他地塊的備份

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core/command/Backup.java)

### CLEAR

清除你站立的地塊。不會重設任何地塊設定或旗標（生物群系設定除外）。

第一個地塊位置參數是可選的。若未指定，則代表目前使用者所在的地塊。

**用法：**
`/plot [[world;]X;Z] clear`

**別名：**
`[ reset ]`

**權限：**

_主要：_

* `plots.clear` - 使用 `/plot clear` 指令的權限

_次要：_

* `plots.admin.command.clear` - 管理員覆寫權限

**原始碼：** [here](https://github.com/IntellectualSites/PlotSquared/blob/main/Core/src/main/java/com/plotsquared/core
### DOWNLOAD

下載你的地皮。

第一個地皮位置參數是可選的。或者，它指的是使用者目前所在的地皮。

**Usage:**
`/plot [[world;]X;Z] download [schematic | world]`

**Aliases:**
`[ download, dl ]`

**Permissions:**

_Primary:_

* `plots.download` - 使用命令 `/plot download` 的權限
* `plots.download.world` - 使用命令 `/plot download <world>` 的權限

_Secondary:_

* `plots.admin.command.download` - 管理員權限，可以下載其他地皮

### SCHEMATIC

使用並管理地皮結構圖。

第一個地皮位置參數是可選的。或者，它指的是使用者目前所在的地皮。

**Usage:**
`/plot [[world;]X;Z] schematic <save | saveall | paste>`

**Aliases:**
`[ sch, schem ]`

**Permissions:**

_Primary:_

* `plots.schematic` - 使用命令 `/plot schematic` 的權限

_Secondary:_

* `plots.admin.command.schematic.paste` - 管理員權限，可以貼上結構圖
* `plots.admin.command.schematic.save` - 管理員權限，可以儲存結構圖
* `plots.schematic.save` - 使用命令 `/plot schematic save` 的權限
* `plots.schematic.paste` - 使用命令 `/plot schematic paste ` 的權限

---

## Rating

### LIKE

喜歡一塊地皮。

第一個地皮位置參數是可選的。或者，它指的是使用者目前所在的地皮。

**Usage:**
`/plot [[world;]X;Z] like [next | purge]`

**Permissions:**

_Primary:_

* `plots.like` - 使用命令 `/plot like` 的權限

_Secondary:_

* `plots.admin.command.rate` - 管理員權限，用於評分

### Dislike

不喜歡一塊地皮。

第一個地皮位置參數是可選的。或者，它指的是使用者目前所在的地皮。

**Usage:**
`/plot [[world;]X;Z] dislike [next | purge]`

**Permissions:**

_Primary:_

* `plots.dislike` - 使用命令 `/plot like` 的權限

_Secondary:_

* `plots.admin.command.rate` - 管理員權限，用於評分

### RATE

評分地皮。

第一個地皮位置參數是可選的。或者，它指的是使用者目前所在的地皮。

**Usage:**
`/plot [[world;]X;Z] rate [# | next | purge]`

**Aliases:**
`[ rt ]`

**Permissions:**

_Primary:_

* `plots.rate` - 使用命令 `/plot rate` 的權限

_Secondary:_

* `plots.comment` - 使用命令 `/plot comment` 的權限
* `plots.admin.command.rate` - 管理員權限，用於評分

---

## Administration

### PLUGIN

顯示插件資訊。

**Usage:**
`/plot plugin`

**Aliases:**
`[ version ]`

**Permissions:**
`plots.use` - 使用命令 `/plot plugin` 的權限

### TEMPLATE

建立或使用世界模板。

**Usage:**

_Primary:_

* `/plot template [import | export] <world> <template>`

_Secondary:_

* `/plot template <import|export> <world> [template]`
* `/plot template export <world>`
* `/plot template import <world> <template>`

**Permissions:**
`plots.admin` - 使用命令 `/plot template` 的權限

### SETUP

地皮世界的設定精靈。

**Usage:**
`/plot setup`

**Aliases:**
`[ create ]`

**Permissions:**
`plots.admin.command.setup`

### AREA

建立新的地皮區域。

**Usage:**

_Primary:_

* `/plot area <create|info|list|tp|regen>`

_Secondary:_

* `/plot visit [area]`
* `/plot area info [area]`
* `+/plot area create [world[:id]] [<modifier>=<value>]...+`
* `/plot area list [#]`

**Aliases:**
`[ world ]`

**Permissions:**

* `plots.area` - 使用命令 `/plot area` 的權限
* `plots.area.list` - 使用命令 `/plot area list` 的權限
* `plots.area.info` - 使用命令 `/plot area info` 的權限
* `plots.area.create` - 使用命令 `/plot area create` 的權限
* `plots.area.tp` - 使用命令 `/plot area tp` 的權限
* `plots.area.regen` - 使用命令 `/plot area regen` 的權限

### CREATEROADSCHEMATIC

使用你目前地皮周圍的道路新增道路結構圖到你的世界。

**Usage:**
`/plot createroadschematic`

**Aliases:**
`[ crs ]`

**Permissions:**

* `plots.createroadschematic` - 使用命令 `/plot createroadschematic` 的權限

### REGENALLROADS

使用設定的道路結構圖重新生成地圖上的所有道路。

**Usage:**
`/plot regenallroads <world> [height]`

**Aliases:**
`[ rgar ]`

**Permissions:**

* `plots.regenallroads` - 使用命令 `/plot regenallroads` 的權限

### PURGE

清除某個世界的所有地皮。

**Usage:**
`/plot purge world:<world> area:<area> id:<id> owner:<owner> shared:<shared> unknown:[true|false] clear:[true|false]`

**Permissions:**

* `plots.admin` - 使用命令 `/plot purge` 的權限

### RELOAD

重新載入翻譯和世界設定。

**Usage:**
`/plot reload`

**Aliases:**
`[ rl ]`

**Permissions:**
`plots.admin.command.reload` - 使用命令 `/plot reload` 的權限

### DATABASE

轉換/備份儲存。

**Usage:**
`/plots database [area] <sqlite | mysql | import>`

**Aliases:**
`[ convert ]`

**Permissions:**
`plots.database` - 使用命令 `/plot database` 的權限

### CONDENSE

壓縮一個地皮世界。

**Usage:**
`/plot condense <area> <start | stop |info> [radius]`

**Permissions:**
`plots.admin` - 使用命令 `/plot condense` 的權限

### TRIM

刪除地皮世界中未修改的部分。

**Usage:**
`/plot trim <world> [regenerate]`

**Permissions:**
`plots.admin` - 使用命令 `/plot trim` 的權限

### CLUSTER

管理地皮群集。

**Usage:**

_Primary:_

* `/plot cluster`

_Secondary:_

* `/plot cluster resize <pos1> <pos2>`
* `/plot cluster leave [name]`
* `/plot cluster info [name]`
* `/plot cluster create <name> <id-bot> <id-top>`
* `/plot cluster delete [name]`
* `/plot cluster list`
* `/plot cluster invite <player>`
* `/plot cluster sethome`
* `/plot cluster helpers <add|remove> <player>`
* `/plot cluster tp <name>`
* `/plot cluster kick <player>`

**Aliases:**
`[ clusters ]`

**Permissions:**

_Primary:_

* `plots.cluster` - 使用命令 `/plot cluster` 的權限

_Secondary:_

* `plots.cluster.delete.other` - 管理員權限，可以刪除其他群集
* `plots.cluster.kick` - 使用命令 `/plot cluster kick` 的權限
* `plots.cluster.leave` - 使用命令 `/plot cluster leave` 的權限
* `plots.cluster.helpers` - 使用命令 `/plot cluster helpers` 的權限
* `plots.cluster.create` - 使用命令 `/plot cluster create` 的權限
* `plots.cluster.resize` - 使用命令 `/plot cluster resize` 的權限
* `plots.cluster.invite.other` - 使用命令 `/plot cluster invite` 的權限
* `plots.cluster.invite` - 使用命令 `/plot cluster invite` 的權限
* `plots.cluster.tp` - 使用命令 `/plot cluster tp` 的權限
* `plots.cluster.<#>` - 限制玩家能擁有的群集數量
* `plots.cluster.resize.expand` - 使用命令 `/plot cluster expand` 的權限
* `plots.cluster.info` - 使用命令 `/plot cluster info` 的權限
* `plots.cluster.sethome.other` - 管理員權限，設定其他群集的家
* `plots.cluster.resize.other` - 管理員權限，調整其他群集大小
* `plots.cluster.tp.other` - 管理員權限，傳送到其他群集
* `plots.cluster.kick.other` - 管理員權限，踢出其他群集的玩家
* `plots.cluster.create.other` - 管理員權限，建立其他群集
* `plots.cluster.list` - 使用命令 `/plot cluster list` 的權限
* `plots.cluster.delete` - 使用命令 `/plot cluster delete` 的權限
* `plots.cluster.resize.shrink` - 使用命令 `/plot cluster resize shrink` 的權限
* `plots.cluster.sethome` - 使用命令 `/plot cluster sethome` 的權限

---

## Debug

### DEBUGSAVETEST

此指令會強制重新建立資料庫中所有地皮。

**Usage:**
`/plot debugsavetest`

**Permissions:**
`plots.debugsavetest` - 使用命令 `/plot debugsavetest` 的權限

### DEBUGLOADTEST

此除錯指令會強制重新載入資料庫中所有地皮。

**Usage:**
`/plot debugloadtest`

**Permissions:**
`plots.debugloadtest` - 使用命令 `/plot debugloadtest` 的權限

### DEBUGALLOWUNSAFE

允許不安全操作直到關閉此功能。

**Usage:**
`/plot debugallowunsafe`

**Aliases:**
`[ debugallowunsafe ]`

**Permissions:**
`plots.debugallowunsafe` - 使用命令 `/plot debugallowunsafe` 的權限

### DEBUG

顯示除錯資訊或所有語言訊息。

**Usage:**
`/plot debug [msg]`

**Permissions:**
`plots.admin` - 使用命令 `/plot debug msg` 的權限

### DEBUGPASTE

上傳一組檔案用於除錯和錯誤回報，包含 `settings.yml`、`worlds.yml`、你的 `latest.log` 以及 Multiverse 的 `worlds.yml`（若有使用）到 `https://athion.net/ISPaster/paste`。

**Usage:**
`/plot debugpaste`

**Aliases:**
`[ dp ]`

**Permissions:**
`plots.debugpaste` - 使用命令 `/plot debugpaste` 的權限

### DEBUGROADREGEN

根據道路結構圖重新生成所有道路。輸入 "plot" 以從地皮高度重新生成，輸入 "height [height]" 以從自訂高度重新生成。

**Usage:**
`/plot debugroadregen <plot | region [height]>`

**Permissions:**
`plots.debugroadregen` - 使用命令 `/plot debugroadregen` 的權限

### DEBUGEXEC

使用多功能除錯指令。

**Usage:**

_Primary:_

* `/plot debugexec`

_Secondary:_

* `/plot debugexec remove-flag <flag>`
* `/plot debugexec allcmd <condition> <command>`
* `/plot debugexec list-scripts [#]`
* `/plot debugexec all <condition> <code>`
* `/plot debugexec addcmd <file>`
* `/plot debugexec analyze <threshold>`

**Aliases:**
`[ exec, $ ]`

**Permissions:**
`plots.admin` - 使用命令 `/plot debugexec` 的權限

---

## Other permissions

* `plots.admin.area.sudo` - ???
* `plots.projectile.unowned` - 在無主地皮射擊投射物
* `plots.projectile.other` - 對他人地皮射擊投射物
* `plots.admin.interact.blockedcommands` - 使用 `blocked-cmds` 標記的封鎖命令權限
* `plots.admin.update.notify` - 接收 SpigotMC 的更新通知
* `plots.admin.exit.denied` - 管理員權限，離開帶有 `deny-exit` 標記的地皮
* `plots.admin.entry.forcefield` - 管理員權限，繞過 `forcefield` 標記
* `plots.admin.destroy.unowned` - 管理員權限，在無主地皮破壞方塊
* `plots.admin.build.unowned` - 管理員權限，在無主地皮建造方塊
* `plots.admin.destroy.groundlevel` - 管理員權限，破壞地面層
* `plots.admin.destroy.other` - 管理員權限，在他人地皮破壞方塊
* `plots.admin.destroy.road` - 管理員權限，在道路上破壞方塊
* `plots.admin.build.road` - 管理員權限，在道路上放置方塊
* `plots.admin.interact.unowned` - 管理員權限，在無主地皮互動
* `plots.admin.interact.other` - 管理員權限，與他人地皮互動
* `plots.admin.build.heightlimit` - 管理員權限，繞過自訂高度限制

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 所翻譯。雖然我們致力於翻譯的準確性，但請注意自動翻譯可能包含錯誤或不準確之處。原始文件之母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯而產生之任何誤解或誤譯負責。