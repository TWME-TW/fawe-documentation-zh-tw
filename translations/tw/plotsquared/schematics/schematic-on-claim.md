<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "81fec9e95f494f56b9c2ace222253b85",
  "translation_date": "2025-05-13T04:07:33+00:00",
  "source_file": "plotsquared/schematics/schematic-on-claim.md",
  "language_code": "tw"
}
-->
# Plot Schematic on Claim

## 介紹

使用 PlotSquared，當玩家獲得新地皮時，可以自動生成預設的地皮結構圖 (`/plot claim`, `/plot auto`, ...)。

{% hint style="tip" %}
地皮結構圖只會影響該地皮本身。若要設定地皮世界的道路結構圖，請參考文章 [Plotworld Road Schematic](../schematics/road-schematic.md)。
{% endhint %}

## 設定

要在地皮被認領時自動貼上結構圖，你需要：

1. 在地皮內建造。如果你想使用外部結構圖，請用 WorldEdit 將它貼到地皮內 ([教學](https://worldedit.enginehub.org/en/latest/usage/clipboard/#clipboard))。
2. 使用 `/plot schematic save` 來儲存結構圖。你可以用 `/plot schematic list` 查詢已儲存的結構圖列表。

現在你有一個可用的結構圖檔案。要讓它在認領時自動貼上，你需要設定你的 `worlds.yml`，以下是一段簡單的範例說明如何操作。

```yaml
# The following is a slice from the plotworld settings, change this for each plotworld
schematic:
    # File name (without .schem)
        file:
           - "<schematic name>"
        # If you want it on claim
        on_claim: true
```

並在 `settings.yml` 中新增或更新以下內容：

```yaml
# Schematic Settings
schematics:
  # Whether schematic based generation should paste schematic on top of plots, or from Y=1
  paste-on-top: false
```

你可以在多個地皮世界使用同一個結構圖。

{% hint style="tip" %}
如果你在 worlds.yml 啟用了 `specify_on_claim` 選項，使用者就能用認領指令自行指定地皮結構圖。
{% endhint %}

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 所翻譯。雖然我們力求準確，但請注意自動翻譯可能包含錯誤或不準確之處。原始文件之母語版本應視為權威依據。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯而產生之任何誤解或誤譯負責。