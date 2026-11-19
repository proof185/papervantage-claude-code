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
/plugin marketplace add proof185/papervantage-claude-code
/plugin install papervantage@papervantage
```

Then run `/mcp`, pick `plugin:papervantage:papervantage` and sign in with your PaperVantage account.

## Without the plugin

Any MCP client can use the server at `https://mcp.papervantage.com/mcp`; the same flow is the
`new_project` prompt and the `get_project_scaffold` tool.

In Claude Code, register the server yourself (the sign-in callback is fixed at port 8090):

```bash
claude mcp add --transport http --callback-port 8090 --client-id 3k2gorgaqb6d2sl89f175eersa papervantage https://mcp.papervantage.com/mcp
```

and, if you want a short command, copy `commands/new-project.md` to `~/.claude/commands/`. It
works there too: it figures out the tool-name prefix (`papervantage` when registered this way)
and passes it to the scaffold, so the generated permission entries match.

## Sign-in

The server uses OAuth. Run `/mcp`, pick the PaperVantage server and sign in. The plugin supplies
the same OAuth client id and callback port (8090, the only localhost callback PaperVantage's
sign-in allows) that PaperVantage's own `claude mcp add` instructions use. If sign-in fails with
a redirect or client error, use the manual route above, or copy the exact command from
PaperVantage's MCP page, which includes `--client-id`.
