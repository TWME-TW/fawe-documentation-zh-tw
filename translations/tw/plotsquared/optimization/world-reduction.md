<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "20d81fbc26d659c5afc44edb0d85e8ec",
  "translation_date": "2025-05-13T04:06:00+00:00",
  "source_file": "plotsquared/optimization/world-reduction.md",
  "language_code": "tw"
}
-->
# 世界縮減

透過以下功能，你可以限制並縮小你的地塊世界大小，以提升效能、節省記憶體，並避免產生大量未使用空間的無盡地塊世界。

## 世界邊界

為防止無止盡的探索，每個地塊世界都可以啟用世界邊界。此選項可在 `worlds.yml` 的 `worlds.<world>.world.border` 中找到。世界邊界是以距離原點 `(0;0)` 最遠的地塊為基準，並會阻止該區域外的區塊被載入。

如果你已有距離原點很遠的地塊，世界邊界的效果就不大。此時你可以使用 [Plot condensation](world-reduction.md#plot-condensation-intensive)。

### 地塊過期

在 `settings.yml` 中找到以下區段

```yaml
# Expiry will clear old or simplistic plots
enabled-components:
  plot-expiry: false
```

```yaml
# This is an auto clearing task called `task1`
auto-clear:
  task1:
    threshold: 1
    required-plots: -1
    confirmation: true
    days: 7
    worlds:
      - "*"
    # See: https://intellectualsites.github.io/plotsquared-documentation/optimization/plot-analysis
    calibration:
      variety: 0
      variety-sd: 0
      changes: 0
      changes-sd: 1
      faces: 0
      faces-sd: 0
      data-sd: 0
      air: 0
      air-sd: 0
      data: 0
```

要啟用 Expire Manager，將 `enabled` 設為 true，並設定過期天數。系統會清理並刪除在指定天數內未登入的地塊擁有者所持有的地塊。

如需更 **進階的地塊清理**，請參考 [plot analysis page](plot-analysis.md)。

### 地塊濃縮（密集）

地塊濃縮（於 2.7.5 新增）會將指定半徑外的現有地塊移動到較接近原點 `(0;0)` 的位置。

## 檢查地塊數量（可選）

要檢查有多少地塊在某個半徑外：`/plot condense <world> info <radius>`. It will also display the minimum radius you can specify.

{% hint style="info" %}
If you already have thousands of plots outside your desired radius, it can take quite a long time.
{% endhint %}

## Run the condensation

To run the task use: `/plot condense <world> start <radius>`.

## World trim (intensive)

The world trim function will attempt to delete as many chunks which contain no plots. It will drastically reduce the size of the world on disk. It is an intensive task, so it is recommended to run it only every week or so.

To run the task use: `/plot trim <world>`。

## 區塊處理器

區塊處理器會在區塊儲存或載入磁碟前進行處理。目前功能輕量，包含：

* 發現過多實體時清除它們
* 發現過多方塊狀態時清除它們

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們力求準確，但請注意，自動翻譯可能會包含錯誤或不精確之處。原始文件之母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用此翻譯而產生之任何誤解或誤釋負責。