# Home Generator HQ — MCP Server

A curated, verified catalog of 33 home backup power products — standby generators, portable generators, portable power stations, solar panels and expansion batteries — with approximate street prices and plain-English sizing help.

**Live endpoint:** `https://homegeneratorhq.com/mcp` (Streamable HTTP, stateless, no auth)
**Website:** https://homegeneratorhq.com
**Official MCP Registry:** `com.homegeneratorhq/generators`

## Connect a client

```json
{
  "mcpServers": {
    "homegeneratorhq-mcp": {
      "url": "https://homegeneratorhq.com/mcp"
    }
  }
}
```

## Tools

| Tool | Description |
|---|---|
| `search_generators` | Search the Home Generator HQ verified catalog of generators. Returns a compact ranked shortlist with prices and links. |
| `get_generator` | Get the full verified record for one generator by name. |
| `compare_generators` | Compare two or more generators side by side on key specs and price. |
| `list_categories` | List the catalog categories with item counts. |
| `catalog_info` | About this catalog: coverage, item count, last update, and usage terms. |
| `sizing_help` | Generator sizing rules of thumb and typical installed cost ranges for standby generators. |

## Run it yourself

The server is a single Cloudflare Worker (`src/worker.js`) with its dataset
bundled in `data/` — the same code that serves the live endpoint, with the
dataset snapshotted from https://homegeneratorhq.com/data/generators.json.

```bash
npm install
npx wrangler dev      # local
npx wrangler deploy   # your own Cloudflare account
```

## Data and attribution

The catalog data is free to use and cite with a link back to
https://homegeneratorhq.com. Prices are verified against vendor pages when the
dataset is updated; the live dataset (and its changelog) is at
https://homegeneratorhq.com/data/generators.json. Some product links are affiliate links — see the
site's affiliate disclosure page.

## License

MIT (code). Catalog data: free with attribution, as above.
