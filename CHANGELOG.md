# Changelog

All notable changes to the **Pidgn Templates** VS Code extension are documented here.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project follows semantic versioning.

## [0.3.1] — 2026-04-18

### Added

- **Snippets** — first set of template scaffolding snippets, including `if`, `ifelse`, `each`, `with`, `partial`, `partialargs`, `comment`, `yield`, `yieldnamed`, `rawblock`, `var`, `raw`, all six built-in pipes (`upper`, `lower`, `truncate`, `default`, `pluralize`, `format_date`), and the new i18n pipes `t` / `tdyn` / `tn`. Also includes common app patterns: `flash-success`, `flash-error`, `csrf`, `pagination`.
- **Syntax: new pipes `t` and `tn`** — highlighted as functions in the pipe chain (`{{"key" | t}}`, `{{count | tn:"items"}}`). Matches the `t` / `tn` pipes added to `pidgn_template` for template-level i18n.
- **Syntax: quoted-string paths** — expressions like `{{"welcome_title" | t}}` now highlight the quoted string as a literal key instead of falling back to the variable rule.
- **Syntax: `format_date` pipe** — now recognised alongside the other built-in pipes.
- **Marketplace metadata** — `icon`, `repository`, `homepage`, `bugs`, `keywords`, `galleryBanner`, `author`, `license`. Category now includes `Snippets` in addition to `Programming Languages`.

### Changed

- Extension description expanded to cover the new snippet and i18n support.

## [0.3.0] — 2026-03-27

### Added

- Initial public release following the `zzz` → `pidgn` rename.
- Syntax highlighting for `.html.pidgn` and `.pidgn` files:
  - Variables `{{name}}` / `{{user.name}}` with dotted-path support.
  - Raw variables `{{{content}}}` (no HTML escaping).
  - Conditionals `{{#if}}` / `{{else}}` / `{{/if}}`.
  - Loops `{{#each items}}` / `{{/each}}`.
  - Scope blocks `{{#with obj}}` / `{{/with}}`.
  - Partials `{{> partial_name}}` with optional `name="value"` args.
  - Yield slots `{{{yield}}}` and named `{{{yield_head}}}`.
  - Raw blocks `{{{{raw}}}}...{{{{/raw}}}}`.
  - Comments `{{! ... }}`.
  - Pipes `{{x | upper}}`, `{{x | truncate:20}}`, `{{x | pluralize:"item":"items"}}`.
- Language configuration: bracket matching, auto-close pairs for `{{ }}` and `{{{ }}}`, code folding for block statements, block comment tokens.
- Embedded HTML, JavaScript, and CSS highlighting within templates.
