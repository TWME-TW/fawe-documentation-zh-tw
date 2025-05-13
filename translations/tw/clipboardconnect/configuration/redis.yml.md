<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "15198987988d3e67589242d5bb8af088",
  "translation_date": "2025-05-13T03:48:37+00:00",
  "source_file": "clipboardconnect/configuration/redis.yml.md",
  "language_code": "tw"
}
-->
# redis.yml

## 介紹

這是 ClipboardConnect 的 redis 連線設定檔。

*位置於:* `/plugins/ClipboardConnect/redis.yml`

## 預設設定

參考：https://github.com/redisson/redisson/wiki/2.-Configuration#23-common-settings
```yaml
singleServerConfig:
  address: "redis://127.0.0.1:6379"
```

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們致力於確保準確性，但請注意，自動翻譯可能包含錯誤或不準確之處。原始文件之母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯所產生之任何誤解或誤譯負責。