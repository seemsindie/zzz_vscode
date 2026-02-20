# Zzz Templates — VS Code Extension

Syntax highlighting for Zzz template files (`.html.zzz`).

## Features

- Full HTML syntax highlighting (inherited from VS Code's built-in HTML grammar)
- Zzz template expression highlighting:
  - Variables: `{{name}}`, `{{user.name}}`
  - Raw (unescaped) variables: `{{{content}}}`
  - Conditionals: `{{#if cond}}` / `{{else}}` / `{{/if}}`
  - Loops: `{{#each items}}` / `{{/each}}`
  - Comments: `{{! this is a comment }}`
- Auto-closing pairs for `{{ }}` and `{{{ }}}`
- Code folding for `{{#if}}` / `{{#each}}` blocks
- Embedded JavaScript and CSS highlighting within HTML

## Installation

### Local development (symlink)

```bash
# macOS / Linux
ln -s "$(pwd)" ~/.vscode/extensions/zzz-templates

# Then reload VS Code (Cmd+Shift+P → "Reload Window")
```

### From VSIX

```bash
# Install vsce if needed
npm install -g @vscode/vsce

# Package the extension
cd zzz_vscode
vsce package

# Install the .vsix file
code --install-extension zzz-templates-0.1.0.vsix
```

## Supported File Extensions

- `.html.zzz` — HTML templates with Zzz expressions
- `.zzz` — standalone Zzz templates
