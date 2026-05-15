---
name: hextra-content-translator
description: Use when an agent needs to translate or synchronize paired Hextra Hugo content between English and Vietnamese in this site. Triggers include creating a missing `.vi.md` or `.md` counterpart, updating one language after the other changed, preserving headings, shortcodes, links, and front matter semantics, and keeping multilingual navigation consistent without rereading unrelated parts of the repository.
---

# Hextra Content Translator

## Overview

Use this skill to keep bilingual content pairs in sync.
It is for structural translation, not free-form rewriting.

## Read Scope First

Read only:

- source page
- target translation page, if present
- `hugo.yaml` language config
- sibling translated pages only when needed for tone or naming

## Responsibilities

- create the paired translation file when missing
- preserve meaning, hierarchy, and formatting
- preserve shortcode structure unless localization requires tiny wording changes
- keep front matter equivalent across languages unless a field is intentionally language-specific

## Translation Workflow

### 1. Detect source and target

Common pairs:

- `page.md` <-> `page.vi.md`
- `_index.md` <-> `_index.vi.md`

### 2. Preserve structure

Keep aligned:

- heading levels
- lists
- tables
- code fences
- shortcodes
- image references

### 3. Localize correctly

Translate:

- titles
- prose
- callout labels when written as content
- menu-facing copy inside the page

Do not translate:

- code
- file paths
- shortcode names
- front matter keys

### 4. Reconcile front matter

Usually preserve:

- `weight`
- `date`
- `tags` when taxonomy is shared
- `prev`
- `next`

Translate only values that are user-facing, such as `title`.

## Guardrails

- do not paraphrase so much that page structure drifts
- do not silently drop blocks that are hard to translate
- do not break shortcode syntax
- do not localize slugs or paths unless the site already follows that pattern

## Completion Criteria

- both language files exist when expected
- structure remains aligned
- user-facing text is translated
- non-translatable syntax remains intact
- navigation semantics still match
