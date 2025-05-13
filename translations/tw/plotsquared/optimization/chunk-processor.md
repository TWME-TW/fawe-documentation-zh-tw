<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "a7ec7420039985b11280a0737f1867c1",
  "translation_date": "2025-05-13T04:05:16+00:00",
  "source_file": "plotsquared/optimization/chunk-processor.md",
  "language_code": "tw"
}
-->
# Chunk processor

## Introduction

{% hint style="danger" %}
這是新功能，不是解決所有問題的神奇方案。
不過它非常有效率，當沒有需要處理的 chunk 時幾乎不會留下任何負擔。
{% endhint %}

chunk processor 會在 chunk 被存取或載入硬碟前進行處理。它目前很輕量，具備以下功能：

* 當偵測到危險數量時清除實體
* 當偵測到危險數量時清除方塊狀態

## Purpose
此處理器的**目的**是：

* 減少伺服器延遲
* 防止潛在危險的 chunk 被存取或載入硬碟
* 避免因危險 chunk 導致伺服器反覆崩潰

通常**造成危險 chunk 的原因**有：

* 玩家濫用 WorldEdit
* 玩家濫用 VoxelSniper
* 任何其他可用來大量產生實體或方塊的伺服器工具

## Configuration

設定是透過 `settings.yml` 進行

要啟用 chunk processor，請設定以下內容：

```yaml
enabled-components:
  # Processes chunks (trimming, or entity/tile limits)
  chunk-processor: true
```

接著可進一步調整這些數值：

```yaml
chunk-processor:
  # Auto trim will not save chunks which aren't claimed
  auto-trim: false
  # Max tile entities per chunk
  max-tiles: 3
  # Max entities per chunk
  max-entities: 512
  # Disable block physics
  disable-physics: false
```

當達到 tile entity / entity 限制時，chunk processor 在儲存 chunk 時會移除超過限制的實體。它也會阻止沒有 `/plot toggle worldedit` enabled from exceeding the limit using WorldEdit.

When the chunk processor is activated, players will not be able to use tile entities as a part of the plot components when using `/plot set`.

{% hint style="tip" %}
If using Paper, you may also enable `tile-entity-check` 權限的玩家在 paper components 下放置新的 tile entity。這樣可以防止玩家在該 chunk 的 tile entity 限制達到後繼續放置新的 tile entity。

{% endhint %}

關於 tile entities 的更多資訊，請參考：
https://papermc.io/javadocs/paper/1.18/org/bukkit/block/package-tree.html +
（或自行用 Google 搜尋。）

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們致力於確保準確性，但請注意，自動翻譯可能包含錯誤或不準確之處。原始文件之母語版本應視為權威來源。對於重要資訊，建議使用專業人工翻譯。我們不對因使用本翻譯而產生之任何誤解或誤譯負責。