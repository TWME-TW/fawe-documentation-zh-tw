<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "d8b72cad8c508c60de58101371b3f5d3",
  "translation_date": "2025-05-13T03:49:53+00:00",
  "source_file": "fastasyncworldedit/advanced-features/patterns.md",
  "language_code": "tw"
}
-->
# Introduction

此頁面目前正在修訂中。

在更改方塊時，會在各種指令中使用 Patterns，例如  
`//set <pattern>` 和 `//material <pattern>`

# Syntax

## Blocks

使用方塊的名稱或 ID（例如 `stone`）。

## Inventory

你可以使用 `hand`，或像是 `slot5` 來使用你的物品欄中的方塊。

## Multiple patterns

用逗號（`,`）來隨機從多個 Patterns 中選擇方塊。  
若要指定比例，可以使用 `%`，例如 `80%stone,20%planks`

## Arguments

Pattern 的參數應該放在中括號內，例如  
`#simplex[10][stone,wood]`

# Pattern list

## \#offset <dx> <dy> <dz> <pattern>

**Desc**: 偏移一個 Pattern

## \#mask <mask> <pattern-true> <pattern-false>

**Desc**: 根據遮罩來套用 Pattern

## \#spread <dx> <dy> <dz> <pattern>

**Desc**: 隨機散佈方塊

## \#buffer <pattern>

**Desc**: 在使用 Pattern 時，每個方塊只放置一次  
搭配筆刷使用，避免重複套用同一個位置

## \#color <color>

**Desc**: 使用最接近特定顏色的方塊

## \#clipboard

**Desc**: 使用剪貼簿中的方塊當作 Pattern

## \#existing

**Desc**: 使用已存在的方塊

## \#biome <biome>

**Desc**: 設定生物群系

## = <expression>

**Desc**: 表達式 Pattern：  
<http://wiki.sk89q.com/wiki/WorldEdit/Expression_syntax>

## \#relative <pattern>

**Desc**: 將 Pattern 偏移到你點擊的位置

## \#saturate <r> <g> <b>

**Desc**: 用顏色飽和現有的方塊

## \#darken

**Desc**: 使現有的方塊變暗

## \#anglecolor <distance>

**Desc**: 根據地形角度，使用較暗的方塊

## \#desaturate <percent>

**Desc**: 降低現有方塊的飽和度

## \#averagecolor <r> <g> <b>

**Desc**: 現有方塊與指定顏色的平均色

## \#fullcopy \[schem|folder|url=#copy\] \[rotate=false\] \[flip=false\]

**Desc**: 在每個方塊位置放置完整剪貼簿內容

## \#buffer2d <pattern>

**Desc**: 在使用 Pattern 時，每個直列只放置一次方塊

## \#angledata

**Desc**: 根據地形角度的方塊資料

## \#lighten \[randomize=true\] \[max-complexity=100\]

**Desc**: 使現有方塊變亮

## \#!x <pattern>

**Desc**: 此 Pattern 不會提供 z 軸資訊。  
範例：!x\[!z\[#~\[#l3d\[pattern\]\]\]\]

## \#surfacespread <distance> <pattern>

**Desc**: 僅套用在表面方塊。從提供的 Pattern 中選擇方塊，並用指定的隨機偏移量 \[0, )。  
例如，使用 `#existing` 來隨機偏移世界中的方塊，或 `#copy` 來偏移剪貼簿中的方塊。

## \#solidspread <dx> <dy> <dz> <pattern>

**Desc**: 隨機散佈實心方塊

## \#linear2d <pattern> \[xscale=1\] \[zscale=1\]

**Desc**: 使用 x,z 座標從清單中選擇方塊

## \#!y <pattern>

**Desc**: 此 Pattern 不會提供 y 軸資訊

## \#linear3d <pattern> \[xscale=1\] \[yscale=1\] \[zscale=1\]

**Desc**: 使用 x,y,z 座標從清單中選擇方塊

## \#linear <pattern>

**Desc**: 從 Pattern 清單中依序設定方塊

## \#!z <pattern>

**Desc**: 此 Pattern 不會提供 z 軸資訊

## \#simplex <scale=10> <pattern>

**Desc**: 使用 simplex 噪聲隨機化方塊

## \#perlin <scale=10> <pattern>

**Desc**: 使用 perlin 噪聲隨機化方塊

## \#rmf <scale=10> <pattern>

**Desc**: 使用 ridged 多重分形噪聲隨機化方塊

## \#voronoi <scale=10> <pattern>

**Desc**: 使用 voronoi 噪聲隨機化方塊

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 所翻譯。雖然我們致力於翻譯準確，但請注意，自動翻譯可能會包含錯誤或不準確之處。原始文件之母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯而產生之任何誤解或誤譯負責。