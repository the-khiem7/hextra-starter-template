---
name: hextra-ia-maintainer
description: Use when an agent needs to maintain content structure and navigation in this Hextra Hugo site while preserving the template's existing page roles. Triggers include adding or moving pages in docs or showcase sections, deciding between direct pages and hub pages, updating `_index` files, adjusting `weight`, and preserving breadcrumb and section navigation expectations while changing as little content as possible.
---

# Hextra IA Maintainer

## Overview

Use this skill for information architecture work.
It focuses on placement, ordering, and navigability.
Default posture: preserve existing page roles and local tree shape.

## Skill Boundaries

Use this skill when the main task is page placement, section shape, or discoverability.

Route elsewhere when needed:

- use `hextra-content-writer` when the page already lives in the right place and mainly needs content work
- use `hextra-content-translator` when the main task is syncing English/Vietnamese counterparts
- use `hextra-theme-customizer` only when discoverability requires a true presentation override rather than content, IA, or config changes

## Read Scope First

Read only:

- target section tree
- local `_index` files
- nearby sibling pages
- `hugo.yaml` menu when top-level navigation is involved

## Responsibilities

- place new pages in the right section
- classify page role before placing it
- maintain `_index` landing pages
- tune `weight` values for stable ordering
- keep docs and showcase navigation predictable
- avoid unnecessary moves or renames

## Workflow

### 1. Identify nav surface

Choose the smallest affected scope:

- local section only
- sidebar ordering
- top-level menu
- multilingual mirrored structure

### 2. Classify page role

Choose one:

- homepage
- direct page
- hub page

Rules:

- homepage = `content/_index.md` and localized variants; not a normal IA playground
- direct page = one topic, not primarily a child-page router
- hub page = parent topic entry that routes to child pages

### 3. Update section shape

Typical actions:

- add or edit `_index.md`
- add or adjust `weight`
- group related pages under a subfolder
- keep translated files mirrored

Placement defaults:

- use `_index.md` for hub pages
- use `index.md` or leaf page files for direct pages
- keep homepage at root and preserve its fixed role

Hub page defaults:

- short intro
- optional callout
- cards or simple links to child pages

Direct page defaults:

- content-first reading flow
- only enough navigation chrome to support the topic

### 4. Validate discoverability

Check that the page is easy to find through:

- section tree
- sidebar
- previous/next links when used
- breadcrumb-friendly placement

Check role fit too:

- direct pages should not become accidental hubs
- hub pages should not become long essays
- homepage should not be repurposed during ordinary IA work

## Guardrails

- do not treat homepage as a normal section landing page
- do not redesign the whole docs tree for a single new page
- do not convert a direct page into a hub page or vice versa without clear need
- do not create deep nesting without evidence from nearby patterns
- do not use `weight` values randomly; keep them locally coherent
- do not split bilingual pairs across different structures

## Decision Shortcuts

- "new top-level topic with child pages" -> create a hub page
- "new standalone page about one thing" -> create a direct page
- "edit homepage navigation/content" -> preserve homepage role and layout, avoid structural rewrites
- if unsure between direct and hub, optimize for current navigation need, not future speculation

## Completion Criteria

- page location fits section intent
- ordering is coherent
- `_index` files stay accurate
- page role is correct for its location
- multilingual structure remains mirrored where expected
