<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "2191b8d058641a17511c92082347aa2a",
  "translation_date": "2025-05-13T03:33:29+00:00",
  "source_file": "clipboardconnect/Commands.md",
  "language_code": "tw"
}
-->
# 這些是 Clipboard Connect 指令
## Clipboard Connect 指令

---
### 載入剪貼簿

此指令會從 redis 載入剪貼簿

**用法:** `/clipboardconnect load`

**別名:** 
- `/gload`

**權限:**
- `clipboardconnect.command.load`

---
### 儲存剪貼簿

此指令會將剪貼簿儲存到 redis

**用法:** `/clipboardconnect save`

**別名:**
- `/gsave`

**權限:**
- `clipboardconnect.command.save`

---
### 設定流程

此指令會啟動設定流程

**用法:** `/clipboardconnect setup`

**別名:** 無

**權限:**
- `clipboardconnect.command.setup`

---

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 所翻譯。雖然我們致力於提供準確的翻譯，但請注意，自動翻譯可能會包含錯誤或不準確之處。原始文件的母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯所引起的任何誤解或誤譯負責。