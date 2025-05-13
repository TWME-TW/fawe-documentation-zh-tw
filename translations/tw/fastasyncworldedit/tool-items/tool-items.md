<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "ab8a07ad6221dad6c1169d1edcffa0c2",
  "translation_date": "2025-05-13T03:54:28+00:00",
  "source_file": "fastasyncworldedit/tool-items/tool-items.md",
  "language_code": "tw"
}
-->
# 工具物品

## 導航工具物品

使用 FAWE 傳送的一種方式是透過「導航物品」。預設是原版的 `compass`。這個物品可以在 `worldedit-config.yml` 中更換：

```yaml
navigation-wand:
  item: minecraft:compass
  max-distance: 100
```

左鍵點擊會執行 [Jumpto](../commands/navigation/navigation.md#jumpto) 指令，右鍵點擊會執行 [Thru](../commands/navigation/navigation.md#thru) 指令。

FAWE 的工具物品（包含導航工具）可以透過一般創造模式物品欄或使用 `//wand -n` command (see [Wand](../commands/selection/selection.md#wand)).

**Permissions:**
- `worldedit.navigation.jumpto.tool`
- `worldedit.navigation.thru.tool`

![Compass](../../../../fastasyncworldedit/tool-items/images/compass.png)

## Wand Tool Item

Positions are defined in various ways. One of these ways is through the use of a "wand-item". By default, this is the
vanilla `wooden_axe` 取得。這個物品可以在 `worldedit-config.yml` 中更換：

```yaml
wand-item: minecraft:wooden_axe
```

用這根魔杖左鍵點擊方塊會設定主要位置（也就是「pos1」），右鍵則設定次要位置（也就是「pos2」）。

FAWE 的工具物品可以透過一般創造模式物品欄或使用 `//wand [-n]` command (see [Wand](../commands/selection/selection.md#wand)).

![Wooden-Axe](../../../../fastasyncworldedit/tool-items/images/wooden_axe.png)


## Far Wand

Positions are defined same as the Wand Tool item but with infinite range and a possible other item.

Take a tool in main hand. Left-clicking a block with this farwand-item defines the primary position (aka "pos1") and right click defines the secondary
position(s) (aka "pos2").

The farwand tool items can be obtained e.g. via the command `/tool farwand` or `/farwand` with a tool in hand.

**Permission:**
- `worldedit.tool.farwand` 取得。

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 所翻譯。雖然我們致力於翻譯的準確性，但請注意自動翻譯可能包含錯誤或不精確之處。原始文件的母語版本應視為權威資料來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯而產生的任何誤解或誤釋負責。