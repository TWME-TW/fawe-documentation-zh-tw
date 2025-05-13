<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "6f70163302691c37403443f57b1a7510",
  "translation_date": "2025-05-13T03:50:22+00:00",
  "source_file": "fastasyncworldedit/advanced-features/transforms.md",
  "language_code": "tw"
}
-->
此頁面目前正在修訂中。

# 介紹

轉換可以套用到筆刷或全域，以修改方塊被改變的位置和方式。

# 語法

## 多重轉換

使用逗號 (`,`) 來隨機從列表中選擇一個轉換，例如  
`#offset[0][1][0],#pattern[stone]`（向上偏移一格方塊，或者改成石頭）

使用與號 (`&`) 來對每個方塊使用多個轉換，例如  
`#offset[0][1][0]&#pattern[stone]`（向上偏移一格方塊，並且改成石頭）

## 參數

轉換參數應該放在中括號內，例如  
`#offset[0][1][0]`

## 設定轉換

### 

權限: `worldedit.global-transform`  
說明: 設定全域遮罩

### 

權限: `worldedit.brush.options.transform`  
說明: 設定筆刷遮罩（多個遮罩用空格 \` \` 或冒號 `:` 分隔）

# 轉換清單

## \#offset <dx> <dy> <dz> \[transform\]

**說明**：偏移轉換

## \#rotate <rotateX> <rotateY> <rotateZ> \[transform\]

**說明**：所有變化將會繞初始位置旋轉

## \#scale <dx> <dy> <dz> \[transform\]

**說明**：所有變化將會被縮放

## \#pattern <pattern> \[transform\]

**說明**：總是使用特定圖案

## \#linear3d <transform>

**說明**：使用 x,y,z 座標從列表中選擇轉換

## \#linear <transform>

**說明**：依序從轉換列表中選擇

## \#spread <dx> <dy> <dz> \[transform\]

**說明**：隨機偏移轉換

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 所翻譯。雖然我們致力於翻譯的準確性，但請注意，自動翻譯可能會包含錯誤或不準確之處。原始文件之母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯而產生之任何誤解或誤譯負責。