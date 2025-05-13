<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "e6282123f2915925d7878daa54732926",
  "translation_date": "2025-05-13T03:58:53+00:00",
  "source_file": "plotsquared/customization/single-plot-area.md",
  "language_code": "tw"
}
-->
# 單一地塊區域

這是 PlotSquared v5.12.0 新增的功能，讓你能在一般世界（非地塊世界）中一個一個建立地塊。流程相當簡單：

## 設定

1. 使用 WorldEdit 的魔杖 (`//wand`) 建立一個正方形或長方體選取區域。選取區域中最低的 Y 值會是地塊高度，決定你預設傳送的位置、使用 `/plot set` 時地板生成的位置等等。
2. 使用 `/plot area single <name>`，其中 `<name>` 是唯一識別碼。這會用於傳送到該區域等操作。
3. 區域現在已建立完成。

建立區域時，PlotSquared 會儲存一個結構圖，當使用 `/plot clear`、`/plot delete` 及其他重生指令時會用來重新生成該區域。因此，地塊可以被清除，恢復到原本的狀態。

地塊區域的設定可以像一般區域設定一樣進行修改。

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們致力於翻譯的準確性，但請注意，自動翻譯可能包含錯誤或不精確之處。原始文件之母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯所產生之任何誤解或誤譯負責。