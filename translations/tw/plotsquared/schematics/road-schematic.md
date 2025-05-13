<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "bed3c5daa5ee621b48c6d6b92a4b8af4",
  "translation_date": "2025-05-13T04:06:50+00:00",
  "source_file": "plotsquared/schematics/road-schematic.md",
  "language_code": "tw"
}
-->
# Plotworld 道路示意圖

## 介紹

PlotSquared 允許使用預設的示意圖來自訂 **地塊間的道路**。

{% hint style="tip" %}
道路示意圖只會影響 plotworld 的道路，不會影響地塊本身。關於如何設定地塊示意圖，請參考文章 [Plot Schematic on Generation](../schematics/schematic-generation.md) 和 [Plot Schematic on Claim](../schematics/schematic-on-claim.md)。
{% endhint %}

{% hint style="info" %}
道路示意圖可以在世界生成後新增。你可以隨時更換道路示意圖，但這只會影響 [新生成的區域](../../../../plotsquared/schematics)，不會改變先前已生成的區域。
{% endhint %}

## 設定

### 1. 道路示意圖建造

首先，你要建造一條圍繞地塊的道路。道路包含牆壁、地塊邊界以及整個路口。因此，你也需要建造路口部分，我們建議往前延伸 3 或 4 格。

PlotSquared 在建立道路時只會考慮道路的兩側，因為你可能也已經注意到，圍繞方形地塊的道路本身也是方形的。數學上只要知道一邊的尺寸就能建出正方形，但 PlotSquared 會考慮最多兩側，讓你可以使用兩種不同的圖案。

{% hint style="info" %}
目前，示意圖需要對稱的邊界建造，否則會導致建造錯誤。
{% endhint %}

以下是你需要建造的道路示意圖部分預覽。粉紅色部分只是建議，但過去經驗顯示，在建立道路示意圖前先加上這些部分會比較好：

![Road schematic](https://i.imgur.com/ISPEJPC.png)

### 2. 儲存示意圖

建立完道路後，站在地塊內並執行以下指令：

`/plot createroadschematic`

道路示意圖會儲存在 `plugins/PlotSquared/schematics/GEN_ROAD_SCHEMATIC/<worldname>`。建立完示意圖後，可以將它 **複製** 到此目錄下的新 `worldname` 資料夾，以便用於新世界的生成。

### 3. 測試

建議測試示意圖，站在另一個沒有用來建立示意圖的地塊內，執行以下指令會重新生成你所在地塊的道路：

`/plot debugroadregen plot`

### 4. 世界重生

#### 透過指令

如果一切正常，你可以開始重生整張地圖的道路。打開主控台並執行以下指令（這可能會花一點時間並造成卡頓）：

`/plot regenallroads <world> [height]`

height 選項（若有指定）會改變示意圖上方要貼上的空氣層數量。

#### 透過世界重置

**另一種方式：** 停止伺服器並刪除世界區塊檔案。重新啟動後，新生成的區塊會依照你的 plotworld 設定生成。

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們力求準確，但請注意，自動翻譯可能包含錯誤或不準確之處。原始文件之母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯所產生之任何誤解或誤譯負責。