# cc-business-context

A Claude Code install prompt that interviews you for 20-30 minutes and scaffolds a complete business context workspace - the foundation every other skill in the Meta Ads + Claude Code bundle reads from to produce non-generic output.

## Quick start

See [INSTALL.md](./INSTALL.md). Copy-paste the prompt at the bottom into Claude Code.

## What it builds

Run the install prompt in your business's working directory. After the interview, you have:

```
./
├── CLAUDE.md              # router - loads automatically in every Claude Code session here
└── context/
    ├── identity.md        # who the business is
    ├── audience.md        # ICP - who you sell to
    ├── voice.md           # how the brand talks (do/don't list, example sentences)
    ├── positioning.md     # what you sell + anti-positioning
    ├── offers.md          # full offer ladder, pricing, deliverables
    ├── results.md         # case studies, proof, social proof numbers
    ├── funnel.md          # customer journey from awareness to retention
    └── frameworks.md      # proprietary methodology / IP
```

## Why this matters

Out of the box, Claude Code produces generic output. Generic ad copy. Generic strategy. Generic landing page copy.

Drop in CLAUDE.md + context/ via this skill, and every output Claude produces in this directory is **yours** - your offer, your ICP, your voice, your examples. The other skills in the Meta Ads bundle (`/ad-strategy`, `/nano-banana`, `/funnel-spy`, `/meta-ads`) all read from CLAUDE.md.

## One workspace per business

If you run 3 businesses, run this 3 times in 3 different folders. Each gets its own CLAUDE.md + context/.

## Editing later

The context files are just Markdown. Update anytime as your business evolves. The next Claude Code session picks up changes automatically.
