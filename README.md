# Shopify Theme Starter

This repository is a Shopify starter theme for agency delivery work. It is based on Shopify Skeleton Theme, but the goal here is practical reuse across client projects: a clean foundation that is responsive, accessible, block-based, theme-editor friendly, and ready to evolve into custom storefront builds.

## Purpose

This theme is intended to:

- speed up new client theme builds without starting from zero
- provide a reusable base for custom Shopify storefront projects
- support responsive experiences across mobile, tablet, and desktop
- target WCAG 2.2 AA accessibility for core storefront experiences
- give merchants flexible, block-based content editing in the Shopify theme editor
- support color theme customization and localization-ready storefront work

Product-level intent is documented in [./.project-workflow/CONSTITUTION.md](./.project-workflow/CONSTITUTION.md).
Implementation guidance lives in [./.github/copilot-instructions.md](./.github/copilot-instructions.md).

## Stack

- Shopify theme architecture using Liquid, JSON templates, sections, blocks, snippets, and locale files
- Shopify CLI for local development, preview, validation, pull, and push workflows

## Prerequisites

Install the current [Shopify CLI](https://shopify.dev/docs/api/shopify-cli).

If you use VS Code, install the [Shopify Liquid extension](https://shopify.dev/docs/storefronts/themes/tools/shopify-liquid-vscode) for Liquid syntax support, linting, inline docs, and autocomplete.

## Getting Started

Clone the repository and install any local tooling you use around Shopify theme development.

```bash
git clone git@github.com:johndetlefs/shopify-theme.git
cd shopify-theme
```

Connect the theme to a development store and start a local preview with Shopify CLI:

```bash
shopify theme dev
```

This will open a preview session and sync theme changes as you work.

## Shopify CLI Workflow

Use Shopify CLI as the default workflow for this project.

Start local development:

```bash
shopify theme dev
```

Pull the current remote theme state when needed:

```bash
shopify theme pull
```

Push local theme changes to a store theme:

```bash
shopify theme push
```

Run theme validation checks before shipping changes:

```bash
shopify theme check
```

List available themes for the connected store:

```bash
shopify theme list
```

You can add store-specific flags such as `--store=<your-store>` when your local CLI session is not already configured.

## Project Structure

```text
.
├── assets          Shared CSS, JavaScript, fonts, and images
├── blocks          Reusable nested theme blocks
├── config          Theme settings and editor configuration
├── layout          Global page wrappers
├── locales         Translation files for storefront text
├── sections        Configurable page modules
├── snippets        Shared partials and reusable Liquid fragments
└── templates       Template definitions for storefront routes
```

## Working Principles

When extending this theme, prefer:

- reusable sections and blocks over hardcoded page layouts
- merchant-readable schema settings and sensible defaults
- locale files for user-facing copy
- semantic HTML and accessible interaction patterns
- responsive styles that work across core storefront breakpoints
- minimal duplication across snippets, sections, and blocks

## References

- [Shopify theme architecture](https://shopify.dev/docs/storefronts/themes/architecture)
- [Shopify JSON templates](https://shopify.dev/docs/storefronts/themes/architecture/templates/json-templates)
- [Shopify sections](https://shopify.dev/docs/storefronts/themes/architecture/sections)
- [Shopify blocks](https://shopify.dev/docs/storefronts/themes/architecture/blocks)
- [Shopify CLI](https://shopify.dev/docs/api/shopify-cli)

## Contributing

Keep changes focused, reusable, and aligned with the starter-theme goal for agency client work. See [./CONTRIBUTING.md](./CONTRIBUTING.md) for the repository contribution process.

## License

This project is licensed under the [MIT License](./LICENSE.md).
