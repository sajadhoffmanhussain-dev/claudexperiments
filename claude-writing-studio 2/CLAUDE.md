# CLAUDE.md

## Who we are
[Company name], [what we do] for [who we serve].
This repo is a shared Claude Code setup for producing near-publish-ready drafts.

## What I'm working on
[Your name], [role]. My writing output includes blog posts, marketing and sales copy,
internal comms, technical and product content, social copy, whitepapers, and case studies.

## Context
Foundation files are loaded automatically. Read them before any drafting task.

@foundation/audience.md
@foundation/voice.md
@foundation/positioning.md
@foundation/verification-rules.md
@foundation/trusted-sources.md
@foundation/content-types.md

## The writing loop
Every piece follows this flow. Never collapse steps.

1. `draft-content` skill produces a first draft from sources/ and foundation files.
2. `fact-check-pass` skill critiques the draft. This runs as a separate pass, not inline.
3. `publish-ready-review` skill produces the final checklist attached to the draft.
4. Human review and revisions.

## How I work
- Be direct. No preamble, no summaries of what you are about to do, just do it.
- Give me options with tradeoffs, not a single answer, when the choice matters.
- Flag assumptions. If you are working with incomplete source material, say so before drafting.
- Cite sources inline whenever you make a factual claim. If you cannot cite, flag the claim.
- Match the voice in foundation/voice.md. Style consistency matters as much as accuracy.

## Hard rules
- Never fabricate statistics, quotes, studies, or sources.
- Never write a claim that isn't supported by either a source in sources/,
  a reference in knowledge-base/, or a web search result with a traceable link.
- Never use the hyperbole or weasel words listed in foundation/verification-rules.md.
- Never skip the fact-check-pass before producing a final draft.
- Never write outside the content folder structure. Drafts go to drafts/,
  reviews to reviews/, published pieces to published/.

## Never (tone)
- "Leverage", "synergies", "best-in-class", "move the needle", "game-changing",
  "revolutionary", "unprecedented", "seamless", "cutting-edge"
- "Studies show", "many experts agree", "it is widely known"
- Empty superlatives without evidence
- Corporate throat-clearing at the start of paragraphs
