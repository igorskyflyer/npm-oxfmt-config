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

- ✨ Pixel-perfect, consistent formatting across all modern file types
- 📦 Handles `JS`, `TS`, `JSX`, `TSX`, `JSON`, `HTML`, `CSS`, `Vue` and more
- 🔍 Intelligent `import sorting` - builtin first, then internal, then external
- 🎯 `Opinionated` defaults - extend and go, zero bikeshedding
- ⚡ Powered by `oxfmt` - `30x` faster than `Prettier`
- 🛡️ `Zero dependencies` - `oxfmt` is a peer dependency only

<br>

## Usage

Install it by executing any of the following, depending on the preferred package manager:

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

Then extend the config in `.oxfmtrc.json`:

```json
{ "extends": "@igorskyflyer/oxfmt-config" }
```

Override any rule locally as needed:

```json
{ "extends": "@igorskyflyer/oxfmt-config", "printWidth": 100 }
```

<br>

## Implementation

The config enforces consistent formatting across all supported file types with a single, versioned source of truth. Import sorting follows a deliberate order - builtin modules first, internal `@igorskyflyer` packages second, external dependencies third, relative imports fourth, style imports last - mirroring a natural debugging flow from most to least familiar.

All decisions are intentional and documented - nothing is left to chance or personal preference on a per-project basis.

### Formatting

- **`semi: false`** - no semicolons, cleaner visual noise reduction, ASI handles it reliably in modern JS/TS
- **`singleQuote: true`** - single quotes throughout, consistent with the broader `@igorskyflyer` ecosystem
- **`trailingComma: "all"`** - trailing commas everywhere, cleaner diffs - adding a new line never modifies the previous one
- **`printWidth: 100`** - 80 is too narrow for modern monitors, 100 is the sweet spot for readability
- **`tabWidth: 2`** - industry standard for JS/TS, consistent with [`@igorskyflyer/tsconfig`](https://www.npmjs.com/package/@igorskyflyer/tsconfig) and [`@igorskyflyer/editorconfig`](https://www.npmjs.com/package/@igorskyflyer/editorconfig)
- **`useTabs: false`** - spaces for consistent rendering across all editors and environments
- **`bracketSpacing: true`** - `{ name }` over `{name}`, objects need room to breathe
- **`bracketSameLine: false`** - closing `>` on its own line, visually separates props from content
- **`arrowParens: "always"`** - always `(x) => x`, consistent regardless of parameter count
- **`objectWrap: "collapse"`** - collapse objects to one line if they fit, expand only when needed
- **`singleAttributePerLine: false`** - let `printWidth` decide, one attribute per line is too aggressive for short props
- **`endOfLine: "lf"`** - Unix line endings, cross-platform standard for source code
- **`insertFinalNewline: true`** - POSIX standard, prevents noisy diffs
- **`embeddedLanguageFormatting: "auto"`** - format embedded code in markdown and HTML automatically
- **`jsxSingleQuote: false`** - double quotes in JSX, mirrors HTML attribute convention
- **`htmlWhitespaceSensitivity: "css"`** - respects CSS display property, matches browser rendering behavior
- **`vueIndentScriptAndStyle: false`** - no extra indent level inside `<script>` and `<style>` tags, reduces horizontal noise
- **`proseWrap: "preserve"`** - GitHub and Bitbucket are linebreak-sensitive, never reflow prose automatically
- **`quoteProps: "as-needed"`** - only quote object keys when necessary, cleaner output

### Ignored Files

- `node_modules/**` - never format dependencies
- `dist/**` - never format compiled output
- `coverage/**` - never format test coverage output
- `*.min.js/css` - never format minified files, formatting destroys them
- **lockfiles** - auto-generated, formatting is pointless and causes noisy diffs

### Import Sorting

Imports follow a deliberate debugging-first order:

1. **`builtin`** - Node.js built-ins, most familiar
2. **`internal + subpath`** - `@igorskyflyer` packages, own code
3. **`external`** - third-party dependencies
4. **`parent + sibling + index`** - relative imports
5. **`style`** - style imports always last

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
