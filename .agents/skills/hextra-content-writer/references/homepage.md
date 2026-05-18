# Homepage Reference

Use this reference when the target is `content/_index.md` or a localized homepage variant such as `content/_index.vi.md`.

## Scope

Homepages in this template are format-sensitive.
Treat the homepage as a fixed-layout file.

## Allowed Edits

- front matter `title`
- quote or short hero support text
- CTA button text and link
- feature-card titles and subtitles
- optional feature-card image swaps
- localized counterparts with the same block structure

## Required Structure

Preserve:

- `layout: hextra-home`
- hero block order
- CTA block position
- feature grid skeleton
- localized file parity

Rule of thumb: keep the skeleton, swap the words.

## Homepage-Only Primitives

These blocks belong to the homepage pattern in this template:

- `hextra/hero-badge`
- `hextra/hero-headline`
- `hextra/hero-subtitle`
- `hextra/hero-button`
- `hextra/feature-grid`
- `hextra/feature-card`

Do not introduce them casually into regular direct pages or hub pages unless the local section already proves that pattern.

## Guardrails

- do not replace `layout: hextra-home`
- do not change shortcode block order
- do not collapse hero sections into plain Markdown headings
- do not swap homepage components for a different layout style
- do not remove feature-grid structure unless the user explicitly requests a redesign
- do not introduce new homepage sections just because content is sparse
