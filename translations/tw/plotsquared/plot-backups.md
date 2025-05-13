<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "d049aae2f20967584d7b1bdaf82b3519",
  "translation_date": "2025-05-13T03:45:55+00:00",
  "source_file": "plotsquared/plot-backups.md",
  "language_code": "tw"
}
-->
# 備份地皮

## 介紹

PlotSquared v5.11.0 推出了一套新的地皮備份系統。這讓你可以為你的地皮建立備份，日後可以還原。

{% hint style="danger" %}
此系統（目前）不支援合併地皮。
{% endhint %}

預設情況下，當執行某些可能會破壞地皮的操作時，系統也會自動建立備份。目前包括：

* 清除地皮
* 設定地皮組件（地板、填充等）

備份系統目前只會儲存地皮內的方塊，不會包含旗標、設定等。備份系統在背後使用地皮結構圖。

## 設定

設定可以在 PlotSquared 的 `settings.yml` 檔案中找到。

```yaml
# Backup related settings
backup:
  # Automatically backup plots when destructive commands are performed
  automatic-backups: false
  # Maximum amount of backups associated with a plot
  backup-limit: 3
  # Whether or not backups should be deleted when the plot is unclaimed
  delete-on-unclaim: true
```

## 指令

* /plot backup save
  * 建立你所在地皮的備份
  * 權限：`plots.backup.save` (and `plots.admin.backup.other` if you're not the plot owner)

* /plot backup list
    * List available plot backups +
  * Permission: `plots.backup.list` (and `plots.admin.backup.other` if you're not the plot owner)

* /plot backup load
    * Restore a plot from the specified backup. +
  * Permission: `plots.backup.load` (and `plots.admin.backup.other`（如果你不是地皮擁有者）

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們致力於準確性，但請注意，自動翻譯可能包含錯誤或不準確之處。原始文件之母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯所產生之任何誤解或誤釋負責。