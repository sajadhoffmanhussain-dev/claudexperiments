# Knowledge Base

Persistent reference material that Claude consults across drafts. This is NOT scratch space for current work (that's `sources/`).

## What lives here

- Reports we trust and cite regularly (e.g. industry benchmarks, internal research)
- Product one-pagers, feature briefs, pricing explainers
- Brand guidelines, messaging frameworks
- Canonical case studies and customer quotes (with attribution)
- Glossary of terms and how we define them
- Historical positioning and campaign recaps worth referencing

## What doesn't live here

- Draft-specific research (use `sources/[topic]/`)
- Unvetted scrapes or uncurated content
- Outdated material (prune regularly)

## Organization

Use subfolders that match how you'll ask for material:

```
knowledge-base/
├── reports/           # Industry and internal research
├── product/           # Product briefs, feature explainers
├── brand/             # Messaging, voice exemplars, guidelines
├── case-studies/      # Customer wins with vetted quotes
└── glossary.md        # How we define our terms
```

## Rule of thumb

If adding something would make Claude's drafts better across multiple future pieces, it belongs here. If it's only relevant to one piece you're writing right now, put it in `sources/` instead.
