# 項目介紹

本參考文檔提供了一個用於監控和維護阿里雲 Redis 連接狀態的 C 語言項目說明。該項目主要應對由於阿里雲 Redis 連接重置所引發的 Celery 運行異常問題。通過定期檢查 Redis 連接狀態，當連接失效時，系統會自動通過郵箱和短信通知管理者；當連接恢復後，系統則會自動向 Docker Swarm 發起服務重啟指令，以確保系統服務的穩定運行。

本項目依賴於以下庫：
- **fonttools**：提供字體處理的基本功能。

## Command

語法：

```shell
python main.py --input-file 用到的字.txt --output-dir output --font-file fonts/font.woff2 --generate-css
```

## Options

描述各命令行選項的用途：

-c, --config
: 指定配置文件的位置。該配置文件中包含 Redis 連接信息、通知設置（如郵箱與短信配置）以及 Docker Swarm 重啟服務所需的相關參數。
