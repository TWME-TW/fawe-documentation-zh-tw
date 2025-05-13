<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "b199dade573d0994fea234a31ddddc56",
  "translation_date": "2025-05-13T03:46:26+00:00",
  "source_file": "plotsquared/plot-membership-tiers.md",
  "language_code": "tw"
}
-->
# Plot 會員等級

## 介紹

PlotSquared 使用以下會員等級來定義 Minecraft 活動、地塊旗標、指令等的不同行為、權限與限制。

會員等級是 PlotSquared 本身的重要部分。它無法用於 LuckPerms，但其他插件可以透過 [PlotSquared API](api/api-documentation.md) 檢查玩家在特定地塊的會員等級。這裡不需要任何設定就能使用會員功能。

## 等級

### Denied

透過 `/p deny ...` 被拒絕 / 封鎖的玩家

* 無法編輯地塊
* 無法進入地塊

### Guest

一般 / 未加入的使用者

* 無法編輯地塊
* 可以進入地塊

### Member

透過 `/p add ...` 加入的使用者

* 可以進入地塊
* 當地塊擁有者在線時，可以放置 / 破壞方塊

### Trusted

透過 `/p trust ...` 信任的使用者

* 可以進入地塊
* 即使地塊擁有者離線，也能放置 / 破壞方塊
* 可以在地塊上使用 WorldEdit

### Owner

地塊擁有者，透過 `/p auto`、`/p claim`、`/p setowner ...` 或其他方式

* 對地塊擁有完全控制權
* 新增或移除使用者
* 可以放置 / 破壞方塊
* 使用 WorldEdit

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們致力於翻譯的準確性，但請注意，自動翻譯可能包含錯誤或不準確之處。原始文件之母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯而產生之任何誤解或誤譯負責。