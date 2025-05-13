<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "e0109d5becfdc8bdbeb75a2664ebc0b9",
  "translation_date": "2025-05-13T04:05:43+00:00",
  "source_file": "plotsquared/optimization/plot-analysis.md",
  "language_code": "tw"
}
-->
# 地塊分析

## 介紹

地塊分析用來更準確判斷地塊的品質，特別是用於清理地塊。它可以手動設定，也可以根據現有的地塊評分進行校準。

這是地塊過期系統的一部分，是在清理超過設定天數的地塊之外的可選檢查項目。

## 為什麼這比之前的修改方塊更好？

單純看修改的方塊數量並不能準確評估地塊品質。玩家可能會大量堆砌方塊，或者像 worldedit 那樣，將地塊設為一大塊石頭。使用地塊分析會將 10 種不同指標與地塊品質做關聯，希望能更準確判斷建築品質，無需逐一人工查看。

## 我該如何手動校準地塊分析？

_請注意也有自動校準功能（見下方）_

在 `settings.yml` 中有一個自動清理的區段：

```yaml
clear:
  auto:
    # If auto clearing is enabled
    enabled: true

    # If the threshold is set to -1, all plots will be cleared
    # Otherwise, any expired plot less than this threshold will be cleared
    threshold: -1

    # This section can be auto calibrated, or done yourself
    calibration:
      changes_sd: 64 # The Standard Deviation of the changes per column
      variety_sd: 1  # The Standard Deviation of the variety of Materials per column
      faces_sd: 32   # The Standard Deviation of the number of block faces showing per column
      air: 0         # The mean of the amount of air per column
      faces: 2       # The mean of the number of block faces showing per column
      changes: 1     # The mean of the changes per column
      data_sd: 1     # The Standard Deviation of the variety of the "BlockData" per column
      variety: 1     # The mean of the variety of Materials per column
      air_sd: 0      # The Standard Deviation of the variety of the amount of air per column
      data: 32       # The mean of the variety of "BlockData" per column

    # The interval at which plots are cleared (lower is faster)
    clear-interval-seconds: 10

    # Any plot older than this will be checked and possibly cleared
    days: 7
```

如果你只想根據修改數量清理地塊，請將所有指標設為 0，只有 "changes" 保持設定，然後根據需要調整複雜度。changes 指標是每欄平均數乘以 100。

*什麼是欄？*  
欄指的是某個方塊所在的整條垂直空間。例如你站在一個方塊上，該欄就是那個方塊以及它正上方和正下方的所有方塊。每欄最多包含 256 個方塊（因為高度是 256 個方塊）。

如果你想清理任何每欄修改少於 7 個方塊的地塊，可以這樣設定：

{% hint style="info" %}
注意，7 ≙ 700 是門檻值，且適用於每個校準參數。
{% endhint %}

```yaml
clear:
  auto:
    # Please note how the threshold is set to 100 * 7 or 700
    threshold: 700

    # This section has be calibrated to only care about blocks changed
    calibration:
      changes_sd: 0
      variety_sd: 0
      faces_sd: 0
      air: 0
      faces: 0
      changes: 1
      data_sd: 0
      variety: 0
      air_sd: 0
      data: 0

    # Set these to whatever you want
    enabled: true
    clear-interval-seconds: 10
    days: 7
```

## 我該如何自動校準地塊分析？

地塊分析可以根據地塊評分自動校準。評分越多，校準就越準確。

**評分地塊請使用：**  
`/plot rate next` - To teleport to the next ratable plot (this is skewed so that low quality plots receive less ratings)  +
``  
`/plot rate <value>` - To rate the plots

The best way to get good data is to just encourage players on the server to rate as many plots as they can - you can always recalibrate.

**To calibrate use:**
``  
`/plot debugexec calibrate-analysis <percentage>`  +
The percentage is what (rough) percent of old plots you would like to have cleared. If you just want to get rid of some really low quality plots e.g. 7% of plots use:   +
``  
`/plot debugexec calibrate-analysis 7`

To view the current complexity of the plot you are in use ``  
`/plot debugexec analyze` - then the same command to view the analysis.

**To recalibrate:**
It is best to clear the current analysis so plots can be re-analyzed:  +
(optional) ``  
`/plot debugexec remove-flag analysis`  +
(required) ``  
`/plot debugexec calibrate-analysis <percentage>`

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 所翻譯。雖然我們力求準確，但請注意自動翻譯可能包含錯誤或不精確之處。原始文件之母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯所產生之任何誤解或誤釋負責。