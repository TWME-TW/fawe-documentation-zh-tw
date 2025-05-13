<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "2d1ce4e64a8452710ae86a0c44c6c953",
  "translation_date": "2025-05-13T03:34:02+00:00",
  "source_file": "fastasyncvoxelsniper/Brushes-and-Features-in-Development.md",
  "language_code": "tw"
}
-->
# 開發中的筆刷與功能
{% hint style="info" %}
有些筆刷目前並未包含在 VoxelSniper 的套件中。
{% endhint %}



## 海岸線製作筆刷
* **/b coast ecc[number] nb[number] sig[number] str[number]**：此筆刷用於生成海岸線。預設參數為 ecc0.75 nb5 sg0.5 str10。
    * **ecc[#]**：偏心率決定筆刷隨機扭曲的範圍有多遠。單位是筆刷大小的倍數。如果想確保重疊，請使用小於 0.5 的偏心率。
    * **nb[#]**：筆刷扭曲後會有多少「斑塊」。斑塊越多，筆刷末端形狀會越平滑、越圓。
    * **sig[#]**：設定 sigmoid 曲線的硬度。參數必須介於 0 到 1 之間。越接近 0，斷崖越陡峭；越接近 1，形狀越柔和。
    * **str[#]**：嘗試從筆刷中心刮除的方塊數量。

## 平坦化筆刷
* **/b f**：平坦化筆刷使用圓柱體將選定範圍內的區域壓平。使用此筆刷時，透過 /vh 設定圓柱高度，筆刷大小決定半徑。
* **/b f f[#]**：設定筆刷的漸變範圍。此參數必須介於 0 到 1 之間，預設為 0.5。
* **/b f s[#]**：設定筆刷漸變的平滑度。此參數同樣介於 0 到 1 之間，預設為 0.5。

## 曲線筆刷
* **/b sp**：此筆刷用於繪製曲線。可以使用端點或控制點來建立曲線。使用 Gunpowder 選擇方塊，使用箭頭移除選取。
* **/b sp ss**：啟用端點選取模式以設定曲線。
* **/b sp sc**：啟用控制點選取模式以設定曲線。
* **/b sp clear**：清除曲線選取。
* **/b sp ren**：根據控制點渲染曲線。

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 所翻譯。雖然我們致力於翻譯準確性，但請注意，自動翻譯可能包含錯誤或不準確之處。原始文件之母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯所產生之任何誤解或誤釋負責。