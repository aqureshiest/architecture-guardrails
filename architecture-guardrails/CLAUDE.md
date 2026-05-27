# Earnest Architecture Guardrails

A living, opinionated document of architectural and engineering guardrails for building high-quality systems at Earnest. Maintained collaboratively by technical leaders.

The artifact is a single self-contained HTML page (`index.html`) styled as a documentation site, with a left sidebar nav, scroll-spy active section highlighting, and a card-based layout per section.

## Audience & purpose

- **Primary readers:** Earnest engineers, tech leads, staff/principal engineers, engineering managers
- **Goal:** establish a shared bar for engineering quality — something every engineer can point to, argue with, and contribute back to
- **Tone:** opinionated and concrete. We prefer specific recommendations grounded in industry lessons over generic platitudes. If a guardrail can't explain *why*, it doesn't belong here.

## Repository structure

```
architecture-guardrails/
├── CLAUDE.md       ← this file (instructions for collaborators / agents)
├── index.html      ← the document itself; single-file HTML
└── memory/         ← agent memory; do not edit by hand
```

There is intentionally no build step, framework, or tooling. Anyone can open `index.html` in a browser and review changes immediately.

## Current sections

1. **Code Craftsmanship & Developer Pride** — naming, consumer-first design, broken windows, review culture
2. **Simplicity & Avoiding Over-Engineering** — complexity as debt, monolith-first, YAGNI, Conway's Law
3. **TDD & Shift-Left Quality** — testing pyramid, mutation/property/fitness functions, CI gates
4. **Third-Party Integration Patterns** — circuit breakers, retries, ACL, secrets, webhooks
5. **Database Performance Patterns** — query discipline, safe migrations, transactions & connections
6. **Observability & Monitoring** — logs/metrics/traces, golden signals, SLOs, post-mortems
7. **AI-Augmented & Agentic Development** — context as primary input, TDD as harness, accountability

Each section has a one-line lead, a Core Insight callout, and 3–4 cards. Cards follow a consistent pattern: title → short framing paragraph → bulleted guardrails.

## How to contribute

We welcome edits, additions, disagreements, and rewrites from any technical leader. The bar is **substance over volume**.

**Good contributions:**
- A guardrail backed by a real incident, postmortem, or named industry lesson
- A reframe that makes existing content clearer or more honest
- A removal — if something is fluff, cut it
- A new card or section that fills a genuine gap (e.g. security, frontend perf, data privacy, ML systems)

**Discouraged:**
- Generic advice without a *why*
- Vendor or framework promotion
- Aspirational language we don't actually practice
- Adding cards just to fill space

When in doubt, leave it terser than you think it should be. The doc is meant to be re-read, not skimmed once.

### Workflow

1. Open `index.html` in a browser and read the affected section in context
2. Edit the HTML directly — sections are clearly delimited by comment banners
3. Confirm the layout still looks clean (cards align, no orphan flow arrows, no weird mid-bullet `<em>` tags that break columns)
4. Bump the version number in the footer (`v0.x`)
5. Open a PR with a short rationale: what changed, why, what you considered and rejected

If you're using an AI agent to help draft, follow the same standard you'd expect of yourself — review carefully, cut anything generic, and own the result.

## Style & writing conventions

- **Section leads** are one or two sentences. They state a principle, not a summary.
- **Core Insight callouts** name the source where possible (Ward Cunningham, Kent Beck, Charity Majors, Rich Hickey, Google SRE, NIST, Conway). One callout per section is plenty.
- **Card titles** are short noun phrases prefixed with a single emoji for visual scannability. Don't overload titles with verbs or sub-clauses.
- **Card body paragraphs** are 1–3 sentences explaining *why* this matters. They should never restate what the bullets already say.
- **Bullets** are 3–5 per card. Each bullet is a complete, self-contained guardrail. Avoid sub-bullets.
- **No em-dash overload, no semicolons mid-bullet, no inline `<em>` or `<code>` mid-list** — they break the layout in subtle ways.
- **Industry references** are welcome but should not require the reader to look anything up to understand the point.
- **Avoid jargon walls.** If a guardrail relies on a term, briefly say what it is the first time it appears.

## Formatting & layout rules

These have been learned the hard way. Please respect them:

- **Cards** use `<div class="card">` with `<h3>` title, optional `<p>` framing, and a `<ul>` of bullets. Don't invent new card variants without discussion.
- **Callouts** come in three flavors: `callout-insight` (blue, for core insights), `callout-warn` (red, for failure modes), `callout-lesson` (amber, for industry lessons). Use them sparingly — at most one or two per section.
- **Flow diagrams** (`<div class="flow">`) are for genuine sequential processes only. They should fit in 3–6 steps. The trailing arrow after the last step is hidden by CSS.
- **Tables** (`<table class="compare-table">`) are for two-column compare/contrast only. Don't shoehorn long lists into them.
- Avoid adding new top-level CSS classes unless you genuinely need them. The existing system covers most cases.

## What this document is *not*

- Not a Wiki dump of every engineering practice we follow
- Not a runbook, onboarding guide, or how-to
- Not a place for team-specific conventions (those belong in team READMEs)
- Not a contract or compliance document — it's guidance, not policy

## Open questions / known gaps

These are areas where we could use input from collaborators:

- **Security & threat modeling** — currently scattered across integrations and AI sections; deserves its own treatment
- **Frontend & client-side guardrails** — the current doc is backend-leaning
- **Data engineering & ML systems** — pipelines, feature stores, model deployment guardrails
- **Cost & efficiency** — when does over-engineering for cost become a guardrail of its own?
- **People & team practices** — on-call health, rotation design, knowledge transfer

If you have strong opinions on any of these, please contribute.

## Versioning

Single integer-after-decimal versions: `v0.1`, `v0.2`, etc. Bump on any meaningful content change. Footer in `index.html` is the source of truth.

---

Maintained by the Earnest engineering leadership group. Questions, disagreements, and proposed changes are all welcome — push back hard, the doc is better for it.
