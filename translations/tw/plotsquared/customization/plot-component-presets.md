<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "26400d6e49e992093ea373c965a3afcd",
  "translation_date": "2025-05-13T03:58:19+00:00",
  "source_file": "plotsquared/customization/plot-component-presets.md",
  "language_code": "tw"
}
-->
# Plot 組件預設

## 介紹

PlotSquared v5.12.0 引入了全新的組件預設系統。這個新系統讓伺服器擁有者可以製作組件預設，玩家透過 GUI 就能套用到自己的地皮上。GUI 選單會覆蓋玩家特定的權限，因此你可以利用 GUI 讓玩家使用平常沒有權限使用的組件。

## 組件

可用的組件以及可使用的數值，和 `/plot set <component>` 指令中相同。

可用組件包括：
* floor
* wall
* all
* air
* main
* middle
* outline
* border

更多資訊請參考：[Plot Components](plot-component-presets.md)

## 設定

系統可在 `settings.yml` 檔案的 `enabled-components` 下切換，預設為啟用。

預設組件設定在 `plugins/PlotSquared/settings/components.yml` 檔案中：

訊息使用 [MiniMessage](https://docs.adventure.kyori.net/minimessage.html) 來格式化。若想預覽效果，可以使用像是 [MiniMessageViewer](https://webui.adventure.kyori.net) 的工具。

```yaml
presets:
  - component: floor
    cost: 0.0
    pattern: '##wool'
    name: <rainbow:2>Disco Floor</rainbow>
    icon: yellow_wool
    description:
      - <gold>Spice up your plot floor</gold>
    permission: ''
```

這是一個強大的系統，因為它允許你利用 [BlockBuckets](../block-bucket.md) 的功能來定義方塊圖案。

## 花費

若設定了非零花費，且同時有安裝 [Vault](https://www.spigotmc.org/resources/34315) 和經濟插件，GUI 將會使用遊戲內貨幣進行扣款。

## 圖示

你可以使用任何 [Minecraft material](https://www.digminecraft.com/lists/item_id_list_pc.php) 作為預設組件的圖示。

## 權限

玩家無法看到沒有權限使用的預設組件。權限設定為 `''` (an empty string) then all players will be able to use that preset.

## /plot components

The command for opening the GUI is `/plot components` and has the permission node `plots.components`。

使用此指令會開啟 GUI 選單，但前提是玩家必須在自己擁有的地皮內。

![image](https://i.imgur.com/brFlzw6.png[component_small.png)

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 所翻譯。雖然我們致力於翻譯的準確性，但請注意自動翻譯可能包含錯誤或不精確之處。原始文件之母語版本應視為權威依據。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯而產生之任何誤解或誤譯負責。