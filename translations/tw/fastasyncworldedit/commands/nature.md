<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "491a3be30fd04d55bf4256c54807895a",
  "translation_date": "2025-05-13T03:52:43+00:00",
  "source_file": "fastasyncworldedit/commands/nature.md",
  "language_code": "tw"
}
-->
# Drain

這個指令會從一個球形區域中移除水（圖 1）。

-   你必須選擇一個有水的位置才能執行此指令。此指令會從你周圍以你目前位置為中心，半徑為 `radius` 的球體範圍內排乾水。

-   注意此指令只會刪除同一個水源中的水：如果半徑內有另一個水池，會被忽略（圖 2）。

-   使用參數 `-w` 可以將方塊的水浸狀態（[block state](https://minecraft.wiki/w/Block_states)）改成「false」。例如，木質階梯會被「烘乾」，不再帶有水浸狀態（圖 3）。

-   使用參數 `-p` 可以移除所有在水中的植物（圖 4）。

以下圖片中，選取範圍的中心以黃色方塊標示。

## 使用方式

`//drain <radius> [-w] [-p]`

## 權限

`worldedit.drain`

## 視覺範例

1.  ![drain.png](https://i.imgur.com/wnjgiXJ.png)

2.  ![drain\_resource.png](https://i.imgur.com/YTGLAqx.png)

3.  ![drain-w.png](https://i.imgur.com/mf5arBW.png)

4.  ![drain-p.png](https://i.imgur.com/r1NAWsr.png)

# Fixwater

這個指令可以幫助你在周圍生成水池，並修復現有的水池（圖 1）。

-   你必須選擇一個有水的位置才能執行此指令。此指令會將你周圍以你目前位置為中心、半徑為 `radius` 的半球範圍內的空氣方塊替換成水（圖 2）。

-   和 `//drain` 類似，此指令只會作用於同一個水池或水坑內的方塊：如果半徑內有另一個水池或水坑，會被忽略（圖 3）。

以下圖片中，選取範圍的中心以黃色方塊標示。

## 使用方式

`//fixwater <radius>`

## 權限

`worldedit.fixwater`

## 視覺範例

1.  ![fixwater.png](https://i.imgur.com/eaFTnG0.png)

2.  ![fixwater-full.png](https://i.imgur.com/Krav8oA.png)

3.  ![fixwater\_resource.png](https://i.imgur.com/FBuYNm4.png)

# Fixlava

這個指令可以幫助你在周圍生成熔岩池，並修復現有的熔岩池（圖 1）。

-   你必須選擇一個有熔岩的位置才能執行此指令。此指令會將你周圍以你目前位置為中心、半徑為 `radius` 的半球範圍內的空氣方塊替換成熔岩（圖 2）。

-   和 `//drain` 類似，此指令只會作用於同一個熔岩池或熔岩坑內的方塊：如果半徑內有另一個熔岩池或熔岩坑，會被忽略（圖 3）。

以下圖片中，選取範圍的中心以黃色方塊標示。

## 使用方式

`//fixlava <radius>`

## 權限

`worldedit.fixlava`

## 視覺範例

1.  ![fixlava.png](https://i.imgur.com/wbA3QsB.png)

2.  ![fixlava-full.png](https://i.imgur.com/0zhsjLL.png)

3.  ![fixlava\_resource.png](https://i.imgur.com/zmaFyy7.png)

# Snow

這個指令會在你周圍生成雪（圖 1）。

-   指令會在你周圍半徑為 `radius` 的圓形範圍內執行。

-   雪只會生成在 X、Z 座標最高的方塊上方，因此 Y 座標不影響，方便你在丘陵或山區使用。

-   指令只會在空曠的實心方塊上方生成雪，不會移除草叢。

以下圖片中，選取範圍的中心以黃色方塊標示。

## 使用方式

`//snow [radius]`

## 權限

`worldedit.snow`

## 視覺範例

1.  ![snow.png](https://i.imgur.com/vsXCLVH.png)

# Thaw

這個指令會在你周圍融化雪（圖 1）。

-   指令會在你周圍半徑為 `radius` 的圓形範圍內執行。

-   雪只會在 X、Z 座標最高的方塊上方被移除，因此 Y 座標不影響，方便你在丘陵或山區使用。

以下圖片中，選取範圍的中心以黃色方塊標示。

## 使用方式

`//thaw [radius]`

## 權限

`worldedit.thaw`

## 視覺範例

1.  ![thaw.png](https://i.imgur.com/Z5f3djS.png)

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 所翻譯。雖然我們力求準確，但請注意自動翻譯可能包含錯誤或不精確之處。原始文件的母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯而產生之任何誤解或誤譯負責。