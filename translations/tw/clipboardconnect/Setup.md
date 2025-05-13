<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "e0a849a5537ae2fa54334cbb7667264d",
  "translation_date": "2025-05-13T03:33:46+00:00",
  "source_file": "clipboardconnect/Setup.md",
  "language_code": "tw"
}
-->
# Clipboard Connect 搭配 Redis 在 Docker 上的完整設定指南
## 介紹
本指南詳細說明如何為 Minecraft 的 Clipboard Connect 外掛搭配 Redis 進行設定。提供多種設定選項，推薦使用 Docker Compose 的自動化設定流程。

## 目錄
- [先決條件](../../../clipboardconnect)
- [Redis 設定選項](../../../clipboardconnect)
    - [選項 B：自動化 Docker Compose 設定（推薦）](../../../clipboardconnect)
    - [選項 A：手動 Docker Compose 設定](../../../clipboardconnect)
    - [選項 C：將 Redis 當作系統套件安裝](../../../clipboardconnect)
- [設定 Clipboard Connect](../../../clipboardconnect)
- [驗證設定](../../../clipboardconnect)
- [結論](../../../clipboardconnect)

## 先決條件
- 伺服器已安裝 Docker 與 Docker Compose（適用於 Docker 選項）。[Docker 安裝指南](https://docs.docker.com/get-docker/) | [Docker Compose 安裝指南](https://docs.docker.com/compose/install/)
- 能使用終端機並擁有安裝系統套件的權限（適用於系統套件選項）。
- Paper 伺服器版本 1.20 或以上。
- Minecraft 伺服器已安裝 WorldEdit 外掛。

## Redis 設定選項

### 選項 B：自動化 Docker Compose 設定（推薦）
此選項使用 Clipboard Connect 的設定指令，自動產生 `docker-compose.yml` 檔案並配置 Redis，簡化設定流程。

#### B.1 執行設定指令
在遊戲內使用 `/clipboardconnect setup` 指令，依照螢幕上的指示自動產生 Docker Compose 檔案並啟動 Redis。

### 選項 A：手動 Docker Compose 設定
適合偏好手動設定的使用者，透過 Docker Compose 建立並設定 Redis。

#### A.1 建立 Redis Docker 容器
建立一個 `docker-compose.yml` 檔案，內容如下：

```yaml
version: '3'
services:
  redis:
    image: redis:latest
    restart: always
    ports:
      - "6379:6379"
    volumes:
      - redis-data:/data

volumes:
  redis-data:
```

#### A.2 啟動 Redis
在 `docker-compose.yml` 檔案所在目錄執行 `docker-compose up -d`。

### 選項 C：將 Redis 當作系統套件安裝
或者，直接使用系統的套件管理工具安裝 Redis。

#### C.1 安裝 Redis
以 Ubuntu 為例，使用：

```bash
sudo apt-get update
sudo apt-get install redis-server
```

#### C.2 設定 Redis
確保 Redis 設定為開機自動啟動，並依需求調整設定。

## 設定 Clipboard Connect
完成 Redis 設定後，配置 Clipboard Connect 使用此 Redis 實例。在遊戲內使用 `/clipboardconnect setup` 指令。

## 驗證設定
測試儲存與載入剪貼簿，確認與 Redis 連線成功且功能正常。

## 結論
你的 Clipboard Connect 現已搭配 Redis 運行，提供穩定的剪貼簿同步方案。請持續更新 Docker 映像檔、系統套件與 Clipboard Connect 外掛。

**免責聲明**：  
本文件係使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 所翻譯。雖然我們致力於確保準確性，但請注意，自動翻譯可能包含錯誤或不準確之處。原始文件之母語版本應視為權威資料來源。對於重要資訊，建議採用專業人工翻譯。我們不對因使用本翻譯而產生之任何誤解或誤譯負責。