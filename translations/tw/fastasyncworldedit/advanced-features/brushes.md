<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "04bc03c8e42582065be2eb2ca4003517",
  "translation_date": "2025-05-13T03:49:04+00:00",
  "source_file": "fastasyncworldedit/advanced-features/brushes.md",
  "language_code": "tw"
}
-->
# Brushes

## 介紹

FAWE 有刷子工具，讓你可以從遠處建造和繪製。啟用刷子後，它會綁定到你目前手持的物品。你可以讓不同工具綁定到不同物品，且一個物品最多可綁定兩個刷子。

## 裝備刷子

* 綁定到任意點擊：
`/br <brush>`
* 裝備到右鍵點擊：
`/br primary <brush>`
* 裝備到左鍵點擊：
`/br secondary <brush>`

### 更改刷子設定

* [`/mat <pattern>`](../patterns/patterns.md) - 圖案決定放置的內容
* [`/mask <mask>`](../masks/masks.md#_masks) - 目的遮罩決定方塊是否要被更改
* [`/smask <mask>`](../masks/masks.md#_smask_masks_) - 來源遮罩決定方塊是否能被放置
* [`/targetmask <mask>`](../masks/masks.md) - 刷子目標的方塊，預設遮罩是 `!air`
* [`/transform <transform>`](../transforms/transforms.md) - 轉換改變方塊放置的位置
* `/range <range>` - 可使用刷子的距離
* `/size <size>` - 刷子大小（例如半徑10的球體）
* `/none` - 解除工具綁定  +
使用 `-h` 標誌來更改你副手刷子的設定。

### 更改刷子目標模式

你可以改變目標模式以協助在不同區域建造（空氣、牆壁、地面等）。
更改 `//brush range` 也很有用。  +
`/br target <0-3>`

* 0 = 目標方塊
* 1 = 目標前方點，距離依俯仰角決定
* 2 = 目標點，距離依離地高度決定
* 3 = 目標方塊面

### 新增刷子動作

使用滑鼠滾輪改變刷子行為

* `/br scroll clipboard <file|folder|asset url>`
* `/br scroll mask <mask1> <mask2...>`
* `/br scroll pattern <mat1> <mat2...>`
* `/br scroll range`
* `/br scroll size`
* `/br scroll target`

### 重置刷子

蹲下（`shift`）並點擊來重置刷子。+
例如這會清除 copypaste 刷子的剪貼簿，並重置 spline 刷子的點。

### 顯示刷子（目前尚未實作）

使用 FAWE 可以視覺化刷子會如何改變方塊：
`/br vis <0-2>`

* 0 = 不顯示
* 1 = 單一點
* 2 = 顯示所有方塊變化

![Video](https://www.youtube.com/watch?v=xX-MTSLoNXw)
![image](https://i.imgur.com/J2g6Qfn.jpeg)

### 刷子：

[欲查看刷子列表，請參考指令頁面。](../main-commands-and-permissions.md#_brush_commands)

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 所翻譯。雖然我們努力追求準確性，但請注意，自動翻譯可能會包含錯誤或不精確之處。原始文件之母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯而產生之任何誤解或誤釋負責。