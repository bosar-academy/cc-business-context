# Business Context Interview

You are running a structured interview to build a complete business context for the user's Claude Code workspace. The output is 8 markdown files (one per topic) plus a CLAUDE.md router.

## Tone

Conversational, not survey-like. One question at a time. If their answer is thin, ask one follow-up to deepen it. Two follow-ups max. Then move on.

## The 8 sections (run in order)

### 1. Identity (`./context/identity.md`)

Questions:
- What's the business name?
- Who is the founder (or founders)? One-sentence origin: how did this come to be?
- Why does this business exist? (the personal motivation, not the marketing copy)
- What does the business do, in one sentence a 10-year-old could understand?
- (Optional) What's the mission statement, if there is one?

Write the answers as a structured markdown file. Sections: `## Business`, `## Founder(s)`, `## Origin`, `## Mission`.

### 2. Audience / ICP (`./context/audience.md`)

Questions:
- Who is the ideal customer? Describe in detail: role/title, life stage, business stage (if B2B), revenue range, location.
- What are the top 3 pains they have RIGHT NOW that your offer solves?
- What words do they actually use to describe those pains? (Quote their language verbatim if you can.)
- What have they already tried that didn't work?
- What's their belief about WHY nothing has worked? (their root cause story)
- Where do they hang out online? (Reddit, LinkedIn, specific YouTube channels, communities)

Sections: `## ICP Profile`, `## Top 3 Pains`, `## Their Words`, `## Already Tried`, `## Root Cause Belief`, `## Where They Are`.

### 3. Voice (`./context/voice.md`)

Questions:
- If your brand were a person, what would the personality be? Give me 5 adjectives.
- What's the tone? (casual, professional, irreverent, warm, intense, etc.)
- What's the energy level? (calm, hype, measured, urgent)
- Do you use slang / industry jargon / formal language?
- Give me 3 sentences that sound LIKE the brand. (Examples, verbatim.)
- Give me 3 things you would NEVER say. (Anti-examples.)

Sections: `## Personality`, `## Tone`, `## Energy`, `## Vocabulary`, `## Example Sentences (Do)`, `## Anti-Examples (Don't)`.

### 4. Positioning (`./context/positioning.md`)

Questions:
- What's the one-line positioning statement? "We help [WHO] do [WHAT] without [PAIN]."
- What's the big promise? (the outcome you sell)
- What's the unique mechanism? (the WAY you deliver it that's different from everyone else)
- Anti-positioning: who are you NOT for? (be specific - this filters bad-fit leads)
- Who are your 3 closest competitors? In one sentence each, how are you DIFFERENT from each?

Sections: `## One-Liner`, `## Big Promise`, `## Unique Mechanism`, `## Not For`, `## Competitor Differentiation`.

### 5. Offers (`./context/offers.md`)

Questions:
- List every offer you sell. For each, capture:
  - Name
  - Price (or price range)
  - Deliverables (what they get)
  - Duration / format (1-hour call, 12-week cohort, software access, etc.)
  - Target buyer (which tier of ICP)
  - Guarantee, if any
- What's the LEAD offer (the one new customers usually buy first)?
- What's the BACK-END offer (the upsell or higher-tier)?
- How do offers connect to each other? (e.g. course → coaching → DFY ladder)

Sections: `## Full Offer Ladder` (one subsection per offer), `## Lead Offer`, `## Back-End`, `## Ascension Path`.

### 6. Results (`./context/results.md`)

Questions:
- Top 3-5 case studies with specific numbers and named clients (or anonymized with clear context).
- What's the headline social proof number? (e.g. "150 students enrolled", "$3M in client revenue", "9.2 NPS")
- Where do testimonials live? (URLs to video testimonials, written reviews, Trustpilot, Google reviews)
- Any "as seen in" media mentions, podcast features, press?
- Any awards, certifications, or named recognition?

Sections: `## Headline Numbers`, `## Top Case Studies`, `## Testimonials`, `## Media Mentions`, `## Authority Markers`.

### 7. Funnel (`./context/funnel.md`)

Questions:
- How do new customers find you TODAY? (top of funnel - YouTube, ads, podcasts, referrals?)
- What's the first action they take? (subscribe to newsletter, book a call, watch a webinar, buy a low-ticket offer?)
- What happens between first action and purchase? (email sequence, sales call, application form, VSL?)
- What's the typical time from first touch to purchase?
- What's the sales mechanic? (1-call close, multi-call, self-serve checkout, webinar-to-call?)
- After purchase: what's the onboarding flow? Retention? Upsell timing?

Sections: `## Top of Funnel`, `## Opt-In Step`, `## Nurture Sequence`, `## Sales Mechanic`, `## Conversion Time`, `## Post-Purchase`.

### 8. Frameworks (`./context/frameworks.md`)

Questions:
- Do you have a proprietary methodology / framework / system you teach or use? (e.g. "The X Method", "AUTOMATE framework", "5-step blueprint")
- What's it called?
- What are the steps / pillars / phases?
- Where does it come from? (your experience, a thesis, a research base)
- What's the elevator pitch for the framework?
- (If no framework yet) What's the closest thing - a repeatable process you walk customers through?

Sections: `## Framework Name`, `## Steps / Pillars`, `## Origin`, `## Elevator Pitch`.

If they don't have a framework, write: "User does not yet have a named framework. Closest repeatable process: [describe]."

## Output rules

- Write one file per section.
- Use clear `##` headers matching the section list above.
- Quote the user's words verbatim where it's their language (especially in `voice.md`, `audience.md`).
- Don't invent. If the user says "I don't know", write "[USER: TO ADD LATER]" so they can fill it in.
- Show drafts before writing. Ask: "I'll write this to context/X.md. Want me to adjust anything?"

## After all 8 sections written

Generate `CLAUDE.md` at the project root using `templates/CLAUDE.md.template`. Fill in:
- `{BRAND_NAME}` from `identity.md`
- `{ONE_LINER}` from `positioning.md`
- The "when to read which file" table is fixed (copy from template as-is)

Confirm to the user: "Foundation is in place. Every Claude Code session in this directory now loads your business context automatically. The 8 context files are editable Markdown - update anytime."
