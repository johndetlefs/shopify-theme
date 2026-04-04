# Copilot Instructions

This file defines technical implementation guidance for this repository.
Project outcomes and product intent live in /.project-workflow/CONSTITUTION.md.

## Scope

- This repository is a Shopify theme based on Shopify Skeleton Theme.
- Keep the codebase minimal, modular, and easy to reuse across client projects.

## Architecture Conventions

- Use Shopify theme directory responsibilities consistently:
  - assets for shared CSS, JS, images, fonts
  - layout for page wrappers
  - templates for page template JSON or Liquid
  - sections for configurable page modules
  - blocks for reusable nested content units
  - snippets for shared partials
  - locales for translation strings
  - config for theme and editor settings
- Prefer JSON templates and schema-driven customization where applicable.

## Liquid and Schema Guidance

- Keep sections and blocks editor-friendly with clear, merchant-readable setting labels.
- Prefer composable blocks and sections over hardcoded page structures.
- Use schema defaults that produce sensible storefront output with minimal setup.
- Reuse snippets before introducing duplicate markup.

## CSS and Frontend Guidance

- Prioritize responsive behavior for mobile, tablet, and desktop.
- Keep critical, global styles in assets/critical.css when needed across all pages.
- Use CSS custom properties for single-value theme settings where practical.
- Use classes for setting combinations that control multiple visual properties.

## Accessibility Guidance

- Target WCAG 2.2 AA for core storefront templates and shared components.
- Preserve semantic HTML structure and keyboard accessibility.
- Ensure interactive controls have accessible names and visible focus states.
- Validate color contrast for text and controls against chosen theme palettes.

## Localization Guidance

- Store user-facing strings in locale files, not hardcoded in templates.
- Keep locale keys structured and reusable across sections and snippets.
- Ensure new features can be translated without structural refactors.

## Quality and Workflow

- Keep changes focused and avoid unrelated refactors.
- Preserve existing public schema and setting IDs unless migration is intentional.
- Use Shopify CLI workflows for local preview and deployment validation.
- Prefer simple, maintainable solutions over heavy abstractions.
