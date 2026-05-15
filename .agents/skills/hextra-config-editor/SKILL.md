---
name: hextra-config-editor
description: Use when an agent needs to edit `hugo.yaml` for this Hextra Hugo site instead of changing templates or content. Triggers include updating languages, menu items, banners, search, theme toggles, footer behavior, edit links, blog listing behavior, and other site-level settings where configuration should be preferred over layout customization.
---

# Hextra Config Editor

## Overview

Use this skill for site-level behavior that belongs in configuration.
Prefer config changes before theme overrides.

## Read Scope First

Read only:

- `hugo.yaml`
- the target docs page about configuration if context is needed
- related files only when a config key points to them

## Responsibilities

- edit `hugo.yaml`
- keep YAML structure clean and minimal
- preserve multilingual consistency
- prefer existing params and menu patterns

## Common Surfaces

- `languages`
- `menu`
- `params.navbar`
- `params.footer`
- `params.search`
- `params.theme`
- `params.editURL`
- `params.blog`
- `params.toc`
- `params.comments`

## Workflow

### 1. Confirm config is the right layer

Use config when the task is about:

- site navigation
- language setup
- search behavior
- footer or navbar options
- theme toggles
- site metadata

Escalate to theme customization only when config cannot express the change.

### 2. Patch the smallest surface

- modify only relevant keys
- preserve ordering style when practical
- avoid rewriting unrelated sections

### 3. Check downstream effects

Watch for impacts on:

- multilingual labels
- menu hierarchy
- search enablement
- links to external resources

## Guardrails

- do not move to layout overrides when config already supports the feature
- do not add duplicate params with competing meanings
- do not rename existing identifiers casually
- do not embed content that belongs in Markdown pages

## Completion Criteria

- requested behavior is represented in `hugo.yaml`
- YAML remains tidy
- affected languages and menus stay coherent
- no unnecessary template edits were introduced
