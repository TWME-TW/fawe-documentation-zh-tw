<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "3cdc04af8a258f76ab03cd5c97074993",
  "translation_date": "2025-05-13T03:57:56+00:00",
  "source_file": "plotsquared/customization/placeholders.md",
  "language_code": "tw"
}
-->
# Placeholders

## 介紹

{% hint style="info" %}
Placeholder 整合讓你能在 PlotSquared 的特定位置顯示來自其他插件的資料。
{% endhint %}

舉例來說，使用 [FeatherBoard](https://www.spigotmc.org/resources/2691) 你可以建立一個計分板（側邊欄），顯示你所在地塊的資訊。搭配 [PlaceholderAPI](https://www.spigotmc.org/resources/6245) 使用時，當玩家 Steve 進入地塊時，你可以使用 `/plot flag set greeting Welcome %player_name%`，會顯示「Welcome Steve」。
此外，需要安裝 PlaceholderAPI 的 `Player` 擴充。

目前，(FeatherBoard 與) PlaceholderAPI 的 placeholder 可以用在地塊的 `greeting` 和 `farewell` 標記中。

## 設定

PlotSquared 明確且官方支援 [PlaceholderAPI](https://www.spigotmc.org/resources/6245) 與 [MVdWPlaceholderAPI](https://www.spigotmc.org/resources/11182)。

請依照這些 placeholder 系統的指示正確安裝。

{% hint style="info" %}
PlotSquared 的 PlaceholderAPI placeholders 不需要額外下載 PAPI 擴充。與其他某些插件不同，PlotSquared 會內部處理所有內容。
{% endhint %}

## 在 PlotSquared 中停用 Placeholder

可以在 `settings.yml` 中關閉 placeholder：

```yaml
  external-placeholders: false
```

## 特定插件的提示

### 聊天系統

如果你使用 **EssentialsChat** 和 **PlaceholderAPI**，必須安裝 [ChatInjector](https://www.spigotmc.org/resources/38327)，才能讓 placeholder 在聊天中顯示。不過，請注意有報告指出 ChatInjector 可能會造成問題。

## PlotSquared placeholders

{% hint style="tip" %}
如果你覺得應該新增 PlotSquared 的 placeholder，請到 [這裡提出 issue](https://github.com/IntellectualSites/PlotSquared/issues/new/choose)。
{% endhint %}

_6.0.0 以後可用的 placeholders：_

| Placeholder                                      | 說明                                                                                                               |
|--------------------------------------------------|---------------------------------------------------------------------------------------------------------------------|
| `%plotsquared_currentplot_alias%`                | Alias of the plot                                                                                                   |
| `%plotsquared_currentplot_owner%`                | Owner of the plot                                                                                                   |
| `%plotsquared_currentplot_members%`              | Amount of players added and trusted to the plot                                                                     |
| `%plotsquared_currentplot_members_added%`        | Amount of players added to the plot                                                                                 |
| `%plotsquared_currentplot_members_added_list%`   | Display a list of added members                                                                                     |
| `%plotsquared_currentplot_members_trusted%`      | Amount of players trusted to the plot                                                                               |
| `%plotsquared_currentplot_members_trusted_list%` | Display a list of trusted members                                                                                   |
| `%plotsquared_currentplot_members_denied%`       | Amount of members denied from the plot                                                                              |
| `%plotsquared_currentplot_members_denied_list%`  | Display a list of denied members                                                                                    |
| `%plotsquared_currentplot_world_name%`           | Get the world name                                                                                                  |
| `%plotsquared_currentplot_can_build%`            | Displays true or false whether the player has build rights on the plot                                              |
| `%plotsquared_world_name%`                       | Get the name of the world                                                                                           |
| `%plotsquared_has_plot%`                         | Displays true or false whether the player has plot                                                                  |
| `%plotsquared_has_plot_(world)%`                 | Displays true or false whether the player has plot in a specific world                                              |
| `%plotsquared_plot_count%`                       | Amount of global plots of a player                                                                                  |
| `%plotsquared_plot_count_(world)%`               | Amount of plots for a player in a specific world                                                                    |
| `%plotsquared_base_plot_count%`                  | Amount of global plots of a player, counting merged plots as one                                                    |
| `%plotsquared_base_plot_count_(world)%`          | Amount of plots for a player in a specific world, counting merged plots as one                                      |
| `%plotsquared_allowed_plot_count%`               | Amount of maximum plots a player can have. Returns "infinite" if you have * permission                              |
| `%plotsquared_currentplot_xy%`                   | Displays the X and Y ID of a plot                                                                                   |
| `%plotsquared_currentplot_x%`                    | Displays the X ID of a plot                                                                                         |
| `%plotsquared_currentplot_y%`                    | Displays the Y ID of a plot                                                                                         |
| `%plotsquared_currentplot_rating%`               | Displays the average rating of a plot                                                                               |
| `%plotsquared_currentplot_biome%`                | Displays the biome of a plot                                                                                        |
| `%plotsquared_currentplot_size%`                 | Displays the size of a merged plot                                                                                  |
| `%plotsquared_currentplot_localflag_<flag>%`     | Display the value of the flag set on current plot                                                                   |
| `%plotsquared_currentplot_flag_<flag>%`          | Display the value of the flag set on current plot or if it's not set: display the inherited flag value (worlds.yml) |
| `%plotsquared_currentplot_creationdate%`         | Display the creation date of the plot                                                                               |
| `%plotsquared_total_grants%`                     | 顯示地塊授權的總數                                                                                               |

## 外部 placeholders

- [PlaceholderAPI placeholders](https://github.com/PlaceholderAPI/PlaceholderAPI/wiki/Placeholders)

- [MVdWPlaceholderAPI placeholders](https://www.spigotmc.org/wiki/mvdw-placeholders)

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們致力於確保準確性，但請注意，自動翻譯可能包含錯誤或不準確之處。原始文件之母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們對於因使用本翻譯所導致之任何誤解或誤譯不負任何責任。