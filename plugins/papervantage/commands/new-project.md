---
description: Set up a new academic project with PaperVantage (project, reading list, local folder)
argument-hint: <project title> [level] [field] [deadline YYYY-MM-DD]
---

Set up a new academic project for me with PaperVantage.

Arguments: $ARGUMENTS

Use the PaperVantage MCP server (provided by this plugin). Follow its `new_project` prompt
exactly if you can use it (title, level, field and deadline come from the arguments above; ask me
for anything missing). If you can't use MCP prompts, do the same flow with the tools: call
`create_project`, then `get_project_scaffold` with the new project's id, and follow its
`instructions`.

When you call `get_project_scaffold`, set `mcp_server` to the name PaperVantage's tools carry in
this session: it is the part of the tool name between `mcp__` and `__<tool>`. For this plugin
that is `plugin_papervantage_papervantage`. The generated `.claude/settings.json` uses it in its
permission entries, so a wrong value there means permission prompts for every PaperVantage tool.

If the PaperVantage tools are not available, stop and tell me to run `/mcp` and sign in to the
`papervantage` server, then try again.
