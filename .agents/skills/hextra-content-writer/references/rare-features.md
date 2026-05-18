# Rare Features Reference

Use this reference only when the page genuinely needs richer content than the common authoring surface.

## Rich Embeds and Advanced Blocks

- `pdf` -> embed a PDF only when the document itself is primary content
- `jupyter` -> notebook-heavy technical content only
- video and embed helpers -> only when the page depends on the media, not as decoration

## Usage Rule

These are valid Hextra features, but use them only with strong content-driven reason.

Prefer ordinary Markdown and common shortcodes unless the richer block materially improves the page.

## Guardrails

- do not use rich embeds just because they are available
- do not use advanced homepage `hextra/*` blocks outside the root homepage unless the local pattern already proves that choice
- theme-level customization is not part of this skill; route to `hextra-theme-customizer` only after content and config options fail
