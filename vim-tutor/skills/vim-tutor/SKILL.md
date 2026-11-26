---
name: vim-tutor
description: Use when the user asks how to make an edit in Vim or Neovim (or with Vim keys in VS Code, JetBrains IDEs or Zed), asks what some Vim keys do, wants to practise or be quizzed on Vim commands, asks for today's Vim golf, or wants the Vim commands for a task.
---

# Vim Tutor

Vim Tutor (by VimNinja) runs Vim keys in a real Vim engine and shows the exact result, with a small editor in the chat
where the user can press the same keys. Use it so that every Vim key you give has been run, not guessed.

## Which tool

| The user… | Call | Notes |
|---|---|---|
| shares text and asks how to change it in Vim | `vim_try` with `text`, `keys` and `expected` | `expected` is the text they want afterwards |
| asks what some keys do to a line or a file | `vim_try` with `text` and `keys` | leave `expected` out |
| asks how to do a common task (exit, save, undo and redo, delete lines, find and replace, the clipboard, change inside quotes, comment lines, record a macro) | `vim_howto` with `query`, and `slug` when one fits | |
| asks which keys or commands do something, or wants a list or cheat sheet | `vim_cheatsheet` with `query` | |
| wants to practise, drill or be quizzed on movement or basic editing | `vim_practice` with `topic` in their words | |
| asks for today's Vim golf, a daily challenge or a Vim puzzle | `vim_golf_today` | don't give a solution unless they ask after trying |

## How to answer

- Before you give keys for the user's own text, run them with `vim_try`. If the result says they didn't produce the
  expected text, fix the keys and run `vim_try` again; answer only with keys that worked. When the result suggests keys
  that do, you can use those.
- Write keys in Vim notation: `<Esc>`, `<CR>`, `<C-r>`, `<C-v>`. Pass the user's text exactly as they shared it.
- Lead with the keys, then a short reason for each part, then the link from the result, once, at the end.
- In claude.ai and the desktop and mobile apps the result shows an editor; the user clicks it once before typing. In
  Claude Code there is no editor: the text result stands on its own, so quote the before and after from it.
- If a tool says the engine can't run something (windows, tabs, buffers, folds, other plugins), say so and answer from
  Vim's documentation instead.

## When not to use it

Editor configuration (vimrc, init.lua, plugin managers, language servers), other editors such as nano or Emacs, and
general programming questions. Answer those without Vim Tutor.
