<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "ad7c40117d6dc839100a64ff09e5a6ae",
  "translation_date": "2025-05-13T03:51:03+00:00",
  "source_file": "fastasyncworldedit/commands/biomes.md",
  "language_code": "tw"
}
-->
# Biomeinfo

顯示目前的生物群系。

- 預設情況下，會列出你區域選取範圍內所有的生物群系（圖1）。

- 如果指定了`-p`標誌，指令會改為顯示你目前所在區塊的生物群系（圖2）。

- 如果指定了`-t`標誌，會顯示你[準心](https://minecraft.wiki/w/File:HUD_example.png)目標方塊的生物群系（圖3）。

在1.16版本之前，生物群系與Y軸無關。從1.16版本開始，生物群系改為以4x4x4的區塊來定義。關於新格式的更多（較技術性的）資訊，可以參考[這裡](https://wiki.vg/Protocol#Chunk_Data)。

## 使用方式

`//biomeinfo [-p] [-t]`

## 權限

`worldedit.biome.info`

## 視覺範例

1.  ![biomeinfo.png](https://i.imgur.com/PxB1JOG.png)

2.  ![biomeinfo-p.png](https://i.imgur.com/I2hD28o.png)

3.  ![biomeinfo-t.png](https://i.imgur.com/R5G8XP9.png)

# Setbiome

設定區域選取範圍內的生物群系。

- 預設情況下，指令會更改你選取範圍內的生物群系（圖1）。

- 使用`-p`可以忽略選取範圍，直接更改你目前位置的生物群系（圖2）。

在1.16版本之前，生物群系與Y軸無關。從1.16版本開始，生物群系改為以4x4x4的區塊來定義。關於新格式的更多（較技術性的）資訊，可以參考[這裡](https://wiki.vg/Protocol#Chunk_Data)。

## 使用方式

`//setbiome <biome> [-p]`

## 權限

`worldedit.biome.set`

## 視覺範例

1.  ![setbiome.png](https://i.imgur.com/ut2Im7O.png)

2.  ![setbiome-p.png](https://i.imgur.com/MxdpUFK.png)

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們致力於提供準確的翻譯，但請注意自動翻譯可能包含錯誤或不準確之處。原始文件的母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們對於因使用本翻譯而產生的任何誤解或誤譯不負任何責任。