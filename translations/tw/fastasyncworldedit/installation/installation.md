<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "23574a55a9578d312963304e55c89c1a",
  "translation_date": "2025-05-13T03:53:52+00:00",
  "source_file": "fastasyncworldedit/installation/installation.md",
  "language_code": "tw"
}
-->
# Installation

## 初始設定

1. [下載插件](https://www.spigotmc.org/resources/13932)
2. 把 "FastAsyncWorldEdit.jar" 放到你的 `plugins` 資料夾裡
3. 重新啟動伺服器，FAWE 會自動產生所有必要的檔案。

{% hint style="info" %}
版本 6.0.0 以上需要 Java 17 才能運行。
{% endhint %}

{% hint style="warning" %}
不要安裝 WorldEdit！FAWE 是 **直接替代品**。
{% endhint %}

# 第三方插件支援

## 區域限制系統

以下區域限制插件是我們原生支援的，其他第三方插件可能未列出：

* [FactionsUUID](https://www.spigotmc.org/resources/1035)
* [GriefDefender](https://www.spigotmc.org/resources/68900)
* [GriefPrevention](https://www.spigotmc.org/resources/1884)
* [PlotSquared](https://www.spigotmc.org/resources/77506)
* [Towny](https://www.spigotmc.org/resources/72694)
* [WorldGuard](https://dev.bukkit.org/projects/worldguard)

{% hint style="tip" %}
這可以在設定檔中關閉，或用 `/wea` 指令或 `fawe.bypass` 權限來繞過。
{% endhint %}

## 其他插件

我們也提供符合 FAWE 限制的非同步版本 VoxelSniper：
[FastAsyncVoxelSniper](https://dev.bukkit.org/projects/favs)

# 紀錄與還原

在 `config.yml` 中啟用 `use-disk` 和 `use-database` 來使用內建的 FAWE 紀錄 / 還原功能。

{% hint style="tip" %}
給一般玩家使用 FAWE 還原功能是安全的。要繞過紀錄請使用 `//fast`。
{% endhint %}

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們致力於提供準確的翻譯，但請注意，自動翻譯可能包含錯誤或不準確之處。原始文件的母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯而產生的任何誤解或誤譯負責。