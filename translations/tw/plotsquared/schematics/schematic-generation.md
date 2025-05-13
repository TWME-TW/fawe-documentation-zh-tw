<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "e831db3d48f3b1fab79dbcd250a87f6c",
  "translation_date": "2025-05-13T04:07:17+00:00",
  "source_file": "plotsquared/schematics/schematic-generation.md",
  "language_code": "tw"
}
-->
# Plot Schematic on Generation

## 介紹

PlotSquared 允許在生成世界時，**在每個地塊中**放置預先定義的結構圖。

{% hint style="tip" %}
地塊結構圖只會影響地塊本身。若要了解如何為地塊世界設置道路結構圖，請參考文章 [Plotworld Road Schematic](../schematics/road-schematic.md)。
{% endhint %}

**範例：**

![image](https://user-images.githubusercontent.com/4140635/121788898-9d254180-cbd1-11eb-9889-d688634f9f90.png)

## 設定

若要讓地塊世界生成時帶有結構圖，請執行以下步驟：

1. 使用 `/plot schematic save` 建立一個地塊結構圖
2. 將建立好的結構圖從 `/plugins/PlotSquared/schematics/` 移動到 `/plugins/PlotSquared/schematics/GEN_ROAD_SCHEMATIC/<world name>/`，並重新命名為 `plot.schematic`/`plot.schem`（視結構圖檔案的副檔名而定）
3. 在 `settings.yml` 中新增或更新以下內容：

```yaml
# Schematic Settings
schematics:
  # Whether schematic based generation should paste schematic on top of plots, or from Y=1
  paste-on-top: false
```

世界現在將會使用該結構圖生成。

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們努力追求準確性，但請注意自動翻譯可能包含錯誤或不準確之處。原始文件的母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯而產生之任何誤解或誤譯負責。