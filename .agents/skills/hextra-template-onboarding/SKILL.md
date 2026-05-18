---
name: hextra-template-onboarding
description: Use when an agent needs to convert a Hextra starter or partially converted template into a first complete infosite for a new domain. Triggers include replacing demo/starter content site-wide, preserving the homepage as `hextra-home`, flattening unnecessary hub trees into root-level direct pages, mapping a provided asset folder into page content, cleaning obsolete sections such as `about`, `blog`, or `docs` when they no longer fit, mirroring the final structure across English and Vietnamese, and verifying the result with a Hugo build.
---

# Hextra Template Onboarding

## Overview

Use this skill for first-pass site conversion.
It turns a Hextra starter or generic content set into a domain-specific infosite.
Default posture: repurpose the site with minimal structural drift from native Hextra, then hand page writing to the existing content and IA skills.

## Skill Boundaries

Use this skill when the main job is onboarding a new domain onto the template.

Route elsewhere when needed:

- use `hextra-content-writer` for routine page writing after the site shape already makes sense
- use `hextra-ia-maintainer` for isolated placement or ordering changes inside an already-converted site
- use `hextra-content-translator` when the main task is only syncing an existing English/Vietnamese pair
- use `hextra-config-editor` when the work is limited to `hugo.yaml`
- use `hextra-theme-customizer` only when content, IA, assets, and config cannot solve the requirement

## Required Inputs

Expect these inputs before or during execution:

- primary domain or topic for the site
- asset folder containing screenshots, images, or other reusable visuals
- optional target tone
- optional target audience
- optional priority content pillars or topic groups

If some optional inputs are missing, infer conservatively from the domain and available assets.

## Read Scope First

Read only the minimum needed to classify and convert the site:

- `hugo.yaml`
- `content/_index.md`
- `content/_index.vi.md` if present
- current top-level content tree under `content/`
- top-level menu config in `hugo.yaml`
- the provided asset folder
- `hextra-content-writer/references/homepage.md`
- `hextra-content-writer/references/page-types.md`
- nearby starter pages only when deciding whether to keep, rewrite, move, or delete them

Do not scan unrelated parts of the repository unless the conversion task truly depends on them.

## Responsibilities

- classify whether the current site is a starter template, partial conversion, or mature infosite
- choose a final infosite shape centered on homepage plus a small set of root-level direct pages
- preserve the homepage as a homepage, not a hub page
- flatten unnecessary starter IA when direct pages are sufficient
- decide which starter/demo sections to delete, replace, or keep
- map provided assets into the new page plan and place visuals directly inside page content
- coordinate with `hextra-content-writer` for page writing
- coordinate with `hextra-ia-maintainer` for flattening, moves, deletes, and root-level placement
- preserve bilingual EN + VI structure
- update navigation so it points to the final root-level direct pages
- verify the final site with a Hugo build

## Onboarding Workflow

### 1. Classify the current site state

Choose one:

- starter template
- partially converted site
- already mature infosite

Starter signals:

- demo copy still dominates homepage or direct pages
- sections like `about`, `blog`, `docs`, or showcase content exist mainly as template examples
- top-level navigation reflects generic starter IA more than the target domain

If the site is already mature, stop using this skill unless the request is a true re-onboarding.

### 2. Lock the target page model

Default target:

- `content/_index.md`
- `content/_index.vi.md`
- a compact set of root-level direct pages
- mirrored `.vi.md` counterparts

Prefer:

- homepage as landing page
- direct pages at root level
- practical infosite reading flow

Avoid by default:

- deep `docs/` trees
- multi-level hubs without clear need
- leftover starter sections that do not serve the domain

Only keep `about`, `blog`, `docs`, or other starter sections if they are clearly necessary for the new site.

### 3. Choose the final content pillars

Derive direct-page topics from the provided domain, audience, tone, and assets.

Good default shapes include domain-specific versions of:

- overview or fundamentals
- setup or onboarding
- implementation or workflow
- operations or best practices

Do not hardcode these names if the real domain suggests better axes.

Keep the final set intentionally small and useful.

### 4. Preserve homepage role and rewrite intent

Treat `content/_index.md` and `content/_index.vi.md` as fixed-layout homepage files.

Homepage rules:

- preserve `layout: hextra-home` when present or required
- replace all demo/starter copy
- hero must clearly state the site is a landing page, guide, or deep-dive resource for the chosen domain
- feature cards must reflect real domain steps or themes
- homepage should summarize and route to the direct pages
- homepage must not become a generic hub or long free-form article

Use `hextra-content-writer` homepage guidance when writing the actual homepage content.

### 5. Flatten IA deliberately

Use `hextra-ia-maintainer` rules to decide what stays at root and what should be removed.

Default IA decisions:

- prefer root-level direct pages over section hubs
- remove unneeded demo trees
- keep bilingual pairs mirrored
- avoid creating nesting unless the topic genuinely requires children

Typical actions:

- delete obsolete starter pages
- move or replace pages that should become root-level direct pages
- adjust menu targets to point at the final direct pages

### 6. Map assets into the site

Treat the provided asset folder as first-class input.

Asset rules:

- copy only the assets actually used
- place them in a stable `static/` path that matches site conventions
- assign visuals to homepage sections and direct pages intentionally
- embed images directly inside page content where they support the explanation
- do not leave visuals as an unused dump in `static/`

Image placement should be contextual:

- hero-support image on homepage when appropriate
- screenshots in setup or workflow pages
- diagrams or UI captures near the section they explain

### 7. Write content through downstream skills

After site shape is chosen:

- use `hextra-content-writer` to rewrite homepage and direct pages
- use `hextra-content-translator` to create or sync `.vi.md` counterparts when needed
- use `hextra-config-editor` if `hugo.yaml` menu or language config must change

Authoring expectations:

- practical, specific, content-rich pages
- no placeholder or demo language
- visuals integrated into the narrative
- minimal valid front matter
- native Hextra structure preserved

### 8. Clean starter residue

Before finishing, remove or replace starter artifacts that no longer fit:

- irrelevant top-level pages
- demo links in navigation
- placeholder copy
- unused mirrored pages that only preserve the old template story

Do not leave the site in a mixed starter/domain state.

### 9. Verify the result

Run a Hugo build after the conversion work is complete.

Validation goals:

- no build errors
- homepage still uses the intended layout
- navigation resolves to the final direct pages
- images resolve from their new static paths
- EN and VI structures remain mirrored where expected

## Decision Shortcuts

- "convert starter into full domain site" -> use this skill first
- "rewrite homepage but keep layout" -> homepage stays `hextra-home`
- "flatten starter docs/blog/about into a few root pages" -> use this skill plus `hextra-ia-maintainer`
- "use screenshots from a folder across the site" -> this skill owns asset mapping, then hands page writing to `hextra-content-writer`
- "add one more page after conversion is done" -> use `hextra-content-writer`, not this skill

## Guardrails

- do not redesign the theme if content, IA, assets, and config already solve the problem
- do not repurpose the homepage into a normal hub page
- do not preserve demo sections out of inertia
- do not create deep navigation just because the starter shipped with it
- do not leave asset usage implicit; place visuals where they support the content
- do not split English and Vietnamese structures during conversion
- do not stop at copy replacement if the site shape still reflects the starter

## Completion Criteria

- homepage remains a homepage and reflects the new domain
- final structure is centered on homepage plus root-level direct pages
- obsolete starter/demo content is removed or fully replaced
- assets from the provided folder are copied and used contextually
- navigation points to the final direct pages
- English and Vietnamese structures are mirrored
- downstream writing and IA work have been applied where needed
- Hugo build completes successfully
