---
name: hextra-content-translator
description: Use when an agent needs to translate or synchronize paired Hextra Hugo content between English and Vietnamese in this site while preserving the original page type and template structure. Triggers include creating a missing `.vi.md` or `.md` counterpart, syncing homepage copy without rewriting homepage layout, preserving direct-page versus hub-page behavior, and keeping multilingual navigation consistent without rereading unrelated parts of the repository.
---

# Hextra Content Translator

## Overview

Use this skill to keep bilingual content pairs in sync.
It is for structural translation, not free-form rewriting.
Default posture: translate the content model exactly before improving wording.

## Skill Boundaries

Use this skill when the main task is keeping English/Vietnamese counterparts aligned.

Route elsewhere when needed:

- use `hextra-content-writer` for net-new monolingual writing or major content revision in one language
- use `hextra-ia-maintainer` when the main issue is page placement, hub/direct structure, or section ordering
- use `hextra-theme-customizer` only when the translation request exposes a real presentation problem that content/config cannot solve

## Read Scope First

Read only:

- source page
- target translation page, if present
- `hugo.yaml` language config
- sibling translated pages only when needed for tone or naming

## Responsibilities

- create the paired translation file when missing
- preserve the source page type
- preserve meaning, hierarchy, and formatting
- preserve shortcode structure unless localization requires tiny wording changes
- keep front matter equivalent across languages unless a field is intentionally language-specific

## Translation Workflow

### 1. Detect source and target

Common pairs:

- `page.md` <-> `page.vi.md`
- `_index.md` <-> `_index.vi.md`

### 2. Detect page type before translating

Choose one from the source page:

- homepage
- direct page
- hub page
- blog article
- showcase page

Page-type invariant:

- homepage stays homepage
- direct page stays direct page
- hub page stays hub page

Do not translate first and classify later.

### 3. Preserve structure

Keep aligned:

- heading levels
- lists
- tables
- code fences
- shortcodes
- image references

Homepage rule:

- treat `content/_index.md` and `content/_index.vi.md` as fixed-layout twins
- preserve `layout: hextra-home`
- preserve hero/CTA/feature-grid block order
- translate hero text, CTA text, feature-card text, optional image choices only

Direct-page rule:

- preserve reading flow and section hierarchy
- keep supporting blocks like callout, details, steps, or tabs in the same role

Hub-page rule:

- preserve landing-page behavior
- keep intro short
- keep child-page routing blocks such as cards or link lists aligned
- do not translate a hub into a long standalone article

### 4. Localize correctly

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

### 5. Reconcile front matter

Usually preserve:

- `layout`, especially homepage layout
- `weight`
- `date`
- `tags` when taxonomy is shared
- `prev`
- `next`

Translate only values that are user-facing, such as `title`.

## Guardrails

- do not paraphrase so much that page structure drifts
- do not change page type during translation
- do not rewrite homepage layout while translating homepage copy
- do not silently drop blocks that are hard to translate
- do not break shortcode syntax
- do not localize slugs or paths unless the site already follows that pattern

## Decision Shortcuts

- `content/_index.md` -> `content/_index.vi.md` = preserve full homepage skeleton, translate copy only
- `_index.md` under a topic folder = assume hub page unless local content proves otherwise
- `index.md` or leaf `page.md` = assume direct page unless child-page routing is the main job
- when one language adds a block, mirror the block first, then translate inside it

## Completion Criteria

- both language files exist when expected
- page type remains matched across languages
- structure remains aligned
- user-facing text is translated
- non-translatable syntax remains intact
- navigation semantics still match
