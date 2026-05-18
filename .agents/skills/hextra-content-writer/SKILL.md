---
name: hextra-content-writer
description: Use when an agent needs to create or revise Hugo content in this Hextra site while preserving the template's existing page formats. Triggers include homepage copy swaps without layout rewrites, choosing between direct pages and hub pages, writing minimal front matter, preserving section conventions, selecting Hextra shortcodes only when already justified by local patterns, and keeping output aligned with the site's bilingual structure and navigation rules. Do not use it as the primary skill for first-time starter-to-infosite conversion; use `hextra-template-onboarding` first.
---

# Hextra Content Writer

## Overview

Use this skill for routine content authoring.
It should preserve the template's existing presentation before attempting any rewrite.
Default posture: replace content, not format.

## Skill Boundaries

Use this skill when the primary job is writing or revising page content.

Route elsewhere when needed:

- use `hextra-template-onboarding` for first-time starter/demo conversion, site-wide infosite repurposing, root-level direct-page planning, asset-driven page planning, and cleanup of obsolete template sections
- use `hextra-content-translator` for bilingual synchronization between `.md` and `.vi.md`
- use `hextra-ia-maintainer` when the main task is deciding placement, section shape, `_index` strategy, or ordering
- use `hextra-theme-customizer` only when content and `hugo.yaml` cannot express the required presentation change

## Read Scope First

Read only the minimum set:

- `hugo.yaml`
- target file, if it already exists
- sibling pages in the same section
- homepage counterpart if editing a homepage translation
- relevant files under the same content subtree
- `references/homepage.md` when editing the homepage
- `references/page-types.md` when deciding between direct page and hub page
- `references/shortcodes.md` when choosing components
- `references/rare-features.md` only when richer embeds or advanced blocks seem necessary

Do not scan the full repository unless the task clearly depends on it.

## Responsibilities

- choose the correct destination under `content/`
- classify the page shape before writing
- write or update front matter
- keep headings, links, shortcode blocks, and page structure consistent
- preserve existing wrapper/layout structure when a template already exists
- use built-in Markdown and Hextra shortcodes only when the local file pattern already supports them
- preserve existing tone and language of the target page
- use Hextra capabilities intentionally so the page feels native to the template, not generic Markdown-only content

## Authoring Workflow

### 1. Classify the page

Choose one using `references/page-types.md`:

- homepage
- direct page
- hub page
- blog article
- showcase page

Do not start writing until one type is chosen.

### 2. Apply the page-type rule

Use the matching reference:

- homepage -> `references/homepage.md`
- direct page or hub page -> `references/page-types.md`

### 3. Pick the correct location

Prefer existing section patterns.

- homepage lives at `content/_index.md`
- docs content belongs under `content/docs/`
- showcase content belongs under `content/showcase/`
- translated pages should use filename suffixes such as `.vi.md`
- hub pages typically use `_index.md`
- direct pages inside singleton sections may use `index.md`

### 4. Write minimal correct front matter

Preserve or add only fields that matter for the page type, such as:

- `title`
- `layout` when already required by the template, especially homepage
- `weight`
- `date`
- `tags`
- `prev`
- `next`

Do not add speculative metadata.

### 5. Choose presentation

Use `references/shortcodes.md`.
Read `references/rare-features.md` only if common blocks are not enough.

### 6. Link safely

- prefer internal links matching local section patterns
- keep multilingual page pairs structurally aligned
- avoid adding broken placeholders

## Guardrails

- do not act as the primary orchestration skill for first-time starter-to-infosite conversion
- do not invent new content architecture when an existing section pattern fits
- do not redesign homepage files when the request is only about content
- do not convert a homepage into a generic Markdown page
- do not convert a direct page into a hub page or vice versa unless the user asks
- do not mix English and Vietnamese in the same page unless the file already does so intentionally
- do not duplicate configuration or theme docs inside content pages

## Decision Shortcuts

See `references/page-types.md`.

## Completion Criteria

- content placed in the right folder
- front matter is minimal and valid
- page type is correctly classified
- homepage layout structure is preserved when applicable
- structure matches nearby pages
- shortcode use is intentional, minimal, and pattern-aligned
- bilingual pairing is preserved when applicable
