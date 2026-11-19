# PaperVantage for Claude Code

A Claude Code plugin marketplace with one plugin, `papervantage`.

```
/plugin marketplace add proof185/papervantage-claude-code
/plugin install papervantage@papervantage
```

See `plugins/papervantage/README.md`. The plugin only provides the connection and a short command;
the work is done by the PaperVantage MCP server.

## Maintaining

The monorepo's `distribution/claude-code/` is canonical; the public repo is a mirror. Publish with
a subtree split (from the monorepo root), then push the result to the public repo's `main`:

```bash
git subtree split --prefix=distribution/claude-code -b claude-plugin-publish
git push git@github.com:proof185/papervantage-claude-code.git claude-plugin-publish:main
```

Validate before publishing with `claude plugin validate ./distribution/claude-code`.
