<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "be806bcb9db96790d57415a2ecc8505f",
  "translation_date": "2025-05-13T03:54:04+00:00",
  "source_file": "fastasyncworldedit/permission/permissions.md",
  "language_code": "tw"
}
-->
# 權限

{% hint style="tip" %}
有關指令相關的權限，請參考[這裡](../main-commands-and-permissions.md)。
{% endhint %}

## 管理員權限

- `fawe.admin`（允許透過 `/wea` 指令繞過限制）
- `fawe.bypass`（自動繞過 WorldEdit 的限制與限制條件）
- `worldedit.anyblock`（繞過 `disallowed-blocks` 在 `worldedit-config.yml` 中的限制）
- `worldedit.inventory.unrestricted`（若啟用，繞過背包限制）

## 使用者權限

- `fawe.limit.<limitgroup>`（授予使用者特定的限制群組。使用限制群組 `unlimited` 時，所有限制皆為無限。）
- [`fawe.permpack.basic`](https://github.com/IntellectualSites/FastAsyncWorldEdit/blob/main/worldedit-bukkit/src/main/resources/plugin.yml#L31)（一系列適用於創造模式伺服器的 WorldEdit 權限）
- `worldedit.navigation.jumpto.tool`（可使用 "jumpto" 工具）
- `worldedit.navigation.thru.tool`（可使用 "thru" 工具）

## 區域權限

FAWE 預設限制在區域內使用，這對於想讓一般玩家使用 WorldEdit 的伺服器很有用。若要啟用區域限制，請將設定項 `region-restrictions` 設為 true，並給予玩家相應的區域權限。如果你想讓管理員能透過 `//wea` 指令在任何地方使用 WorldEdit，請給他們 `fawe.admin` 權限。

### WorldGuard

若使用插件 [WorldGuard](https://dev.bukkit.org/projects/worldguard)，的限制權限。

- `fawe.worldguard` - 允許 WorldGuard 區域擁有者 (`/rg addowner ...`) 使用 WorldEdit。
- `fawe.worldguard.member` - 允許 WorldGuard 區域成員 (`/rg addmember ...`) 使用 WorldEdit。
- `fawe.worldguardextraflags` - 若安裝了 [WorldGuard Extra Flags](https://www.spigotmc.org/resources/4823)，此權限也會被使用。

### PlotSquared

若使用插件 [PlotSquared](https://www.spigotmc.org/resources/77506)，的限制權限。

- `fawe.plotsquared` - 允許 PlotSquared 擁有者 (`/plot setowner ...`) 和受信任者 (`/plot trust ...`) 使用 WorldEdit。
- `fawe.plotsquared.member` - 允許 PlotSquared 成員 (`/plot add ...`) 使用 WorldEdit。
- `fawe.plotsquared.admin` - 允許在任何 PlotSquared 地塊中使用 WorldEdit（但不包含道路）。

{% hint style="info" %}
`fawe.plotsquared` 權限在 [plugin.yml](https://github.com/IntellectualSites/FastAsyncWorldEdit/blob/e40a657faf993536133b2e1bbe771a5c96619bd7/worldedit-bukkit/src/main/resources/plugin.yml#L14-L17) 中預設啟用！若要覆寫權限，建議使用此權限而非子權限 `fawe.plotsquared.trusted`，因為它優先權較高。
{% endhint %}

### GriefPrevention

若使用插件 [GriefPrevention](https://www.spigotmc.org/resources/1884)，的限制權限。

- `fawe.griefprevention`

### Towny Advanced

若使用插件 [Towny Advanced](https://www.spigotmc.org/resources/72694)，的限制權限。

- `fawe.towny`
- `fawe.towny.member`
- `fawe.towny.*`

### PlotMe

若使用插件 [PlotMe](https://www.spigotmc.org/resources/2131)，的限制權限。（過時的插件！已多年不建議使用。）

- `fawe.plotme`

## 擴展的 WorldEdit 權限

- `worldedit.schematic.load.other`（當啟用 per-player-schematics 時，允許透過 `../` 載入主架構資料夾中的圖紙）
- `worldedit.schematic.save.other`（當啟用 per-player-schematics 時，允許透過 `../` 儲存至主架構資料夾中的圖紙）

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們努力追求準確，但請注意自動翻譯可能會包含錯誤或不準確之處。原始文件之母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。本公司不對因使用本翻譯所引起之任何誤解或誤譯負責。