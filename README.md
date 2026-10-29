# My Spain Visa MCP server

[![Listed on AllMCPs](https://allmcps.com/api/badge/my-spain-visa?style=shield)](https://allmcps.com/mcp/my-spain-visa)

Remote MCP server from My Spain Visa, an immigration law firm in Barcelona working since 2010. Ask your AI assistant about Spanish visas and it answers with figures from the BOE and from our own case files instead of guessing.

Free. No account, no key. Streamable HTTP.

**Server URL:** `https://myspainvisa.com/api/mcp`

More information: https://myspainvisa.com/mcp/

This repository only holds the public description and the `server.json` used for the Official MCP Registry, where the server is listed as `com.myspainvisa/spain-visa`. The server itself runs on our own hosting.

## Tools

| Tool | What it does |
| --- | --- |
| `spain_visa_requirements` | Requirements for the Non-Lucrative Visa, the Digital Nomad Visa, the student visa and the family routes: income figures for you and your family, work rights, where to apply, key documents and legal deadlines. |
| `schengen_90_180_calculator` | Give it your trips and it returns the days used, the days left and the next date you can come back. |
| `consulate_processing_times` | How long the Spanish consulates in the US and the UK took to decide our own clients' applications from January 2025 to October 2026, next to the wait each consulate publishes. |
| `which_spain_visa` | A quick first look at which route fits, from a few answers (why you are moving, income, family). |
| `personal_visa_assessment` | Optional. With your name, email and consent, you get an email put together from your answers and our own figures, signed by our immigration lawyer. |
| `request_consultation` | Optional. Passes your request to our team, with a reference you can use on WhatsApp. |

The last two only run when the user gives a name and email and says yes to being contacted. The assistant has to show our privacy notice first.

## Add it to your assistant

**Claude:** Settings, Connectors, Add custom connector. Paste the server URL.

**Claude Code:**

```bash
claude mcp add --transport http myspainvisa https://myspainvisa.com/api/mcp
```

**ChatGPT:** Settings, Apps and Connectors, Advanced settings, turn on developer mode, create a connector with the server URL and no authentication. Developer mode is available on paid plans.

**Cursor** (`mcp.json`):

```json
{"mcpServers": {"myspainvisa": {"url": "https://myspainvisa.com/api/mcp"}}}
```

**VS Code** (`.vscode/mcp.json`):

```json
{"servers": {"myspainvisa": {"type": "http", "url": "https://myspainvisa.com/api/mcp"}}}
```

## Where the numbers come from

Visa figures come from the BOE: the 2026 IPREM of 600 euros a month and the 2026 minimum wage set by Royal Decree 126/2026. Processing times come from our own cases. Everything the server returns is general information, not legal advice.

## Contact

david@myspainvisa.com
