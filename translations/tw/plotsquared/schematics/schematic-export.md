<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "318b096209756f9d2eccde36d5579985",
  "translation_date": "2025-05-13T04:07:10+00:00",
  "source_file": "plotsquared/schematics/schematic-export.md",
  "language_code": "tw"
}
-->
# Schematic export

## Step 1: Choosing a directory

以下這行是設定 schematic export 目錄。`save_path` 節點需要使用絕對路徑。
例如：`C:/xampp/htdocs/schematics/`、`C:/wamp/www/schematics` 或 `C:/minecraft/plugins/PlotSquared/schematics`。

```yaml
schematics:
  save_path: /var/www/schematics
```

## Step 2: Exporting a schematic

使用指令 `/plot schematic save` while standing in a plot to save the plot to a schematic. To export all plots use `/plot schematic exportall`（從控制台執行）。

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們致力於翻譯的準確性，但請注意，自動翻譯可能包含錯誤或不準確之處。原始文件之母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用此翻譯所產生的任何誤解或誤譯負責。