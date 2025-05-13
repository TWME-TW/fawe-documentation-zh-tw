<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "bb5bf7de972595be4a4a364523521991",
  "translation_date": "2025-05-13T03:34:20+00:00",
  "source_file": "fastasyncvoxelsniper/Commands.md",
  "language_code": "tw"
}
-->
# 這些是 Voxel Sniper 指令
## VoxelSniper 預設指令

---
### 重置你的筆刷

這個指令用來重置你的筆刷設定

![img.png](../../../fastasyncvoxelsniper/images/Commands/brushReset.png)

**用法:** `/d`

**別名:** 無

**權限:**

主要:

{% hint style="info" %}
當你剛開始使用 VoxelSniper 時，養成每次工作後都重置筆刷的習慣，尤其是進行大量地形修改時，一次點擊可能會造成很大的清理困擾。{% endhint %}

---

### VoxelSniper 設定

這個指令會列印出 VoxelSniper 目前所有設定，讓你在執行前先檢查。

![img.png](../../../fastasyncvoxelsniper/images/Commands/vs.png)

**用法:** `/vs`

**別名:** `[voxelsniper,favs,fastasyncvoxelsniper]`

**權限:**

主要:

{% hint style="info" %}
替換和墨水資訊只會在適用的筆刷上顯示。如果你看不到，請確認你使用的是正確的筆刷！ /vs brushes 筆刷清單。這個指令會回傳所有 VoxelSniper 的筆刷選項。
{% endhint %}

---

### **vs brusheslong**

筆刷全名清單。這個指令會列出筆刷的全名版本。

![img.png](../../../fastasyncvoxelsniper/images/Commands/brushesLong.png)

**用法:** `/vs brusheslong`

**別名:** `[voxelsniper brusheslong, fastasyncvoxelsniper brusheslong]`

**權限:**

---

### **vs brushes**

筆刷縮寫清單。這個指令會列出筆刷的縮寫版本。

![img.png](../../../fastasyncvoxelsniper/images/Commands/brushesAbbreviated.png)

**用法:** `/vs brushes`

**別名:** `[voxelsniper brushes, fastasyncvoxelsniper brushes]`

**權限:**

主要:

---

### **vs perf**

表演者清單。這個指令會回傳所有 VoxelSniper 表演者的縮寫名稱。

![img.png](../../../fastasyncvoxelsniper/images/Commands/perfAbbreviated.png)

**用法:** `/vs perf`

**別名:** `[voxelsniper perf, fastasyncvoxelsniper perf]`

**權限:**

主要:

---

### **vs perflong**

表演者全名清單。這個指令會列出表演者的全名版本。

![img.png](../../../fastasyncvoxelsniper/images/Commands/perfLong.png)

**用法:** `/vs perflong`

**別名:** `[voxelsniper perflong, fastasyncvoxelsniper perflong]`

**權限:**

主要:

## 筆刷

---

### **/b [指令]**

筆刷指令是進入 VoxelSniper 世界編輯奇蹟的入口。這個指令可以很簡單地改變目前使用的筆刷類型、大小，或是發出一連串指令（像是侵蝕筆刷的設定）。許多筆刷會根據你設定的 Sniper 筆刷參數有截然不同的行為，因此在執行前務必清楚你正在使用哪些變數！

![img.png](../../../fastasyncvoxelsniper/images/Commands/brush.png)

**用法:** `/b [instructions]`

**別名:** 無

**權限:**

主要:

{% hint style="info" %}
每個筆刷都有自己的遊戲內說明！要取得，只要向 VoxelSniper 詢問該筆刷的 "info" 即可。
{% endhint %}

{% hint style="success" %}
`/b b info` - 會給你 Ball Brush 的資訊。
{% endhint %}

{% hint style="info" %}
你喜愛的筆刷名稱可能已從 VS4 改變到 VS5，請務必閱讀下方的表演者章節。
{% endhint %}

---

## 表演者

你可以使用 **/v m** 來設定筆刷的表演者。m 是你想用在筆刷上的方塊或圖案的佔位符。
以下是範例：

![img.png](../../../fastasyncvoxelsniper/images/Commands/performerExample.png)

**別名:**

**權限:**

{% hint style="warning" %}
這部分的文件可能已過時或目前不完全適用！
{% endhint %}

{% hint style="info" %}
一般的球形筆刷是 **/b b m**（m 代表材質）
{% endhint %}

{% hint style="success" %}
墨水球筆刷是 **/b b i**（i 代表墨水）
{% endhint %}

{% hint style="info" %}
有些筆刷，例如侵蝕筆刷或怪物筆刷，並不使用表演者，因為這樣不會增強它們的功能。
{% endhint %}

* 要用泥土球替換石頭球，使用 `/b b mm`
    * 第一個 m 表示你只放置材質，就像圓盤範例一樣。跟之前一樣，你需要 `/v dirt`。第二個 m 表示你只替換材質，同理你需要 `/vr stone`。
* 要用紅木原木球替換石頭球，使用 `/b b cm`
    * c 表示你放置的是材質 (`/v log`) 和資料 (`/vi 1`)，m 表示你只替換材質 (`/vr stone`)。
* 要將一組有資料值 2 的鵝卵石樓梯和木樓梯旋轉成資料值 3（面向不同方向），且不影響旁邊資料值為 10 的布料，使用 `/b b ii`
    * 第一個 i 表示你放置資料 (`/vi 3`)，第二個 i 表示你只替換特定墨水 (`/vir 2`)。
* 要在靜止水塊中狙擊，使用 `/b s mp`
    * m 表示你放置材質 (`/v 9`)，p 表示侵蝕時不會觸發物理效果。這個參數可以想成是整體「筆刷強度」的一半。
* `rf[#]` - 筆刷執行填充的遞迴次數。

{% hint style="info" %}
遞迴次數建議從小開始，必要時再逐步增加！在不同位置使用較弱的筆刷反覆狙擊，效果通常比少量位置使用強力筆刷更好！
{% endhint %}

* `b[#]` - 筆刷大小（例如：b23）

{% hint style="info" %}
侵蝕筆刷的理想大小通常介於 8-20 之間。較大的筆刷使用起來較笨重且常常產生不想要的結果。  
{% endhint %}

---

## 指令集結構解析

我們來看看侵蝕筆刷「melt」預設的指令是怎麼達成效果的。預設指令如下：

`/b e e2 f5 re1 rf1 b10.`

**別名:** 無

**權限:**

* **e2** - 筆刷會侵蝕有 2 個以上暴露面的方塊。這代表只有深埋在地形裡的方塊會被侵蝕，讓地形呈現我們想要的「枯萎」效果。
* **f5** - 只有當被侵蝕的區域產生一個有 5 個被覆蓋面的空間時，才會生成新方塊。這樣可以讓地形在融化過程中更平滑。
* **re1** - 這是侵蝕筆刷的強度參數。melt 筆刷在指定區域內執行一次侵蝕。
* **ref** - 這是填充筆刷的強度參數。melt 筆刷在指定區域內執行一次填充。

{% hint style="info" %}
注意 melt 筆刷只用 *一次* 遞迴就能產生強大效果！
{% endhint %}

---

## 隨機侵蝕筆刷

一般侵蝕筆刷的缺點是，反覆使用時區域會變得過度平滑。地形看起來像融化的蠟而非泥土和石頭。這個隨機版本能產生類似效果，但不會產生這些非自然的特徵。
每次點擊時，四個侵蝕參數會隨機變化。此筆刷也較容易使用，因為它使用標準筆刷大小變數。

用法: `/b re`

**別名:**

**權限:**

{% hint style="info" %}
使用 **箭頭工具** 版本的筆刷偏向侵蝕，而 **火藥工具** 版本偏向填充。
{% endhint %}

**箭頭工具範例：**
![img.png](../../../fastasyncvoxelsniper/images/Commands/randomErodeArrow.png)

**火藥工具範例：**
![img.png](../../../fastasyncvoxelsniper/images/Commands/randomErodeGunpowder.png)
---

## 覆蓋層 / 表土筆刷

覆蓋層筆刷會在現有地形上塗層。

![img.png](../../../fastasyncvoxelsniper/images/Commands/bOverlay.png)

用法: `/b over d[#]:`  
覆蓋層筆刷會將區域內最上層的方塊「噴塗」成你用 "/v" 指令設定的方塊類型。這可以用來輕鬆清理侵蝕筆刷後露出的材料，或是創造新的填充材料將兩塊地形連接起來。

用法: `/b over info:`

![img.png](../../../fastasyncvoxelsniper/images/Commands/overlayInfo.png)

**別名:** 

**權限:**

{% hint style="info" %}
預設情況下，這支筆刷只會塗覆「自然」材料（石頭、泥土、礫石、草、樹木、礦石等）。
{% endhint %}

覆蓋層筆刷的作用範圍由筆刷大小變數決定。
使用此筆刷時，箭頭工具會將塗層「噴灑」到區域內最頂層的方塊。

**/b over all** 會設定筆刷對所有材料類型進行塗覆。
你可以用 **/b over some** 回到「自然」模式，覆蓋層筆刷會只噴灑在這些材料附近。

{% hint style="success" %}
**/b over d5 + /v 12 + /b 20 + /b over all** 將成為一支強力的「沙漠製造者」筆刷，使用箭頭工具時能摧毀沿途的任何結構。
{% endhint %}

---

## 飛濺覆蓋筆刷

這支筆刷結合了飛濺筆刷和覆蓋筆刷的功能。

![img.png](../../../fastasyncvoxelsniper/images/Commands/splatterOverlay.png)

用法:  `/b sover s[#] g[#] r[#]`

**別名:**

**權限:**

{% hint style="info" %} 透過 /b sover info 看到的內容： {% endhint %}

![img.png](../../../fastasyncvoxelsniper/images/Commands/splatterOverlayInfo.png)

`/v` Voxel Select 值用來像覆蓋筆刷一樣塗覆，並使用飛濺的種子 (s)、生長 (g) 和遞迴 (r) 參數。

---

## 底層筆刷

底層筆刷基本上是覆蓋筆刷的相反，會依據你的 **/v** 指令塗覆洞穴和建築物的天花板。 (d) 變數決定筆刷的深度，也就是你想讓筆刷穿透的高度。

![img.png](../../../fastasyncvoxelsniper/images/Commands/underlayInfo.png)

用法:  `/b under d[#]`

**別名:** 

**權限:**

---

## 混合筆刷

這組筆刷讓狙擊手能清理不同材料之間參差不齊的邊界。
筆刷會查看作用範圍內每個方塊的鄰近方塊，找出最常出現的鄰近材料。
如果能找到一個最常見的鄰近材料（不含平手情況），該方塊會被改成更符合周圍方塊的材料。

使用者可以選擇是否包含空氣在搜尋中：

使用 **箭頭工具** 時包含空氣，因此反覆使用這些筆刷的效果類似侵蝕筆刷的融化和平滑預設。

反之，排除空氣（使用 **火藥工具**）會讓混合筆刷的效果更像侵蝕筆刷的填充預設。

此外，水也可以選擇包含或排除（預設為排除）。

混合筆刷使用標準筆刷大小和多種可用大小的形狀：

![img.png](../../../fastasyncvoxelsniper/images/Commands/blendBall.png)

**用法:**
* `/b bd`: 混合圓盤
* `/b bb`: 混合球體
* `/b bvd`: 混合體素圓盤
* `/b bv`: 混合體素
* `/b bb water`: 混合球體，切換是否排除水

**別名:**

**權限:**

---

## 排水筆刷

排水筆刷會移除球狀範圍內的所有液體（水或熔岩），使用標準筆刷大小變數。

![img.png](../../../fastasyncvoxelsniper/images/Commands/drain.png)

用法: `/b drain`

* */b drain d*: 切換筆刷形狀為圓盤。
* */b drain true|false*: 使用真球體演算法或一般演算法。

**別名:**

**權限:**

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們致力於翻譯的準確性，但請注意自動翻譯可能包含錯誤或不準確之處。原始文件的母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯而產生的任何誤解或誤譯負責。