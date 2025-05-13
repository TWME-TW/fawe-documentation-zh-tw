<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "64309298c9dd719356920331a49c0846",
  "translation_date": "2025-05-13T03:51:16+00:00",
  "source_file": "fastasyncworldedit/commands/commands.md",
  "language_code": "tw"
}
-->
{% hint style="info" %}
此頁面目前仍在進行中。您可以在[這裡](../../../../fastasyncworldedit/commands)找到原始頁面。
{% endhint %}

{% hint style="info" %}
這個維基是由我們的志工手動更新已知的錯誤，這些錯誤會以紅色框標示在維基上。因此，列出的錯誤可能已經被修正。欲了解更多細節及最新狀態，請參考 GitHub Issue Tracker。
{% endhint %}

# 指令語法

指令語法提供指令可接受的有效參數總覽。指令語法位於所有指令的說明中。

範例：`//fill <pattern> <radius> [depth] [direction]`

- `<...>` = 必填參數
- `[...]` = 選填參數（具體預設值請參考連結的詳細頁面）

# 方向參數

許多指令會使用 `[direction]` 參數。你可以從以下方向中選擇：

## 基本方位
- `north` 或 `n`
- `east` 或 `e`
- `south` 或 `s`
- `west` 或 `w`

## 相對於你的位置／視角
- `up` 或 `u`
- `down` 或 `d`
- `forward` 或 `f` = `me` 或 `m`
- `back` 或 `b`
- `left` 或 `l`
- `right` 或 `r`

（若無輸入，預設會使用方向參數 `forward`。）

# 指令列表

`/fawe` 指令前綴可以與以下別名互換使用：

- `/fastasyncworldedit ...`
- `/worldedit ...`
- `/we ...`

## 基本指令

| 指令                                            | 說明                              |
|------------------------------------------------|----------------------------------|
| [Help](../../../../fastasyncworldedit/commands/basic-commends/basic-commends)     | 顯示 FAWE 指令的說明             |
| [Confirm](../../../../fastasyncworldedit/commands/basic-commends/basic-commends) | 確認部分 FAWE 動作的指令         |

## 選取

| 指令                                                     | 說明                                    |
|----------------------------------------------------------|-----------------------------------------|
| [Sel](selection/selection.md#sel)                        | 取消選取或更改選取類型                 |
| [Wand](selection/selection.md#wand)                      | 取得選取工具物品                       |
| [Pos1 & Pos2](selection/selection.md#pos1-and-pos2)      | 設定選取區域的角落                     |
| [Hpos1 & Hpos2](selection/selection.md#hpos1-and-hpos2)  | 設定選取區域的角落                     |
| [Chunk](selection/selection.md#chunk)                    | 選取區塊                               |
| [Shift](selection/selection.md#shift)                    | 將選取區向某方向移動                   |
| [Inset](selection/selection.md#inset)                    | 將選取區向內縮小                       |
| [Outset](selection/selection.md#outset)                  | 將選取區向外擴大                       |
| [Contract](selection/selection.md#contract)              | 沿所有頂點將選取區收縮                 |
| [Expand](selection/selection.md#expand)                  | 沿所有頂點將選取區擴展                 |

## 管理

| 指令                                                         | 說明                                  |
|--------------------------------------------------------------|--------------------------------------|
| [Version](administrative/administrative.md#version)           | 顯示目前使用的 FAWE 版本             |
| [Threads](administrative/administrative.md#threads)           | 顯示所有執行緒堆疊                   |
| [Reload](administrative/administrative.md#reload)             | 使用最後的設定重新載入外掛           |
| [Timezone](administrative/administrative.md#timezone)         | 設定快照的時區                       |
| [Debugpaste](administrative/administrative.md#debugpaste)     | 產生並上傳技術除錯資訊               |
| [WorldEditAnywhere](administrative/administrative.md#worldeditanywhere) | 避開區域限制                     |

## 導航

| 指令                                             | 說明                                |
|--------------------------------------------------|------------------------------------|
| [Jumpto](navigation/navigation.md#jumpto)        | 傳送你到指定位置                   |
| [Unstuck](navigation/navigation.md#unstuck)      | 讓你從卡住的方塊中脫困             |
| [Thru](navigation/navigation.md#thru)            | 穿越你面前的牆壁                   |
| [Ascend](navigation/navigation.md#ascend)        | 往上一層樓                         |
| [Descend](navigation/navigation.md#descend)      | 往下一層樓                         |
| [Up](navigation/navigation.md#up)                  | 向上移動一段距離                   |
| [Ceil](navigation/navigation.md#ceil)              | 往最近的天花板上方移動             |

## 分析

| 指令                                               | 說明                                      |
|----------------------------------------------------|--------------------------------------------|
| [Nbtinfo](analysis/analysis.md#nbtinfo)            | 以易讀格式顯示方塊的 NBT 資訊             |
| [Chunkinfo](analysis/analysis.md#chunkinfo)        | 取得你所在區塊的資訊                       |
| [Distr](analysis/analysis.md#distr)                 | 取得選取區或剪貼簿內方塊的分佈             |
| [Count](analysis/analysis.md#count)                 | 取得選取區內特定類型方塊的數量             |
| [Size](analysis/analysis.md#size)           | 取得選取範圍或剪貼簿的各種尺寸測量       |

## Geometric

| Command                                         | Description                    | more details                   |
|-------------------------------------------------|--------------------------------|--------------------------------|
| `//fill <pattern> <radius> [depth] [direction]` | 用半圓形填補洞穴 | [here](geometry.md#fill)       |
| `//removenear <block> [size]`                   | 移除你附近的方塊         | [here](geometry.md#removenear) |

## Biomes

| Command                   | Description                           | more details                |
|---------------------------|---------------------------------------|-----------------------------|
| `//biomelist [-p <page>]` | 取得所有可用生物群系的清單    | [here](biomes.md#nbtinfo)   |
| `//biomeinfo [-p] [-t]`   | 顯示方塊或區域的生物群系 | [here](biomes.md#biomeinfo) |
| `//setbiome <biome> [-p]` | 設定區域的生物群系           | [here](biomes.md#setbiome)  |

## Nature

| Command                      | Description                             | more details               |
|------------------------------|-----------------------------------------|----------------------------|
| `//drain <radius> [-w] [-p]` | 移除你周圍水池的水 | [here](nature.md#drain)    |
| `//fixwater <radius>`        | 生成或修復水源             | [here](nature.md#fixwater) |
| `//fixlava <radius>`         | 生成或修復熔岩源              | [here](nature.md#fixlava)  |
| `//snow [radius]`            | 在半徑範圍內生成雪               | [here](nature.md#snow)     |
| `//thaw [radius]`            | 在半徑範圍內融化雪                   | [here](nature.md#thaw)     |

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們致力於確保準確性，但請注意自動翻譯可能包含錯誤或不準確之處。原始文件之母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯而產生之任何誤解或誤譯負責。