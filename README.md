# ChinaPulse API & MCP Server

Clean, deduplicated, **English-translated Chinese Tech, Finance, Open-Source & Trending Intelligence API** with **AI Sentiment Scoring (`bullish` / `neutral` / `bearish`, `-1.0` to `+1.0`)** and native **Model Context Protocol (MCP)** support.

Built for AI Agents (**Cursor, Claude, Windsurf, Dify, n8n**) and global developers who need reliable, low-token Chinese public market & tech intelligence.

- **Live Demo & Console**: https://pulse.cnpulse.cn
- **RapidAPI Marketplace**: https://rapidapi.com/liyangxiao/api/chinapulse-bilingual-china-tech-finance-sentiment-api
- **Interactive OpenAPI Docs**: https://pulse.cnpulse.cn/docs

## Key Features

- **6 High-Signal Chinese Public Sources** (auto-refreshed every 15 minutes):
  - **Finance**: WallstreetCN 7x24, EastMoney Flash
  - **Tech**: ITHome, SSPai
  - **Dev**: OSChina
  - **Trending**: Baidu Realtime Hot
- **AI Bilingual & Sentiment Pipeline**:
  - Automatic idiomatic English headlines (`title_en`) and crisp 1-sentence summaries (`summary_en`)
  - Market & tech sentiment classification (`bullish` / `neutral` / `bearish`) + numeric `sentiment_score` (`-1.0` to `+1.0`)
  - Low-token Markdown output (`?format=markdown`)
- **Dual Protocol**:
  - REST API (`/v1/pulse`, `/v1/search`, `/v1/digest`, `/v1/sources`, `/v1/usage`) with `lang=both|en|zh` and `sentiment` filters
  - Native Streamable HTTP **MCP Server** at `POST /mcp` (`get_china_pulse`, `search_china_pulse`, `get_daily_digest`, `list_pulse_sources`)

## Quick Start (MCP Server)

Add this to **Cursor**, **Claude Desktop**, or any MCP-compatible AI Agent using the public demo key (`200 req/day`):

```json
{
  "mcpServers": {
    "chinapulse": {
      "url": "https://pulse.cnpulse.cn/mcp",
      "headers": {
        "X-API-Key": "cp_demo_public_readonly"
      }
    }
  }
}
```

## Quick Start (REST API)

```bash
curl -H "X-API-Key: cp_demo_public_readonly" \
  "https://pulse.cnpulse.cn/v1/pulse?category=finance&lang=both&limit=5"
```

Need higher quotas? Subscribe on [RapidAPI](https://rapidapi.com/liyangxiao/api/chinapulse-bilingual-china-tech-finance-sentiment-api).
