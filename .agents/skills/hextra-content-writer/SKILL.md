---
name: hextra-content-writer
description: Use when an agent needs to create or revise Hugo content in this Hextra site while preserving the template's existing page formats. Triggers include homepage copy swaps without layout rewrites, choosing between direct pages and hub pages, writing minimal front matter, preserving section conventions, selecting Hextra shortcodes only when already justified by local patterns, and keeping output aligned with the site's bilingual structure and navigation rules.
---

# Hextra Content Writer

## Overview

Use this skill for routine content authoring.
It should preserve the template's existing presentation before attempting any rewrite.
Default posture: replace content, not format.

## Skill Boundaries

Use this skill when the primary job is writing or revising page content.

Route elsewhere when needed:

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

Choose one:

- homepage
- direct page
- hub page
- blog article
- showcase page

Do not start writing until one type is chosen.

### 2. Apply the page-type rule

#### Homepage

Homepages in this template are format-sensitive.
Treat `content/_index.md` and localized variants such as `content/_index.vi.md` as fixed-layout files.

Allowed homepage edits:

- title in front matter
- quote or short hero support text
- CTA button text/link
- feature card titles, subtitles, optional images
- translated counterparts with the same block structure

Homepage guardrails:

- do not replace `layout: hextra-home`
- do not change shortcode block order
- do not collapse hero sections into plain Markdown headings
- do not swap homepage components for a different layout style
- do not remove feature-grid structure unless the user explicitly requests a redesign
- do not introduce new homepage sections just because content is sparse

Rule of thumb: keep the skeleton, swap the words.

#### Direct page

Use for a single topic or standalone section page.

Traits:

- focused on one subject
- normal reading flow
- may contain callout, steps, details, tabs, or cards when content benefits
- does not exist primarily to route to child pages

Common destinations:

- leaf content pages like `content/about/index.md`
- dated articles under `content/blog/`
- standalone docs pages under a topic folder

#### Hub page

Use for a parent topic with child pages.

Traits:

- introduces the big topic briefly
- routes readers to children
- acts as landing/index for that subtree
- usually uses `_index.md`

Hub page defaults:

- short intro
- optional callout
- cards or link list pointing to child pages

Hub page guardrails:

- keep prose shorter than a direct page
- optimize for navigation first, explanation second
- do not turn a hub into a long essay

### 3. Know the Hextra authoring surface

Use this compressed map of Hextra features when choosing how to write.
The goal is not to use more components.
The goal is to choose the smallest component that makes the page clearer.

#### Core writing blocks

- plain Markdown -> default for normal prose, headings, lists, tables, code blocks, images
- `callout` -> note, warning, important caveat, or highlighted tip
- `details` -> collapsible secondary information that should not interrupt flow
- `steps` -> ordered procedural guidance with named steps
- `tabs` -> parallel variants such as OS, framework, language, or mode

#### Navigation and structure blocks

- `cards` / `card` -> hub-page navigation, feature lists, next-step choices
- `filetree` -> explain directory structure or nested content trees
- `term` -> lightweight inline glossary or definition hint

#### Visual and semantic accents

- `icon` -> small semantic cue when nearby patterns already use icons
- `badge` -> compact status/tag/accent, not for core body prose

#### Rich embeds and advanced blocks

- `pdf` -> embed a PDF only when the document itself is primary content
- `jupyter` -> notebook-heavy technical content only
- video/embed helpers -> only when the page depends on the media, not as decoration

#### Homepage-only primitives

- `hextra/hero-badge`
- `hextra/hero-headline`
- `hextra/hero-subtitle`
- `hextra/hero-button`
- `hextra/feature-grid`
- `hextra/feature-card`

Homepage primitives are special.
Do not introduce them casually into regular direct pages or hub pages unless the local section already does so.

### 4. Pick the correct location

Prefer existing section patterns.

- homepage lives at `content/_index.md`
- docs content belongs under `content/docs/`
- showcase content belongs under `content/showcase/`
- translated pages should use filename suffixes such as `.vi.md`
- hub pages typically use `_index.md`
- direct pages inside singleton sections may use `index.md`

### 5. Write minimal correct front matter

Preserve or add only fields that matter for the page type, such as:

- `title`
- `layout` when already required by the template, especially homepage
- `weight`
- `date`
- `tags`
- `prev`
- `next`

Do not add speculative metadata.

### 6. Choose presentation

Prefer simple Markdown first.
Upgrade to Hextra features only when they clearly help:

- callout -> note, warning, tip
- details -> optional depth without cluttering the main flow
- steps -> procedures, onboarding, tutorials, checklists with sequence
- cards -> hub navigation or feature lists
- tabs -> parallel variants such as OS or language choices
- filetree -> directory explanation
- term -> short inline definition
- badge/icon -> compact accents only when they improve scanability

Presentation priority:

1. preserve existing page skeleton
2. preserve nearby section pattern
3. simplify content before adding shortcodes
4. add shortcodes only when they solve a clear reading or navigation problem

### 7. Choose components by page type

#### Homepage

- preserve the existing hero/feature skeleton
- vary the copy, CTA, and feature-card content
- optional feature-card image changes are acceptable
- do not improvise a new component system

#### Direct page

Good defaults:

- plain Markdown for main flow
- `callout` for highlighted context
- `details` for side notes or optional depth
- `steps` for procedures
- `tabs` for parallel variants
- `term` for small definitions

Avoid:

- overusing `cards` when the page is not acting as a router
- decorative badges/icons with no reading benefit

#### Hub page

Good defaults:

- short intro paragraph
- optional `callout`
- `cards` for child-page navigation
- occasional `filetree` if the subtree structure itself matters

Avoid:

- long tutorial-like flows
- too many collapsible sections
- turning navigation surfaces into essay pages

### 8. Link safely

- prefer internal links matching local section patterns
- keep multilingual page pairs structurally aligned
- avoid adding broken placeholders

## Rare Features

These are valid Hextra features, but use them only with strong content-driven reason:

- `jupyter` for notebook-first technical pages
- `pdf` when the embedded document is the subject
- advanced homepage `hextra/*` blocks outside root homepage only when the existing local pattern already proves that choice
- theme-level customization is not part of this skill; route to `hextra-theme-customizer` only after content and config options fail

## Guardrails

- do not invent new content architecture when an existing section pattern fits
- do not redesign homepage files when the request is only about content
- do not convert a homepage into a generic Markdown page
- do not convert a direct page into a hub page or vice versa unless the user asks
- do not overuse shortcodes for plain prose
- do not treat every available Hextra shortcode as an invitation to use it
- do not use rich embeds or visual accents when plain Markdown communicates better
- do not mix English and Vietnamese in the same page unless the file already does so intentionally
- do not duplicate configuration or theme docs inside content pages

## Decision Shortcuts

Use these defaults when the user is brief:

- "rewrite homepage" -> keep homepage format, replace copy only
- "create page about X" -> direct page unless child-page navigation is central
- "create section for X with child pages" -> hub page
- "make Vietnamese version" -> mirror the source file structure first, then translate content

If uncertain between direct page and hub page, ask:
"Is this page mainly for reading one topic, or mainly for routing to child pages?"

## Completion Criteria

- content placed in the right folder
- front matter is minimal and valid
- page type is correctly classified
- homepage layout structure is preserved when applicable
- structure matches nearby pages
- shortcode use is intentional, minimal, and pattern-aligned
- bilingual pairing is preserved when applicable
