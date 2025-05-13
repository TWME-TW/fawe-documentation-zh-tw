<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "c3d6c017c2cd057dfab72c751b079108",
  "translation_date": "2025-05-13T03:35:16+00:00",
  "source_file": "fastasyncvoxelsniper/Entity-Brushes.md",
  "language_code": "tw"
}
-->
# Entity Brushes

{% hint style="info" %}
這些刷子不會使用 Performers
{% endhint %}

## The Entity Brush
**/b en [EntityType]**：Entity Brush 讓使用者能從安全距離狙擊生成單一或一群（由刷子大小變數決定）實體。（Item, XPOrb, Painting, Arrow, Snowball, Fireball, SmallFireball, ThrownEnderpearl, EyeOfEnderSignal, ThrownExpBottle, PrimedTnt, FallingSand, Minecart, Boat, Creeper, Skeleton, Spider, Giant, Zombie, Slime, Ghast, PigZombie, Enderman, CaveSpider, Silverfish, Blaze, LavaSlime, EnderDragon, WitherBoss, Bat, Witch, Pig, Sheep, Cow, Chicken, Squid, Wolf, MushroomCow, SnowMan, Ozelot, VillagerGolem, Villager, EnderCrystal)。*感謝 xmlns 提供 SpawnMob 的 Mob Class。*

{% hint style="success" %}
輸入 "/b en Sheep" 和 "/b 5" 後，點擊狙擊器會在狙擊點生成 5 隻羊。
{% endhint %}

{% hint style="info" %}
你必須在 Bukkit 啟用你想生成的動物或怪物，才能用 VoxelSniper 創建它。
{% endhint %}

**/b en info**：顯示所有可用實體的完整清單。

## Entity Removal Brush

**/b er**：移除刷子大小區塊範圍內所有實體，除了物品框和畫作。

## The Heat Ray

**/b hr**：Heat Ray Brush 燒毀附近方塊，並將其他方塊改為像是鵝卵石或黑曜石等「燒焦」狀態。試試用它燒毀一個村莊吧！Heat Ray Brush 使用刷子大小變數調整光束寬度。

* **/b hr oct[int]**：噪音產生器的倍頻參數。
* **/b hr amp[float]**：噪音產生器的振幅參數。
* **/b hr freq[float]**：噪音產生器的頻率參數。

## The Lightning Brush
**/b light**：閃電會擊中狙擊的方塊。

## VoxelLightning Mode
**/vs lightning**：啟動 VoxelLightning 模式。每次你拉動狙擊器扳機，點擊的方塊也會被閃電擊中。

{% hint style="info" %}
請注意，正常的狙擊動作會同時執行，若你只想要閃電效果，請使用 lightning brush。
{% endhint %}

## The Meteor Brush
**/b meteor**：向狙擊的方塊發射一個惡魂火球。 
{% hint style="warning" %}
無法復原！此外，防爆炸的反破壞插件可能會削弱此刷子的效果。
{% endhint %}

## The Weather Wizard

**/vs weather**：在接下來幾秒內清除所有雨雪。

## The Warp-in-Style Brush

**/b w**：這個刷子會用箭矢將你傳送到狙擊的方塊，火藥則會在狙擊點產生閃電，驚艷你的朋友！

## The Jockey Brush

**/b jockey** 這個刷子讓你能坐在其他玩家或生物身上。騎著史萊姆，或惹惱你希望他下線的人。胯下＋臉＝超好玩！
* **-i:[y|n]** - 啟用 (y) 或停用 (n) 反向模式。反向模式會讓目標坐在你身上。
* **-po:[y|n]** - 啟用 (y) 或停用 (n) 玩家專用模式。啟用後，只有其他玩家能成為目標。
* **-s:[y|n]** - 啟用 (y) 或停用 (n) 疊加模式。啟用時，會在玩家刷子大小範圍內將所有實體堆疊在玩家身上。

## Three-Point Circle Brush

**缺少圖片**

三點圓刷範例

**/b tpc accurate|default|smooth** - 使用箭矢刷選擇三個點，形成三角形的三個頂點。使用火藥刷讓 VoxelSniper 繪製該三角形的外接圓。可用於任意角度，但某些角度效果較佳。
* **accurate|default|smooth** - 切換此刷子放置方塊的精準度。
    * *accurate* - 僅放置數學上盡可能完美接近的方塊。
    * *default* - 平衡模式，通常相當精準，但在某些奇怪角度可能會有空隙。
    * *smooth* - 會放置所有合理屬於圓的一部分方塊，會讓圓盤較厚。某些極端狀況可能會漏掉少數方塊，但大多數圓形都能涵蓋。

{% hint style="info" %}
僅在版本 5.155 及以上可用。
{% endhint %}

## Move Brush
Move Brush 可將選取區域移動指定方塊數量。（最大 5000000 方塊）
* **/b mv x[#] y[#] z[#]** - 指定選取區移動的數量與方向。（X: 正數向東，Y: 正數向上，Z: 正數向南）
* **/b mv reset** - 將移動數量與方向重設為 0

## Punish Brush

此刷子有專屬權限：**voxelsniper.punish**

Punish Brush 會對刷子大小半徑內的所有人施加特定懲罰。

**/b p [punishment]**

輸入 **/b p info** 可列出所有可用懲罰。

部分懲罰接受額外藥水等級參數，用來定義效果的強度，預設為 10。使用 **/vc [level]** 設定。也可以用 **/vh [duration]** 設定持續秒數。

## Sign Overwrite Brush

Sign Overwrite Brush 會覆寫招牌文字。**/b sio**

箭矢設定一個或多個招牌。火藥工具會讀取目標招牌的文字到內部緩衝區。

可用參數：

* **-1 [...]** - 設定內部緩衝區第一行文字。（例如 /b sio -1 這是文字。）
* **-2 [...]** - 設定內部緩衝區第二行文字。（例如 /b sio -2 這是文字。）
* **-3 [...]** - 設定內部緩衝區第三行文字。（例如 /b sio -3 這是文字。）
* **-4 [...]** - 設定內部緩衝區第四行文字。（例如 /b sio -4 這是文字。）
* **-clear** - 清空內部緩衝區，將所有行設為空字串。（別名：-c）
* **-multiple [on|off]** - 啟用或停用範圍模式。啟用時，會設定一個盒子內所有招牌（x=z=2*brushSize+1，y=2*voxelHeight+1）。請注意招牌每行最大長度為 15。

## Extrude Brush

* **/b ex**：Extrude Brush 會以圓盤面為基底，推拉柱狀區塊。複製高度依據 /vh <height>，圓盤面半徑依 /b #，被推拉的方塊類型依 /vl 設定。用箭矢點擊會向內「推」，用火藥點擊會向外「拉」，相對於點擊的面。
* **/b ex true**：使用真圓盤進行推拉。
* **/b ex false**：關閉真圓盤（預設）。
* **/vl**：決定哪些方塊會被推拉。

{% hint style="info" %}
/b ex /vh 5 /b 10 /vl 1 5 *用火藥左鍵點擊* 這會將半徑 10 方塊內的所有石頭和木頭向外推拉，依點擊面方向。
{% endhint %}

## Snow cone brush
**/b snow**：非常適合製作積雪山頂。此刷子只用火藥點擊雪塊才會生成。

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 所翻譯。雖然我們致力於翻譯的準確性，但請注意自動翻譯可能包含錯誤或不準確之處。原始文件的母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯所引起之任何誤解或誤釋負責。