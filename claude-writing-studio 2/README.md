# Claude Writing Studio

A shared Claude Code setup for producing near-publish-ready drafts with built-in guardrails against hallucinations, false claims, and hyperbole.

## What this is

A repo that gives Claude Code four things before it starts writing:

1. **Context** about who we are, who we write for, and how we sound
2. **Rules** about what counts as hallucination, exaggeration, or puffery
3. **Reach** into source docs, our knowledge base, and the web
4. **Operation** via skills that produce drafts, critique them, and attach a publish-ready checklist

The goal: drafts that need light human editing, not a full rewrite. And a feedback loop that catches problems before they ship.

## Quick start (first time setup)

```bash
# 1. Clone the repo
git clone <repo-url>
cd claude-writing-studio

# 2. Install Claude Code (if you haven't)
npm install -g @anthropic-ai/claude-code

# 3. Fill in your personal details
#    Open CLAUDE.md and replace the [PLACEHOLDERS]
#    Open foundation/ files and fill them in (see each file's instructions)

# 4. Start Claude
claude
```

On first run, Claude will read `CLAUDE.md` automatically, which pulls in the foundation files. Ask it "what do you know about our audience and voice?" to confirm the context layer loaded correctly.

## Folder structure

```
claude-writing-studio/
├── CLAUDE.md              # Operating manual, auto-loaded every session
├── foundation/            # Context layer (audience, voice, rules, sources)
├── knowledge-base/        # Persistent reference material (reports, briefs)
├── sources/               # Per-draft source docs (transcripts, research)
├── drafts/                # Work in progress
├── published/             # Archive of shipped pieces
├── reviews/               # Fact-check reports produced by skills
└── .claude/
    ├── settings.json      # Permissions
    └── skills/            # Repeatable workflows
```

## How the writing loop works

The intended flow for any piece:

1. **Drop source material** into `sources/[topic-name]/` (transcripts, research, interview notes, product specs, competitive intel).
2. **Invoke the `draft-content` skill** with a brief. Claude reads your sources, loads relevant foundation files, optionally consults `knowledge-base/`, and produces a draft in `drafts/`.
3. **Run the `fact-check-pass` skill** on the draft. Claude self-critiques, extracts every claim, flags anything unsupported, and produces a revised draft plus a critique log.
4. **Run the `publish-ready-review` skill** for the final checklist: claims with sources, hyperbole audit, weasel word audit, voice fit, audience fit, positioning alignment.
5. **Human review.** The checklist makes this fast. Approve or ask for targeted revisions.
6. **Move to `published/`** once it ships.

## The guardrail philosophy

Claude is fluent, which means it's good at sounding confident about things it can't actually back up. This setup is designed around that risk:

- `foundation/verification-rules.md` defines what we consider hallucination, exaggeration, and hyperbole
- `foundation/trusted-sources.md` lists preferred sources and how to scope web search
- Every skill explicitly loads those files
- The fact-check pass runs as a separate skill, not an afterthought inside drafting, so critique and generation don't collapse into the same voice

## Working as a team

This repo is designed to be shared. A few conventions:

- **Treat `foundation/` as shared canon.** Changes go through PR review so everyone writes from the same baseline.
- **Keep personal workflow in branches** if you're experimenting with new skills before promoting them to `main`.
- **`knowledge-base/` grows slowly and deliberately.** Add vetted reference material, not every doc you touch. Stale reference material is worse than none.
- **Use `sources/[topic]/` per piece** and delete or archive when done. It's scratch space, not a library.
- **`drafts/` can be messy.** `published/` should be clean.

## Updating the foundation

Foundation files decay. Audience vocabulary drifts, positioning shifts, voice evolves. Run `find-skills` weekly to surface patterns worth automating, and schedule a quarterly foundation audit.

## Troubleshooting

**Claude is ignoring my foundation files.**
Check your `@foundation/...` imports in `CLAUDE.md`. Paths are relative to the project root. If Claude responds generically to questions about your audience or voice, the imports aren't wired correctly.

**A skill isn't firing.**
Skills need YAML frontmatter at the top (a `---` block with `name` and `description`). Without it, Claude doesn't register the file as a skill. Check the examples in `.claude/skills/`.

**Web search is pulling from sources we don't trust.**
Invoke the `refine-web-sources` skill to scope the search to the domains in `foundation/trusted-sources.md`.

## Reference

- Claude Code docs: https://docs.claude.com
- `claude --help` in your terminal for command reference
