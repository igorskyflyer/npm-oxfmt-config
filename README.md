<div align="center">
  <img src="https://raw.githubusercontent.com/igorskyflyer/npm-oxfmt-config/main/media/oxfmt-config.png" alt="Icon of Oxfmt Config" width="256" height="256">
  <h1>Oxfmt Config</h1>
</div>

<blockquote align="center">oxfmt Powered • Import Sorting • Zero Bikeshedding • Extend and Go</blockquote>

<h4 align="center">
  ✨ Pixel-perfect code formatting opinions, oxfmt-powered and ready to extend. ⚓
</h4>

<br>

## Table of Contents

- ✨ [**Features**](#features)
- 🕵🏼 [**Usage**](#usage)
- ⚙️ [**Implementation**](#implementation)
- 🎯 [**Motivation**](#motivation)
- 📝 [**Changelog**](#changelog)
- 🪪 [**License**](#license)
- 💖 [**Support**](#support)
- 🧬 [**Related**](#related)
- 👨🏻‍💻 [**Author**](#author)

<br>

## Features

- ✨ Consistent formatting for JS, TS, JSX, TSX, JSON, HTML, CSS, Vue and more
- 📦 Intelligent import sorting with custom internal package support
- 🎯 Opinionated but practical defaults
- ⚡ Powered by `Oxfmt` (very fast Rust-based formatter)
- 🛡️ `Zero dependencies` - `oxfmt` is a peer dependency only

<br>

## Usage

Install it by executing any of the following, depending on the preferred package manager:

```bash
bun add -D @igorskyflyer/oxfmt-config
```

```bash
pnpm add -D @igorskyflyer/oxfmt-config
```

```bash
yarn add -D @igorskyflyer/oxfmt-config
```

```bash
npm i -D @igorskyflyer/oxfmt-config
```

<br>

Then extend the config in **.oxfmtrc.json**:

`.oxfmtrc.json`

```json
{ "extends": "@igorskyflyer/oxfmt-config" }
```

Override any rule locally as needed:

`.oxfmtrc.json`

```json
{
  "extends": "@igorskyflyer/oxfmt-config",
  "printWidth": 100,
  "endOfLine": "crlf",
  "arrowParens": "avoid"
}
```

<br>

## Implementation

The formatting configuration is defined in a single `.oxfmtrc.json` file that serves as the authoritative source of truth for all formatting decisions across the project.

All rules are intentional, documented, and designed to produce clean, readable, and diff-friendly code with minimal visual noise.

### Formatting Decisions

- **`semi: false`** - No semicolons. Reduces visual noise while relying on modern JavaScript ASI rules.
- **`singleQuote: true`** - Single quotes for strings, consistent across the entire `@igorskyflyer` ecosystem.
- **`trailingComma: "all"`** - Trailing commas in all applicable places (objects, arrays, functions) for cleaner git diffs.
- **`printWidth: 80`** - Standard line width that balances readability and compactness.
- **`tabWidth: 2`** - Two-space indentation, aligned with the project’s TypeScript and EditorConfig standards.
- **`useTabs: false`** - Uses spaces for consistent rendering across all editors and platforms.
- **`bracketSpacing: true`** - Adds space inside object brackets (`{ name }` instead of `{name}`).
- **`bracketSameLine: false`** - Keeps the closing `>` of JSX elements on its own line for better visual separation.
- **`arrowParens: "always"`** - Always includes parentheses around arrow function parameters.
- **`objectWrap: "preserve"`** - Preserves intentional multi-line objects when the developer chooses to break them.
- **`singleAttributePerLine: false`** - Allows multiple short attributes on one line when they fit within the print width.
- **`endOfLine: "lf"`** and **`insertFinalNewline: true`** - Unix line endings and final newline for POSIX compliance.
- **`jsxSingleQuote: false`** - Uses double quotes in JSX attributes to match HTML conventions.
- **`quoteProps: "as-needed"`** - Only quotes object keys when required by JavaScript syntax.
- **`embeddedLanguageFormatting: "auto"`**, **`htmlWhitespaceSensitivity: "css"`**, **`proseWrap: "preserve"`** - Sensible defaults for embedded code, HTML, and Markdown.

### Import Sorting

Imports are sorted in a deliberate order optimized for human readability and debugging:

1. **`builtin`** - Node.js built-in modules (most familiar)
2. **`internal + subpath`** - Internal packages including `@igorskyflyer/*`
3. **`external`** - Third-party dependencies
4. **`parent + sibling + index`** - Relative imports
5. **`style`** - Style and CSS imports (always last)
6. **`unknown`** - Catch-all for any remaining imports

### Ignored Files

- `node_modules/**`, `dist/**`, `coverage/**`
- Minified files (`*.min.js`, `*.min.css`)
- Package lockfiles (never format auto-generated files)

This configuration is applied uniformly via Oxfmt.

<br>

## Motivation

Formatting decisions are a source of endless bikeshedding across projects. Each project ends up with its own slightly different config, slightly outdated, with no single source of truth.

`@igorskyflyer/oxfmt-config` solves this by providing one opinionated, versioned config that propagates across all projects via a simple `extends`.

_Update once, apply everywhere_ - just like all packages of the `@igorskyflyer` ecosystem do!

<br>

## Changelog

Read about the latest changes in the [**CHANGELOG**](https://github.com/igorskyflyer/npm-oxfmt-config/blob/main/CHANGELOG.md).

<br>

## License

Licensed under the [**MIT license**](https://github.com/igorskyflyer/npm-oxfmt-config/blob/main/LICENSE).

<br>

## Support

<div align="center">
  Engineering and documenting open-source projects<br>
  involves a significant investment of time.
  <br><br>
  If this project or its implementation has provided value,<br>
  support is greatly appreciated.
  <br><br>
  <a href="https://ko-fi.com/igorskyflyer" target="_blank"><img src="https://raw.githubusercontent.com/igorskyflyer/igorskyflyer/main/assets/ko-fi.png" alt="Donate to igorskyflyer" width="180" height="46"></a>
  <br><br>
  <em>Thank you for supporting these efforts!</em> 🙏😊
</div>

<br>

## Related

This package is part of the [**dotfiles**](https://github.com/igorskyflyer/dotfiles) DX config suite - a curated index of independently installable configuration packages for linting, formatting, editing, JS/TS, React, Vue and many more.

### Other related packages

[**@igorskyflyer/astro-render-component**](https://www.npmjs.com/package/@igorskyflyer/astro-render-component)

> _🤖 Astro component renderer. Zero configuration. Produces clean HTML strings directly in Node.js without any DOM environment. 🐬_

<br>

[**@igorskyflyer/adblock-filter-counter**](https://www.npmjs.com/package/@igorskyflyer/adblock-filter-counter)

> _🐲 A lightweight npm module for counting ad-block filter rules, ultra-simple, fast, and perfect for list maintainers, filter testers, and privacy tool developers.🦘_

<br>

[**@igorskyflyer/zep**](https://www.npmjs.com/package/@igorskyflyer/zep)

> _🧠 Zep is a zero-dependency, efficient debounce module. ⏰_

<br>

[**@igorskyflyer/magic-string**](https://www.npmjs.com/package/@igorskyflyer/magic-string)

> _🧵 An expressive and chainable library for advanced string manipulations. Supports appending, prepending, trimming, quoting, and path formatting with customizable whitespace handling. Makes advanced String manipulations a piece of cake. 🦥_

<br>

[**@igorskyflyer/valid-path**](https://www.npmjs.com/package/@igorskyflyer/valid-path)

> _🧰 Determines whether a given value can be a valid file/directory name. 🏜_

<br>

## Author

Created by **Igor Dimitrijević ([_@igorskyflyer_](https://github.com/igorskyflyer/))**.
