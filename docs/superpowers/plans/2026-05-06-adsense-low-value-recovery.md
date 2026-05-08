# AdSense Low-Value Content Recovery Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Rebuild Game520 News Hub into an English, software-architect-led technology practice publication with roughly thirty substantial articles and complete AdSense trust signals.

**Architecture:** Keep the current static HTML site and reuse the existing CSS system. Replace the generic multi-author news framing with one expert author identity, five topic clusters, stronger index/list pages, and article pages with consistent metadata, related links, and long-form practical content.

**Tech Stack:** Static HTML, existing `css/style.css`, existing Google Analytics/AdSense snippets, XML sitemap, manual browser validation, Python standard library validation scripts run from shell.

---

## File Structure Map

### Core pages

- Modify: `index.html`
  - Responsibility: Homepage positioning, topic cluster entry points, selected long-form articles, author credibility block, recent updates, trust links.
- Modify: `blog.html`
  - Responsibility: Article index grouped by five topic clusters instead of a flat generic news feed.
- Modify: `categories.html`
  - Responsibility: Topic map with meaningful descriptions for AI Engineering, Cloud Architecture, Security Engineering, Developer Productivity, and Tech Strategy.
- Modify: `about.html`
  - Responsibility: Explain the expert-led editorial identity, content standards, scope, and correction process.
- Modify: `authors.html`
  - Responsibility: Present one primary software architect author profile and connect it to the article clusters.
- Modify: `contact.html`
  - Responsibility: Provide contact, corrections, copyright, and editorial feedback instructions.
- Modify: `privacy.html`
  - Responsibility: Explain cookies, Google AdSense, Google Analytics, third-party images, contact data, and user choices.
- Modify: `terms.html`
  - Responsibility: Explain informational nature, no professional advice, permitted use, copyright, and corrections.

### Article pages

- Modify or replace all files under `articles/` so the public article inventory contains thirty expert-led articles.
- Remove public links to low-fit article files that are not part of the thirty-article recovery inventory.
- Keep URLs stable when a current slug can be reused for a new topic.

### Styling and metadata

- Modify: `css/style.css`
  - Responsibility: Add reusable classes for cluster grids, author boxes, editorial notes, article metadata, and related reading where existing classes are insufficient.
- Modify: `sitemap.xml`
  - Responsibility: Include the final core pages and thirty article URLs with current lastmod dates.
- Inspect: `robots.txt`
  - Responsibility: Confirm sitemap reference and no accidental blocking.
- Inspect: `ads.txt`
  - Responsibility: Confirm publisher identifier is present and not malformed.

### Documentation

- Existing spec: `docs/superpowers/specs/2026-05-06-adsense-low-value-recovery-design.md`
- This plan: `docs/superpowers/plans/2026-05-06-adsense-low-value-recovery.md`

---

## Final Topic Cluster Inventory

Use this exact article inventory for implementation.

### AI Engineering

1. `articles/rag-systems-enterprise.html` — How I Evaluate RAG Systems Before Production Rollout
2. `articles/ai-product-development.html` — Turning AI Prototypes Into Products Engineers Can Maintain
3. `articles/ai-evaluation-framework.html` — A Practical Evaluation Framework for LLM Features
4. `articles/ai-cost-control.html` — Controlling LLM Cost Before It Becomes Architecture Debt
5. `articles/ai-governance-engineering.html` — AI Governance for Engineering Teams, Not Policy Slides
6. `articles/ai-incident-review.html` — What AI Incidents Teach Us About Product Reliability

### Cloud Architecture

1. `articles/cloud-cost-optimization.html` — Cloud Cost Optimization Starts With Architecture, Not Discounts
2. `articles/cloud-reliability-patterns.html` — Reliability Patterns I Use Before Adding More Infrastructure
3. `articles/observability-stack-design.html` — Designing Observability That Engineers Actually Use
4. `articles/platform-engineering-lessons.html` — Platform Engineering Lessons From Internal Tooling Work
5. `articles/cloud-migration-decisions.html` — When Cloud Migration Is Worth the Organizational Cost
6. `articles/serverless-tradeoffs.html` — Serverless Trade-Offs Beyond the Pricing Calculator

### Security Engineering

1. `articles/zero-day-response-playbook.html` — A Zero-Day Response Playbook for Engineering Leaders
2. `articles/supply-chain-security.html` — Software Supply Chain Security Checks That Catch Real Risk
3. `articles/access-control-review.html` — How I Review Access Control Before It Fails an Audit
4. `articles/security-baseline-engineering.html` — Building Security Baselines Developers Will Follow
5. `articles/vulnerability-prioritization.html` — Vulnerability Prioritization Without Spreadsheet Theater
6. `articles/security-logging-practices.html` — Security Logging Practices That Help During Incidents

### Developer Productivity

1. `articles/code-review-systems.html` — Code Review Systems That Improve Design Instead of Slowing Teams
2. `articles/ci-cd-quality-gates.html` — CI/CD Quality Gates That Prevent Rework Without Blocking Flow
3. `articles/technical-debt-control.html` — A Practical Model for Controlling Technical Debt
4. `articles/developer-metrics.html` — Developer Productivity Metrics That Do Not Punish Developers
5. `articles/internal-tools-roi.html` — When Internal Tools Are Worth Building
6. `articles/onboarding-engineering-teams.html` — Engineering Onboarding as a System Design Problem

### Tech Strategy

1. `articles/eu-ai-act-compliance.html` — What the EU AI Act Means for Software Architecture Decisions
2. `articles/technology-selection-framework.html` — A Technology Selection Framework for Long-Lived Systems
3. `articles/build-vs-buy-software.html` — Build vs Buy Decisions for Engineering Leaders
4. `articles/architecture-evolution.html` — Architecture Evolution Without Rewrite Drama
5. `articles/hype-cycle-evaluation.html` — How I Evaluate Technology Hype Before It Reaches the Roadmap
6. `articles/maintainability-strategy.html` — Maintainability as a Business Strategy, Not a Refactoring Slogan

---

## Task 1: Create the shared editorial model

**Files:**
- Modify: `index.html`
- Modify: `about.html`
- Modify: `authors.html`
- Modify: `blog.html`
- Modify: `categories.html`
- Modify: `contact.html`
- Modify: `privacy.html`
- Modify: `terms.html`
- Modify: `articles/*.html`

- [ ] **Step 1: Use one author identity everywhere**

Use this exact public author identity across pages and articles:

```text
Name: James Chen
Role: Software Architect and Engineering Strategy Writer
Bio: James Chen writes about AI engineering, cloud architecture, security engineering, developer productivity, and long-term technology strategy. His articles focus on practical trade-offs that engineering teams face when systems move from prototype to production.
Short byline: James Chen, Software Architect
Contact email: contact@game520game.com
```

- [ ] **Step 2: Replace generic team claims**

Replace claims like these wherever they appear:

```text
our team of real people—engineers, analysts, and industry insiders
7 Industry Experts
Meet Our Authors
former Google engineer
hospital CIO
Fortune 500 COO
former investment banker
contributors
editorial team
```

Use this framing instead:

```text
Game520 News Hub is an independent technology practice publication written by James Chen, a software architect focused on how engineering teams make practical decisions about AI systems, cloud platforms, security, developer workflows, and long-term architecture.
```

- [ ] **Step 3: Run a consistency search**

Run:

```bash
python - <<'PY'
from pathlib import Path
bad = [
    'Sarah Chen', 'Michael Ross', 'David Park', 'Emma Watson', 'Richard Chen',
    'Sarah Mitchell', 'Michael Thompson', 'Elena Rodriguez', 'Marcus Chen',
    'Dr. Richard Feynman', 'Hospital CIO', 'Fortune 500', 'Former Google',
    'our team of real people', '7 Industry Experts', 'contributors'
]
for path in Path('.').glob('**/*.html'):
    text = path.read_text(encoding='utf-8', errors='ignore')
    hits = [term for term in bad if term in text]
    if hits:
        print(path, '=>', ', '.join(hits))
PY
```

Expected: no output after the replacements are complete.

---

## Task 2: Update shared navigation and remove pre-review ad blocks

**Files:**
- Modify: `index.html`
- Modify: `blog.html`
- Modify: `categories.html`
- Modify: `about.html`
- Modify: `authors.html`
- Modify: `contact.html`
- Modify: `privacy.html`
- Modify: `terms.html`
- Modify: `articles/*.html`

- [ ] **Step 1: Standardize top navigation on root pages**

Use this navigation on root-level pages:

```html
<ul class="nav-menu" id="navMenu">
    <li><a href="index.html" class="nav-link">Home</a></li>
    <li><a href="blog.html" class="nav-link">Articles</a></li>
    <li><a href="categories.html" class="nav-link">Topics</a></li>
    <li><a href="authors.html" class="nav-link">Author</a></li>
    <li><a href="about.html" class="nav-link">About</a></li>
    <li><a href="contact.html" class="nav-link">Contact</a></li>
</ul>
```

Keep the `active` class only on the current page.

- [ ] **Step 2: Standardize top navigation on article pages**

Use this navigation on article pages:

```html
<ul class="nav-menu" id="navMenu">
    <li><a href="../index.html" class="nav-link">Home</a></li>
    <li><a href="../blog.html" class="nav-link">Articles</a></li>
    <li><a href="../categories.html" class="nav-link">Topics</a></li>
    <li><a href="../authors.html" class="nav-link">Author</a></li>
    <li><a href="../about.html" class="nav-link">About</a></li>
    <li><a href="../contact.html" class="nav-link">Contact</a></li>
</ul>
```

- [ ] **Step 3: Remove visible ad placeholders during recovery**

Remove all page body blocks matching this structure:

```html
<div class="ad-container">
    <div class="ad-label">Advertisement</div>
    <div class="ad-placeholder">
        <ins class="adsbygoogle"
```

Keep the existing AdSense script in `<head>` only if the site already needs it for verification. Do not add visible ad units before review.

- [ ] **Step 4: Verify no visible ad placeholders remain**

Run:

```bash
python - <<'PY'
from pathlib import Path
for path in Path('.').glob('**/*.html'):
    text = path.read_text(encoding='utf-8', errors='ignore')
    if 'ad-container' in text or 'YOUR_AD_SLOT' in text:
        print(path)
PY
```

Expected: no output.

---

## Task 3: Add reusable CSS for topic clusters and article trust blocks

**Files:**
- Modify: `css/style.css`

- [ ] **Step 1: Append focused reusable styles**

Append this CSS to the end of `css/style.css`:

```css
/* Editorial recovery components */
.editorial-note,
.author-summary,
.cluster-intro,
.article-framework,
.related-reading {
    background: var(--card-bg);
    border: 1px solid var(--border-color);
    border-radius: 18px;
    padding: 1.5rem;
}

.cluster-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
    gap: 1.5rem;
}

.cluster-card {
    background: var(--card-bg);
    border: 1px solid var(--border-color);
    border-radius: 18px;
    padding: 1.5rem;
    transition: var(--transition);
}

.cluster-card:hover {
    transform: translateY(-4px);
    border-color: var(--primary-color);
    box-shadow: var(--shadow-glow);
}

.cluster-card h3,
.author-summary h3,
.related-reading h3 {
    margin-bottom: 0.75rem;
}

.cluster-card p,
.editorial-note p,
.author-summary p,
.article-framework p,
.related-reading p {
    color: var(--text-secondary);
    line-height: 1.7;
}

.article-meta-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 0.75rem 1.25rem;
    color: var(--text-secondary);
    font-size: 0.95rem;
    margin-top: 1rem;
}

.article-framework ul,
.related-reading ul {
    color: var(--text-secondary);
    line-height: 1.8;
    padding-left: 1.25rem;
    margin-top: 0.75rem;
}

.article-framework li,
.related-reading li {
    margin-bottom: 0.5rem;
}

.content-container-narrow {
    max-width: 920px;
    margin: 0 auto;
    padding: 0 2rem;
}

@media (max-width: 768px) {
    .article-meta-grid {
        flex-direction: column;
        gap: 0.5rem;
    }

    .content-container-narrow {
        padding: 0 1rem;
    }
}
```

- [ ] **Step 2: Verify CSS does not duplicate existing selectors excessively**

Run:

```bash
python - <<'PY'
from pathlib import Path
text = Path('css/style.css').read_text(encoding='utf-8')
required = ['.cluster-grid', '.cluster-card', '.author-summary', '.related-reading', '.article-meta-grid']
for selector in required:
    count = text.count(selector)
    print(selector, count)
PY
```

Expected: each selector appears at least once. More than three occurrences for a selector means review for accidental duplicate appends.

---

## Task 4: Rebuild the homepage

**Files:**
- Modify: `index.html`

- [ ] **Step 1: Update `<head>` metadata**

Use this title and description:

```html
<title>Game520 News Hub - Practical AI, Cloud, Security and Software Architecture</title>
<meta name="description" content="Independent software architecture articles on AI engineering, cloud systems, security engineering, developer productivity, and long-term technology strategy.">
<meta name="keywords" content="software architecture, AI engineering, cloud architecture, security engineering, developer productivity, technology strategy">
```

- [ ] **Step 2: Replace hero positioning**

Replace the homepage hero copy with this content:

```html
<div class="hero-badge">Independent Software Architecture Notes</div>
<h1 class="hero-title">
    Practical Technology Analysis for <span>Engineering Decisions</span>
</h1>
<p class="hero-description">
    Game520 News Hub is written by James Chen, a software architect focused on the decisions teams face when AI systems, cloud platforms, security controls, and developer workflows move from slide decks into production.
</p>
<p style="color: var(--text-secondary); font-size: 1rem; margin-bottom: 2rem; max-width: 600px;">
    The goal is not to chase every technology headline. Each article explains trade-offs, failure modes, and implementation patterns that help technical leaders make better long-term decisions.
</p>
<div class="hero-stats">
    <div class="stat-item">
        <div class="stat-number">30</div>
        <div class="stat-label">Long-Form Articles</div>
    </div>
    <div class="stat-item">
        <div class="stat-number">5</div>
        <div class="stat-label">Engineering Topics</div>
    </div>
    <div class="stat-item">
        <div class="stat-number">1</div>
        <div class="stat-label">Expert Author</div>
    </div>
</div>
```

- [ ] **Step 3: Replace category cards with five cluster cards**

Use these cluster labels and descriptions:

```text
AI Engineering — Production lessons for RAG, LLM evaluation, AI product design, governance, cost control, and reliability.
Cloud Architecture — Practical trade-offs for cloud cost, observability, reliability, migration, platform engineering, and serverless design.
Security Engineering — Engineering-led approaches to incident response, supply chain risk, access control, vulnerability prioritization, and security logging.
Developer Productivity — Systems for code review, CI/CD quality, technical debt control, developer metrics, internal tools, and onboarding.
Tech Strategy — Decision frameworks for technology selection, build-vs-buy, architecture evolution, regulation, maintainability, and hype evaluation.
```

- [ ] **Step 4: Feature one representative article from each cluster**

Use these featured links:

```html
<a href="articles/rag-systems-enterprise.html">How I Evaluate RAG Systems Before Production Rollout</a>
<a href="articles/cloud-cost-optimization.html">Cloud Cost Optimization Starts With Architecture, Not Discounts</a>
<a href="articles/zero-day-response-playbook.html">A Zero-Day Response Playbook for Engineering Leaders</a>
<a href="articles/code-review-systems.html">Code Review Systems That Improve Design Instead of Slowing Teams</a>
<a href="articles/technology-selection-framework.html">A Technology Selection Framework for Long-Lived Systems</a>
```

- [ ] **Step 5: Add an author credibility block**

Add this block above the footer:

```html
<section class="section">
    <div class="container">
        <div class="author-summary">
            <h2>Written from an architecture seat, not a news desk</h2>
            <p>James Chen writes for readers who have to turn technology choices into operating systems, product commitments, budgets, and maintenance plans. The articles favor practical engineering judgment over vendor language or trend summaries.</p>
            <a href="authors.html" class="btn btn-secondary" style="margin-top: 1rem; display: inline-flex;">Read the author profile</a>
        </div>
    </div>
</section>
```

- [ ] **Step 6: Validate homepage copy**

Run:

```bash
python - <<'PY'
from pathlib import Path
text = Path('index.html').read_text(encoding='utf-8')
required = ['James Chen', 'AI Engineering', 'Cloud Architecture', 'Security Engineering', 'Developer Productivity', 'Tech Strategy']
for term in required:
    assert term in text, f'missing {term}'
print('homepage ok')
PY
```

Expected: `homepage ok`.

---

## Task 5: Rebuild Blog and Categories pages as topic maps

**Files:**
- Modify: `blog.html`
- Modify: `categories.html`

- [ ] **Step 1: Update blog page heading**

Use this copy:

```html
<span class="section-label">Article Library</span>
<h1 class="page-title">Engineering Articles by Topic Cluster</h1>
<p class="page-description">Browse practical long-form articles on AI engineering, cloud architecture, security engineering, developer productivity, and technology strategy.</p>
```

- [ ] **Step 2: Replace blog filters with cluster sections**

Create five sections using this exact structure pattern:

```html
<section class="section">
    <div class="container">
        <div class="cluster-intro">
            <h2>AI Engineering</h2>
            <p>Production AI work is mostly about evaluation, reliability, cost, governance, and the gap between a promising demo and a maintainable product.</p>
        </div>
        <div class="articles-grid" style="margin-top: 2rem;">
            <!-- six AI Engineering article cards -->
        </div>
    </div>
</section>
```

Use the final topic cluster inventory from this plan for the article cards.

- [ ] **Step 3: Update categories page heading**

Use this copy:

```html
<span class="section-label">Topics</span>
<h1 class="section-title">Five Engineering Lenses for Technology Decisions</h1>
<p class="section-description">The site is organized around the recurring decisions software teams face: what to build, what to buy, how to secure it, how to run it, and how to keep it maintainable.</p>
```

- [ ] **Step 4: Replace old categories with five cluster cards**

Use the five cluster descriptions from Task 4 Step 3. Each card should link to `blog.html#ai-engineering`, `blog.html#cloud-architecture`, `blog.html#security-engineering`, `blog.html#developer-productivity`, and `blog.html#tech-strategy`.

- [ ] **Step 5: Validate all thirty article links appear on blog page**

Run:

```bash
python - <<'PY'
from pathlib import Path
blog = Path('blog.html').read_text(encoding='utf-8')
slugs = [
'rag-systems-enterprise.html','ai-product-development.html','ai-evaluation-framework.html','ai-cost-control.html','ai-governance-engineering.html','ai-incident-review.html',
'cloud-cost-optimization.html','cloud-reliability-patterns.html','observability-stack-design.html','platform-engineering-lessons.html','cloud-migration-decisions.html','serverless-tradeoffs.html',
'zero-day-response-playbook.html','supply-chain-security.html','access-control-review.html','security-baseline-engineering.html','vulnerability-prioritization.html','security-logging-practices.html',
'code-review-systems.html','ci-cd-quality-gates.html','technical-debt-control.html','developer-metrics.html','internal-tools-roi.html','onboarding-engineering-teams.html',
'eu-ai-act-compliance.html','technology-selection-framework.html','build-vs-buy-software.html','architecture-evolution.html','hype-cycle-evaluation.html','maintainability-strategy.html'
]
missing = [slug for slug in slugs if slug not in blog]
assert not missing, missing
print('blog inventory ok')
PY
```

Expected: `blog inventory ok`.

---

## Task 6: Rebuild About, Author, Contact, Privacy, and Terms pages

**Files:**
- Modify: `about.html`
- Modify: `authors.html`
- Modify: `contact.html`
- Modify: `privacy.html`
- Modify: `terms.html`

- [ ] **Step 1: Rebuild About page around editorial standards**

Include these sections in `about.html`:

```text
About Game520 News Hub
Why this site exists
What I write about
Editorial standards
What this site is not
Corrections and contact
```

Use this key paragraph:

```html
<p>Game520 News Hub is an independent technology practice site written by James Chen. It exists for readers who need more than headlines: engineering managers, software architects, senior developers, technical founders, and operators who have to decide how new technology should be evaluated, funded, secured, and maintained.</p>
```

- [ ] **Step 2: Rebuild Authors page as a single author page**

Use this author profile content:

```html
<h1 class="section-title">James Chen</h1>
<p class="section-description">Software Architect and Engineering Strategy Writer</p>
<p>James writes about the engineering decisions behind AI systems, cloud platforms, security programs, developer productivity, and long-term technology strategy. His work focuses on practical trade-offs: what breaks in production, what teams underestimate, and what leaders should evaluate before committing to a technology direction.</p>
```

Include a list of the five topic clusters and link to the blog sections.

- [ ] **Step 3: Rebuild Contact page**

Include these contact categories:

```html
<ul>
    <li>General questions: contact@game520game.com</li>
    <li>Corrections: include the article URL and the sentence that needs review.</li>
    <li>Copyright concerns: include the page URL and the material in question.</li>
    <li>Editorial suggestions: explain the engineering problem readers need help solving.</li>
</ul>
```

- [ ] **Step 4: Update Privacy page**

Ensure `privacy.html` includes these exact topics:

```text
Information we collect
Cookies
Google Analytics
Google AdSense
Third-party images and external resources
Contact email data
How users can control cookies
Policy updates
```

- [ ] **Step 5: Update Terms page**

Ensure `terms.html` includes these exact topics:

```text
Informational content only
No professional advice
Acceptable use
Intellectual property
External links
Corrections
Limitation of liability
Contact
```

- [ ] **Step 6: Validate trust pages**

Run:

```bash
python - <<'PY'
from pathlib import Path
checks = {
    'about.html': ['James Chen', 'Editorial standards', 'What this site is not'],
    'authors.html': ['James Chen', 'Software Architect', 'AI Engineering', 'Cloud Architecture'],
    'contact.html': ['contact@game520game.com', 'Corrections', 'Copyright'],
    'privacy.html': ['Google AdSense', 'Google Analytics', 'Cookies'],
    'terms.html': ['Informational content only', 'No professional advice', 'Intellectual property'],
}
for file, terms in checks.items():
    text = Path(file).read_text(encoding='utf-8')
    for term in terms:
        assert term in text, f'{file} missing {term}'
print('trust pages ok')
PY
```

Expected: `trust pages ok`.

---

## Task 7: Create the standard article template and rewrite AI Engineering articles

**Files:**
- Modify: `articles/rag-systems-enterprise.html`
- Modify: `articles/ai-product-development.html`
- Create: `articles/ai-evaluation-framework.html`
- Create: `articles/ai-cost-control.html`
- Create: `articles/ai-governance-engineering.html`
- Create: `articles/ai-incident-review.html`

- [ ] **Step 1: Use this article page structure for each AI Engineering article**

```html
<section class="page-header" style="padding-top: 100px; padding-bottom: 2rem;">
    <div class="container">
        <div class="article-header">
            <span class="article-category">AI Engineering</span>
            <h1 class="article-header-title">ARTICLE_TITLE</h1>
            <div class="article-meta-grid">
                <span>By James Chen</span>
                <span>Published May 6, 2026</span>
                <span>Updated May 6, 2026</span>
                <span>12-16 min read</span>
            </div>
        </div>
    </div>
</section>
```

Replace `ARTICLE_TITLE` with the exact title from the inventory.

- [ ] **Step 2: Include this author block in each AI article**

```html
<div class="author-summary" style="margin: 2rem 0;">
    <h3>Author's note</h3>
    <p>James Chen writes from the perspective of a software architect evaluating how AI systems behave after the demo, when teams must own cost, reliability, security, and maintenance.</p>
</div>
```

- [ ] **Step 3: Write each AI article body with this structure**

Each article must include these headings:

```html
<h2>The engineering problem</h2>
<h2>Where teams usually get stuck</h2>
<h2>The decision framework I use</h2>
<h2>Implementation checklist</h2>
<h2>Common mistakes</h2>
<h2>Final recommendation</h2>
```

Each article body must contain at least 900 English words and must not contain Chinese text.

- [ ] **Step 4: Add related reading to each AI article**

Use this related block, with links adjusted so each page links to at least three AI Engineering pages:

```html
<div class="related-reading">
    <h3>Related reading</h3>
    <ul>
        <li><a href="rag-systems-enterprise.html">How I Evaluate RAG Systems Before Production Rollout</a></li>
        <li><a href="ai-evaluation-framework.html">A Practical Evaluation Framework for LLM Features</a></li>
        <li><a href="ai-cost-control.html">Controlling LLM Cost Before It Becomes Architecture Debt</a></li>
    </ul>
</div>
```

- [ ] **Step 5: Validate AI articles**

Run:

```bash
python - <<'PY'
from pathlib import Path
import re
files = [
'rag-systems-enterprise.html','ai-product-development.html','ai-evaluation-framework.html','ai-cost-control.html','ai-governance-engineering.html','ai-incident-review.html'
]
for name in files:
    path = Path('articles') / name
    assert path.exists(), f'missing {name}'
    text = path.read_text(encoding='utf-8')
    assert 'James Chen' in text, f'{name} missing author'
    assert 'AI Engineering' in text, f'{name} missing cluster'
    assert 'related-reading' in text, f'{name} missing related reading'
    visible = re.sub(r'<[^>]+>', ' ', text)
    words = re.findall(r"\b[A-Za-z][A-Za-z'-]*\b", visible)
    assert len(words) >= 900, f'{name} has only {len(words)} words'
    assert not re.search(r'[一-鿿]', text), f'{name} contains Chinese text'
print('ai articles ok')
PY
```

Expected: `ai articles ok`.

---

## Task 8: Rewrite Cloud Architecture articles

**Files:**
- Modify: `articles/cloud-cost-optimization.html`
- Create: `articles/cloud-reliability-patterns.html`
- Create: `articles/observability-stack-design.html`
- Create: `articles/platform-engineering-lessons.html`
- Create: `articles/cloud-migration-decisions.html`
- Create: `articles/serverless-tradeoffs.html`

- [ ] **Step 1: Use the standard article structure**

Use the article page structure from Task 7 Step 1, with this category:

```html
<span class="article-category">Cloud Architecture</span>
```

- [ ] **Step 2: Use these required headings in every Cloud article**

```html
<h2>The architecture problem</h2>
<h2>The cost of the obvious solution</h2>
<h2>The trade-off model</h2>
<h2>Operational signals to watch</h2>
<h2>Checklist for engineering leaders</h2>
<h2>Final recommendation</h2>
```

- [ ] **Step 3: Add Cloud related reading**

Each Cloud article should link to at least three Cloud Architecture articles and one adjacent article from AI Engineering or Developer Productivity.

Use this example block:

```html
<div class="related-reading">
    <h3>Related reading</h3>
    <ul>
        <li><a href="cloud-cost-optimization.html">Cloud Cost Optimization Starts With Architecture, Not Discounts</a></li>
        <li><a href="observability-stack-design.html">Designing Observability That Engineers Actually Use</a></li>
        <li><a href="platform-engineering-lessons.html">Platform Engineering Lessons From Internal Tooling Work</a></li>
        <li><a href="developer-metrics.html">Developer Productivity Metrics That Do Not Punish Developers</a></li>
    </ul>
</div>
```

- [ ] **Step 4: Validate Cloud articles**

Run:

```bash
python - <<'PY'
from pathlib import Path
import re
files = ['cloud-cost-optimization.html','cloud-reliability-patterns.html','observability-stack-design.html','platform-engineering-lessons.html','cloud-migration-decisions.html','serverless-tradeoffs.html']
for name in files:
    path = Path('articles') / name
    assert path.exists(), f'missing {name}'
    text = path.read_text(encoding='utf-8')
    assert 'James Chen' in text
    assert 'Cloud Architecture' in text
    assert 'related-reading' in text
    words = re.findall(r"\b[A-Za-z][A-Za-z'-]*\b", re.sub(r'<[^>]+>', ' ', text))
    assert len(words) >= 900, f'{name}: {len(words)} words'
    assert not re.search(r'[一-鿿]', text), f'{name} contains Chinese text'
print('cloud articles ok')
PY
```

Expected: `cloud articles ok`.

---

## Task 9: Rewrite Security Engineering articles

**Files:**
- Modify: `articles/zero-day-response-playbook.html`
- Create: `articles/supply-chain-security.html`
- Create: `articles/access-control-review.html`
- Create: `articles/security-baseline-engineering.html`
- Create: `articles/vulnerability-prioritization.html`
- Create: `articles/security-logging-practices.html`

- [ ] **Step 1: Use the standard article structure**

Use the article page structure from Task 7 Step 1, with this category:

```html
<span class="article-category">Security Engineering</span>
```

- [ ] **Step 2: Use these required headings in every Security article**

```html
<h2>The security problem</h2>
<h2>Why generic advice fails</h2>
<h2>The engineering control model</h2>
<h2>Signals worth measuring</h2>
<h2>Review checklist</h2>
<h2>Final recommendation</h2>
```

- [ ] **Step 3: Add Security related reading**

Each Security article should link to at least three Security Engineering articles and one adjacent Tech Strategy or Cloud Architecture article.

- [ ] **Step 4: Validate Security articles**

Run:

```bash
python - <<'PY'
from pathlib import Path
import re
files = ['zero-day-response-playbook.html','supply-chain-security.html','access-control-review.html','security-baseline-engineering.html','vulnerability-prioritization.html','security-logging-practices.html']
for name in files:
    path = Path('articles') / name
    assert path.exists(), f'missing {name}'
    text = path.read_text(encoding='utf-8')
    assert 'James Chen' in text
    assert 'Security Engineering' in text
    assert 'related-reading' in text
    words = re.findall(r"\b[A-Za-z][A-Za-z'-]*\b", re.sub(r'<[^>]+>', ' ', text))
    assert len(words) >= 900, f'{name}: {len(words)} words'
    assert not re.search(r'[一-鿿]', text), f'{name} contains Chinese text'
print('security articles ok')
PY
```

Expected: `security articles ok`.

---

## Task 10: Rewrite Developer Productivity articles

**Files:**
- Create: `articles/code-review-systems.html`
- Create: `articles/ci-cd-quality-gates.html`
- Create: `articles/technical-debt-control.html`
- Create: `articles/developer-metrics.html`
- Create: `articles/internal-tools-roi.html`
- Create: `articles/onboarding-engineering-teams.html`

- [ ] **Step 1: Use the standard article structure**

Use the article page structure from Task 7 Step 1, with this category:

```html
<span class="article-category">Developer Productivity</span>
```

- [ ] **Step 2: Use these required headings in every Developer Productivity article**

```html
<h2>The productivity problem</h2>
<h2>What teams usually measure incorrectly</h2>
<h2>The system-level view</h2>
<h2>Practical implementation steps</h2>
<h2>Failure modes to avoid</h2>
<h2>Final recommendation</h2>
```

- [ ] **Step 3: Add Developer Productivity related reading**

Each Developer Productivity article should link to at least three Developer Productivity articles and one adjacent Cloud Architecture or Tech Strategy article.

- [ ] **Step 4: Validate Developer Productivity articles**

Run:

```bash
python - <<'PY'
from pathlib import Path
import re
files = ['code-review-systems.html','ci-cd-quality-gates.html','technical-debt-control.html','developer-metrics.html','internal-tools-roi.html','onboarding-engineering-teams.html']
for name in files:
    path = Path('articles') / name
    assert path.exists(), f'missing {name}'
    text = path.read_text(encoding='utf-8')
    assert 'James Chen' in text
    assert 'Developer Productivity' in text
    assert 'related-reading' in text
    words = re.findall(r"\b[A-Za-z][A-Za-z'-]*\b", re.sub(r'<[^>]+>', ' ', text))
    assert len(words) >= 900, f'{name}: {len(words)} words'
    assert not re.search(r'[一-鿿]', text), f'{name} contains Chinese text'
print('developer productivity articles ok')
PY
```

Expected: `developer productivity articles ok`.

---

## Task 11: Rewrite Tech Strategy articles

**Files:**
- Modify: `articles/eu-ai-act-compliance.html`
- Create: `articles/technology-selection-framework.html`
- Create: `articles/build-vs-buy-software.html`
- Create: `articles/architecture-evolution.html`
- Create: `articles/hype-cycle-evaluation.html`
- Create: `articles/maintainability-strategy.html`

- [ ] **Step 1: Use the standard article structure**

Use the article page structure from Task 7 Step 1, with this category:

```html
<span class="article-category">Tech Strategy</span>
```

- [ ] **Step 2: Use these required headings in every Tech Strategy article**

```html
<h2>The strategic decision</h2>
<h2>Why the easy answer is risky</h2>
<h2>The evaluation framework</h2>
<h2>Organizational signals to consider</h2>
<h2>Decision checklist</h2>
<h2>Final recommendation</h2>
```

- [ ] **Step 3: Add Tech Strategy related reading**

Each Tech Strategy article should link to at least three Tech Strategy articles and one adjacent AI Engineering, Cloud Architecture, Security Engineering, or Developer Productivity article.

- [ ] **Step 4: Validate Tech Strategy articles**

Run:

```bash
python - <<'PY'
from pathlib import Path
import re
files = ['eu-ai-act-compliance.html','technology-selection-framework.html','build-vs-buy-software.html','architecture-evolution.html','hype-cycle-evaluation.html','maintainability-strategy.html']
for name in files:
    path = Path('articles') / name
    assert path.exists(), f'missing {name}'
    text = path.read_text(encoding='utf-8')
    assert 'James Chen' in text
    assert 'Tech Strategy' in text
    assert 'related-reading' in text
    words = re.findall(r"\b[A-Za-z][A-Za-z'-]*\b", re.sub(r'<[^>]+>', ' ', text))
    assert len(words) >= 900, f'{name}: {len(words)} words'
    assert not re.search(r'[一-鿿]', text), f'{name} contains Chinese text'
print('tech strategy articles ok')
PY
```

Expected: `tech strategy articles ok`.

---

## Task 12: Remove or de-emphasize old low-fit content from navigation and sitemap

**Files:**
- Modify: `index.html`
- Modify: `blog.html`
- Modify: `categories.html`
- Modify: `sitemap.xml`

- [ ] **Step 1: Ensure old low-fit slugs are not linked from public index pages**

Remove links to these low-fit legacy topics from `index.html`, `blog.html`, and `categories.html` unless they have been rewritten into the final thirty-article inventory:

```text
market-outlook-2026.html
blockchain-finance.html
electric-vehicles.html
esg-investing.html
metaverse-future.html
space-technology.html
sustainable-tech.html
quantum-computing.html
future-of-work.html
innovation-ecosystems.html
web3-adoption.html
5g-technology.html
remote-work-future.html
robotics-automation.html
ml-healthcare.html
ai-healthcare.html
fintech-banking.html
```

- [ ] **Step 2: Rebuild sitemap with core pages and final thirty articles**

Use current domain format already present in `sitemap.xml`. Set `lastmod` to `2026-05-06` for all updated pages and final article URLs.

- [ ] **Step 3: Validate public links do not point to legacy low-fit content**

Run:

```bash
python - <<'PY'
from pathlib import Path
legacy = ['market-outlook-2026.html','blockchain-finance.html','electric-vehicles.html','esg-investing.html','metaverse-future.html','space-technology.html','sustainable-tech.html','quantum-computing.html','future-of-work.html','innovation-ecosystems.html','web3-adoption.html','5g-technology.html','remote-work-future.html','robotics-automation.html','ml-healthcare.html','ai-healthcare.html','fintech-banking.html']
for file in ['index.html','blog.html','categories.html','sitemap.xml']:
    text = Path(file).read_text(encoding='utf-8')
    hits = [slug for slug in legacy if slug in text]
    assert not hits, f'{file} still links {hits}'
print('legacy links removed')
PY
```

Expected: `legacy links removed`.

---

## Task 13: Validate site quality and link integrity

**Files:**
- Inspect: all `*.html`
- Inspect: `sitemap.xml`
- Inspect: `robots.txt`
- Inspect: `ads.txt`

- [ ] **Step 1: Run local static server**

Run:

```bash
python -m http.server 8080
```

Expected: local site is available at `http://localhost:8080/`.

- [ ] **Step 2: Validate internal file links**

In another terminal, run:

```bash
python - <<'PY'
from pathlib import Path
from html.parser import HTMLParser

class LinkParser(HTMLParser):
    def __init__(self):
        super().__init__()
        self.links = []
    def handle_starttag(self, tag, attrs):
        attrs = dict(attrs)
        if tag == 'a' and 'href' in attrs:
            self.links.append(attrs['href'])
        if tag == 'img' and 'src' in attrs:
            self.links.append(attrs['src'])

missing = []
for path in Path('.').glob('**/*.html'):
    parser = LinkParser()
    parser.feed(path.read_text(encoding='utf-8', errors='ignore'))
    for link in parser.links:
        if link.startswith(('http://','https://','mailto:','#','data:')):
            continue
        clean = link.split('#')[0].split('?')[0]
        if not clean:
            continue
        target = (path.parent / clean).resolve()
        if not target.exists():
            missing.append((str(path), link))
if missing:
    for item in missing:
        print(item[0], '=>', item[1])
    raise SystemExit(1)
print('links ok')
PY
```

Expected: `links ok`.

- [ ] **Step 3: Validate no Chinese text remains in English public pages**

Run:

```bash
python - <<'PY'
from pathlib import Path
import re
for path in Path('.').glob('**/*.html'):
    text = path.read_text(encoding='utf-8', errors='ignore')
    if re.search(r'[一-鿿]', text):
        print(path)
        raise SystemExit(1)
print('language ok')
PY
```

Expected: `language ok`.

- [ ] **Step 4: Validate all thirty final articles exist**

Run:

```bash
python - <<'PY'
from pathlib import Path
slugs = '''rag-systems-enterprise.html ai-product-development.html ai-evaluation-framework.html ai-cost-control.html ai-governance-engineering.html ai-incident-review.html cloud-cost-optimization.html cloud-reliability-patterns.html observability-stack-design.html platform-engineering-lessons.html cloud-migration-decisions.html serverless-tradeoffs.html zero-day-response-playbook.html supply-chain-security.html access-control-review.html security-baseline-engineering.html vulnerability-prioritization.html security-logging-practices.html code-review-systems.html ci-cd-quality-gates.html technical-debt-control.html developer-metrics.html internal-tools-roi.html onboarding-engineering-teams.html eu-ai-act-compliance.html technology-selection-framework.html build-vs-buy-software.html architecture-evolution.html hype-cycle-evaluation.html maintainability-strategy.html'''.split()
missing = [slug for slug in slugs if not (Path('articles') / slug).exists()]
assert not missing, missing
print('article inventory ok')
PY
```

Expected: `article inventory ok`.

- [ ] **Step 5: Validate sitemap includes all thirty final articles**

Run:

```bash
python - <<'PY'
from pathlib import Path
sitemap = Path('sitemap.xml').read_text(encoding='utf-8')
slugs = '''rag-systems-enterprise.html ai-product-development.html ai-evaluation-framework.html ai-cost-control.html ai-governance-engineering.html ai-incident-review.html cloud-cost-optimization.html cloud-reliability-patterns.html observability-stack-design.html platform-engineering-lessons.html cloud-migration-decisions.html serverless-tradeoffs.html zero-day-response-playbook.html supply-chain-security.html access-control-review.html security-baseline-engineering.html vulnerability-prioritization.html security-logging-practices.html code-review-systems.html ci-cd-quality-gates.html technical-debt-control.html developer-metrics.html internal-tools-roi.html onboarding-engineering-teams.html eu-ai-act-compliance.html technology-selection-framework.html build-vs-buy-software.html architecture-evolution.html hype-cycle-evaluation.html maintainability-strategy.html'''.split()
missing = [slug for slug in slugs if slug not in sitemap]
assert not missing, missing
print('sitemap ok')
PY
```

Expected: `sitemap ok`.

- [ ] **Step 6: Inspect `robots.txt` and `ads.txt`**

Run:

```bash
python - <<'PY'
from pathlib import Path
robots = Path('robots.txt').read_text(encoding='utf-8', errors='ignore')
ads = Path('ads.txt').read_text(encoding='utf-8', errors='ignore')
assert 'Sitemap:' in robots, 'robots.txt missing Sitemap'
assert 'google.com' in ads and 'pub-5020869002919663' in ads, 'ads.txt missing Google publisher line'
print('robots and ads ok')
PY
```

Expected: `robots and ads ok`.

---

## Task 14: Manual review before AdSense resubmission

**Files:**
- Inspect: rendered site in browser

- [ ] **Step 1: Review homepage**

Open `http://localhost:8080/index.html` and verify:

```text
The homepage clearly explains the site is written by James Chen.
The page links to five topic clusters.
The page does not claim a fake editorial team.
The page does not show visible ad placeholders.
```

- [ ] **Step 2: Review article library**

Open `http://localhost:8080/blog.html` and verify:

```text
Articles are grouped by five clusters.
Each cluster has six articles.
The article links work.
The page has explanatory text, not only cards.
```

- [ ] **Step 3: Review trust pages**

Open these URLs and verify the stated purpose is consistent:

```text
http://localhost:8080/about.html
http://localhost:8080/authors.html
http://localhost:8080/contact.html
http://localhost:8080/privacy.html
http://localhost:8080/terms.html
```

- [ ] **Step 4: Review representative articles**

Open one article from each cluster and verify:

```text
The article has a clear author.
The article has a publish and update date.
The article is substantial and practical.
The article links to related reading.
The article does not contain placeholder text or mixed language.
```

Recommended samples:

```text
articles/rag-systems-enterprise.html
articles/cloud-cost-optimization.html
articles/zero-day-response-playbook.html
articles/code-review-systems.html
articles/technology-selection-framework.html
```

---

## Self-Review Notes

- Spec coverage: The plan covers site positioning, personal expert identity, five topic clusters, thirty-article inventory, trust pages, article templates, internal linking, sitemap, robots, ads.txt, and validation.
- Placeholder scan: The plan avoids open-ended placeholders. Article writing tasks define exact files, categories, required headings, author block, related reading requirements, and validation checks.
- Scope check: The work is large but cohesive: one static-site AdSense recovery pass. The article rewrite tasks are split by topic cluster so they can be executed and reviewed independently.
- Git note: The writing-plans skill recommends commits, but project/user instructions say not to perform git commits unless explicitly requested. This plan intentionally omits mandatory commit steps.
