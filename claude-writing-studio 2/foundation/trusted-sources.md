# Trusted Sources

Where Claude should look when verifying claims or supporting new writing. This file controls the scope of web search: general by default, or narrowed to this list when the piece demands high-credibility citations.

## How web search is scoped

Three modes, toggled per draft via the `refine-web-sources` skill or directly in a prompt:

1. **General** - any credible source, used for background color and quick fact checks on widely-known information
2. **Trusted-only** - search limited to the domains listed below, used for anything cited in the final draft
3. **Custom** - a list specified for a single piece (e.g., a specific competitor or a named report)

Default for fact-check-pass and publish-ready-review is **Trusted-only**.

## Trusted domains

Edit this list to match what your team considers credible. Group by category so Claude can pick the right one for the claim type.

### Tier 1: primary research and official sources
[Government statistics, standards bodies, and primary research publishers. Cite freely.]
- [e.g. bls.gov, census.gov, sec.gov]
- [e.g. nist.gov, ieee.org]

### Tier 2: major research firms and analysts
[Industry analyst firms. Cite but note the analyst relationship if relevant.]
- [e.g. gartner.com, forrester.com, idc.com, mckinsey.com, bcg.com]

### Tier 3: reputable publications and academic sources
[Established journalism and peer-reviewed work.]
- [e.g. hbr.org, mit.edu, stanford.edu]
- [e.g. wsj.com, nytimes.com, economist.com, ft.com]

### Tier 4: credible trade press
[Industry-specific publications. Useful for niche claims, weaker for big ones.]
- [e.g. techcrunch.com, stratechery.com, ben-thompson.com]
- [Add your industry's relevant trade press]

### Company sources
[Specific companies whose data we cite. Competitor earnings, customer case studies.]
- [e.g. company-investor-relations-sites]

## Sources we do NOT trust

Domains to avoid even in general search. Aggregators, SEO farms, or low-quality content.

- Content farms with thin, aggregated content
- Wikipedia as a primary source (use it to find primary sources)
- Press release wires for independent verification
- [Add your own]

## Citation format

When Claude includes a claim from a web source, it should cite like this:

```
Claim. [Publication, headline or title, publication date, URL]
```

Example:
```
B2B buyers complete ~70% of their research before talking to sales.
[Gartner, "The New B2B Buying Journey," 2019, gartner.com/...]
```

Inline in drafts, use markdown-style links: `[source](url)`.

## Per-draft overrides

When drafting, you can override the default scope:

- "Use general web for this piece, trusted-only for any specific stat."
- "Only cite from this specific report: [URL]."
- "Don't use web at all, source docs only."

Claude should respect the most restrictive scope set for the session.

## How to use this file

When running any skill that does fact-checking or research, Claude should:
- Default to Tier 1-3 domains when a claim needs external support
- Use Tier 4 only when higher tiers don't have what's needed, and note that the source is trade press
- Never cite from the "do not trust" list
- Format citations as specified above
