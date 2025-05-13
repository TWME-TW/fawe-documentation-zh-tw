<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "b1475c2558c5d43f64254916386aa745",
  "translation_date": "2025-05-13T03:54:38+00:00",
  "source_file": "fastasyncworldedit/commands/administrative/administrative.md",
  "language_code": "tw"
}
-->
# 管理指令

## 版本

這個指令可以用來顯示已安裝的 FAWE 版本。

**用法：**
`/fawe version`

**視覺範例：**

![Example 1](../../../../../fastasyncworldedit/commands/administrative/images/version.png)

## 執行緒

這個指令會列印所有執行緒堆疊。由於輸出非常長，建議透過主控台使用。

**用法：**
`/fawe threads`

**權限：**
`worldedit.threads`

**範例：**

```
[15:34:08] [AsyncNotifyKeyedQueue - 1/INFO]: --------------------------------------------------------------------------------------------
[15:34:08] [AsyncNotifyKeyedQueue - 1/INFO]: Thread: Async Tab Complete Thread - #2 | Id: 133 | Alive: true
[15:34:08] [AsyncNotifyKeyedQueue - 1/INFO]: java.base@17.0.1/jdk.internal.misc.Unsafe.park(Native Method)
[15:34:08] [AsyncNotifyKeyedQueue - 1/INFO]: java.base@17.0.1/java.util.concurrent.locks.LockSupport.park(LockSupport.java:341)
[15:34:08] [AsyncNotifyKeyedQueue - 1/INFO]: java.base@17.0.1/java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionNode.block(AbstractQueuedSynchronizer.java:506)
[15:34:08] [AsyncNotifyKeyedQueue - 1/INFO]: java.base@17.0.1/java.util.concurrent.ForkJoinPool.unmanagedBlock(ForkJoinPool.java:3463)
...
```

## 重新載入

這會用最新的設定重新載入外掛。

**用法：**
`/fawe reload`

**Permissions:**
`worldedit.reload`

## Timezone

Change the time zone for the internal time definition of FAWE. This command assists player to measure the time correctly 
to recover the snapshots. The time is used in particular for snapshots, as these are saved and assigned with a time specification.

**Usage:**
`/fawe tz <timezone offset>`

- The default time is [UTC](https://en.wikipedia.org/wiki/Coordinated_Universal_Time). The offset defines the hours that are added / subtracted (e.g. `+1` or `-2`).

**Visual Example:**

![Example 1](../../../../../fastasyncworldedit/commands/administrative/images/timezone.png)

## Debugpaste

Generate and upload basic server information, the last server-log and snapshots from the FAWE configuration to 
https://athion.net/ISPaster/paste for a faster technical support. This information is important for identifying customer 
mistakes or technical problems and replicating bugs.

{% hint style="tip" %}
To minimize the publication of personal data from your players and to exclude dependency problems with other external plugins from the beginning, the final bug test and `/fawe debugpaste` output should be from a test server.
{% endhint %}

**Usage:**
`/fawe debugpaste`

**Permissions:**
`worldedit.debugpaste`

## WorldEditAnywhere

Toggle your bypass for region restrictions.

**Usage:**
`//wea`

**Aliases:**
`//worldeditanywhere`

**Permissions:**
`fawe.admin`

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們致力於翻譯準確性，但請注意自動翻譯可能包含錯誤或不精確之處。原始文件的母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯所產生之任何誤解或曲解負責。