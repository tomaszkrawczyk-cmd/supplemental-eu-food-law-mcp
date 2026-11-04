# Supplemental EU Food Law MCP Server

Remote MCP server from [supplemental.pl](https://supplemental.pl) — an EU and Polish food-law reference for food supplement businesses. It lets AI assistants search supplemental.pl knowledge articles and check official EU registers (health claims, Novel Food Catalogue), Polish GIS notification steps and nutrition declarations.

- **Read-only**: all tools only read data; nothing is created or changed.
- **Not legal advice**: results are reference information. Verify against the official sources and consult a qualified adviser.
- **No prices**: there is no paid plan and no pricing.

This repository contains documentation only; the server is hosted by supplemental.pl.

## Endpoint

| | |
|---|---|
| URL | `https://mcp.supplemental.pl/mcp` |
| Transport | Streamable HTTP |
| Authentication | None |

## Configuration

```json
{
  "mcpServers": {
    "supplemental-eu-food-law": {
      "type": "streamable_http",
      "url": "https://mcp.supplemental.pl/mcp"
    }
  }
}
```

URL-only variant (for clients that detect the transport):

```json
{
  "mcpServers": {
    "supplemental-eu-food-law": {
      "url": "https://mcp.supplemental.pl/mcp"
    }
  }
}
```

## Tools

| Tool | Title | Description |
|---|---|---|
| `search_articles` | Search supplemental.pl knowledge articles | Full-text search of articles on EU/PL food law (health claims, novel food, supplements, labelling, CJEU case law) in Polish, English or German. |
| `get_article` | Get a supplemental.pl article | One article by URL or slug: summary, headings, excerpt, legal references and PL/EN/DE versions. |
| `check_health_claim` | Check the EU Register of health claims | Look up a nutrient/substance in the EU Register of nutrition and health claims: status, conditions of use, EFSA question and legal act. |
| `novel_food_status` | Check the EU Novel Food Catalogue | Look up a food or ingredient in the EU Novel Food Catalogue: status per part/form, with links to Reg. 2015/2283 and the Union list. |
| `search_claims_foodlaw` | Match health claims with C.L.A.I.M.S. | Match an ingredient (and optional dose) against Reg. 432/2012 authorised claims and the SANCO/11074/2013 botanical list (botanicals are always "on_hold"). |
| `get_claim_foodlaw` | Get a C.L.A.I.M.S. claim by ID | Fetch one C.L.A.I.M.S. claim by its numeric ID from `search_claims_foodlaw`. |
| `gis_notification_steps` | Polish GIS notification of a food supplement — steps | Step-by-step procedure for notifying a food supplement to the Polish Chief Sanitary Inspectorate (GIS). |
| `nutrition_calc` | Calculate a nutrition declaration (Nutrimetr) | Deterministic nutrition calculation for a recipe: per-100 g values, %NRV, candidate nutrition claims, allergens and QUID hints. |

## Data sources

- European Commission: EU Register of nutrition and health claims and the EU Novel Food Catalogue (refreshed weekly).
- supplemental.pl knowledge articles.
- C.L.A.I.M.S. (FOODLAW.ai) for claim matching.

Data from the European Commission registers is reused under CC BY 4.0, with attribution to the European Commission.

## Usage limits

Requests are subject to a per-IP daily limit (some tools have their own per-day caps, stated in their descriptions). If you need more, contact tomaszkrawczyk@supplemental.pl. There are no prices or paid tiers.

## Links

- Server page: https://supplemental.pl/en/tools/mcp-server/
- Privacy policy: https://supplemental.pl/en/privacy-policy/
- Contact: tomaszkrawczyk@supplemental.pl

## 简体中文摘要

Supplemental EU Food Law MCP 是 supplemental.pl 提供的远程 MCP 服务器，为食品补充剂企业提供欧盟及波兰食品法规参考资料，包括知识文章检索、欧盟健康声称登记册、欧盟新型食品目录、波兰 GIS 备案步骤以及营养成分计算。

- 端点：`https://mcp.supplemental.pl/mcp`（Streamable HTTP，无需认证）
- 全部工具均为只读，共 8 个
- 内容仅供参考，不构成法律意见；无收费
- 按 IP 每日限额，如需更多请联系 tomaszkrawczyk@supplemental.pl
- 欧盟委员会登记册数据依 CC BY 4.0 使用

## License

This README and documentation are licensed under [CC BY 4.0](LICENSE).
