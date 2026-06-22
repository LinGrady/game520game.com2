# AdSense Site Restructure Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Rework Game520 News Hub into a focused software-engineering practice site for AdSense review.

**Architecture:** Keep static HTML and existing CSS. Rebuild public entry pages around engineering decision clusters, add recent practical articles, and update sitemap links without touching `ads.txt`.

**Tech Stack:** Static HTML, existing `css/style.css`, XML sitemap, Git.

---

### Task 1: Rebuild Public Entry Pages

**Files:**
- Modify: `index.html`
- Modify: `blog.html`
- Modify: `categories.html`
- Modify: `about.html`
- Modify: `authors.html`
- Modify: `contact.html`

- [ ] Replace news-style public framing with engineering practice framing.
- [ ] Remove decorative mojibake/icon residue from rewritten pages.
- [ ] Curate primary article links to strong AI, cloud, security, productivity, and strategy pieces.
- [ ] Keep one clear author identity, James Chen.

### Task 2: Add Recent Engineering Notes

**Files:**
- Create: `articles/ai-release-readiness-review.html`
- Create: `articles/cloud-bill-review-routine.html`
- Create: `articles/security-exception-register.html`

- [ ] Add three practical articles with engineering checklists, failure modes, and related links.
- [ ] Avoid broad market-news claims and generic trend language.

### Task 3: Update Discovery and Verify

**Files:**
- Modify: `sitemap.xml`

- [ ] Add new article URLs to `sitemap.xml` with `2026-06-22` lastmod.
- [ ] Verify no `ads.txt` changes.
- [ ] Run a local link check for missing internal HTML targets.
