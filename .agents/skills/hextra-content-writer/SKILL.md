---
name: hextra-content-writer
description: Use when an agent needs to create or revise everyday Hugo content in this Hextra site, especially docs, blog, or showcase pages from a short brief. Triggers include choosing the correct content path, writing front matter, preserving section conventions, selecting Hextra shortcodes such as callout, cards, and tabs, and keeping output aligned with the site's bilingual structure and navigation rules without reading the full repository.
---

# Hextra Content Writer

## Overview

Use this skill for routine content authoring.
It should favor existing site conventions over inventing new structure.

## Read Scope First

Read only the minimum set:

- `hugo.yaml`
- target file, if it already exists
- sibling pages in the same section
- relevant docs under `content/docs`

Do not scan the full repository unless the task clearly depends on it.

## Responsibilities

- choose the correct destination under `content/`
- write or update front matter
- keep headings, links, and page structure consistent
- use built-in Markdown and Hextra shortcodes when they improve readability
- preserve existing tone and language of the target page

## Authoring Workflow

### 1. Classify the page

Choose one:

- docs page
- blog article
- showcase page
- section landing page

### 2. Pick the correct location

Prefer existing section patterns.

- docs content belongs under `content/docs/`
- showcase content belongs under `content/showcase/`
- translated pages should use filename suffixes such as `.vi.md`
- section landing pages typically use `_index.md`

### 3. Write minimal correct front matter

Preserve or add only fields that matter for the page type, such as:

- `title`
- `weight`
- `date`
- `tags`
- `prev`
- `next`

Do not add speculative metadata.

### 4. Choose presentation

Prefer simple Markdown first.
Upgrade to Hextra features only when they clearly help:

- callout -> note, warning, tip
- cards -> navigation or feature lists
- tabs -> parallel variants such as OS or language choices
- filetree -> directory explanation

### 5. Link safely

- prefer internal links matching local section patterns
- keep multilingual page pairs structurally aligned
- avoid adding broken placeholders

## Guardrails

- do not invent new content architecture when an existing section pattern fits
- do not overuse shortcodes for plain prose
- do not mix English and Vietnamese in the same page unless the file already does so intentionally
- do not duplicate configuration or theme docs inside content pages

## Completion Criteria

- content placed in the right folder
- front matter is minimal and valid
- structure matches nearby pages
- shortcode use is intentional and minimal
- bilingual pairing is preserved when applicable
