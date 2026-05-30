# Part 1: What You're Getting

A copy-paste Claude Code prompt that interviews you for 20-30 minutes and builds the complete business context every other Claude Code skill in the Meta Ads bundle needs to produce non-generic output.

I walk through why this matters in the Meta Ads + Claude Code video here: https://youtu.be/_TODO_VIDEO_URL_

Without this, every other skill in the bundle (`/ad-strategy`, `/nano-banana`, `/funnel-spy`, `/meta-ads`) produces generic, theoretical output. With it, every output Claude generates is **yours** - your offer, your ICP, your brand voice, your funnel, your examples - because the context lives in `CLAUDE.md` + a `context/` folder that loads automatically at the start of every Claude Code session.

This is the **invisible foundation** of the whole system. Skip it and the rest of the bundle is 10x less useful.

## What It Does

Run the install prompt in any working directory (your business workspace). The prompt:

1. Reads any brand knowledge base file you have (e.g. PDF, markdown, doc) - optional, but speeds things up if you have one
2. Interviews you one section at a time across these 8 topics:
   - **Identity** - who the business is, founders, origin, mission
   - **Audience (ICP)** - who you sell to, their pain points, their language
   - **Voice** - how the brand talks (tone words, do/don't list, example sentences)
   - **Positioning** - what you sell, what you're NOT, anti-positioning
   - **Offers** - the full offer ladder with pricing and deliverables
   - **Results** - case studies, social proof, named numbers
   - **Funnel** - your current customer journey (top of funnel to retention)
   - **Frameworks** - your proprietary methodology / IP, if any
3. Writes one file per topic to `./context/`:
   - `context/identity.md`
   - `context/audience.md`
   - `context/voice.md`
   - `context/positioning.md`
   - `context/offers.md`
   - `context/results.md`
   - `context/funnel.md`
   - `context/frameworks.md`
4. Writes a `CLAUDE.md` router at the project root that tells Claude which file to read for which kind of work (e.g. "for ad copy, read voice.md + positioning.md + audience.md")

## Why This Format

`CLAUDE.md` files load automatically into every Claude Code session in that working directory. So you only fill this out once. Every future Claude Code session in this directory starts with full business context already loaded - no re-explaining.

The `context/` files are referenced by name from `CLAUDE.md`, so Claude loads only what it needs for each task (saves context budget on long sessions).

## What You Need

- **Claude Code** - https://claude.ai/code
- **20-30 minutes** for the interview
- (Optional) Any existing brand knowledge base file - speed up the interview by attaching it to the chat

## Heads Up

- **One workspace per business.** If you run 3 businesses, run this 3 times in 3 different folders. Each gets its own CLAUDE.md + context/. The Meta Ads bundle skills read from the current working directory.
- **You can edit the context files anytime** - they're just Markdown. The interview is a starting point, not a final answer. Update `voice.md` as your brand evolves.
- **Re-running the prompt** in the same directory updates existing files (it asks before overwriting). Useful when your offer changes.

---

# Part 2: Copy-Paste This Into Claude Code

```
I want you to install the cc-business-context Claude Code prompt from https://github.com/bosar-academy/cc-business-context and run the business context interview to scaffold CLAUDE.md + context/ files in my current working directory.

Step 1 - Clone the prompt repo (read-only - we won't install into ~/.claude/skills/):

Run:
  git clone https://github.com/bosar-academy/cc-business-context /tmp/cc-business-context

Step 2 - Confirm working directory:

Tell me which directory we're in (run `pwd`) and confirm this is where I want my business context to live. If I want a different directory, ask me to cd there first and re-run the prompt.

Standard pattern: one workspace per business. So if I run 3 businesses, this should be in business-specific folders like ~/Projects/my-coaching-biz/ or ~/Projects/ecom-store/.

Step 3 - Ask if I have a brand knowledge base file:

Ask me: "Do you have an existing brand knowledge base file (PDF, doc, markdown) that I should read first to speed up the interview? If yes, paste the path. If not, just say 'skip' and I'll interview you from scratch."

If I provide a file, read it and use its content to pre-fill answers (then confirm each with me before writing). If I skip, do a full cold interview.

Step 4 - Run the interview:

Open /tmp/cc-business-context/prompts/business-context-interview.md and walk me through the 8 sections one at a time. For each section:

  1. Read the section's questions from the prompt
  2. Ask me each question conversationally (don't list-dump - it feels like a survey)
  3. Synthesize my answers into structured markdown
  4. Show me the draft for confirmation before writing the file
  5. Once confirmed, write to ./context/<section>.md
  6. Move to next section

The 8 sections are:
  1. Identity (./context/identity.md)
  2. Audience / ICP (./context/audience.md)
  3. Voice (./context/voice.md)
  4. Positioning (./context/positioning.md)
  5. Offers (./context/offers.md)
  6. Results (./context/results.md)
  7. Funnel (./context/funnel.md)
  8. Frameworks (./context/frameworks.md)

Pace: 3-4 minutes per section. ~20-30 min total. Don't rush, but don't loiter either. If I give a thin answer, ask one follow-up to deepen it. Two follow-ups max - then move on.

Step 5 - Write the CLAUDE.md router:

Once all 8 context files are written, generate ./CLAUDE.md using the template at /tmp/cc-business-context/templates/CLAUDE.md.template. The router tells Claude which context files to load for which kind of work:

  - For ad copy → voice.md + positioning.md + audience.md
  - For social content → voice.md + audience.md + results.md
  - For web copy → voice.md + positioning.md + offers.md
  - For strategy decisions → all 8 files
  - For new offers / pricing → offers.md + results.md
  - For sales call talking points → audience.md + results.md + offers.md

Fill in the brand name and any project-specific overrides from the interview.

Step 6 - Confirm I'm ready:

Tell me the foundation is in place. Remind me:

- Every Claude Code session in this directory now starts with my business context loaded automatically (via CLAUDE.md)
- The context/ files are just Markdown - edit anytime as my business evolves
- This foundation feeds every other skill in the Meta Ads bundle (/ad-strategy, /nano-banana, /funnel-spy, /meta-ads) - they all read from CLAUDE.md to produce non-generic output
- If I want to run this for a SECOND business, cd to a different directory and re-run the install prompt

That's it - the invisible foundation is in place.
```
