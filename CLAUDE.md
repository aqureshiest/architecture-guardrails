# Earnest Eng Journals

A collection of engineering proposals, architecture documents, and living design documents from the Earnest engineering team.

## Repository structure

```
earnest-eng-journals/
├── CLAUDE.md                        ← this file (root-level instructions)
├── index.html                       ← home page listing all documents
├── architecture-guardrails/
│   ├── CLAUDE.md                    ← section-specific instructions
│   └── index.html
├── infra-ai-improvements/
│   └── index.html
├── earnest-agents/
│   └── index.html
├── avp-laps-poc/
│   └── index.html
└── sdlc-improvements/
    └── index.html
```

There is intentionally no build step, framework, or tooling. Anyone can open any `index.html` in a browser immediately.

## Adding a new document

1. Create a new folder with a short kebab-case name (e.g. `my-proposal/`)
2. Add an `index.html` inside it — standalone HTML, self-contained styles
3. Optionally add a `CLAUDE.md` inside the folder if the doc has its own editorial conventions
4. Add a card for it in the root `index.html` grid
5. Bump the version in the root `index.html` footer
6. Open a PR with a short rationale

## Root index.html

The home page (`index.html`) is a simple card grid — one card per document. Each card has:
- A **tag** (short category label, e.g. "Proposal", "Architecture", "POC", "Guardrails", "DX")
- A **title** (the document's name)
- A **description** (1–2 sentences on what it covers)

Keep descriptions honest and specific. Don't add a card without a real description.

## Document conventions

- Each document is a **single self-contained HTML file** (`index.html` inside its folder)
- Documents may have their own styling — no shared CSS framework is required
- Documents should be readable standalone, without needing the home page for context
- No minification, bundling, or preprocessing — raw HTML only

## What belongs here

- Architecture proposals and RFCs
- Design documents for significant initiatives
- Living guardrails and standards docs
- POC write-ups worth preserving

## What does not belong here

- Runbooks or operational playbooks (those belong in team wikis)
- Team-specific conventions (those belong in team READMEs)
- Ephemeral notes or drafts (use a PR description instead)
- Compliance or policy documents

## Versioning

Root `index.html` footer tracks the journal version (`v0.1`, `v0.2`, etc.). Bump on any meaningful addition or change.
