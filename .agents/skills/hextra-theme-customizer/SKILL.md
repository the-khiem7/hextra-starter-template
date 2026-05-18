---
name: hextra-theme-customizer
description: Use when an agent needs small, site-level Hextra presentation overrides that cannot be solved cleanly in `hugo.yaml` or page content alone. Triggers include custom CSS variables, footer partials, head-end scripts, and narrowly scoped layout overrides. Do not use it for ordinary content rewrites, homepage copy swaps, or direct-page versus hub-page decisions; prefer content and IA skills first.
---

# Hextra Theme Customizer

## Overview

Use this skill only after content and config options are insufficient.
It should minimize drift from upstream Hextra.
Default posture: if the request can be solved in Markdown, front matter, shortcode choice, or `hugo.yaml`, do not customize the theme.

## Skill Boundaries

Use this skill only for true presentation-layer work.

Route elsewhere when needed:

- use `hextra-content-writer` for homepage copy, feature-card text, and normal page content revisions
- use `hextra-content-translator` for English/Vietnamese synchronization
- use `hextra-ia-maintainer` for direct-page versus hub-page decisions, section placement, `_index` strategy, or ordering

## Read Scope First

Read only the files needed for the chosen override path:

- `hugo.yaml`
- target content file when deciding whether this is really a content problem
- existing custom CSS or partials
- the exact layout or partial being overridden
- the relevant customization docs page when needed

## First Decision: Is this really a theme task?

Before editing theme files, classify the request:

- content-only change
- IA/content-structure change
- config change
- true theme customization

Route by default:

- homepage title, quote, CTA, feature-card copy -> content task, not theme task
- deciding between direct page and hub page -> IA/content task, not theme task
- changing menu, languages, theme toggles, banner, footer config -> `hugo.yaml` task, not theme override
- changing visual presentation that content/config cannot express -> theme task

If the request is content-only, stop using this skill and switch to the content skill.

## Preferred Override Order

1. content and shortcode choice
2. `hugo.yaml` configuration
3. custom CSS variables or selectors
4. custom partials under `layouts/_partials/custom/`
5. full layout override as last resort

## Responsibilities

- choose the lightest viable customization layer
- reject theme edits when content or config already solves the request
- keep overrides site-specific
- preserve maintainability during future theme upgrades

## Common Surfaces

- `assets/css/custom.css`
- `layouts/_partials/custom/head-end.html`
- `layouts/_partials/custom/footer.html`
- mirrored layout files under `layouts/`

## Guardrails

- do not use theme overrides for homepage copy updates
- do not use theme overrides to reshape direct pages or hub pages
- do not touch theme files when the user only wants different content inside an existing template
- do not override a full layout when a small partial or CSS variable is enough
- do not duplicate large upstream templates without strong reason
- do not hardcode content that belongs in Markdown or config
- do not introduce custom scripts when plain HTML or CSS solves the need

## Decision Shortcuts

- "rewrite homepage" -> edit `content/_index.md`, not theme files
- "translate homepage" -> edit `content/_index.vi.md`, not theme files
- "add child-page landing" -> use hub page content/IA work, not theme files
- "change spacing/color/footer rendering globally" -> likely theme customization
- "make homepage a different layout" -> only then consider theme work, after checking config/content limits

## Completion Criteria

- smallest override layer was chosen
- content/config alternatives were ruled out first
- customization is easy to locate
- upstream divergence is minimized
- config and content remain the first-class source of truth
