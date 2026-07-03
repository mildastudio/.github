# Milda

**A platform-neutral design language for design systems — and the toolchain that
turns one into real, generated component libraries.**

Milda lets you describe *what a component is* — its contract, anatomy, behavior,
and styling intent — once, in a canonical model that carries no platform
assumptions. From that single description, Milda generates idiomatic output for
each target (React, CSS, Figma variables, and more by design), so a design system
stays consistent everywhere without being hand-maintained per platform.

## Open source

The language and the engine are open (MIT):

| Repo | What it is | npm |
| --- | --- | --- |
| [**milda-lang**](https://github.com/mildastudio/milda-lang) | The Milda language: canonical AST, prelude (stdlib as data), token model, validation & conformance | [`milda`](https://www.npmjs.com/package/milda) |
| [**milda-engine**](https://github.com/mildastudio/milda-engine) | The component IR + semantics, contract diff/versioning, and the code generators | [`@mildastudio/core`](https://www.npmjs.com/package/@mildastudio/core), `contract`, `generate`, `release` |

```bash
npm install milda @mildastudio/core @mildastudio/generate
```

## Design principles

- **Platform-neutral by construction.** The language and IR encode no CSS
  pseudo-classes, DOM tags, or framework APIs. Target-specific lowering lives only
  in the generators.
- **The IR is the contract.** A component's public surface is data — so it can be
  digested, diffed, and versioned with real semver, not inferred from generated code.
- **Honest escape hatches.** Where a value can't be expressed cleanly for a target,
  the model says so explicitly rather than silently approximating.

## The product

The open packages are the engine. The visual **Milda Studio** editor — where you
design systems and press *generate* — is the product built on top. This is
open-core: the language and generators are yours to use and extend freely.

<sub>Everything here is <code>0.x</code> and evolving quickly — expect the shape to change before <code>1.0</code>.</sub>
