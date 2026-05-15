---
name: hextra-ia-maintainer
description: Use when an agent needs to maintain content structure and navigation in this Hextra Hugo site. Triggers include adding or moving pages in docs or showcase sections, updating `_index` files, adjusting `weight`, keeping sidebar and section ordering coherent, and preserving breadcrumb and section navigation expectations while changing as little content as possible.
---

# Hextra IA Maintainer

## Overview

Use this skill for information architecture work.
It focuses on placement, ordering, and navigability.

## Read Scope First

Read only:

- target section tree
- local `_index` files
- nearby sibling pages
- `hugo.yaml` menu when top-level navigation is involved

## Responsibilities

- place new pages in the right section
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

### 2. Update section shape

Typical actions:

- add or edit `_index.md`
- add or adjust `weight`
- group related pages under a subfolder
- keep translated files mirrored

### 3. Validate discoverability

Check that the page is easy to find through:

- section tree
- sidebar
- previous/next links when used
- breadcrumb-friendly placement

## Guardrails

- do not redesign the whole docs tree for a single new page
- do not create deep nesting without evidence from nearby patterns
- do not use `weight` values randomly; keep them locally coherent
- do not split bilingual pairs across different structures

## Completion Criteria

- page location fits section intent
- ordering is coherent
- `_index` files stay accurate
- multilingual structure remains mirrored where expected
