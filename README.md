# Serenity Radar

> 半导体/AI 基础设施投研 RSS 监控管线。基于 [TrendRadar](https://github.com/sansan0/TrendRadar) 配置。

自动抓取金融/半导体 RSS 源 → 关键词过滤 → DeepSeek AI 分析 → Telegram 推送。

## 数据源

### X/Twitter（通过 Nitter RSS 桥接）

| 账号 | 覆盖领域 |
|------|------|
| jukan05 | 存储/韩国半导体/供应链 |
| Serenity (aleabitoreddit) | 光互联/产业生态/宏观 |
| Labubu (labubu_trader) | 市场结构/操作节奏 |
| qinbafrank | AI/TMT·半导体设备/材料 |
| Corsica267 | 宏观·真实利率/美元 |
| dubidubabap | 数据中心/云 |
| TrendForce | 行业数据/供应链 |
| zephyr_z9 | 内存/DRAM |

> NuttyCLD、Kay2289123 已移除——长文深度分析不适合 RSS 片段，改手动关注。

### 金融/半导体 RSS

| 源 | 说明 |
|------|------|
| Yahoo Finance | 综合财经新闻 |
| Seeking Alpha | 投资分析 |
| Semiconductor Today | 半导体行业新闻 |

## 工作流

```
RSS 抓取 → 关键词过滤 → DeepSeek AI 分析 → Telegram 推送
   ↑            ↑              ↑                ↑
  早晚各一次   17组关键词     Bullish/Bearish   早晚推送
```

## 配置

- `config/config.yaml` — 主配置
- `config/frequency_words.txt` — 关键词
- `config/ai_analysis_prompt.txt` — AI 分析提示词

## 部署

GitHub Actions 免费运行。Secrets 配置（Settings → Secrets and variables → Actions）：

| Secret | 说明 |
|--------|------|
| `TELEGRAM_BOT_TOKEN` | Telegram Bot Token |
| `TELEGRAM_CHAT_ID` | Telegram Chat ID |
| `AI_API_KEY` | DeepSeek API Key |

## 许可

基于 TrendRadar (GPL-3.0)。本项目仅为个人配置实例。
