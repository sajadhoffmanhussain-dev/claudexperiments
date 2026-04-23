# Content Types

Per-format conventions. Claude applies the matching profile based on what you're drafting.

## Blog posts / articles

**Typical length**: 800-2000 words
**Structure**: Hook, problem, insight, evidence, implication, action
**Voice tilt**: Conversational end of the core voice, first person allowed
**Claim density**: Higher. Opinions okay if labeled. Stats need sources.
**CTA**: Usually soft. Subscribe, related reading, share. Not a sales ask.

## Marketing / sales copy

**Typical length**: Varies wildly. Landing pages 300-800 words. Emails 100-300.
**Structure**: Claim, proof, action. Every section earns its place.
**Voice tilt**: Tighter, more direct. Less first person, more "you."
**Claim density**: Highest stakes. Every claim ships to a buyer. Zero tolerance for unsupported claims.
**CTA**: Specific, explicit, measurable.

## Internal comms / docs

**Typical length**: Whatever's needed, rarely long.
**Structure**: Headline, context, decision or ask, next steps.
**Voice tilt**: Direct. No performance. Assume the reader is busy.
**Claim density**: Facts matter. Opinions labeled. No persuasion posture.
**CTA**: Usually an action or decision needed by a specific date.

## Technical / product content

**Typical length**: 500-1500 words for announcements, longer for guides.
**Structure**: What it is, why it matters, how to use it, what to watch out for.
**Voice tilt**: Precise. Jargon only when it's the right word. Explain on first use.
**Claim density**: Facts only. Feature claims must match the spec exactly.
**CTA**: Docs link, trial, upgrade path. Specific.

## Social copy

**Typical length**: LinkedIn 1200-1800 chars. Twitter 240. Threads up to 10 posts.
**Structure**: Hook first line, specific middle, clean landing.
**Voice tilt**: Boldest version of the core voice. Personality turned up.
**Claim density**: Lower tolerance for hedging, higher tolerance for opinion. But claims still need backing.
**CTA**: Low-pressure. Reply, share, or click through.

## Whitepapers

**Typical length**: 2000-5000 words. Research-dense.
**Structure**: Executive summary, problem, research findings, implications, recommendations.
**Voice tilt**: Authoritative but not stuffy. Evidence over adjectives.
**Claim density**: Highest evidence bar. Every claim cited. Footnotes or inline links.
**CTA**: Implicit or soft. Downloads, demo requests, follow-up briefings.

## Case studies

**Typical length**: 800-1500 words.
**Structure**: Customer context, challenge, approach, result, customer quote.
**Voice tilt**: Customer-led. Their words before ours.
**Claim density**: All results must match the source material in `sources/`. No embellishment.
**CTA**: Usually a soft "see if this could work for you" link.

## How Claude uses this file

When you invoke `draft-content`, tell Claude the content type. Claude will:
- Apply the matching length target, structure, and voice tilt
- Adjust claim density and citation rigor
- Shape the CTA to match the type
- Note which content type the draft is targeted at in the header of the output

If you don't specify, Claude asks before drafting.
