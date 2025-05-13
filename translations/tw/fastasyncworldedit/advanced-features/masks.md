<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "2568ea3bf3252dc2db27cb82eb640db8",
  "translation_date": "2025-05-13T03:49:27+00:00",
  "source_file": "fastasyncworldedit/advanced-features/masks.md",
  "language_code": "tw"
}
-->
# Introduction

本頁面目前正在修訂中。

# Masks

**想了解 WorldEdit 提供的基本遮罩請點擊  
[here](https://worldedit.readthedocs.io/en/latest/usage/general/masks/)。**

遮罩是在放置方塊時的編輯限制，例如只替換石頭下面的方塊。全域遮罩會套用到所有編輯，畫筆遮罩則只套用於目前的畫筆。

# Syntax

## Blocks

使用方塊的名稱或 ID（例如 `stone`）。

## Multiple masks

使用 `,`(OR) 或 `&`(AND) 來分隔多個遮罩，例如  
`grass_block,$desert`

## Arguments

遮罩參數應該放在中括號內，例如 `#offset[0][5][3]`

# Setting a mask

## 

Perm: `worldedit.global-mask`  
Desc: 此指令會將遮罩套用到你所有的 WorldEdit 動作，全域生效。此遮罩是根據目標方塊（也就是世界中的方塊）判斷。

## 

Perm: `worldedit.global-mask`  
Desc: 全域來源遮罩會套用到你所有的編輯，遮罩是根據來源方塊判斷（例如剪貼簿中的方塊）

## 

Perm: `worldedit.brush.options.mask`  
Desc: 設定畫筆的目標遮罩

## 

Perm: `worldedit.brush.options.mask`  
Desc: 設定畫筆的來源遮罩

# Mask list

## \#offset <dx> <dy> <dz> <mask>

**Desc**: 偏移遮罩

## % <chance>

**Desc**: 百分比機率

## \#id

**Desc**: 限制為初始 ID

## \#existing

**Desc**: 如果存在非空氣方塊

## \#data

**Desc**: 限制為初始資料值

## { <min> <max>

**Desc**: 限制方塊在初始方塊特定半徑範圍內

## \#surface

**Desc**: 限制為表面方塊（任何與空氣相鄰的實心方塊）

## = <expression>

**Desc**: 表達式遮罩

## ! <mask>

**Desc**: 否定另一個遮罩

## $ <biome>

**Desc**: 在特定生物群系中。生物群系列表請使用 //biomelist

## \#region

**Desc**: 在指定選取範圍內

## ~ <mask> \[min=1\] \[max=8\]

**Desc**: 與特定數量的其他方塊相鄰

## / <min> <max>

**Desc**: 限制於特定地形角度  
-o 參數只會疊加  
範例：/\[0d\]\[45d\]  
說明：允許相鄰方塊角度在 0 到 45 度之間的任何方塊。  
範例：/\[3\]\[20\]  
說明：允許相鄰方塊在下方 3 到 20 個方塊範圍內的任何方塊。

## \#dregion

**Desc**: 在玩家選取範圍內

## \#xaxis

**Desc**: 限制於初始 X 軸

## \#liquid

**Desc**: 如果有實心方塊

## true

**Desc**: 永遠為真

## false

**Desc**: 永遠為假

## > <mask>

**Desc**: 在特定方塊上方

## \#wall

**Desc**: 限制於牆壁（任何與空氣相鄰的方塊，方向為北、東、南、西）

## \#zaxis

**Desc**: 限制於初始 Z 軸

## \#yaxis

**Desc**: 限制於初始 Y 軸

## < <mask>

**Desc**: 在特定方塊下方

## \#simplex <scale=10> <min=0> <max=100>\`

**Desc**: 使用 simplex 噪音作為遮罩

## \#solid

**Desc**: 如果有實心方塊

## \#surfaceangle\[min\]\[max\]\[depth\] (material)

**Desc**: 替換方塊表面

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們力求準確，但請注意，自動翻譯可能包含錯誤或不準確之處。原始文件之母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯所產生之任何誤解或誤釋負責。