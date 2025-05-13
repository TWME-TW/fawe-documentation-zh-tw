<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "c0dc4c593a464f79c00bfca96108e579",
  "translation_date": "2025-05-13T03:38:23+00:00",
  "source_file": "fastasyncworldedit/main-commands-and-permissions.md",
  "language_code": "tw"
}
-->
# Commands and Permissions

:experimental: // 用於鍵盤按鈕

## 介紹

要在遊戲內查看此資訊，請使用 `//help [category|command]`

## 指令語法

* `<arg>` - 必填參數
* `[arg]` - 選填參數
* `<arg1|arg2>` - 多重參數選項
* `<arg=value>` - 預設或建議值
* `-a` - 指令標誌，例如 `//<command> -a [flag-value]`

另見：

* [Biomes](commands/biomes.md)
* [Brushes](advanced-features/brushes.md)
* [Geometry](commands/geometry.md)
* [Nature](commands/nature.md)
* [Navigation](commands/navigation/navigation.md)
* [Selection](commands/selection/selection.md)
* [Masks](advanced-features/masks.md)
* [Patterns](advanced-features/patterns.md)
* [Transforms](advanced-features/transforms.md)

## 內容

點擊分類以查看指令列表，或使用 `More Info` 查看詳細說明

* [World Edit Commands](../../../fastasyncworldedit) - 更新、資訊、除錯及幫助指令
* [Utility Commands](../../../fastasyncworldedit) - 各種實用指令
* [Region Commands](../../../fastasyncworldedit) - 操作區域的指令
* [Selection Commands](../../../fastasyncworldedit) - 更改選取點、模式或查看選取資訊
* [History Commands](../../../fastasyncworldedit) - 撤銷、重做及清除歷史的指令
* [Schematic Commands](../../../fastasyncworldedit) - 操作結構檔案的指令
* [Clipboard Commands](../../../fastasyncworldedit) - 複製與貼上方塊相關指令
* [Generation Commands](../../../fastasyncworldedit) - 建造結構與地形特徵
* [Biome Commands](../../../fastasyncworldedit) - 更改、列出及檢視生物群系
* [Super Pickaxe Commands](../../../fastasyncworldedit) - 超級稿指令
* [Navigation Commands](../../../fastasyncworldedit) - 控制玩家移動的指令
* [Snapshot Commands](../../../fastasyncworldedit) - 列出、載入及查看快照資訊
* [Scripting Commands](../../../fastasyncworldedit) - 執行工藝腳本
* [Chunk Commands](../../../fastasyncworldedit) - 檢查區塊
* [Options Commands](../../../fastasyncworldedit) - 玩家切換、設定與物品資訊
* [Brush Options Commands](../../../fastasyncworldedit) - 工具指令
* [Tool Commands](../../../fastasyncworldedit) - 綁定功能到手持物品
* [Brush Commands](../../../fastasyncworldedit) - 遠距建造與繪圖指令
* [/Masks](../../../fastasyncworldedit) - 各種遮罩的幫助說明
* [/Patterns](../../../fastasyncworldedit) - 各種圖案的幫助說明
* [/Transforms](../../../fastasyncworldedit) - 各種轉換的幫助說明
* [Create From Image](../../../fastasyncworldedit) - 從圖片建立世界，目前尚未實作

### 未分類

| 別名             | 權限               | 標記  | 用法                                   |
|------------------|--------------------|-------|----------------------------------------|
| //cancel         | `fawe.cancel`      | 無    | 取消你目前的操作                       |
| /plot replaceall | `plots.replaceall` | 無    | 替換整個地塊世界的方塊                |


### *世界編輯指令*
資訊、除錯與幫助指令

#### /we threads

*權限*: `worldedit.threads`  
*說明*: 列印所有執行緒堆疊

#### /we version

*說明*: 取得 WorldEdit/FAWE 版本

#### /we help [\<command>]

*權限*: `worldedit.help`  
*說明*: 顯示 FAWE 指令的幫助資訊

#### /we reload

*權限*: `worldedit.reload`  
*說明*: 重新載入設定檔

#### /we cui

*說明*: 完成 CUI 握手 (內部使用)

#### /fawe debugpaste

*權限*: `worldedit.debugpaste`  
*說明*: 上傳除錯資訊到 https://athion.net/ISPaster/paste

#### /we tz [timezone]

*說明*: 設定快照的時區

---

### *實用指令*
各種實用指令

---

#### /remove \<type> \<radius>

*權限*: `worldedit.remove`  
*說明*: 移除指定類型的所有實體

#### //fill \<pattern> \<radius> [depth] [direction]

*權限*: `worldedit.fill`  
*說明*: 填補一個洞

#### //help [\<command>]

*說明*: 顯示 WorldEdit 指令的幫助資訊

#### //drain \<radius>

*權限*: `worldedit.drain`  
*說明*: 排乾水池

#### /transforms [page=1|search|transform]

*權限*: `worldedit.transforms`  +  
*說明*: 變換會改變方塊的放置方式  
- 使用 [中括號] 表示參數  
- 用 , 表示或 (OR) 多個條件  
- 用 & 表示且 (AND) 多個條件  

#### //removenear \<block> [size]

*權限*: `worldedit.removenear`  
*說明*: 移除你附近的方塊

#### //fixlava \<radius>

*權限*: `worldedit.fixlava`  
*說明*: 修正岩漿使其保持靜止

#### //removeabove [size] [height]

*權限*: `worldedit.removeabove`  
*說明*: 移除你頭頂上的方塊

#### /masks [page=1|search|mask]

*權限*: `worldedit.masks`  
*說明*: 遮罩決定方塊是否能被放置  
- 使用 [中括號] 表示參數  
- 用 , 表示或 (OR) 多個條件  
- 用 & 表示且 (AND) 多個條件  

例如 >[stone,dirt],#light[0][5],$jungle

#### //fillr \<pattern> \<radius> [depth]

*權限*: `worldedit.fill.recursive`  
*說明*: 遞迴填補洞穴

#### /patterns [page=1|search|pattern]

*權限*: `worldedit.patterns`  
*說明*: 模式決定放置哪些方塊  
- 使用 [中括號] 表示參數  
- 用 , 表示或 (OR) 多個條件  

例如 #surfacespread[10][#existing],andesite

#### //replacenear \<size> \<from-id> \<to-id> [-f]

*權限*: `worldedit.replacenear`  
*說明*: 替換附近的方塊

#### //snow [radius]

*權限*: `worldedit.snow`  
*說明*: 模擬下雪

#### //thaw [radius]

*權限*: `worldedit.thaw`  
*說明*: 融化區域

#### //removebelow [size] [height]

*權限*: `worldedit.removebelow`  
*說明*: 移除你下方的方塊

#### //fixwater \<radius>

*權限*: `worldedit.fixwater`  
*說明*: 修正水源使其保持靜止

#### /butcher [radius] [-p] [-l] [-a] [-n] [-g] [-b] [-t] [-f] [-r]

*權限*: `worldedit.butcher`  
*說明*: 根據半徑殺死附近生物，若無指定則使用設定檔預設值。  
標記：  
-p 也殺死寵物  
-n 也殺死 NPC  
-g 也殺死鐵巨人  
-a 也殺死動物  
-b 也殺死環境生物  
-t 也殺死帶名字標籤的生物  
-f 結合以上所有標記  
-r 也破壞盔甲架  
-l 目前無作用

#### //confirm

*權限*: `fawe.confirm`  
*說明*: 確認指令

#### //green [radius] [-f]

*權限*: `worldedit.green`  
*說明*: 讓區域變綠

#### //calc \<expression>

*權限*: `worldedit.calc`  
*說明*: 計算數學表達式

#### //ex [radius]

*權限*: `worldedit.extinguish`  
*說明*: 撲滅附近火焰

#### /heightmapinterface

*權限*: `fawe.admin`  
*說明*: 產生高度圖介面

---

### *區域指令*
操作區域的指令
---

#### //replace [from-mask] \<to-pattern> [-f]

*權限*: `worldedit.region.replace`  
*說明*: 用另一種方塊替換選取區域的所有方塊

#### //stack [count] [direction] [-s] [-a] [-m]

*權限*: `worldedit.region.stack`  
*說明*: 重複選取區域的內容。  
標記：  
-s 將選取區域移到最後一個複製的位置  
-a 跳過空氣方塊

#### //set [pattern]

*權限*: `worldedit.region.set`  
*說明*: 設定選取區域內所有方塊

#### //fall [replace] [-m]

*權限*: `worldedit.region.fall`  
*說明*: 讓選取區域內的方塊下落  
-m 標記表示只在垂直選取範圍內下落

#### //faces \<pattern>

*權限*: `worldedit.region.faces`  
*說明*: 建造選取區域的牆壁、天花板與地板

#### //hollow [\<thickness>[ \<pattern>]]

*權限*: `worldedit.region.hollow`  
*說明*: 挖空選取區域內的物體。  
可選擇用指定方塊填滿挖空部分。  
厚度以曼哈頓距離計算。

#### //center \<pattern>

*權限*: `worldedit.region.center`  
*說明*: 設定中心方塊

#### //setskylight

*權限*: `worldedit.light.set`  
*說明*: 設定選取區域的天空光照

#### //nbtinfo

*權限*: `worldedit.nbtinfo`  
*說明*: 查看方塊的 NBT 資訊

#### //setblocklight

*權限*: `worldedit.light.set`  
*說明*: 設定選取區域的方塊光照

#### //curve \<pattern> [thickness] [-h]

*權限*: `worldedit.region.curve`  
*說明*: 在選取點間繪製樣條曲線。  
僅能用於凸多面體選取。  
標記：  
-h 只產生外殼

#### //overlay \<pattern>

*權限*: `worldedit.region.overlay`  
*說明*: 在區域內的方塊上方放置方塊

#### //lay \<pattern>

*權限*: `worldedit.region.overlay`  
*說明*: 設定區域頂層方塊

#### //naturalize

*權限*: `worldedit.region.naturalize`  
*說明*: 表層三層土壤，下方為岩石

#### //walls \<pattern>

*權限*: `worldedit.region.walls`  
*說明*: 建造選取區域的四面牆壁

#### //getlighting

*權限*: `worldedit.light.fix`  
*說明*: 取得指定位置的光照

#### //removelight

*權限*: `worldedit.light.remove`  
*說明*: 移除選取區域的光照

#### //fixlighting

*權限*: `worldedit.light.fix`  
*說明*: 修正指定位置的光照

#### //smooth [iterations] [mask]

*權限*: `worldedit.region.smooth`  
*說明*: 平滑選取區域的高度。  
標記：  
-l 設定雪塊下方的雪層數量  
-m 使用指定遮罩作為高度圖

#### //line \<pattern> [thickness] [-h]

*權限*: `worldedit.region.line`  
*說明*: 在立方體選取的角落間繪製線段。  
僅能用於立方體選取。  
標記：  
-h 只產生外殼

#### //regen [biome] [seed]

*權限*: `worldedit.regen`  
*說明*: 重新生成目前選取區域的內容。  
此指令可能會影響同一區塊中選取區外的區域。

#### //wea

*權限*: `fawe.admin`  
*說明*: 繞過區域限制

#### //move [count] [direction] [leave-id] [-s]

*權限*: `worldedit.region.move`  
*說明*: 移動選取區域的內容。  
-s 將選取區移到目標位置。  
-b 同時移動生物群系  
-e 同時移動實體  
-a 忽略空氣  
-m 設定包含遮罩，不符合的方塊變成空氣  
可選擇用填充物填滿原本位置。

#### //forest [type] [density]

*權限*: `worldedit.region.forest`  
*說明*: 在區域內生成森林

#### //deform \<expression> [-r] [-o]

*權限*: `worldedit.region.deform`  
*說明*: 用表達式變形選取區域  
此表達式會對每個方塊執行，並預期修改 x, y, z 變數以指向新方塊。  
詳見 tinyurl.com/wesyntax。

#### //flora [density]

*權限*: `worldedit.region.flora`  
*說明*: 在區域內生成植物

#### //wer

*權限*: `fawe.worldeditregion`  
*說明*: 選取你目前被允許的區域

---

### *選取指令*
更改選取點、模式或查看選取資訊
---

#### //count \<block> [-d]

*權限*: `worldedit.analysis.count`  
*說明*: 計算特定方塊的數量

#### //size [-c]

*權限*: `worldedit.selection.size`  
*說明*: 取得選取區域資訊

#### //expand \<amount> [reverse-amount] \<direction>

*權限*: `worldedit.selection.expand`  
*說明*: 擴展選取區域

#### //shift \<amount> [direction]

*權限*: `worldedit.selection.shift`  
*說明*: 移動選取區域

#### //sel [cuboid|extend|poly|ellipsoid|sphere|cyl|convex] [-d]

*說明*: 選擇區域選取模式

#### //contract \<amount> [reverse-amount] [direction]

*權限*: `worldedit.selection.contract`  
*說明*: 收縮選取區域

#### //pos2 [coordinates]

*權限*: `worldedit.selection.pos`  
*說明*: 設定位置 2

#### //pos1 [coordinates]

*權限*: `worldedit.selection.pos`  
*說明*: 設定位置 1

#### //chunk [x,z coordinates] [-s] [-c]

*權限*: `worldedit.selection.chunk`  
*說明*: 將選取區域設為你目前所在的區塊。  
使用 -s 標記會擴展你的選取區域，包含所有相關區塊。  
指定座標會使用該位置而非目前位置。  
用 -c 指定區塊座標，否則會視為完整座標。  
（例如座標 5,5 與 -c 0,0 是一樣的）

#### //hpos1

*權限*: `worldedit.selection.hpos`  
*說明*: 將位置 1 設為目標方塊

#### //outset \<amount> [-h] [-v]

*權限*: `worldedit.selection.outset`  
*說明*: 向四周擴展選取區域指定距離。  
標記：  
-h 僅水平擴展  
-v 僅垂直擴展

#### //wand

*權限*: `worldedit.wand`  
*說明*: 取得魔杖物件

#### /toggleeditwand

*權限*: `worldedit.wand.toggle`  
*說明*: 切換編輯魔杖功能

#### //hpos2

*權限*: `worldedit.selection.hpos`  
*說明*: 將位置 2 設為目標方塊

#### //inset \<amount> [-h] [-v]

*權限*: `worldedit.selection.inset`  
*說明*: 向內收縮選取區域指定距離。  
標記：  
-h 僅水平收縮  
-v 僅垂直收縮

#### //distr  [-c] [-d]

*權限*: `worldedit.analysis.distr`  
*說明*: 取得選取區域內方塊的分布狀況。  
-c 標記取得剪貼簿的分布狀況。  
-d 標記依數據分開方塊

---

### *歷史指令*
復原、重做與清除歷史紀錄的指令
---

#### //clearhistory

*權限*: `worldedit.history.clear`  
*說明*: 清除歷史紀錄

#### //undo [times] [player]

*權限*: `worldedit.history.undo`  
*說明*: 復原上一次動作

#### //redo [times] [player]

*權限*: `worldedit.history.redo`  
*說明*: 重做上一次動作（從歷史）

#### //inspect

*權限*: `worldedit.tool.inspect`  
*說明*: 掃描方塊變動

#### //frb history \<user=Empire92> \<radius=5> \<time=3d4h>

*權限*: `worldedit.history.rollback`  
*說明*: 復原特定編輯。時間格式可用 s, m, h, d, y。  
- 從硬碟匯入：/frb #import

---

### *結構指令*
操作結構檔案的指令
---

#### /schematic clear

*權限*: `worldedit.clipboard.clear`, `worldedit.schematic.clear`  
*說明*: 清空剪貼簿

#### /schematic load [\<format>] \<filename>

*權限*: `worldedit.clipboard.load`, `worldedit.schematic.load`, `worldedit.schematic.upload`, `worldedit.schematic.load.other`  
*說明*: 載入結構檔到剪貼簿

#### /schematic delete \<filename|*>

*權限*: `worldedit.schematic.delete`, `worldedit.schematic.delete.other`  
*說明*: 從結構檔列表刪除結構檔

#### /schematic list [global|mine|\<filter>] [page=1] [-d] [-n] [-p]

*權限*: `worldedit.schematic.list`  
*說明*: 列出結構檔目錄中的所有結構檔  
-p 印出指定頁面  
-f 限制格式

#### /schematic save [format] \<filename>

*權限*: `worldedit.clipboard.save`, `worldedit.schematic.save`, `worldedit.schematic.save.other`  
*說明*: 將結構檔存到剪貼簿

#### /schematic unload [file]

*權限*: `worldedit.clipboard.clear`, `worldedit.schematic.clear`  
*說明*: 從多剪貼簿中移除剪貼簿

#### /schematic loadall [<format>] \<filename|url>

*權限*: `worldedit.clipboard.load`, `worldedit.schematic.load`, `worldedit.schematic.upload`  
*說明*: 載入多個剪貼簿  
-r 標記會隨機旋轉

#### /schematic move \<directory>

*權限*: `worldedit.schematic.move`, `worldedit.schematic.move.other`  
*說明*: 移動你目前載入的結構檔

#### /schematic formats

*權限*: `worldedit.schematic.formats`  
*說明*: 列出可用的格式

#### /schematic show [global|mine|<filter>] [-d] [-n] [-p]

*權限

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們致力於翻譯的準確性，但請注意，自動翻譯可能會包含錯誤或不準確之處。原始文件的母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用此翻譯所產生之任何誤解或誤譯負責。