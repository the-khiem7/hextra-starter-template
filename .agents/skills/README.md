# Hextra Starter Skills

Core daily-use skills for authoring and maintaining this Hugo site with the Hextra theme.

## Skills

- `hextra-template-onboarding` — convert the starter into a first domain-specific infosite
- `hextra-content-writer` — create or update docs, blog, and showcase pages
- `hextra-content-translator` — sync English and Vietnamese content pairs
- `hextra-ia-maintainer` — maintain section structure, ordering, and navigation
- `hextra-config-editor` — edit `hugo.yaml` for menu, i18n, search, footer, and theme settings
- `hextra-theme-customizer` — apply minimal site-level theme overrides without over-customizing

## Suggested Workflow

Use the skills by phase, not all at once.

### 1. First-time template conversion

Start with `hextra-template-onboarding` when the site is still a starter or needs a full repurpose into a new domain infosite.

Use it to:

- decide the final homepage + root-level direct-page shape
- flatten or remove starter sections like `about`, `blog`, or `docs` when they no longer fit
- plan how provided assets should be copied and used in the site
- preserve the homepage as `hextra-home`
- define what downstream skills need to do next

### 2. Structure and placement

Use `hextra-ia-maintainer` when the main task is information architecture.

Use it to:

- flatten, move, delete, or create pages
- choose between direct pages and hub pages
- maintain `_index` behavior where needed
- keep navigation and ordering coherent

For large first-time conversions, let `hextra-template-onboarding` lead first, then use this skill for the concrete IA changes.

### 3. Content writing

Use `hextra-content-writer` after the site shape already makes sense.

Use it to:

- rewrite the homepage while preserving native Hextra layout
- write or revise direct pages
- keep front matter minimal and valid
- use Markdown and Hextra shortcodes in a pattern-aligned way

Do not use it as the primary skill for first-time starter-to-infosite conversion.

### 4. Bilingual synchronization

Use `hextra-content-translator` when English and Vietnamese counterparts must stay aligned.

Use it to:

- create missing `.vi.md` or `.md` counterparts
- keep structure mirrored across languages
- translate copy without changing page type

### 5. Config and navigation

Use `hextra-config-editor` when the required change belongs in `hugo.yaml`.

Use it to:

- update menu items
- adjust language config
- change footer, theme toggles, search, or similar config-backed settings

### 6. Theme-level changes

Use `hextra-theme-customizer` only when content, IA, assets, and config are not enough.

Use it for:

- small CSS overrides
- partial overrides
- narrowly scoped presentation changes

Do not use it for normal page writing or first-pass template conversion.

### 7. Final verification

After major conversion or content restructuring work:

- run Hugo build
- confirm homepage role is preserved
- confirm navigation points to the intended pages
- confirm assets resolve correctly
- confirm EN and VI structures still match

## Common Flows

### Starter template -> full infosite

`hextra-template-onboarding` -> `hextra-ia-maintainer` -> `hextra-content-writer` -> `hextra-content-translator` -> `hextra-config-editor` -> Hugo build

### Add or revise one page

`hextra-content-writer` -> `hextra-content-translator` if needed -> Hugo build

### Reorganize navigation or page placement

`hextra-ia-maintainer` -> `hextra-config-editor` if needed -> Hugo build

### Small visual override without redesign

`hextra-theme-customizer` after content/config options are ruled out

## Format

Each skill folder contains:

- `SKILL.md` — universal skill instructions
- `agents/openai.yaml` — Codex/OpenAI UI metadata
