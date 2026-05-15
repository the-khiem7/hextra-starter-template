# Hextra Content Migration Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Migrate all public English content and required supporting assets/config from `../hextra/docs` into `hextra-starter-template` while keeping future English–Vietnamese support possible.

**Architecture:** Treat `hextra/docs/content` and `hextra/docs/static` as the source of truth for public site material. Copy only English content plus page-supporting assets into the starter site, then selectively merge Hugo config for menus, outputs, params, and future multilingual scaffolding without copying theme internals.

**Tech Stack:** Hugo, Hugo Modules, Hextra theme, Markdown content, YAML config

---

### Task 1: Replace starter content tree

**Files:**
- Modify: `hextra-starter-template/content/**`
- Source: `hextra/docs/content/**`

- [ ] Remove starter demo pages that conflict with migrated structure.
- [ ] Copy English homepage, docs, blog, about, showcase, archives, and glossary content.
- [ ] Skip non-English variants during this pass.

### Task 2: Copy site-supporting static assets

**Files:**
- Create/Modify: `hextra-starter-template/static/**`
- Source: `hextra/docs/static/**`

- [ ] Copy docs-site static assets needed by migrated pages.
- [ ] Preserve relative paths expected by homepage and section content.

### Task 3: Merge Hugo configuration

**Files:**
- Modify: `hextra-starter-template/hugo.yaml`
- Source: `hextra/docs/hugo.yaml`

- [ ] Keep module import of `github.com/imfing/hextra`.
- [ ] Add outputs, enableGitInfo, menus, params, and content behavior required by migrated content.
- [ ] Add multilingual-ready `languages.en` and `languages.vi` scaffolding while migrating English content only.
- [ ] Keep Hextra branding temporarily.

### Task 4: Build and repair

**Files:**
- Verify: `hextra-starter-template/**`

- [ ] Run Hugo module tidy if needed.
- [ ] Build site.
- [ ] Fix broken paths/config blockers found during build.

### Task 5: Update baseline if execution changes reality

**Files:**
- Optional Modify: `migration/*.md`

- [ ] Reflect any major migration reality discovered during execution.
