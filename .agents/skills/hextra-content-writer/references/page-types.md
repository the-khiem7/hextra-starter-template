# Page Types Reference

Use this reference when classifying a page or choosing how much structure to add.

## Types

- homepage
- direct page
- hub page
- blog article
- showcase page

Do not start writing until one type is chosen.

## Direct Page

Use for a single topic or standalone section page.

Traits:

- focused on one subject
- normal reading flow
- may contain `callout`, `steps`, `details`, `tabs`, or light `cards` when content benefits
- does not exist primarily to route to child pages

Common destinations:

- leaf content pages like `content/about/index.md`
- dated articles under `content/blog/`
- standalone docs pages under a topic folder

Good defaults:

- plain Markdown for main flow
- `callout` for highlighted context
- `details` for side notes or optional depth
- `steps` for procedures
- `tabs` for parallel variants
- `term` for small definitions

Avoid:

- overusing `cards` when the page is not acting as a router
- decorative badges or icons with no reading benefit

## Hub Page

Use for a parent topic with child pages.

Traits:

- introduces the big topic briefly
- routes readers to children
- acts as landing/index for that subtree
- usually uses `_index.md`

Defaults:

- short intro
- optional `callout`
- `cards` or link list pointing to child pages
- occasional `filetree` if subtree structure itself matters

Guardrails:

- keep prose shorter than a direct page
- optimize for navigation first, explanation second
- do not turn a hub into a long essay
- avoid long tutorial-like flows
- avoid too many collapsible sections

## Location Defaults

- homepage lives at `content/_index.md`
- docs content belongs under `content/docs/`
- showcase content belongs under `content/showcase/`
- translated pages should use filename suffixes such as `.vi.md`
- hub pages typically use `_index.md`
- direct pages inside singleton sections may use `index.md`

## Decision Shortcuts

- "rewrite homepage" -> keep homepage format, replace copy only
- "create page about X" -> direct page unless child-page navigation is central
- "create section for X with child pages" -> hub page
- "make Vietnamese version" -> mirror the source file structure first, then translate content

If uncertain between direct page and hub page, ask:
"Is this page mainly for reading one topic, or mainly for routing to child pages?"
