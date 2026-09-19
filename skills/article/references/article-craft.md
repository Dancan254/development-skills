# Article Craft Guide

How to build a long-form written article in your voice. Load this together with the voice profile at
`SKILL_DIR/references/voice-profile.md` before drafting. The voice profile owns *how it sounds*; this
guide owns *how it's structured and grounded*.

An article is a published, long-form written piece — Substack newsletter, dev.to, Medium, Hashnode.
It is not a LinkedIn post (short), not a video script (spoken), not a PDF.

---

## The spine

Your pieces follow a consistent arc. Fill each beat; don't pad between them.

0. **Title + subtitle.** Every piece opens with a title line and, directly under it, a one-line
   subtitle that promises the payoff. The title names the idea, the subtitle sells the read. Both are
   always present.
1. **The ritual open.** `Dearest gentle readers,` + a *fresh* warm check-in tied to the theme (see
   voice profile — this is locked).
2. **The reframe / stakes.** Name the reader's real situation and why this matters now. Often a
   confession or a "here's the truth" pivot. This is where the SEO hook lands on cold platforms.
3. **The problem, made vivid.** A concrete scene or a real backend scenario. Second person. Make the
   reader *feel* the pain before the fix ("Picture it. …").
4. **The build.** The teaching core. Brute-force first → find the bottleneck → the clean solution.
   Numbered framework if it fits. A worked example traced by hand *before* any code.
5. **The code.** Introduced only after the reasoning is done, living inside the narrative, explained
   for WHY not WHAT. Keep samples short and idiomatic to your stack (Java 25, Spring Boot 4).
6. **The payoff.** "What actually changed here" — zoom out, state the lesson and the trade-off
   plainly (e.g. "we traded a little memory for a huge speed win").
7. **The homework / CTA.** One concrete thing to do tonight. Small, specific, doable.
8. **The ritual close.** Short warm sign-off + "Keep building." Locked.

A personal / community piece bends the middle: beats 3–6 become storytelling and reflection instead
of a technical build, but beats 1, 2, 7, 8 hold.

---

## Ground it in something real

Never invent experience. Pull the substance from one of:

- a **feature or diff** you actually shipped (read the code / `git log`),
- a **concept you actually learned**,
- a **real learning note**,
- a **real talk / event / project**.

If the source is thin, ask one focused question about the angle — don't fabricate a war story or a
metric. The authenticity is the whole point; a made-up anecdote breaks the reader's trust and yours.

---

## Platform notes

| Platform | Shape |
|----------|-------|
| **Substack** (default) | Full personal warmth. Opener at full strength — it's a relationship. Newsletter cadence ("since we last spoke"). |
| **dev.to / Hashnode** | Same voice, but the line after the check-in must carry the search hook hard (cold traffic). Add a short intro line for tags/canonical if asked. |
| **Medium** | As dev.to; slightly more formal subheads are fine. |

Output is a **plain-text `.txt` file**, never markdown. Most platforms render pasted markdown as
literal junk. So: no `#` subheads, no `**bold**`, no backticks, no `---` rules, no fenced code.
Section headings are plain lines. Code lives between `[ CODE BLOCK: <lang> ]` and
`[ END CODE BLOCK ]` markers, raw code in between, so you drop each snippet into the platform's
code-block button and delete the markers. No em-dashes or en-dashes anywhere, including the markers.

---

## Length

Default to a **complete piece**, not a teaser — aim for substance (1,200–2,500 words). But every
paragraph earns its place; a tight 1,400-word piece beats a padded 2,400-word one. Match length to the
substance, not a word target.

---

## Self-check before shipping

- [ ] Has a title line and a subtitle line before the opener
- [ ] Plain-text `.txt`, no markdown syntax; code in `[ CODE BLOCK: … ]` markers; no dashes anywhere
- [ ] Opens with the locked `Dearest gentle readers,` ritual
- [ ] Check-in line is **fresh** — not reused from a previous piece
- [ ] Grounded in something real, no invented experience or metrics
- [ ] Brute-force-first teaching arc, worked example before code (for technical pieces)
- [ ] Ends with concrete homework/CTA
- [ ] Closes with the locked sign-off + "Keep building." / 🧱
- [ ] No banned phrases (corporate speak, cold clichés, decorative emoji)
- [ ] Reads in your rhythm: short punchy lines, one-sentence beats, second person
