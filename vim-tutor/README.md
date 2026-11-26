# Vim Tutor for Claude

Learn Vim in Claude. Vim Tutor runs Vim keys on your own text in a real Vim engine and shows the text before and after,
then lets you press the same keys yourself in a small editor right in the chat. It also has short practice sets, answers
to common Vim tasks, a daily Vim golf hole and a command reference. It's for anyone learning Vim or Neovim, or using Vim
keys in VS Code, JetBrains IDEs or Zed.

This plugin adds two things:

- **The Vim Tutor connector**, VimNinja's remote MCP server at `https://www.vimninja.com/mcp/claude`. It is the same
  server as the Vim Tutor listing in Claude's directory, so if you have both you see one set of tools.
- **A skill** that tells Claude when each tool helps, and to run the Vim keys it suggests before answering.

## Install

In Claude Code:

```
/plugin install vim-tutor --marketplace jaipandya/vim-tutor-claude-plugin
```

In claude.ai and the Claude apps, add Vim Tutor from the directory once it's listed, or add the connector yourself:
Plugins, Add, Add custom connector, name it Vim Tutor, paste `https://www.vimninja.com/mcp/claude`, No sign-in.

## How to use it

Ask Claude a Vim question, for example:

- "How do I wrap each of these lines in double quotes in Vim?" followed by a few lines
- "What do the keys `ci"final<Esc>` do to this line: `status = "draft"`?"
- "Give me a short exercise to practise the w, b and e motions."
- "Give me today's Vim golf challenge."
- "Which Vim commands move to the start and the end of a line?"

In claude.ai and the Claude apps the answer includes an editor: click it once, then type. In Claude Code the answer is
text only.

## Data

No account and no sign-in. When Claude calls a tool, it sends that tool's inputs to VimNinja's server: for `vim_try`,
the text and keys you ask about; for the others, your question or topic. The server uses them only to answer. It
doesn't store or log your text, and the plugin sends nothing anywhere else. Privacy policy:
https://www.vimninja.com/privacy#assistants

## Tools

| Tool | What it returns |
|---|---|
| `vim_try` | The text before and after running Vim keys, and whether the keys produced the text you expected |
| `vim_practice` | Five short exercises on a topic, checked as you type |
| `vim_howto` | The keys for a common task, with a short exercise |
| `vim_golf_today` | Today's Vim golf hole: start, target and par |
| `vim_cheatsheet` | Up to 12 commands for a task, one line each |

## Support

support@vimninja.com · https://www.vimninja.com/ai

## License

The files in this repository are MIT licensed (see `LICENSE`). The Vim Tutor server and vimninja.com are not part of
this repository.
