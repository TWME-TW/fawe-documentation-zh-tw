<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "29b9725845f3799ee16789aa381a3e48",
  "translation_date": "2025-05-13T03:36:34+00:00",
  "source_file": "fastasyncvoxelsniper/Stencil-Brush.md",
  "language_code": "tw"
}
-->
# Stencil Brush

Stencil 的操作方式和 schematics 類似，你選擇一個區域，儲存起來，之後再載入並貼上。Stencil 最大可選擇的立方體區域為 10 萬個方塊。

* **/b st**：顯示遊戲內的說明。
* **/b st [fill|full|replace] [name]**：選擇 stencil 的貼上方式以及要貼上的 stencil。如果沒有指定貼上方式，預設為 fill。要建立新的 stencil，輸入 /b st [name]，用前兩次箭頭右鍵選擇立方體區域，第三次箭頭右鍵選擇貼上點。用火藥右鍵貼上。
    * *fill：只貼到空氣方塊。*
    * *full：貼到所有方塊。*
    * *replace：只貼到已存在的方塊。*

## StencilList Brush

StencilList brush 會隨機貼上現有的多個 stencil。這在貼一組樹木時很實用。要建立 StencilList，請到 **plugins\VoxelSniper\stencilLists\** 建立一個 .txt 檔案，檔名即為你的 stencilList 名稱。檔案內容是每行一個 stencil 名稱。

要載入 stencilList，輸入 **/b sl [name]**。現在你用箭頭右鍵點擊時，就會隨機貼上檔案中定義的其中一個 stencil。

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們致力於準確性，但請注意自動翻譯可能包含錯誤或不準確之處。原始文件之母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯所引起之任何誤解或誤譯負責。