# pidgn_vscode

Syntax highlighting, snippets, and language support for [pidgn](https://pidgn.dev) template files in VS Code.

[![VS Code Marketplace](https://img.shields.io/visual-studio-marketplace/v/Pidgn.pidgn-templates?label=VS%20Marketplace)](https://marketplace.visualstudio.com/items?itemName=Pidgn.pidgn-templates)
[![Installs](https://img.shields.io/visual-studio-marketplace/i/Pidgn.pidgn-templates)](https://marketplace.visualstudio.com/items?itemName=Pidgn.pidgn-templates)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

## Features

Full HTML syntax highlighting (inherited from VS Code's built-in HTML grammar), plus pidgn template expressions:

- **Variables**: `{{name}}`, `{{user.name}}` (dotted paths)
- **Raw (unescaped)**: `{{{content}}}`
- **Conditionals**: `{{#if cond}}` / `{{else}}` / `{{/if}}`
- **Loops**: `{{#each items}}` / `{{/each}}`
- **Scope blocks**: `{{#with obj}}` / `{{/with}}`
- **Partials**: `{{> partial_name}}`, with `name="value"` args
- **Yield slots**: `{{{yield}}}`, `{{{yield_head}}}`, etc.
- **Raw blocks**: `{{{{raw}}}} ... {{{{/raw}}}}`
- **Comments**: `{{! comment }}`
- **Pipes**: `{{x | upper}}`, `{{x | truncate:20}}`, `{{count | pluralize:"item":"items"}}`, `{{ts | format_date:"YYYY-MM-DD"}}`
- **i18n pipes** (new): `{{"welcome_title" | t}}`, `{{count | tn:"items"}}` — see [Locale & i18n](https://docs.pidgn.dev/core/i18n/)
- **Quoted-string keys**: `{{"any_string" | t}}` treated as a literal, not a field path

Plus:

- **Snippets** for all block tags, all pipes, and common patterns (flash messages, CSRF field, pagination nav).
- **Auto-closing pairs** for `{{ }}` and `{{{ }}}`.
- **Code folding** for `{{#if}}` / `{{#each}}` / `{{#with}}` blocks.
- **Embedded JavaScript and CSS** highlighting inside `.html.pidgn` templates.

## Snippets (selection)

| Prefix | Expands to |
|--------|------------|
| `if`, `ifelse`, `each`, `with` | Block tags |
| `var`, `raw`, `comment` | Simple interpolations |
| `partial`, `partialargs`, `yield`, `yieldnamed` | Layout / composition |
| `upper`, `lower`, `truncate`, `default`, `pluralize`, `formatdate` | Built-in pipes |
| `t`, `tdyn`, `tn` | Translation pipes (literal key, dynamic key, plural) |
| `flash-success`, `flash-error`, `csrf`, `pagination` | Common app patterns |

Type the prefix in a `.html.pidgn` file and press `Tab`.

## Installation

### From the Marketplace

Search for **Pidgn Templates** in the VS Code Extensions panel, or:

```
ext install Pidgn.pidgn-templates
```

### Local development (symlink)

```bash
# macOS / Linux
ln -s "$(pwd)" ~/.vscode/extensions/pidgn-templates
# Then reload VS Code (Cmd+Shift+P -> "Reload Window")
```

### From VSIX

```bash
npm install -g @vscode/vsce
cd pidgn_vscode
vsce package
code --install-extension pidgn-templates-*.vsix
```

## Supported File Extensions

- `.html.pidgn` -- HTML templates with pidgn expressions
- `.pidgn` -- standalone pidgn templates

## Ecosystem

| Package | Description |
|---------|-------------|
| [pidgn.zig](https://github.com/seemsindie/pidgn) | Core web framework |
| [pidgn_db](https://github.com/seemsindie/pidgn_db) | Database ORM (SQLite + PostgreSQL) |
| [pidgn_jobs](https://github.com/seemsindie/pidgn_jobs) | Background job processing |
| [pidgn_mailer](https://github.com/seemsindie/pidgn_mailer) | Email sending |
| [pidgn_template](https://github.com/seemsindie/pidgn_template) | Template engine |
| [pidgn_cli](https://github.com/seemsindie/pidgn_cli) | CLI tooling |

## License

MIT License -- Copyright (c) 2026 Ivan Stamenkovic
