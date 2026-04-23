# Verification Rules

What counts as a hallucination, a false claim, an exaggeration, or hyperbole. Claude uses these rules during the fact-check pass and publish-ready review.

## Hallucinations (never ship)

A hallucination is any claim that is fabricated, even if it sounds plausible. These must be caught and fixed, not softened.

- **Fabricated statistics.** A number without a cited source is a hallucination, even if it sounds right.
- **Invented studies or reports.** "A recent study found..." with no citation. If the study is real, cite it. If not, cut the claim.
- **Manufactured quotes.** Never attribute a quote to a person unless it appears in a source doc, the knowledge base, or a verified external source.
- **Fake case studies.** All customer stories must map to a real, cited case in `knowledge-base/case-studies/` or `sources/`.
- **Composite people.** No "imagine a CMO named Sarah who..." unless clearly labeled as hypothetical.
- **Plausible-but-unverified specifics.** Dates, prices, version numbers, feature names. If not in a source, flag or cut.

## False claims (fix before shipping)

Statements that might be literally wrong even if Claude didn't invent them.

- Outdated facts (a stat that was true two years ago but isn't now)
- Misattributed quotes (real quote, wrong person)
- Wrong company names, product names, or feature names
- Incorrect math (percentages, growth rates, comparisons)
- Claims that contradict our own `positioning.md` or product reality

## Exaggerations (tighten the language)

Technically true but overstated. Weakens credibility more than it adds power.

- "Dramatically increased" when the number is modest
- "Transformed their business" for an incremental improvement
- "All of our customers" when we mean most
- Comparisons to "industry average" without showing the math
- Superlatives without qualifiers ("the fastest," "the best")

## Hyperbole (cut or replace)

Words that promise more than the evidence supports. The words below are banned by default. Override only with explicit source backing.

**Banned words and phrases**
- revolutionary, unprecedented, game-changing, game-changer
- cutting-edge, best-in-class, world-class, next-generation
- seamless, frictionless, effortless
- transformative, paradigm shift
- leverage, synergies, move the needle
- 10x, 100x (unless the source says so and we show the math)

**Banned framings**
- "The only X that Y" (almost always false, easy to disprove)
- "Everyone is doing X" (cite the actual data)
- "X is dead" / "X is over" (lazy hook, rarely true)

## Weasel words (replace with specifics)

Language that sounds evidence-based but isn't.

- "Studies show" (which studies?)
- "Many experts agree" (name one)
- "It is widely believed" (by whom?)
- "Leading companies" (which ones?)
- "Most organizations" (most of which set?)
- "Research indicates" (which research?)

## Puffery (cut)

Empty adjectives that sound like marketing.

- "Comprehensive", "robust", "innovative", "dynamic", "scalable"
  when used without a specific thing to attach them to
- Strings of three adjectives (common in decks, fatal in drafts)
- Generic "solutions" language

## What to do when a claim is flagged

During the fact-check pass, Claude should tag every claim with one of:

- **[sourced]** - directly supported by a cited source, include the citation
- **[traceable]** - supported by the knowledge base, include the reference
- **[web-verified]** - supported by a web search, include the link
- **[unverifiable]** - no source found, recommend cutting or rewriting
- **[hallucinated]** - fabricated, must be cut

Claims marked `[unverifiable]` or `[hallucinated]` block the draft from moving to publish-ready.

## How to use this file

When running `fact-check-pass` or `publish-ready-review`, Claude should:
- Extract every factual claim, stat, quote, and attribution
- Classify each using the tags above
- Flag any hyperbole, weasel words, or puffery from the banned lists
- Produce a review report that makes it obvious what needs to be fixed
