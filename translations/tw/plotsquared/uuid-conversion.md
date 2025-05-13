<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "8b78db1ca8b232b7e65c0e68687cf7e5",
  "translation_date": "2025-05-13T03:47:26+00:00",
  "source_file": "plotsquared/uuid-conversion.md",
  "language_code": "tw"
}
-->
# UUID 轉換

## 介紹
此功能從版本 2.10 開始加入。UUID 轉換讓你可以在伺服器上切換不同的 UUID 儲存方式。

### 離線模式

會使用離線模式伺服器相同的 UUID。UUID 將根據玩家名稱（區分大小寫）產生。

### 小寫模式

離線模式但不區分大小寫，會從小寫的使用者名稱取得 UUID。

### 在線模式

使用 Mojang 提供的在線模式 UUID。

{% hint style="danger" %}
如果你使用的是 Bukkit 的 pre-UUID 版本，或伺服器設定為離線模式，這個模式將無法正常運作。請檢查你的 `server.properties` 以確保安全。
{% endhint %}

{% hint style="info" %}
如果你使用代理伺服器（例如 BungeeCord 或 Waterfall），請依照此文件轉發玩家的 UUID。這樣 PlotSquared 的在線 UUID 模式才能正常運作。
{% endhint %}

## 使用方式

必須執行指令才能進行轉換。

{% hint style="danger" %}
強烈建議你在轉換前備份資料庫。如果出錯，地皮可能會遺失！
{% endhint %}

`/plot uuidconvert <mode>`

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們致力於提供準確的翻譯，但請注意自動翻譯可能會包含錯誤或不準確之處。原始文件的母語版本應被視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯所產生的任何誤解或誤譯負責。