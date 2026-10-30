<p align="center"><img src="logo.png" width="96" alt="IsraBase logo"></p>

# IsraBase MCP Server

Free, read-only remote MCP server for the Israeli company registry. Search 730K+ companies, 75K nonprofits (עמותות) and 28K partnerships (שותפויות) from data.gov.il by name, number, city, year or type.

ישראבייס: חיפוש חברות, עמותות ושותפויות מרשם החברות בישראל, ישירות מתוך סוכני AI. חינם, ללא מפתח API.

- Endpoint: `https://israbase.com/mcp` (Streamable HTTP, no authentication)
- Official MCP Registry: `com.israbase/israbase`
- Website: https://israbase.com
- API docs: https://israbase.com/developers
- OpenAPI: https://israbase.com/openapi.json
- For AI agents: https://israbase.com/llms.txt

## Install

Claude Code:

```
claude mcp add --transport http israbase https://israbase.com/mcp
```

Cursor, Windsurf, Claude Desktop and other clients with remote MCP support (`mcp.json`):

```json
{
  "mcpServers": {
    "israbase": { "url": "https://israbase.com/mcp" }
  }
}
```

VS Code (`.vscode/mcp.json`):

```json
{
  "servers": {
    "israbase": { "type": "http", "url": "https://israbase.com/mcp" }
  }
}
```

Cline and clients that only run stdio servers:

```json
{
  "mcpServers": {
    "israbase": { "command": "npx", "args": ["-y", "mcp-remote", "https://israbase.com/mcp"] }
  }
}
```

## Tools

| Tool | What it does |
| --- | --- |
| `search_companies` | Search companies, nonprofits or partnerships by name or number, with optional city, status and segment filters. |
| `list_companies_by_city` | List companies registered in one Israeli city (paged). |
| `list_companies_by_year` | List companies by registration year (paged). |
| `list_companies_by_type` | List government, public, foreign or bond-issuing companies (paged). |
| `list_recent_companies` | Newest companies by incorporation date. |
| `get_company` | Full registry record for one company by its 9-digit number (ח.פ). |
| `get_nonprofit` | Full registry record for one nonprofit (עמותה) by registration number. |
| `get_partnership` | Full registry record for one partnership (שותפות) by registration number. |
| `list_marketplace_listings` | Active businesses for sale on IsraBase, by category or city. |
| `get_stats` | Registry totals, company status breakdown and top cities. |
| `get_nesach_order_link` | Link to order an official company extract (38 ILS incl. VAT). The tool never takes payment. |

## Example prompts

- "Is company 514924323 still active? Where is it registered?"
- "Find Israeli companies named Elbit and show their status."
- "List 20 companies registered in Haifa in 2024."
- "Which Israeli government companies exist?"
- "Look up nonprofit 580699635 and summarize its purpose."
- "How many active companies are there in Israel, and which cities have the most?"
- "מצא חברות בשם 'אלביט' והצג את הסטטוס שלהן."

## Limits and data

- Read-only. No sign-up and no API key.
- Fair use: 30 requests per minute per IP.
- Data: Israeli Companies Registrar, Nonprofits Registrar and Partnerships Registrar via [data.gov.il](https://data.gov.il). Please credit IsraBase and data.gov.il.

This repository holds documentation only. The server is hosted by [IsraBase](https://israbase.com).
