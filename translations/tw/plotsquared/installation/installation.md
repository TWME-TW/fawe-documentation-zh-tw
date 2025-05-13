<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "ebff9caf98f5f4d233b5a6b3001bca05",
  "translation_date": "2025-05-13T03:59:02+00:00",
  "source_file": "plotsquared/installation/installation.md",
  "language_code": "tw"
}
-->
# 安裝

## 初始設定

1. [下載外掛](https://www.spigotmc.org/resources/77506)
2. 將 "PlotSquared-Bukkit-7.x.jar" 放入你的 `plugins` 資料夾
3. 如果你還沒安裝，[WorldEdit 7.2.x 或更新版本](https://dev.bukkit.org/projects/worldedit/files) 或 [FAWE](https://www.spigotmc.org/resources/13932) 是必須的。
4. 如果你是從舊的大版本升級，比如 v3、v4 或 v5，請先閱讀 [這篇](migrating-from-an-older-major-release.md) 文章。
5. 重新啟動伺服器，PlotSquared 會自動產生所有必要的檔案。

{% hint style="info" %}
PlotSquared 6.0.0 版及以上需要 Java 17 才能運行。
{% endhint %}

## 資料庫設定

本節說明如何設定 PlotSquared 的資料庫存取。

PlotSquared 支援的資料庫類型有 "MYSQL" 和 "SQLite"。如果你不清楚兩者的差異，可以參考這篇 [文章](https://dzone.com/articles/sqlite-vs-mysql) 的簡短比較。

{% hint style="tip" %}
你可以隨時用 `/plot database` 指令在 MySQL 與 SQLite 間切換。
{% endhint %}

請記得你只能選擇 MySQL 或 SQLite，不能同時使用兩者。

### 資料庫：SQLite

如果你沒有 MySQL 資料庫，系統會自動設為使用 "SQLite"，這步驟可以跳過。
(設定檔位於 `/plugins/PlotSquared/config/storage.yml`。)

### 資料庫：MySQL

*啟用 MySQL 也同時支援像 MariaDB 這類的其他儲存類型：*

* 前往 `/plugins/PlotSquared/config/storage.yml`
* 設定你的 MySQL 資料庫帳號密碼。

## 地皮設定

你現在可以建立 plotworld，或是在現有世界中設定[單一地皮](../customization/single-plot-area.md)。

### 預設世界設定

如果你不需要原版世界，可以把預設世界設成 plotworld。

1. （先停止伺服器，然後）刪除像下面選擇的原版世界 `world`、`world_nether` 和 `world_the_end`：

![image](https://i.imgur.com/6kAMx34.png)

2. 接著打開 `server.properties` 檔案，這個檔案在伺服器根目錄。

- 找到以下這行：

```text
level-name=world
```

- 把 `world` 改成你想用的 plotworld 名稱。這範例中，我們改成 `plotworld`。
結果會長這樣：

```text
level-name=plotworld
```

3. 編輯 bukkit.yml：
 ** 打開 `bukkit.yml` 檔案（同樣在伺服器根目錄）。我們需要告訴伺服器要用哪個世界產生器，*不然世界生成會出錯*。

這個設定在檔案中還不存在，所以要加在檔案底部：

```yaml
worlds:
  plotworld:
    generator: PlotSquared
```

4. 接著就可以照後續步驟進行。

## 透過 Plot Setup 建立

你可以用設定精靈來建立 plotworld。使用 `/plot setup` to start the wizard.  +
Every step requires the command, e.g. `/plot setup PlotSquared` and replace "PlotSquared" with your desired value.
When you are done, PlotSquared will teleport you to the generated plotworld.

## Alternative: Creation via Multiverse

If you use the plugin [Multiverse](https://dev.bukkit.org/projects/multiverse-core) you can create a world using the command `/mv create <worldname> normal -g PlotSquared`.

{% hint style="info" %}
Now you can edit the `/plugins/Multiverse-Core/worlds.yml` to change the default world options such as "pvp", "respawnWorld", "spawning" and etc.
{% endhint %}

## Manually Switching The Generator Set in the Bukkit.yml (optional)

Sometimes PlotSquared will be unable to switch the generators for your plotworlds. If this is the case, you will need to manually switch the generator over while the server is stopped.

Open the `bukkit.yml` 檔案（位於伺服器根目錄）並在伺服器*停止*狀態下，依照以下格式更改產生器：

```yaml
worlds:
  plotworld:
    generator: PlotSquared
```

把 `plotworld` 換成你的 plotworld 名稱。 ([bukkit 幫助頁](https://bukkit.gamepedia.com/Bukkit.yml#.2AOPTIONAL.2A_worlds))

## 加入 Plotworld 道路結構（可選）

用預設的結構自訂地皮間的道路。

**說明:** [Plotworld 道路結構](../schematics/road-schematic.md)

## 加入地皮結構（可選）

### 生成時的地皮結構

允許在所有地皮生成時套用自訂結構。

**說明:** [生成時的地皮結構](../schematics/schematic-generation.md)

### 領取時的地皮結構

玩家領取地皮時會獲得自訂結構。如果想，玩家也可以用領取指令自訂地皮結構。

**說明:** [領取時的地皮結構](../schematics/schematic-on-claim.md)

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們致力於提供準確的翻譯，但請注意自動翻譯可能包含錯誤或不準確之處。原始文件的母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們對於因使用本翻譯所產生的任何誤解或誤譯不負任何責任。