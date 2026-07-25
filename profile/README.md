# Milda

**A platform-neutral design language for design systems, and the toolchain that
turns one into real, generated component libraries.**

Milda lets you describe *what a component is* (its contract, anatomy, behavior,
and styling intent) once, in a canonical model that carries no platform
assumptions. From that single description, Milda generates idiomatic output for
each target (React, CSS, Figma variables, and more by design), so a design system
stays consistent everywhere without being hand-maintained per platform.

Docs: **[milda.dev](https://milda.dev)**

## Open source

The language, engine, and editor tooling are open (MIT).

### Language & engine

| Repo | What it is | npm |
| --- | --- | --- |
| [**milda-lang**](https://github.com/mildastudio/milda-lang) | The Milda language: canonical AST, prelude (stdlib as data), token model, validation & conformance | [`@mildastudio/milda`](https://www.npmjs.com/package/@mildastudio/milda) |
| [**milda-engine**](https://github.com/mildastudio/milda-engine) | The component IR + semantics, contract diff/versioning, and the code generators | [`@mildastudio/core`](https://www.npmjs.com/package/@mildastudio/core), `contract`, `generate`, `release` |

```bash
npm install @mildastudio/milda @mildastudio/core @mildastudio/generate
```

### Editor tooling

Write `.milda` with syntax highlighting, diagnostics, completion, hover docs,
go-to-definition, document outline, and folding, all powered by one language
server. The three editors' highlighters are generated from a single shared
vocabulary, so they can't drift.

| Repo | What it is | Get it |
| --- | --- | --- |
| [**milda-lsp**](https://github.com/mildastudio/milda-lsp) | The language server (LSP) for any LSP-capable editor (Neovim, Zed, Emacs, Helix, ...) | [`@mildastudio/milda-lsp`](https://www.npmjs.com/package/@mildastudio/milda-lsp) |
| [**milda-vscode**](https://github.com/mildastudio/milda-vscode) | VS Code / Open VSX extension (also Cursor, Windsurf, VSCodium); the server ships inside it | [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=milda.milda-vscode) &middot; [Open VSX](https://open-vsx.org/extension/milda/milda-vscode) |
| [**milda-jetbrains**](https://github.com/mildastudio/milda-jetbrains) | JetBrains plugin (IntelliJ IDEA Ultimate, WebStorm, PyCharm, GoLand, Rider, ...); the server ships inside it | JetBrains Marketplace |

## Design principles

- **Platform-neutral by construction.** The language and IR encode no CSS
  pseudo-classes, DOM tags, or framework APIs. Target-specific lowering lives only
  in the generators.
- **The IR is the contract.** A component's public surface is data, so it can be
  digested, diffed, and versioned with real semver, not inferred from generated code.
- **Honest escape hatches.** Where a value can't be expressed cleanly for a target,
  the model says so explicitly rather than silently approximating.
- **Values are first-class.** Colors are space-aware functions (`oklch`, `srgb`,
  `hex`, ...) and dimensions carry their units (`8px`, `0.5rem`, `150ms`), typed in
  the language itself, not opaque strings.

## The product

The open packages are the engine. The visual **Milda Studio** editor, where you
design systems and press *generate*, is the product built on top. This is
open-core: the language and generators are yours to use and extend freely.

<sub>Everything here is <code>0.x</code> and evolving quickly; expect the shape to change before <code>1.0</code>.</sub>
