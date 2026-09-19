---
name: article
description: "Write a long-form technical article in your voice — Substack newsletter, dev.to, Medium, or Hashnode — grounded in a real feature, concept, or learning note, drafted as a plain-text (.txt) file for review. Every piece has a title and a subtitle. Reads the shared voice profile so it sounds like you, not an LLM: the locked 'Dearest gentle readers' open, brute-force-first teaching arc, homework CTA, 'Keep building' close. Never publishes. Use when asked to write an article, blog post, newsletter, dev.to/Medium/Hashnode piece, 'turn this feature into an article', or 'write up X as a post'. Not short-form social copy."
---

# Article Skill

Writes a full long-form article that reads like **you wrote it** — because it's authored to your
recorded voice and grounded in work you actually did. Substance in (a feature, a concept, a learning
note), a publish-ready plain-text draft out.

It never invents your experience and never publishes — it drafts for your review.

**Output format is locked: a single `.txt` file, never markdown.** Most newsletter platforms do not
render pasted markdown cleanly — `#` headings, `**bold**`, and fenced code show up as literal junk.
Plain text avoids that. Code that can't live in the prose goes in
`[ CODE BLOCK: <lang> ]` … `[ END CODE BLOCK ]` markers so you can drop each snippet into the
platform's own code-block button and delete the two marker lines. See Step 3 for the full format.

`SKILL_DIR` = the directory containing this SKILL.md.

**Before drafting, always load both:**

1. `SKILL_DIR/references/voice-profile.md` — how you sound (the locked rituals live here). It ships
   as a template with `[Your Name]` / `[Your Publication]` placeholders; fill those in before the
   first draft. If it's missing, say so and stop — the whole point is the voice; don't fake it.
2. `SKILL_DIR/references/article-craft.md` — how the article is structured and grounded.

---

## Step 0 — Gather inputs

| Field | Required | Example / default |
|-------|----------|-------------------|
| `source` | Yes | what it's about + where the substance comes from — a feature/diff, a concept, a learning note, a talk, or a raw idea |
| `platform` | No | `substack` (default) · `dev.to` · `medium` · `hashnode` |
| `angle` | No | the specific take/hook; inferred from the source if omitted |
| `length` | No | default: a complete piece (~1,200–2,500 words), sized to the substance |

If the source is a raw idea with no real grounding, ask **one** focused question to anchor it in
something you actually did — then proceed. Don't interrogate, and don't fabricate a story to fill the
gap.

---

## Step 1 — Get the real substance

Never write from thin air. Pull the concrete material first:

- Feature/diff → read the code and `git log` for what actually shipped and why.
- Concept → make sure the technical spine is correct before drafting.
- Learning note → read the note.
- Talk/event/project → use only details the user gives; invent nothing.

Extract the real worked example, the real trade-off, the real "this bug almost finished me" moment.
Authenticity is the product — a made-up metric or anecdote breaks it.

---

## Step 2 — Load the voice and design the spine

Load the voice profile and `article-craft.md`. Lay out the beats from the craft guide's spine:
ritual open → reframe/stakes → vivid problem → build (brute-force-first) → code → payoff → homework →
ritual close. For a personal/community piece, bend the middle to storytelling but keep the rituals and
the CTA.

Write a **fresh** check-in line for the opener (never reuse a previous one) and a fresh sign-off.

---

## Step 3 — Draft

Write the full piece as **plain text**, to the voice profile and the spine. Non-negotiables:

- Open with a **title** on the first line and a **subtitle** on the next non-blank line. Every piece
  has both. The title names the idea; the subtitle is one line that promises the payoff (it becomes
  the Substack subtitle field). Then the `Dearest gentle readers,` opener + the fresh check-in.
- Your rhythm: short punchy standalone lines, one-sentence beats, second-person scene-painting,
  triads, the signpost phrases. Not generic "engaging blog" prose.
- Reframe the technical into a real backend scenario; teach the reasoning before the code; explain
  WHY not WHAT in code.
- On dev.to/Medium/Hashnode, make the line after the check-in carry the search hook.
- End with concrete homework, then the locked sign-off + "Keep building." (the brick emoji 🧱 is
  optional here since the file is not rendered).
- No corporate speak, no cold clichés.

**Plain-text format (locked — no markdown):**

- No `#` headings, no `**bold**`, no `` `backticks` ``, no `---` rules. Section headings are plain
  lines (you style them as H2 in the platform yourself). Blank lines separate blocks.
- **No em-dashes or en-dashes anywhere**, including in the code-block markers. Use a comma, colon, or
  full stop.
- Code goes between `[ CODE BLOCK: <lang> ]` and `[ END CODE BLOCK ]` marker lines, with the raw code
  in between. You paste the code into the platform's code-block button and delete the two markers.

Save to `~/content/articles/<slug>.txt` (create the dir if needed) unless the user names another path.
`.txt` only — never write a `.md` draft.

---

## Step 4 — Self-check and report

Run the self-check from `article-craft.md` against the draft. Then report, leading with the verdict:

```
━━━ ARTICLE ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Title ............ "Slow Down to Speed Up"
Subtitle ......... The 10-step framework I wish I'd had before my first system-design round
Platform ......... substack
Grounded in ...... learning note on interview frameworks
Length ........... ~1,600 words
Voice check ...... opener ✓ (fresh check-in) · subtitle ✓ · homework CTA ✓ · sign-off ✓
                   no banned phrases ✓ · no em/en-dashes ✓ · plain text, no markdown ✓
Saved ............ ~/content/articles/slow-down-to-speed-up.txt
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
VERDICT: ✅ Draft ready for review

Next: read it top to bottom for voice, then publish yourself.
```

Never publish or post. The draft is yours to review, tweak, and ship. If the voice profile was
missing or the source couldn't be grounded in anything real, say so plainly instead of papering over it.
