<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "ca656535ea0784e4149e2e11619b9757",
  "translation_date": "2025-05-13T03:59:27+00:00",
  "source_file": "plotsquared/installation/migrating-from-an-older-major-release.md",
  "language_code": "tw"
}
-->
# 從舊的大版本升級

## 介紹

如果你使用的是 PlotSquared 4 版或更舊版本，請仔細閱讀以下步驟，以順利升級到 v5 或更新版本。請記得在更新 PlotSquared 的同時，也需要更新其他相依套件，例如 WorldEdit、Fawe 或伺服器本身，才能讓 P2 正常運作。  
每個大版本都有自己的遷移處理器，PlotSquared 會嘗試升級自己的檔案。圖紙（schematics）無法更新，需要重新製作。

### 從 PlotMe 遷移：

1. 從 [spigotmc.org](https://www.spigotmc.org/resources/plotme-official.2131) 取得最新的 PlotMe 版本。壓縮檔中有 3 個 jar，但你只需要 `PlotMe-Core.jar`。用最新版本替換你目前的 PlotMe 版本。
2. 使用最新的 PlotMe 版本啟動伺服器，查看日誌確保沒有錯誤（沒有錯誤代表所有外掛都沒錯誤!!），這樣你才能開始遷移。
3. 從 [bukkit.org](https://dev.bukkit.org/projects/plotsquared/files/2647923) 取得最新的 PlotSquared v3。用 PlotSquared v3 替換 PlotMe，啟動伺服器，確保沒有錯誤或警告，然後關閉伺服器。
4. 從 [spigotmc.org](https://www.spigotmc.org/resources/plotsquared-v4-v5-out-now.1177) 取得最新的 PlotSquared v4。用 v4 替換 PlotSquared v3，啟動伺服器，確保沒有錯誤或警告，然後關閉伺服器。如果遇到錯誤或警告，請仔細閱讀並依照指示處理，忽略可能會導致後續問題。你可能需要回頭檢查 `/plugins/PlotSquared/settings/worlds.yml` 並自行更新方塊材質，v5 以前的版本在這方面不太智能。請參考 [1.18 PaperMC JavaDocs](https://papermc.io/javadocs/paper/1.18/org/bukkit/Material.html) 取得最新的有效材質名稱清單。
5. 從 [spigotmc.org](https://www.spigotmc.org/resources/plotsquared-v5.77506) 取得最新的 PlotSquared v5。用 v5 替換 PlotSquared v4，啟動伺服器，執行相同流程，檢查日誌確保沒有警告或錯誤。

完成了，轉換就完成了。

### 從 PlotSquared v3 遷移：

1. 從 [bukkit.org](https://dev.bukkit.org/projects/plotsquared/files/2647923) 取得最新的 PlotSquared v3。用 PlotSquared v3 替換目前版本，啟動伺服器，確保沒有錯誤或警告，然後關閉伺服器。
2. 從 [spigotmc.org](https://www.spigotmc.org/resources/plotsquared-v4-v5-out-now.1177/) 取得最新的 PlotSquared v4。用 v4 替換 v3，啟動伺服器，確保沒有錯誤或警告，然後關閉伺服器。如果遇到錯誤或警告，請仔細閱讀並依照指示處理，忽略可能會導致後續問題。你可能需要回頭檢查 `/plugins/PlotSquared/settings/worlds.yml` 並自行更新方塊材質，v5 以前的版本在這方面不太智能。請參考 [1.18 PaperMC JavaDoc](https://papermc.io/javadocs/paper/1.18/org/bukkit/Material.html) 取得最新的有效材質名稱清單。
3. 從 [spigotmc.org](https://www.spigotmc.org/resources/plotsquared-v5.77506) 取得最新的 PlotSquared v5。用 v5 替換 v4，啟動伺服器，執行相同流程，檢查日誌確保沒有警告或錯誤。

完成了，轉換就完成了。

### 從 PlotSquared v4 遷移：

1. 從 [spigotmc.org](https://www.spigotmc.org/resources/plotsquared-v4-v5-out-now.1177) 取得最新的 PlotSquared v4。用 v4 替換目前版本，啟動伺服器，確保沒有錯誤或警告，然後關閉伺服器。如果遇到錯誤或警告，請仔細閱讀並依照指示處理，忽略可能會導致後續問題。
2. 從 [spigotmc.org](https://www.spigotmc.org/resources/plotsquared-v6.77506/download?version=402158) 取得最新的 PlotSquared v5。用 v5 替換 v4，啟動伺服器，執行相同流程，檢查日誌確保沒有警告或錯誤。你可能需要回頭檢查 `/plugins/PlotSquared/settings/worlds.yml` 並自行更新方塊材質，v5 以前的版本在這方面不太智能。請參考 [1.18 PaperMC JavaDocs](https://papermc.io/javadocs/paper/1.18/org/bukkit/Material.html) 取得最新的有效材質名稱清單。欲了解更多指示，請參考文章 [Updating from 1.12 to 1.13](updating-from-1.12-to-1.13.md)。

完成了，轉換就完成了。

### 從 PlotSquared v5 遷移：

1. 從 [spigotmc.org](https://www.spigotmc.org/resources/plotsquared-v6.77506/download?version=402158) 取得最新的 PlotSquared v5。用 v5 替換目前版本，啟動伺服器，確保沒有錯誤或警告，然後關閉伺服器。如果遇到錯誤或警告，請仔細閱讀並依照指示處理，忽略可能會導致後續問題。
2. 從 [spigotmc.org](https://www.spigotmc.org/resources/77506) 取得最新的 PlotSquared v6。用 v6 替換 v5，啟動伺服器，執行相同流程，檢查日誌確保沒有警告或錯誤。  
請仔細閱讀 [Changelog for v6](../old/changelog-old.md)，確保後續不會遺漏手動更新。

完成了，轉換就完成了。

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 所翻譯。雖然我們力求準確，但請注意自動翻譯可能包含錯誤或不準確之處。原始文件之母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。本公司不對因使用本翻譯所導致之任何誤解或誤譯負責。