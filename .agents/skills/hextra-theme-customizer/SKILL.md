---
name: hextra-theme-customizer
description: Use when an agent needs small, site-level Hextra presentation overrides that cannot be solved cleanly in `hugo.yaml` or page content alone. Triggers include custom CSS variables, footer partials, head-end scripts, and narrowly scoped layout overrides, with an emphasis on minimal customization and avoiding unnecessary divergence from the upstream Hextra theme.
---

# Hextra Theme Customizer

## Overview

Use this skill only after content and config options are insufficient.
It should minimize drift from upstream Hextra.

## Read Scope First

Read only the files needed for the chosen override path:

- `hugo.yaml`
- existing custom CSS or partials
- the exact layout or partial being overridden
- the relevant customization docs page when needed

## Preferred Override Order

1. content and shortcode choice
2. `hugo.yaml` configuration
3. custom CSS variables or selectors
4. custom partials under `layouts/_partials/custom/`
5. full layout override as last resort

## Responsibilities

- choose the lightest viable customization layer
- keep overrides site-specific
- preserve maintainability during future theme upgrades

## Common Surfaces

- `assets/css/custom.css`
- `layouts/_partials/custom/head-end.html`
- `layouts/_partials/custom/footer.html`
- mirrored layout files under `layouts/`

## Guardrails

- do not override a full layout when a small partial or CSS variable is enough
- do not duplicate large upstream templates without strong reason
- do not hardcode content that belongs in Markdown or config
- do not introduce custom scripts when plain HTML or CSS solves the need

## Completion Criteria

- smallest override layer was chosen
- customization is easy to locate
- upstream divergence is minimized
- config and content remain the first-class source of truth
