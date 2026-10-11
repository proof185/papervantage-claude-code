---
description: Set up a new academic project with PaperVantage (project, reading list, local folder)
argument-hint: <project title> [level] [field] [deadline YYYY-MM-DD]
---

Set up a new academic project for me with PaperVantage.

Arguments: $ARGUMENTS

Use the PaperVantage MCP server. Work out the name its tools carry in this session: the part of a
PaperVantage tool name between `mcp__` and `__<tool>`. Installed as this plugin it is
`plugin_papervantage_papervantage`; registered by hand it is usually `papervantage`. Call that
value `MCP_NAME`.

Then follow the server's `new_project` prompt if you can use it, passing `mcp_server=MCP_NAME`
along with the title, level, field and deadline from the arguments above (ask me for anything
missing). If you can't use MCP prompts, run the same flow with the tools: `create_project`, then
`get_project_scaffold(project_id, mcp_server=MCP_NAME)`, and follow its `instructions`.

`MCP_NAME` matters: the generated `.claude/settings.json` uses it in its permission entries, so a
wrong value means a permission prompt for every PaperVantage tool.

If the PaperVantage tools are not available, stop and tell me to run `/mcp` and sign in to the
PaperVantage server, then try again.
