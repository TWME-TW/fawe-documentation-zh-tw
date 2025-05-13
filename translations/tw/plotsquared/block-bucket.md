<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "85aa716110e0b0e6feeaff3cdbd3d4eb",
  "translation_date": "2025-05-13T03:39:56+00:00",
  "source_file": "plotsquared/block-bucket.md",
  "language_code": "tw"
}
-->
# Block Buckets

## 介紹

Block buckets 讓你可以為圖表的每個元件指定任意數量的方塊。你可以設定方塊的權重，決定該方塊從桶中被選中的機率。

* `stone,grass_block,cobblestone,sandstone` 會自動推斷四種方塊各佔 25%
* `stone:50,grass_block:30,sandstone:20` 會使用 50% 的石頭、30% 的草方塊和 20% 的砂岩。

## 格式

方塊格式可以是 `namespace:block[property1=value1,property2=value2]`（屬性和命名空間是可選的，`grass_block` 會解析成 `minecraft:grass_block[snowy=false]`。[更多資訊](https://minecraft.wiki/w/Block_states)）

也接受複雜的模式：

* [FAWE Patterns](/fastasyncworldedit/advanced-features/patterns.md)（如果你有安裝 FAWE）
* [WorldEdit Patterns](https://worldedit.enginehub.org/en/latest/usage/general/patterns/)

## 禁止使用的方塊

若要限制模式允許使用的方塊，請在 `plugins/WorldEdit/config.yml` 的 `disallowed-blocks` 清單中設定，或是在 `plugins/FastAsyncWorldEdit/worldedit-config.yml` 中設定。

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們致力於翻譯的準確性，但請注意，自動翻譯可能包含錯誤或不準確之處。原始文件的母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用此翻譯而產生的任何誤解或誤釋負責。