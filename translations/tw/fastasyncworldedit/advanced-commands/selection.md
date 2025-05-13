<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "44221cd23c9b48362be8f56599bd8b41",
  "translation_date": "2025-05-13T03:48:54+00:00",
  "source_file": "fastasyncworldedit/advanced-commands/selection.md",
  "language_code": "tw"
}
-->
## 介紹

有時候你會想排除某些區域，因為你不想編輯它們，  
例如當不想要的部分在另一個想要的部分裡面。  
在這個範例中，我們使用 [WorldEditSUI plugin](https://www.spigotmc.org/resources/worldeditsui-visualize-your-selection.60726/)（可選，但有助於理解每個步驟）來視覺化選取範圍。

{% hint style="info" %} 這個範例是在一塊地上做一個 y 高度為 1 的立方體選取，你也可以使用不同的選取類型、高度，甚至可以在普通世界使用 {% endhint %}


### 步驟教學

1. 使用 `//pos1` 和 `//pos2` 選取內部區域，或在按住 ``//wand``item.
![excludeRegionsGmask.png](../../../../fastasyncworldedit/advanced-commands/images/excludeRegionsGmask.png)


2. Add a gmask containing your selection with `//gmask !#region`
![excludeRegionsGmask2.png](../../../../fastasyncworldedit/advanced-commands/images/excludeRegionsGmask2.png)


3. Select outer region using the same commands as in ``1.`` (or outset/expand/move/wer etc.)
![excludeRegionsGmask3.png](../../../../fastasyncworldedit/advanced-commands/images/excludeRegionsGmask3.png)


4. Run the command of your choice and the inner region will not be affected, in this example we used ``//set stone`` 時，透過左鍵和右鍵互動  
![excludeRegionsGmask4.png](../../../../fastasyncworldedit/advanced-commands/images/excludeRegionsGmask4.png)

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們努力確保翻譯的準確性，但請注意自動翻譯可能包含錯誤或不準確之處。原始文件的母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯所產生的任何誤解或誤譯負責。