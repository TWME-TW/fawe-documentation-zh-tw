<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "1b95a1ba16cfe7f44e2a9c0529dfc56a",
  "translation_date": "2025-05-13T03:48:10+00:00",
  "source_file": "plotsquared/worldedit-features.md",
  "language_code": "tw"
}
-->
# WorldEdit & FAWE 功能

{% hint style="info" %}
如果你想讓 WorldEdit 的其他部分也能非同步運作，可以考慮安裝 [FasAsyncWorldEdit](https://www.spigotmc.org/resources/13932)。關於在地皮中允許 FAWE 的所有權限，可以在這裡找到 [here](/fastasyncworldedit/basic-commands/main-commands-and-permissions.md)。
{% endhint %}

PlotSquared 提供了幾個與 WorldEdit 相關的選項。預設情況下，如果你沒有繞過權限，系統會執行以下操作：

* 限制 WorldEdit 僅能在地皮內使用
* 阻擋可能造成危害的 WorldEdit 指令
* 限制多種刷子的最大迭代次數，避免伺服器崩潰
* 限制最大體積為 5,000 萬方塊

繞過權限是 `plots.worldedit.bypass`，使用 `/plot toggle worldedit`。

為了進一步擴充功能，PlotSquared 提供了一個可以啟用的 WE 處理器：

* 限制編輯時的最大方塊狀態和實體數量（啟用 chunk-processor）
* 更快且非同步的 WorldEdit 變更（啟用 experimental-fast-async-worldedit）（可用 `/plot toggle worldedit` 繞過）

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 所翻譯。雖然我們力求準確，但請注意，自動翻譯可能包含錯誤或不準確之處。原始文件的母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯而產生的任何誤解或誤譯負責。