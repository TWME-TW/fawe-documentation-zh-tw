<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "145d8e37c80a7844877c9541bd502605",
  "translation_date": "2025-05-13T04:02:40+00:00",
  "source_file": "plotsquared/old/changelog-old.md",
  "language_code": "tw"
}
-->
# 變更紀錄（舊版）

## 介紹

最新的變更紀錄可以在 GitHub 的 Releases 頁籤取得。

各版本的直接連結：

## v4 到 v5：

* [點此](spigot-changelog-v4-and-v5.md)

## V5：

* [v5.0.0 到 5.9.0](../../../../plotsquared/old)
* [v5.10.0](../../../../plotsquared/old)
* [v5.10.1](../../../../plotsquared/old)
* [v5.10.2](../../../../plotsquared/old)
* [v5.10.3]內部變更，未釋出公開版本。
* [v5.10.4](../../../../plotsquared/old)
* [v5.10.5](../../../../plotsquared/old)
* [v5.11.0](../../../../plotsquared/old)
* [v5.11.1](../../../../plotsquared/old)
* [v5.12.0](../../../../plotsquared/old)
* [v5.12.1](../../../../plotsquared/old)
* [v5.12.2](../../../../plotsquared/old)
* [v5.12.3](../../../../plotsquared/old)
* [v5.12.4](../../../../plotsquared/old)
* [v5.13.0](../../../../plotsquared/old)
* [v5.13.1](../../../../plotsquared/old)
* [v5.13.2](../../../../plotsquared/old)
* [v5.13.3](../../../../plotsquared/old)
* [v5.13.4](../../../../plotsquared/old)
* [v5.13.5](../../../../plotsquared/old)
* [v5.13.6](../../../../plotsquared/old)
* [v5.13.7]內部變更，未釋出公開版本。
* [v5.13.8](../../../../plotsquared/old)
* [v5.13.9](../../../../plotsquared/old)
* [v5.13.10](../../../../plotsquared/old)
* [v5.13.11](../../../../plotsquared/old)

## V6：

* [v6.0.0](../../../../plotsquared/old)
* [v6.0.1](../../../../plotsquared/old)
* [v6.0.2](../../../../plotsquared/old)
* [v6.0.3](../../../../plotsquared/old)
* [v6.0.4](../../../../plotsquared/old)
* [v6.0.5](../../../../plotsquared/old)
* [v6.0.6](../../../../plotsquared/old)
* [v6.0.7](../../../../plotsquared/old)

## v5.0.0 到 5.9.0

旗標：

* 完全重寫旗標系統
* 改善旗標資料庫處理
* 在旗標中加入對材質標籤/分類的支援
* 改善 /plot flag info 和 /plot flag list
* 新增旗標指令補完
* 重寫 wiki 旗標頁面
* 讓魔像包含在動物攻擊範圍內
* 修正合併地塊中方塊點燃問題
* 修正液體流動問題
* 修正不受信任訪客問題
* 修正飛行無法正確恢復玩家飛行狀態
* 新增 coral-dry 旗標
* 新增聊天旗標以處理地塊聊天

效能：

* 避免插件中同步載入區塊，極大降低 /plot auto 對效能的影響

產生器：

* 確保清除附加地塊時，若為完整原版地形不會生成牆壁
* 使用 WorldEdit 重新生成附加地塊區塊（警告：非常慢！）
* 支援 schematics v2（生物群系、實體等！）

其他：

* 修正 1.15 版本離線玩家檔案讀取問題
* 新增選項讓道路重生可跨重啟持續
* 新增選項讓 /plot purge 同時清除被清除的地塊
* 讓 PlotSquared 事件與平台無關
* 讓 PlotSquared 事件更整潔
* 修正 /plot swap 未正確更新擁有者問題
* 修正 /plot move 未清除地塊問題
* 修正 /plot swap 未正確更新地塊告示牌問題
* 改善交換/移動 API
* 修正 /plot comment（來自 V4）
* 修正圖案生成（來自 V4）
* 修正舊版轉換器（來自 V4）
* 允許在 redstone.disable-offline 啟用時，紅石可用於伺服器地塊
* 修正生物群系設定（現在支援 1.13-1.15+）
* 修正液體會從邊界/牆壁流入地塊問題
* 改善地塊擁有者 API
* 透過移除大量魔法數值與增加程式碼封裝性，提升內部程式碼品質
* 允許信任用戶使用 /plot set
* 為 PlotSquared 新增 PAPI 佔位符（從擴充中移出）
* 修正 Bukkit 世界 API 非同步存取導致 PlotSquared 附加產生失敗（近期 Paper 版本）
* 更佳的程式碼庫組織
* 完全重構套件名稱
* 新增強制地塊聊天選項
* 其他許多小幅改動

## v5.10.0

* 修正更新通知問題
* 修正地塊清除極度緩慢問題

## v5.10.1

* 修正因 Spigot API 回傳 5.1 而非 5.10 導致的更新器問題
* 更新預設地塊生物群系設定格式以符合 WorldEdit，並修正錯誤格式的現有設定值

## v5.10.2

* 更新通知改為每 30 分鐘輪詢一次，且只會在首次檢測到最新版本時祝賀。啟用更新檢查後，玩家加入時不再每次輪詢。
* 修正取得地塊評論問題
* 修正 PlaceholderAPI 空值錯誤，並調整邏輯，即使玩家不在地塊內，仍可使用相關佔位符

## v5.10.4

* 新增 Paper 專用監聽器（可設定）：
  - 防止生物漫遊離開地塊
  - 改善生物生成防止效能
* 進一步降低預設更新輪詢頻率（預設 6 小時，可設定）
* 啟用 LiquidFlow 旗標會覆蓋方塊物理拒絕設定
* 旗標名稱限制為最多 64 字元（有助於避免舊資料庫結構錯誤）
* 地塊世界中地塊 + 道路尺寸小於 16 不再導致生成問題

*此版本亦包含以下變更：*

* 新增設定選項，更新後停止輪詢（且不再列印更新訊息於控制台），但遊戲內玩家仍會收到提示
* 正確偵測新版可用以對抗 Spigot API 延遲
* LiquidFlow 旗標改為三值 enum：default、enabled、disabled
* 更新 SpawnReasons 與 Spigot 保持一致
* 地塊過期訊息可點擊執行指令
* 地塊設定將正確顯示世界類型選項

## v5.10.5

* 修正地塊分析時錯誤
* 正確顯示已使用及剩餘授權
* 修正使用 /plot auto 時授權問題
* 修正重啟後旗標中方塊標籤（#buttons）問題
* 修正 /plot merge all
* 不再將聊天監控訊息發送給訊息發送者

## v5.11.0

這是一個較大型更新，強烈建議詳細閱讀相關連結。請注意備份系統預設啟用，會延遲 `/plot clear` 和 `/plot set <component>`，直到地塊快照完成。此功能可在設定檔中關閉。

如果有非常大的地塊（寬度超過 200 方塊），建議關閉自動備份。

*若您要與 FAWE 一起使用備份系統，請務必更新到最新 FAWE 版本！*

*新功能*：

* 新增地塊備份 https://wiki.intellectualsites.com/en/plotsquared/backups
* 新增 `keep-inventory` 旗標
* 新增設定選項，禁止在 `/plot set` 使用特定方塊（於 settings.yml）(https://i.imgur.com/pO0grZd.png)。預設包含：https://pastie.io/qhceln.txt
* 新增 `/plot set` 相關 wiki 頁面：https://wiki.intellectualsites.com/en/plotsquared/plot-settings
* 新增 `/plot set` 指令補完：https://i.imgur.com/kNz3zks.png
* 新增更新的法文翻譯

*修正*：

* 修正史萊姆導航錯誤
* 修正實體戰鬥監聽器潛在問題
* 修正 `/plot merge auto`

## v5.11.1

本次更新重點為區塊處理器，並更新其 wiki 頁面：https://wiki.intellectualsites.com/en/plotsquared/optimization/chunk-processor。此系統對於伺服器有大量方塊實體數量的情況非常有用，且現在能正常運作。

*新增*：

* 新增 `prevent-creative-copy` 旗標，防止在地塊中複製 NBT 資料
* 新增 Paper 使用時方塊放置觸發方塊實體檢查選項
* 新增 bStats 圖表以追蹤 FAWE 使用狀況

*變更*：

* （目前僅限 WE，不支援 FAWE）更新 WE 監聽器，正確限制方塊實體數量，且限制改為每區塊而非每次編輯
* 讓 `/plot set <component>` 遵守方塊實體限制
* 更新區塊管理程式碼
* 若伺服器只有一個地塊區域，允許非地塊區域使用 `/plot auto`
* 在地塊移動、交換時複製 NBT 資料

*修正*：

* 第 950 次修正更新通知器
* 修正 `/plot set ##*category` 可繞過黑名單問題
* 修正方塊實體與實體限制會刪除區塊中所有實體問題
* 修正 style.yml 不更新預設值問題
* 讓 `/plot setbiome` 在更新生物群系前正確載入區塊
* 讓 `/plot clear` 在移除前清空方塊實體

*若您使用 FastAsyncWorldEdit，請更新至最新 FAWE 版本，因為 PlotSquared 區塊管理已改變*

## v5.12.0

_由於此版本對地塊元件進行變更，強烈建議使用最新 FastAsyncWorldEdit 版本（若要使用 FAWE）。_

## 重大變更

### 單一地塊區域

此版本讓您更容易在非地塊世界中建立[單一地塊](../customization/single-plot-area.md)，利用 WorldEdit 選取功能。現在您可以在任何地方建立地塊，並在所有世界中使用 PlotSquared 的功能。

### 地塊元件 GUI

PlotSquared 現在允許您建立[元件預設](../customization/plot-components.md)，可透過 GUI 使用。

### UUID 系統重寫

我們從頭重寫了 UUID 處理，UUID 與使用者名稱的對應將更可靠，能解決「未知」地塊成員、擁有者等問題。

當您從不同來源（以下順序）自動取得使用者名稱：

* 記憶體快取
* 新版 user_data.db（SQLite 快取）
* 舊版 userdata.db（SQLite 快取）
* Bukkit 離線玩家 / Paper 檔案
* （選用）Essentials 使用者檔案
* （選用）LuckPerms 使用者資料
* （選用）BungeePerms 使用者資料
* Mojang API

首次執行 PlotSquared v5.12.0 可能會花較長時間，取決於伺服器上缺少 UUID 數量。之所以特別慢，是因 Mojang 對請求數量有嚴格限制。完成一次後，PlotSquared 可在幾秒內索引數千 UUID。

_若您使用離線模式伺服器且無 BungeeCord，舊有 UUID 快取可能失效，導致所有人初次加入前顯示為「未知」。若發生此狀況，請於 Discord 聯繫我們，以便評估您的環境並協助解決。_

此系統也代表您可以在玩家未曾加入伺服器前，將其加入地塊並設為擁有者等。

## 其他變更

### 功能

* 新增內部世界管理系統
* 新增 `/plot visit` 指令補完
* 新增 `/plot list` 指令補完
* 新增 `/plot <add|trust|deny|kick|remove>` 指令補完
* 新增非同步指令補完支援（僅限 Paper）
* 新增 `/plot toggle debug`，當旗標改變事件結果時通知地塊擁有者與管理員

### 變更

* 更換問題追蹤系統，改用 [YouTrack](https://issues.intellectualsites.com/projects/ps)
* PlotSquared 現在會註冊於 `bukkit.yml`，解決世界未被識別為地塊世界問題
* 讓大型操作較不易導致伺服器崩潰
* 移動立方體操作方法，使 FAWE 可控制如 `/plot set` 的操作
* 更換內部地塊區域映射為 [R-tree](https://en.wikipedia.org/wiki/R-tree)，在世界有大量地塊區域時效能更佳
* 大幅改善地塊區域 API
* 新增地塊查詢 API 並內部使用
* 重構 `/plot setup` 指令內部，並加入指令補完（例如方塊）
* 設定紙指令補完器作用的指令別名列表

### 修正

* 修正結構保存問題 ([#2836](https://github.com/IntellectualSites/PlotSquared/commit/d5d18a60fb68e95115a1f8678043e6f01a76d328))
* 修正地塊聊天間諜啟用時，聊天未送給行為者問題 ([#PS-7](https://issues.intellectualsites.com/issue/PS-7))
* 新 UUID 系統避免「未知」問題
* 修正訪問帶您至錯誤玩家地塊問題
* 修正合併地塊時生成方塊高度錯誤為道路高度問題 ([#PS-46](https://issues.intellectualsites.com/issue/PS-46))
* 修正過期期間發送的保留指令

## v5.12.1

此版本為 v5.12.0 的小型熱修正

*變更：*

* 修正舊玩家物件未正確清理問題，原因為 Spigot 事件順序錯誤（含衍生版本）
* 修正指令無法正常運作問題

## v5.12.2

此更新專注於 1.16 版本的新功能與增強

https://www.spigotmc.org/resources/plotsquared-v5.77506/update?update=346686

**警告：** 若 `/plots home` 無法運作，請刪除您的 `plugins/PlotSquared/config/commands.yml` 檔案。

*新增*：

* 新增 `%plotsquared_currentplot_localflag_<flag>%` 和 `%plotsquared_currentplot_flag_<flag>%` 佔位符以回傳地塊旗標值
* 新增 1.16.1 支援
* 新增設定選項，可設定快取過期時間
* 新增設定選項，可關閉背景 UUID 快取
* 新增鉤子，可介入地塊清除並修改行為，讓像 FAWE 這類插件能提升清除速度
* 新增設定旗標給地塊道路，可於 worlds.yml 設定

*變更*：

* 將指令補完快取時間從 1 分鐘降至 15 秒
* 只有在啟用經濟時初始化 EconHandler，且停止直接存取靜態實例
* 將 Vault 權限處理與經濟處理分離
* 新增 `plots.admin.alias.remove` 和 `plots.admin.alias.set` 權限節點
* `/plot visit` 與 `/plot home` 指令拆分為兩個（現在可無障礙傳送至第 12384 個地塊）
* `/plot visit` 與 `/plot home` 現有分別的權限節點：`plots.visit` 和 `plots.home`

**TIP:** 請參考新語法：[/p home](https://wiki.intellectualsites.com/en/plotsquared/commands-and-permissions#home) 和 [/p visit](https://wiki.intellectualsites.com/en/plotsquared/commands-and-permissions#visit)。新佔位符說明見[這裡](https://wiki.intellectualsites.com/en/plotsquared/placeholders)。

*修正*：

* 修正 OfflinePlayerUUIDService 在未載入世界時崩潰問題
* 修正數字有時被誤解析為使用者名稱
* 修正「非有效地塊 ID」訊息重複發送
* 修正 /plot kick 顯示「無效玩家」訊息
* 修正 Plot#claim 世界邊界更新問題 [[PS-13](https://issues.intellectualsites.com/issue/PS-13)]
* 修正地塊備份問題
* 修正道路交叉口生物群系資料錯誤 [[PS-50](https://issues.intellectualsites.com/issue/PS-50)]
* 修正 /plot 別名指令補完錯誤

若您在 1.16.1 地塊世界遇到持續下雨問題，請更新您的 SpigotMC 版本（或衍生版本）。此問題為 Spigot 端錯誤，現已修復 [[SPIGOT-5849](https://hub.spigotmc.org/jira/browse/SPIGOT-5849)]。

## v5.12.3

*變更*：

* 移除 `commands.yml`，將於版本 6 重新實作

*修正*：

* 修正玩家無法與自己地塊互動問題
* 修正玩家無法傳送至合併地塊問題
* 修正地塊過期任務無法啟動問題

## v5.12.4

*修正*：

* 修正與分配器及地塊道路相關的多項問題 ([#2874](https://github.com/IntellectualSites/PlotSquared/pull/2874))
* 修正 `%plotsquared_currentplot_owner%` 佔位符拋出例外錯誤 (PS-62)
* 修正殺死道路生物 (PS-73)
* 修正與活塞及地塊道路相關問題 ([#2875](https://github.com/IntellectualSites/PlotSquared/pull/2875) / PS-39)

*變更*：

* 玩家移動時立即發送傳送取消訊息 (PS-33)
* 將失敗的
* 修正 `/plot deny *` 未能將所有玩家從地塊傳送出去的問題 [PS-182](https://issues.intellectualsites.com/issue/PS-182)
* 修正 `/plot f set disable-physics` 造成漂浮鬼魂方塊的問題 [PS-159](https://issues.intellectualsites.com/issue/PS-182)
* 修正結構偏移量 x/z 被重複計算的問題
* 修正嘗試依擁有者/新增者清除時的錯誤

## v5.13.10

*修正*：

* `/plot debugpaste` 未正確讀取 Multiverse 的 worlds.yml 問題

## v5.13.11

*新增*：

* 在 bStats 新增幾項指標。

*修正*：

* 修正 [[PS-188](https://issues.intellectualsites.com/issue/PS-188)]
* 修正伺服器版本 >= 1.13.2 時 `java.lang.NoSuchFieldException: mustSave` 啟動失敗
* 修正 settings.yml 中的 `teleport.per-world-visit` 問題

## v6.0.0

## Settings.yml 變更：

以下條目已被移除或修改，可放心從檔案中刪除。

### 移除：

* 因為資產介面在 v4 和 v5 中已不存在，選項 `web.assets` 已被移除。
* 選項 `chat.console_color` 已被移除。PlotSquared 現在會正確支援舊版及冒險模式元件，並會始終傳送正確顏色。
* 選項 `uuid.use-sqluuidhandler`、`enabled_components.per-world-visit`、`chunk.block-cache`、`enabled_components.permission-cache`、`chat.interactive` 已被移除，因為不再有用途。
* 類別 `chat` 已被移除。
* 獨立選項 `titles` 已移動至自己的設定區塊，並新增相關選項。

### 新增：

以下條目已新增，這些會在 v6 第一次啟動時自動加入。

* 新增選項 `enabled-components.default-locale`，指定的值會用來尋找正確的翻譯檔。
* 新增選項 `enabled-components.per-user-locale`，啟用後，PlotSquared 會在有翻譯時以使用者的語系傳送文字。
* 新增選項 `teleport.on-clear` 和 `teleport.on-delete`，用來決定清除或刪除時是否傳送傳送玩家。
* 新增選項 `timeformat.date-format` 和 `timeformat.time-zone`，用來格式化地塊建立日期的佔位符與 `/plot info` 中的顯示。修改格式不會影響儲存的日期。
* 新增選項 `titles.titles-fade-in`、`titles.titles-stay`、`titles.titles-fade-out` 和 `titles.titles-as-actionbar`，讓地塊標題的持續時間可自訂，並可選擇是否以動作欄訊息傳送地塊標題。
* 之前的選項 `titles` 已轉換為 `titles.display-titles`。
* 新增選項 `ratings.block-0`，設定 `/plot rate` GUI 使用的方塊數量，預設為 8。
* 新增選項 `chat.log-plotchat-to-console`，決定是否將地塊聊天記錄輸出到主控台。
* 新增選項 `chat.notification-as-actionbar`，決定通知旗標（如 notify-enter、notify-leave、greeting 或 farewell）是否以動作欄訊息取代一般聊天訊息。

## Worlds.yml 變更：

* 新增選項 `plot.sign_material`（1.13 版本則為 `plot.legacy_sign_material`），可更改地塊告示牌的材質。
* 因 Nashorn 腳本引擎被移除並改用 [WorldEdit Expressions](https://worldedit.enginehub.org/en/latest/usage/other/expressions/)，價格表達式不再用 `+{arg}+`，改用 `+{plots}+`，使用上更直覺。若偵測到相關欄位，PlotSquared 會自動轉換。如果你之前使用過類似 `Math.pow()` 的 JS 函數，需要手動更新。可參考 WorldEdit Wiki 或在 Discord 求助。

## 翻譯變更：

* 從 v6 開始，PlotSquared 使用 Adventure 來處理翻譯，支援六角色碼、漸層等。詳情請參考 [說明](https://docs.adventure.kyori.net/minimessage.html#color)。
* 我們現在使用 Crowdin Enterprise 來管理翻譯。歡迎幫助我們[翻譯 PlotSquared](https://intellectualsites.crowdin.com/plotsquared)成你的語言。
* 你可以在 settings.yml 中透過 `<key>` 變更 PlotSquared 的語言，無需再重新命名任何檔案。
* 翻譯檔放在 `lang` 資料夾，舊的 `translations` 資料夾可安全刪除，已不再需要。

## 權限變更：

____
在 PlotSquared v6 中，若玩家是管理員 (/op [player])，預設不會自動獲得權限。PlotSquared 採用複雜的權限系統，建議配合權限管理插件使用，例如 [LuckPerms](https://www.spigotmc.org/resources/luckperms.28140/)。
不過，你仍可用節點 `plots.*` 授予玩家所有 PlotSquared 權限。
____

### 單一權限變更

#### 新增：

* 新增權限 `plots.admin.music.other`，允許在他人地塊使用 `/plot music`。
* 新增權限 `plots.visit.denied`，無此權限玩家無法造訪被拒絕的地塊。
* 新增權限 `plots.add.<amount>`、`plots.trust.<amount>` 和 `plots.deny.<amount>`，運作方式類似 `plots.plot.<amount>` 範圍型權限，可在節點中指定數量。
* 新增權限 `plots.admin.flight`，可繞過 `fly` 旗標。
* 新增權限 `plots.flag.notify-leave.bypass`，`plots.flag.notify-enter.bypass` 不再涵蓋兩種類型。
* 新增權限 `plots.admin.components.other`，作為管理覆寫，可在非自己擁有但需管理的地塊使用 `/plot components`。

#### 變更：

* `/plot flag remove <flag>` 現在需要 `plots.flag.remove` 權限節點，之前是繼承自 `plots.flag.add`。
* 修正權限 `plots.admin.command.unlink`。
* 權限 `plots.set.alias` 已被 `plots.alias.set` 取代。
* 權限 `plots.admin.command.rate` 已被 `plots.admin.command.purge.ratings` 取代。
* 權限 `plots.admin.command.chat` 已被 `plots.admin.command.chatspy` 取代。
* 指令 `/plot toggle <attribute>` 現在也需要基礎權限 `plots.toggle`。

#### 移除：

* 移除權限 `plots.list.unknown`。
* 移除權限 `plots.admin.command.update`。

### 權限包變更

所有 `plotme.<pack>` 權限包已被移除。以下列出取代被移除權限包的新權限包或要指定的權限節點。
注意：如果你之前沒用過舊版 PlotMe 權限，可以忽略下表！

| 移除的權限              | 替代權限                                                                                                                                                                                                  |
|------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| plotme.use             | `plots.permpack.basic`, `plots.plot.1`                                                                                                                                                                  |
| plotme.admin           | `plots.admin`                                                                                                                                                                                        |
| plotme.admin.clear     | `plots.admin.command.clear`                                                                                                                                                                                        |
| plotme.admin.reset     | `plots.admin.command.delete`                                                                                                                                                                                        |
| plotme.admin.add       | `plots.admin.command.add`                                                                                                                                                                                        |
| plotme.admin.deny      | `plots.admin.command.deny`                                                                                                                                                                                        |
| plotme.admin.remove    | `plots.admin.command.remove`                                                                                                                                                                                        |
| plotme.admin.undeny    | `plots.admin.command.remove`                                                                                                                                                                                        |
| plotme.admin.bypassdeny| `plots.admin.entry.denied`                                                                                                                                                                                        |
| plotme.admin.setowner  | `plots.admin.command.setowner`                                                                                                                                                                                        |
| plotme.admin.move      | `plots.admin.command.move`                                                                                                                                                                                        |
| plotme.admin.weanywhere| `plots.admin.weanywhere`                                                                                                                                                                                        |
| plotme.admin.list      | `plots.list.world`, `plots.list.world.*`, `plots.list.top`, `plots.list.all`, `plots.list.unowned`, `plots.list.player`, `plots.list.done`, `plots.list.expired`, `plots.list.fuzzy`, `plots.list.area` |
| plotme.admin.dispose   | `plots.admin.command.delete`                                                                                                                                                                                        |
| plotme.admin.done      | `plots.admin.command.done`                                                                                                                                                                                        |
| plotme.admin.expired   | `plots.list.expired`                                                                                                                                                                                        |
| plotme.admin.buildanywhere | `plots.admin.vehicle.*`, `plots.admin.interact.*`, `plots.admin.build.*`, `plots.admin.destroy.*`                                                                                                                   |
| plotme.use.middle      | `plots.middle`                                                                                                                                                                                        |
| plotme.use.buy         | `plots.buy`                                                                                                                                                                                        |
| plotme.use.sell        | `plots.set`, `plots.flag`, `plots.set.flag`, `plots.set.flag.price.*`                                                                                                                        |
| plotme.use.dispose     | `plots.delete`                                                                                                                                                                                        |
| plotme.use.done        | `plots.done`                                                                                                                                                                                        |
| plotme.use.claim       | `plots.claim`                                                                                                                                                                                        |
| plotme.use.auto        | `plots.auto`                                                                                                                                                                                        |
| plotme.use.reset       | `plots.delete`                                                                                                                                                                                        |
| plotme.use.home        | `plots.home`                                                                                                                                                                                         |
| `plotme.use.info`       | `plots.info`                                                                                                                                                                                         |
| plotme.use.biome       | `plots.set`, `plots.set.biome`                                                                                                                                                                  |
| plotme.use.clear       | `plots.clear`                                                                                                                                                                                        |
| plotme.use.list        | `plots.list`, `plots.list.forsale`, `plots.list.mine`, `plots.list.shared`                                                                                                                        |
| plotme.use.add         | `plots.add`, `plots.trust`, `plots.add.everyone`, `plots.trust.everyone`                                                                                                                        |
| plotme.use.deny        | `plots.deny`, `plots.deny.everyone`                                                                                                                                                                  |
| plotme.use.remove      | `plots.remove`                                                                                                                                                                                        |
| plotme.use.undeny      | `plots.remove`                                                                                                                                                                                        |
| plotme.use.protect     | `plots.set`, `plots.flag`, `plots.set.flag`, `plots.set.flag.keep.*`                                                                                                                        |
| plotme.use.nameplot    | `plots.alias.set`, `plots.alias.remove`                                                                                                                                                                  |
| plotme.limit.*         | `plots.plot.*`                                                                                                                                                                                        |
| plotme.limit.1         | `plots.plot.1`                                                                                                                                                                                        |
| plotme.limit.5         | `plots.plot.5`                                                                                                                                                                                        |
| plotme.limit.10        | `plots.plot.10`                                                                                                                                                                                        |

## 佔位符變更

### 新增：

* 新增佔位符 `%plotsquared_currentplot_creationdate%`，顯示地塊建立日期。格式可在 settings.yml 的 timeformat 區段自訂。
* 新增佔位符 `%plotsquared_currentplot_members_trusted_list%`、`%plotsquared_currentplot_members_added_list%` 和 `%plotsquared_currentplot_members_denied_list%`，分別顯示新增、信任和拒絕的玩家清單。

### 變更：

* `%plotsquared_currentplot_world%` 改名為 `%plotsquared_currentplot_world_name%`。
* `%plotsquared_has_build_rights%` 改名為 `%plotsquared_currentplot_can_build`，更符合 `/plot info`。
* `%plotsquared_allowed_plot_count%` 現在如果有 * 權限會回傳 `infinite`。

## 指令變更

* 指令 `/plot save` 已移除，改由 Arkitektonika 透過 `/plot download` 於遊戲內使用。
* 指令 `/plot download` 已改用 Arkitektonika，現在會附帶刪除金鑰和下載 URL，可隨時刪除結構圖。
* 指令 `/plot wea` 因棄用已移除，改由 `/plot toggle worldedit` 取代，另外別名有 `/plot toggle wea` 或 `/plot toggle we`。
* `/plot help` 現在支援分類的分頁補全，且無法存取特定說明頁時會通知使用者。

## 可用性變更

* 幾乎所有指令都新增分頁補全，會建議合適參數，前提是使用者有權限。
* 現在預設使用 Vault 作為貨幣系統，允許其他插件提供自己的貨幣（如 $、€ 等）。
* 已移除破壞性地塊指令，如 `clear` 或 `delete` 在地塊世界的地塊中無法使用。
* 多數地塊指令現在會在執行時帶上地塊 ID，例如 `/plot clear` 或 `/plot set biome`。
* 地塊世界的地塊索引分隔符由冒號改為底線 (`_`)。
* `/plot setowner` 現在會尊重授權。

## 旗標變更

### 新增：

* 新增旗標 `leaf-decay`，決定葉子是否會腐爛。預設為 true，要停止腐爛需透過 `/plot flag set leaf-decay false` 設定。
* 新增旗標 `fall-damage`，決定實體或玩家是否會承受跌落傷害。
* 新增旗標 `crop-grow`，決定作物是否能生長。
* 新增旗標 `deny-portals` 和 `deny-portal-travel`，分別決定是否能建立和使用傳送門。
* 新增旗標 `deny-portal-travel`，決定玩家是否能跨維度透過傳送門旅行。
* 新增旗標 `lectern-read-book`，決定玩家是否能打開講桌閱讀書本。注意：此功能需搭配 `use` 旗標和 `lectern` 輸入。
* 新增旗標 `entity-change-block`，允許更細緻控制雜項實體事件，例如玩家跳上大滴水葉。

### 變更：

* 旗標 `weather` 現在僅接受 `rain` 和 `clear` 兩種輸入，符合原版命名規則。

## 錯誤修正（僅列出先前版本存在的問題，非 v6 新增後修正）

* 修正合併地塊儲存與讀取問題 [PS-29](https://issues.intellectualsites.com/issue/PS-29), [PS-197](https://issues.intellectualsites.com/issue/PS-197)
* 修正玩家未被加入地塊卻跳入鍋子滅火時會抽乾水的問題 [3034](https://github.com/IntellectualSites/PlotSquared/issues/3034)
* 修正踢出或拒絕玩家時，若未設定重生點，玩家不會被踢出伺服器的問題 [3057](https://github.com/IntellectualSites/PlotSquared/issues/3057)
* 修正與龍蛋相關的幾個問題 [3074](https://github.com/IntellectualSites/PlotSquared/issues/3074), [3076](https://github.com/IntellectualSites/PlotSquared/issues/3076)
* 修正 `/plot rate` 無法渲染空物品堆疊的問題 [3063](https://github.com/IntellectualSites/PlotSquared/issues/3063)
* 相容並支援 Java 16
* 修正 `/plot inbox` 相關問題：[3021](https://github.com/IntellectualSites/PlotSquared/issues/3021), [3020](https://github.com/IntellectualSites/PlotSquared/issues/3021)

## 其他變更

* 我們的 [Javadocs](https://ci.athion.net/job/PlotSquared-v6-Javadocs/) 現在可搜尋，並連結到所用相依套件的外部資源。
* 完整支援 Minecraft 1.17
* 需求 Java 16 或以上版本。

## v6.0.1

*變更*：

* PlotAPI 版本改為 6
* 已棄用的 API 方法將標示即將移除

*修正*：

* 修正重啟後更改語系無效，需使用 /plot reload 才生效 [#3099](https://github.com/IntellectualSites/PlotSquared/issues/3099)
* 修正設定後清除及刪除地塊未將所有玩家傳送出地塊的問題 [#3102](https://github.com/IntellectualSites/PlotSquared/issues/3102)
* 修正 Citizens 使用假 UUID 的問題 [#3105](https://github.com/IntellectualSites/PlotSquared/issues/3105)

## v6.0.2

*變更*：

* 更新至最新支援 1.

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們致力於確保準確性，但請注意，自動翻譯可能包含錯誤或不準確之處。原始文件之母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。本公司對於因使用本翻譯所產生之任何誤解或誤譯概不負責。