<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "834138badf7029c8f255e0973f872f72",
  "translation_date": "2025-05-13T03:54:51+00:00",
  "source_file": "fastasyncworldedit/commands/analysis/analysis.md",
  "language_code": "tw"
}
-->
# 分析指令

## Nbtinfo

顯示你[準心](https://minecraft.wiki/w/File:HUD_example.png)目標方塊的 NBT 資訊，以使用者友善的字串（純文字）形式呈現。

「命名二進位標籤」（NBT）是 Minecraft 中用來以樹狀結構存放各種標籤資料的格式。更多關於 NBT 格式的資訊可以在[這裡](https://minecraft.wiki/w/NBT_format)找到。

**用法：**
`//nbtinfo`

**權限：**
`worldedit.nbtinfo`

**視覺範例：**

![Example 1](../../../../../fastasyncworldedit/commands/analysis/images/nbtinfo.png)

## Chunkinfo

使用此指令可以取得你所在[區塊](https://minecraft.wiki/w/Chunk)的資訊。

- 第一行會顯示你所在區塊的 X 和 Z 座標。
- 另外兩行會顯示區塊檔案的名稱。

更多關於區域檔案格式的資訊可以在[這裡](https://minecraft.wiki/w/Region_file_format)找到。

{% hint style="tip" %}
使用客戶端快捷鍵 `F3 + G` 可以看到區塊邊界。
{% endhint %}

**用法：**
`//chunkinfo`

**權限：**
`worldedit.chunkinfo`

**視覺範例：**

![Example 1](../../../../../fastasyncworldedit/commands/analysis/images/chunkinfo.png)

## Distr

此指令會取得選取區域內方塊的分佈，包括百分比分佈、數量以及在你的 Minecraft 客戶端語言中翻譯的方塊名稱。

將滑鼠移到方塊名稱上可以看到技術名稱（例如 "minecraft:acacia_leaves"），使用 `-d` 參數則會同時顯示方塊數值（方括號內）（見圖2）。

**用法：**
`//distr [-cd] [-p <page>]`

- 你可以使用 `-c` 參數來分析剪貼簿的方塊分佈（例如在執行 `//copy` 指令後），而非選取區域。
- 使用 `-d` 參數時，方塊清單會將不同方塊數值的方塊分開列出。
- 可搭配選用的 `-p` 參數和側邊數字切換清單顯示位置。

**權限：**
`worldedit.analysis.distr`

**視覺範例：**

![Example 1](../../../../../fastasyncworldedit/commands/analysis/images/distr.png)

![Example 2](../../../../../fastasyncworldedit/commands/analysis/images/distr-d.png)

## Count

此指令會取得你選取區域中特定種類方塊的數量。實體（Entities）無法被計數。

**用法：**
`//count <mask>`

- 你可以使用方括號指定方塊數值來搜尋方塊（例如 `acacia_log[axis=x]` 或 `rose_bush[half=upper]`）

**權限：**
`worldedit.analysis.count`

**視覺範例：**

![Example 1](../../../../../fastasyncworldedit/commands/analysis/images/count.png)

## Size

此指令會取得你選取區域的各種尺寸與其他資訊。

輸出細節程度取決於分析的資料來源：

### 分析選取區域

1.  選取類型
2.  類型特定的選取資訊
3.  最大長度、高度與寬度尺寸
4.  對角線距離（以方塊長度計）
5.  方塊數量（使用 `AIR`）

![Example 1](../../../../../fastasyncworldedit/commands/analysis/images/size.png)

### 分析剪貼簿

1.  剪貼簿列表編號
2.  長度、高度與寬度的立方體尺寸
3.  複製位置
4.  方塊數量（使用 `AIR`）

![Example 1](../../../../../fastasyncworldedit/commands/analysis/images/size-c_normal.png)

### 分析結構方塊檔

1.  結構方塊檔名稱
2.  長度、高度與寬度的立方體尺寸
3.  複製位置（若有）
4.  方塊數量（使用 `AIR`）

{% hint style="info" %}
注意，結構方塊檔總是呈現立方體形狀。
{% endhint %}

![Example 1](../../../../../fastasyncworldedit/commands/analysis/images/size-c_schematic.png)

**用法：**
`//size [-c]`

- 你可以使用 `-c` 參數分析剪貼簿／結構方塊檔（例如執行 `//copy` 指令後），而非選取區域的方塊尺寸。

**權限：**
`worldedit.selection.size`

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們致力於翻譯的準確性，但請注意自動翻譯可能包含錯誤或不準確之處。原始文件之母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。本公司不對因使用本翻譯所引起之任何誤解或誤譯負責。