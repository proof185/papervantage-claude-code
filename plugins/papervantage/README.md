# PaperVantage plugin for Claude Code

Connects Claude Code to the PaperVantage MCP server and adds one command:

```
/papervantage:new-project <title> [level] [field] [deadline]
```

It creates a PaperVantage project, helps you turn your assignment brief (PDF) into a ranked
reading list, and writes a project folder on your machine with skills (`find-sources`,
`read-paper`, `outline-from-notes`, `rubric-check`, `cite-check`), a `CLAUDE.md` and scoped
permissions.

## Install

```
/plugin marketplace add <owner>/<repo>
/plugin install papervantage@papervantage
```

Then run `/mcp`, pick `plugin:papervantage:papervantage` and sign in with your PaperVantage account.

## Without the plugin

Any MCP client can use the server at `https://mcp.papervantage.com/mcp`, and the same flow is the
`new_project` prompt / `get_project_scaffold` tool. See the PaperVantage site's MCP page.
