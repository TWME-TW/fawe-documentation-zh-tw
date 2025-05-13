<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "92e4cfedc63c65f6c1de93dc2d24ce34",
  "translation_date": "2025-05-13T03:51:56+00:00",
  "source_file": "fastasyncworldedit/commands/geometry.md",
  "language_code": "tw"
}
-->
# Fill

這個指令會根據定義的 `radius` 產生一個半圓。

-   這個指令的使用範例可能是用來填補世界中的洞穴（圖片 1）。

-   只有空氣會被定義的 `pattern` 方塊所取代。

-   預設情況下，半圓的 `depth` 深度為 1 個方塊（圖片 2）。
    當達到設定的深度後，圓形會被「切斷」。

-   `depth` 的最大值是半徑（圖片 3）。

-   預設的 `direction` 是「向下」，但你也可以使用 FAWE 提供的其他方向選項（圖片 4）。

下方圖片中選取範圍的中間以黃色方塊標示。

## 使用方式

`//fill <pattern> <radius> [depth] [direction]`

## 權限

`worldedit.fill`

## 視覺範例

1.  ![fill\_example.png](https://i.imgur.com/6WItisE.png)

2.  ![fill.png](https://i.imgur.com/6EZs2B2.png)

3.  ![fill\_depth.png](https://i.imgur.com/EwP81Kg.png)

4.  ![fill\_direction.png](https://i.imgur.com/vvEzTvC.png)

# Removenear

這個指令會移除你周圍立方體區域內所有指定 `block` 類型的方塊（圖片 1）。

-   `size` 參數定義了你的位置（中心點）到邊界的距離。

-   預設 `size` 為 50，因此指令會在一個 99 x 99 方塊的立方體區域內執行。

下方圖片中選取範圍的中間以黃色方塊標示。

## 使用方式

`//removenear <block> [size]`

## 權限

`worldedit.removenear`

## 視覺範例

1.  ![removenear.png](https://i.imgur.com/riMmbhq.png)

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 所翻譯。雖然我們努力確保翻譯準確，但請注意自動翻譯可能會包含錯誤或不準確之處。原始文件之母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯而產生之任何誤解或誤譯負責。