# AdSense Low-Value Content Recovery Design

## Goal

Rework the current site into an English, expert-led technology publication that is strong enough for a renewed Google AdSense review. The site should no longer feel like a generic AI-generated news collection. It should present clear expertise, a consistent editorial point of view, useful long-form content, and complete trust pages.

## Site Positioning

Game520 News Hub will remain the site name, but the editorial positioning will shift to a software architect's technology practice journal. The core value proposition is practical interpretation: how AI, cloud, security, developer tooling, and technology strategy affect real engineering teams and system decisions.

The site should avoid broad news summaries and keyword-driven trend pieces. Articles should be written from a software engineering and architecture perspective, with concrete scenarios, trade-offs, implementation considerations, and opinionated conclusions.

## Editorial Identity

The site will use a personal expert model instead of an anonymous media-team model. The main author should be presented as a software engineer / architect who writes from hands-on experience with system design, cloud platforms, AI integration, security practices, and engineering productivity.

The About and Authors pages should explain:

- who writes the content
- what topics the author covers
- how articles are selected and reviewed
- what the site does not claim to be
- how readers can request corrections or contact the author

The site must avoid unverifiable claims such as large editorial staff, fake company scale, fake certifications, or fabricated client names.

## Content Architecture

The site will use five topic clusters, each with approximately six high-quality English articles, for a target total of around thirty articles.

1. AI Engineering
   - RAG systems
   - AI product rollout
   - model evaluation
   - AI cost management
   - governance and compliance
   - production failure modes

2. Cloud Architecture
   - cloud cost optimization
   - reliability practices
   - observability
   - platform engineering
   - migration decisions
   - infrastructure trade-offs

3. Security Engineering
   - incident response
   - vulnerability handling
   - software supply chain security
   - access control
   - security baselines
   - practical risk management

4. Developer Productivity
   - code review quality
   - CI/CD design
   - technical debt control
   - engineering metrics
   - internal tools
   - team workflow improvements

5. Tech Strategy
   - technology selection
   - architecture evolution
   - regulation impact
   - build vs buy decisions
   - market hype evaluation
   - long-term maintainability

Each cluster should have a short introduction on the category or blog page and strong internal links between related articles.

## Page-Level Design

### Home

The homepage should clearly state the site's expert-led technology practice focus. It should include:

- a concise positioning statement
- five topic cluster entry points
- selected long-form articles
- a short author credibility block
- recent updates
- links to About, Authors, Contact, Privacy, and Terms

### Blog

The blog page should move beyond a flat article list. It should group articles by topic cluster and include short descriptions that explain why each cluster exists.

### Categories

The categories page should act as a topic map. Each category should include a useful summary, not only a label and links.

### About

The About page should support E-E-A-T by explaining the author's background, editorial focus, site purpose, and content standards.

### Authors

The Authors page should focus on the main software architect identity. It should connect the author to their published articles and expertise areas.

### Contact

The Contact page should include a working contact email or contact method, editorial feedback instructions, copyright concerns, and correction requests.

### Privacy and Terms

The Privacy and Terms pages should clearly cover cookies, Google AdSense, third-party services, image sources, contact form data, analytics if used, and general content disclaimers.

### Article Pages

Each article page should include:

- clear title and meta description
- author name
- publication and update dates
- topic cluster label
- substantial original article body
- practical examples or decision frameworks
- related articles
- article tags
- no fake download links or misleading calls to action

## Article Quality Standard

Each major article should target roughly 900-1400 English words. The goal is depth and usefulness, not word count alone.

Recommended structure:

1. Problem context
2. Real-world scenario
3. Engineering or architecture analysis
4. Practical recommendations
5. Common mistakes
6. Clear conclusion

Articles should avoid:

- generic trend summaries
- copied or lightly rewritten external material
- keyword stuffing
- repetitive introductions
- unsupported claims
- thin listicles
- mixed Chinese and English content
- obvious placeholder text

A reader should leave each article with a decision framework, checklist, implementation consideration, or clear engineering judgment.

## Internal Linking Strategy

Every article should link to two to four related articles. Links should be contextual and useful, not mechanically inserted. Topic cluster pages should link to all articles in that cluster, while article pages should link back to their cluster and to adjacent topics when relevant.

## Technical Design

The implementation should keep the current static HTML structure. Do not introduce a CMS, build system, database, or dependency-heavy workflow for this recovery pass.

Expected files to update include:

- `index.html`
- `blog.html`
- `categories.html`
- `about.html`
- `authors.html`
- `contact.html`
- `privacy.html`
- `terms.html`
- files under `articles/`
- sitemap and robots metadata if article URLs change

CSS and JavaScript should be reused where possible. Visual changes should be limited to what is needed for clear topic clusters, author credibility, and readable article pages.

## Validation Criteria

The recovery work is complete when:

- the site has around thirty substantial English articles
- each of the five topic clusters has at least five to six articles
- home, blog, and category pages contain meaningful original text
- About, Authors, Contact, Privacy, and Terms are complete and consistent
- article pages show author, dates, cluster, tags, and related reading
- there is no obvious placeholder content
- there is no mixed-language artifact in English articles
- all navigation and footer links work
- sitemap and robots references are consistent
- no intrusive ads are added before review
- the site reads like a real expert-maintained publication rather than a generated content dump

## Out of Scope

This design does not include:

- adding ad placements
- changing domain or hosting
- adding a CMS
- creating fake author identities
- creating fake external references or fabricated credentials
- mass-generated low-effort articles
- broad visual rebranding unless required by existing layout limitations
