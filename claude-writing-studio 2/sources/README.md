# Sources

Per-draft working material. One subfolder per piece you're drafting.

## How to use

When starting a new piece, create a subfolder named for the topic:

```
sources/
└── q3-launch-announcement/
    ├── product-spec.md
    ├── customer-interview-acme.txt
    ├── competitor-teardown.md
    └── internal-brief.pdf
```

Drop in anything Claude should treat as source-of-truth for that piece:

- Interview transcripts
- Research notes
- Product specs
- Competitive intel gathered for this piece
- Customer quotes (with attribution)
- Draft briefs or outlines
- Stats and data points you want cited

Then invoke the `draft-content` skill and point it at the folder.

## Cleanup

When the piece ships, either:
- Delete the subfolder (recommended for most work)
- Move any reusable material into `knowledge-base/`

Don't let `sources/` accumulate. Stale per-draft material clutters the signal.
