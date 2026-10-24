# Helmbeam agent plugins

Official plugins from Helmbeam that connect your AI agent to Helmbeam, the company research app. Your agent researches the companies you follow with Helmbeam's data and saves a research brief to your account. You read every brief in the Helmbeam app, and every version is kept.

You need Helmbeam Pro (the free trial counts) or Trader, and the Helmbeam app 2.2.4 or later on your phone. You approve every agent in the app.

## Claude Code

```
claude plugin marketplace add scydex/helmbeam
claude plugin install helmbeam@scydex
claude mcp login plugin:helmbeam:helmbeam
```

The last command opens a Helmbeam page in your browser with a 6-digit number: type it in the Helmbeam app on your phone and tap Approve. Then start Claude Code, or run /reload-plugins in an open session. An agent setting this up for you runs the sign-in as `script -q /dev/null claude mcp login plugin:helmbeam:helmbeam`, which gives the command the terminal it needs, so you only approve on your phone.

The plugin adds the Helmbeam MCP server and the helmbeam-research skill, which tells your agent how to research with Helmbeam and keep your briefs up to date.

## Gemini CLI

```
gemini extensions install https://github.com/scydex/helmbeam
```

Then, in a Gemini CLI session, run /mcp auth helmbeam and approve in the Helmbeam app.

## Other apps

Steps for Claude on the web, desktop and mobile, ChatGPT, Codex, Cursor, VS Code and Perplexity are at https://helmbeam.com/agents. Agents can read the same steps at https://helmbeam.com/agents.md.

## What's in this repository

- `.claude-plugin/marketplace.json`: the Claude Code marketplace, named scydex.
- `plugins/helmbeam/`: the Claude Code plugin, with the MCP server in `.mcp.json` and the skill in `skills/helmbeam-research/`.
- `gemini-extension.json`: the Gemini CLI extension.

The server is `https://mcp.helmbeam.com` (Streamable HTTP, OAuth sign-in). This repository holds no Helmbeam code, data or credentials.

## Licence

MIT, copyright Scydex Ltd. The licence covers the files in this repository only, not the Helmbeam service, its data or its methodology.

## Support

support@helmbeam.com. Helmbeam provides research tools. It does not place trades, move money or give personal advice.
