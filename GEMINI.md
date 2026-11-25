# supplemental.pl — EU/PL food law

Read-only reference tools for EU and Polish food-law questions that affect food supplement businesses. Results are not legal advice. Verify them against the official sources and, where needed, consult a qualified adviser. There is no paid plan and the tools do not discuss prices.

## Tools

- `search_articles` — full-text search of supplemental.pl knowledge articles (PL/EN/DE) on health claims, novel food, supplements, labelling and CJEU case law.
- `get_article` — one article by URL or slug, with a summary, headings, excerpt, legal references and language versions.
- `check_health_claim` — look up a nutrient or substance in the EU Register of nutrition and health claims (status, conditions of use, EFSA question, legal act).
- `novel_food_status` — look up a food or ingredient in the EU Novel Food Catalogue (status per part or form, with links to Regulation (EU) 2015/2283 and the Union list).
- `search_claims_foodlaw` — match an ingredient (and optional dose) against Regulation (EU) 432/2012 authorised claims and the SANCO/11074/2013 botanical list (botanicals are always "on_hold").
- `get_claim_foodlaw` — fetch one C.L.A.I.M.S. claim by the numeric ID returned by `search_claims_foodlaw`.
- `gis_notification_steps` — step-by-step procedure for notifying a food supplement to the Polish Chief Sanitary Inspectorate (GIS).
- `nutrition_calc` — deterministic nutrition calculation for a recipe (per 100 g, %NRV, candidate nutrition claims, allergens and QUID hints).

All tools only read data; nothing is created or changed.

## Sources

- European Commission: EU Register of nutrition and health claims, and the EU Novel Food Catalogue (refreshed weekly; reused under CC BY 4.0, with attribution to the European Commission).
- Knowledge articles on [supplemental.pl](https://supplemental.pl).
- C.L.A.I.M.S. (FOODLAW.ai) for claim matching.

Endpoint: `https://mcp.supplemental.pl/mcp` (Streamable HTTP, no authentication). Requests are subject to a per-IP daily limit. Contact: tomaszkrawczyk@supplemental.pl.
