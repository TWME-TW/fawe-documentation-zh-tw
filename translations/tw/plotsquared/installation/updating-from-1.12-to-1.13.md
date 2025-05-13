<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "4d3171d6ba8565c70fdb355a97fca3f1",
  "translation_date": "2025-05-13T04:00:01+00:00",
  "source_file": "plotsquared/installation/updating-from-1.12-to-1.13.md",
  "language_code": "tw"
}
-->
# 從 1.12 更新到 1.13

## 更新到 1.13

如果你要更新到 1.13，可能需要手動修改一些設定。

PlotSquared 會在啟動時嘗試轉換你的 `worlds.yml` 設定檔。完成後，請檢查該檔案，確保所有內容都已正確轉換。

請注意，目前 PlotSquared 1.13 版本只支援 Bukkit。

### Schematics

PlotSquared 不會自動更新你的 schematics，因此你可能需要手動更新。
新版的 PlotSquared 引入了一種用於設定不同地塊元件方塊的格式：[block buckets](../block-bucket.md)。這個改變讓你可以在每個地塊元件中使用多種方塊類型。

### 依賴項

PlotSquared 現在依賴 [WorldEdit](https://dev.bukkit.org/projects/worldedit/files) 或 [FastAsyncWorldEdit](https://www.spigotmc.org/resources/fast-async-worldedit.13932)，因此你需要在伺服器上安裝其中一個才能使用 PlotSquared。

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們致力於準確性，但請注意自動翻譯可能包含錯誤或不準確之處。原始文件之母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯而產生之任何誤解或誤釋負責。