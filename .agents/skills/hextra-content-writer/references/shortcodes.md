# Shortcodes Reference

Use this reference when choosing presentation.

The goal is not to use more components.
The goal is to choose the smallest component that makes the page clearer.

## Core Writing Blocks

- plain Markdown -> default for prose, headings, lists, tables, code blocks, images
- `callout` -> note, warning, important caveat, highlighted tip
- `details` -> collapsible secondary information that should not interrupt flow
- `steps` -> ordered procedural guidance with named steps
- `tabs` -> parallel variants such as OS, framework, language, or mode

## Navigation and Structure

- `cards` / `card` -> hub-page navigation, feature lists, next-step choices
- `filetree` -> explain directory structure or nested content trees
- `term` -> lightweight inline glossary or definition hint

## Visual and Semantic Accents

- `icon` -> small semantic cue when nearby patterns already use icons
- `badge` -> compact status, tag, or accent, not for core body prose

## Presentation Heuristics

Prefer simple Markdown first.
Upgrade to Hextra features only when they clearly help:

- `callout` -> note, warning, tip
- `details` -> optional depth without cluttering the main flow
- `steps` -> procedures, onboarding, tutorials, checklists with sequence
- `cards` -> hub navigation or feature lists
- `tabs` -> parallel variants such as OS or language choices
- `filetree` -> directory explanation
- `term` -> short inline definition
- `badge` / `icon` -> compact accents only when they improve scanability

Presentation priority:

1. preserve existing page skeleton
2. preserve nearby section pattern
3. simplify content before adding shortcodes
4. add shortcodes only when they solve a clear reading or navigation problem

## Guardrails

- do not overuse shortcodes for plain prose
- do not treat every available Hextra shortcode as an invitation to use it
- do not use visual accents when plain Markdown communicates better
