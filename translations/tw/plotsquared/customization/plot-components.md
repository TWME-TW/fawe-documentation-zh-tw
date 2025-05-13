<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "4d398efdd72f9d2244a9abf350baef7e",
  "translation_date": "2025-05-13T03:58:33+00:00",
  "source_file": "plotsquared/customization/plot-components.md",
  "language_code": "tw"
}
-->
# 地皮組件

## 介紹

`/plot set` 指令讓你可以設定地皮的各種組件，包括：

* 地皮生態群系
* 地皮別名
* 地皮家位置
* （組件）地皮地板下方區域的方塊
* （組件）地皮地板上的方塊
* （組件）地皮地板上方區域的方塊
* （組件）整個地皮內的所有方塊
* （組件）地皮牆壁內的方塊
* （組件）地皮邊界的方塊
* （組件）地皮周圍區域的方塊
* （組件）地皮中央的方塊

## 組件指令

### /plot set biome

這是 `/plot setbiome` 的別名，且擁有 `plots.set.biome` 權限節點。從 v5.11.0 版本開始，這個指令支援完整的指令補全。

### /plot set alias

這是 `/plot setalias` 的別名，擁有 `plots.alias` 權限節點。此指令會更改地皮在列表中顯示的名稱，並允許你執行 `/plot visit <alias>`。

### /plot set home

這是 `/plot sethome` 的別名，擁有 `plots.set.home` 權限節點。

如果沒有提供參數，地皮家位置會設定為你目前所在的位置。若要移除自訂的家位置，請使用 `/plot sethome unset/reset/remove/none`。

### /plot set <component>

這讓你能更新地皮的各個部分。現有的組件有：

* `main`：地皮地板下方區域的方塊
* `floor`：地皮地板上的方塊
* `air`：地皮地板上方區域的方塊
* `all`：整個地皮內的所有方塊
* `wall`：地皮牆壁內的方塊
* `border`：地皮邊界的方塊
* `outline`：地皮周圍區域的方塊
* `middle`：地皮中央的方塊

每個組件都有獨立的權限節點，即 `plots.set.<component>`，且它們共用 `/plot set <component> <pattern>` 的語法。

這是一個強大的系統，因為它讓你能利用 [BlockBuckets](../block-bucket.md) 的功能來定義方塊圖案。

## 禁止使用的方塊

v5.11.0 版本引入了一項新的安全措施，防止在地皮組件中使用不安全的方塊。這項功能在早期的 4 版本中有實裝，但後來為了配合 WorldEdit 方塊黑名單而被移除。現在設定檔（settings.yml）包含了黑名單方塊清單（預設為[這些](../configuration/settings.md)）。若要覆蓋黑名單，請給自己 `plots.admin.unsafe` 權限節點。

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們力求準確，但請注意自動翻譯可能包含錯誤或不精確之處。原始文件之母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯所產生之任何誤解或誤釋負責。