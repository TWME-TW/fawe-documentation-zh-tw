<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "ac52be161da279f18dc9e32c235f10a2",
  "translation_date": "2025-05-13T03:57:42+00:00",
  "source_file": "plotsquared/configuration/storage.md",
  "language_code": "tw"
}
-->
# 儲存設定

## 介紹

這是 PlotSquared 的主要資料庫設定檔。

*位於：* `/plugins/PlotSquared/config/storage.yml`  
如果你使用 SQLite，`storage.db` 位於 `/plugins/PlotSquared/storage.db`

## 預設

```yaml
prefix: ''

# SQLite section
sqlite:
  # Should SQLite be used?
  use: true
  # The file to use
  db: "storage"

# MySQL section
mysql:
  # Should MySQL be used?
  use: false
  host: "localhost"
  port: "3306"
  user: "root"
  password: "password"
  database: "plot_db"
  # Set additional properties: https://dev.mysql.com/doc/connector-j/en/connector-j-reference-configuration-properties.html
  properties:
    - "useSSL=false"
```

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們致力於翻譯的準確性，但請注意自動翻譯可能會包含錯誤或不準確之處。原始文件之母語版本應視為權威來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯所產生之任何誤解或誤譯負責。