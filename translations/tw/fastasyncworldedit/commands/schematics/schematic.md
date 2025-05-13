<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "f4540e489fa87ed30fc29e6c051528e4",
  "translation_date": "2025-05-13T03:55:48+00:00",
  "source_file": "fastasyncworldedit/commands/schematics/schematic.md",
  "language_code": "tw"
}
-->
# Schematic Commands

FAWE 允許你複製已建造的結構並將其儲存為獨立檔案，方便轉移到其他電腦／世界／伺服器，或在其他外部網路平台提供下載。預設的檔案格式為 WorldEdit 和 FAWE 使用的「Schematic-Format」（.schem）。

## Schematic

這是管理結構檔的主要指令。

**用法：** `//schematic ...`

**別名：**  
`//schem`

## Schematic List

此指令會列出你的結構檔及結構資料夾。

**用法：** `//schematic list [-dn] [-p <page>] [-f <formatName>] [filter or directory]`

- 你可以依建立日期排序結構檔清單：使用 `-n` 參數會從最新的結構開始列出，使用 `-d` 則從最舊的開始。
- 使用可選的 `-p` 參數加上頁碼，可以切換清單頁面。
- 使用 `-f` 可以依目標結構檔格式過濾結果。
- 可使用搜尋字串（`filter`）來搜尋特定名稱（包含副檔名）的檔案或資料夾，搜尋不區分大小寫。或者，也可以透過指定 `directory`（例如 `//schematic list Houses/`）來列出目標資料夾下的所有內容。

**權限：** `worldedit.schematic.list`

**視覺範例：**

![Example 1](../../../../../fastasyncworldedit/commands/schematics/images/schematic-list.png)

## Schematic Move

此指令可用來將[已載入的結構](../../../../../fastasyncworldedit/commands/schematics)移動到指定的資料夾。

**用法：** `//schematic move <directory>`

- 使用 `directory` 參數指定目標資料夾。路徑結構由個人主資料夾開始，接著是檔案分隔符（依作業系統而異）、子資料夾，依此類推。

**權限：** `worldedit.schematic.move` & `worldedit.schematic.move.other`

**視覺範例：**

![Example 1](../../../../../fastasyncworldedit/commands/schematics/images/schematic-list.png)

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 所翻譯。雖然我們努力追求準確性，但請注意，自動翻譯可能包含錯誤或不準確之處。原始文件之母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯而產生之任何誤解或誤釋負責。