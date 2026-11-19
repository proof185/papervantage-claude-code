# Installing the PaperVantage MCP server (for AI agents such as Cline)

PaperVantage is a **remote** MCP server: there is nothing to clone, build or run locally.

- Endpoint: `https://mcp.papervantage.com/mcp`
- Transport: Streamable HTTP
- Auth: OAuth 2.1 (dynamic client registration), or a Bearer API key

## Steps

1. Ask the user to sign in at <https://papervantage.com/connect/mcp> (a free account works) and click
   **Generate API Key**. Ask them to paste the key; never guess or reuse one.
2. Add this entry to the MCP settings file (for Cline: `cline_mcp_settings.json`), replacing `<API_KEY>`:

   ```json
   {
     "mcpServers": {
       "papervantage": {
         "type": "streamableHttp",
         "url": "https://mcp.papervantage.com/mcp",
         "headers": {
           "Authorization": "Bearer <API_KEY>"
         }
       }
     }
   }
   ```

   Clients that support MCP OAuth can leave out `headers`: they open a browser sign-in on first use.
3. Check the connection by calling `list_projects` (or `search_papers` with any query). A `401` means the
   key is missing or wrong.

## What it does

Search arXiv papers by meaning across full text, read paper transcripts, explore citation graphs, rank papers for
an assignment brief, save exact-quote passages and notes into projects, and export BibTeX/RIS. Tool and setup
reference: <https://papervantage.com/connect/mcp> and <https://papervantage.com/docs/api>.
