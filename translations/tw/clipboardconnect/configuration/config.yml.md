<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "c391d9691d00708cb5aa224da2e09b57",
  "translation_date": "2025-05-13T03:48:30+00:00",
  "source_file": "clipboardconnect/configuration/config.yml.md",
  "language_code": "tw"
}
-->
# config.yml

## 介紹

這是 ClipboardConnect 的主要設定檔。

*位置在：* `/plugins/ClipboardConnect/config.yml`

## 預設值

```yaml
# The Server Message to announce to other servers
servername: 'Server-A'
# The duration how long the redis will keep a clipboard inside of the memory 
# Examples:
# 6h = 6 Hours
# 1d = 24h
# 7d = 7 Days
# 14d = 2 Weeks
duration: '6h'
```

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們力求準確，但請注意，自動翻譯可能會包含錯誤或不準確之處。原始文件的母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯而產生的任何誤解或誤釋負責。