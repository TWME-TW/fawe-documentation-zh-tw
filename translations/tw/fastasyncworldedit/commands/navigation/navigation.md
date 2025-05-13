<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "c5089368ba22e3a5d1b8f99813b22432",
  "translation_date": "2025-05-13T03:55:27+00:00",
  "source_file": "fastasyncworldedit/commands/navigation/navigation.md",
  "language_code": "tw"
}
-->
# 導航指令

## Jumpto

使用這個指令可以瞬間傳送到指定位置。

為了避免卡住，你會被傳送到垂直方向上下一個實心方塊的上方，並且有兩個空氣方塊的高度可供站立。

**用法：**
`//jumpto [-f] [<world>,<x>,<y>,<z>]`

- 預設目標位置是你正在看的[準心](https://minecraft.wiki/w/File:HUD_example.png)。
- 另外，你也可以用`<world>,<x>,<y>,<z>`來定義目標位置。

**別名：**
`//j`

**權限：**
`worldedit.navigation.jumpto.command`

**示意圖：**

![Example 1](../../../../../fastasyncworldedit/commands/navigation/images/jumpto-topblock.png)

## Unstuck

使用這個指令可以讓你從卡在方塊裡的狀態脫困。

和`//jumpto`類似，你會被傳送到垂直方向上最近的實心方塊上方，且該方塊上方有兩個空氣方塊。

**用法：**
`//unstuck`

**權限：**
`worldedit.navigation.unstuck`

## Thru

使用這個指令可以讓你穿過你準心方向的牆壁。

使用此指令時，你必須站在牆壁前方。最大傳送距離為6格，因此牆壁最多可有5格厚。

**用法：**
`//thru`

**權限：**
`worldedit.navigation.thru.command`

**示意圖：**

![Example 1](../../../../../fastasyncworldedit/commands/navigation/images/thru.png)

## Ascend

使用這個指令可以讓你向上傳送指定層數。

你會被傳送到垂直方向上下一個實心方塊的上方，該方塊上方有兩個空氣方塊可供站立。樓層間距不影響傳送。

**用法：**
`//ascend [levels]`

- 使用`levels`參數來指定向上傳送的樓層數，若未指定，`level`預設為「1」。

**權限：**
`worldedit.navigation.ascend`

**示意圖：**

![Example 1](../../../../../fastasyncworldedit/commands/navigation/images/ascend.png)

## Descend

使用這個指令可以讓你向下傳送指定層數。

你會被傳送到垂直方向上下個實心方塊的上方，該方塊上方有兩個空氣方塊可供站立。樓層間距不影響傳送。

**用法：**
`//descend [levels]`

- 使用`levels`參數來指定向下傳送的樓層數，若未指定，`level`預設為「1」。

**權限：**
`worldedit.navigation.descend`

**示意圖：**

![Example 1](../../../../../fastasyncworldedit/commands/navigation/images/descend.png)

## Up

使用這個指令可以讓你向上傳送指定的`distance`距離。

**用法：**
`//up [-fg] <distance>`

- 預設情況下，你會站在一個玻璃方塊上以保持穩定。

**權限：**
`worldedit.navigation.up`

**示意圖：**

![Example 1](../../../../../fastasyncworldedit/commands/navigation/images/up.png)

## Ceil

使用這個指令可以讓你傳送到你頭頂上最近的天花板下方。

**用法：**
`//ceil [-fg] [clearance]`

- 預設情況下，你會站在一個玻璃方塊上以保持穩定。
- 使用`clearance`選項可以指定你頭部與天花板間的距離，預設為0，表示頭頂沒有空隙。

**權限：**
`worldedit.navigation.ceiling`

**示意圖：**

![Example 1](../../../../../fastasyncworldedit/commands/navigation/images/ceil.png)

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 所翻譯。雖然我們致力於準確性，但請注意自動翻譯可能包含錯誤或不準確之處。原始文件之母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯所產生之任何誤解或誤譯負責。