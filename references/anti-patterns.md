# anti-patterns — what NOT to do

> Before every forward output, scan this list. The most common failure mode of this skill is **being too good a writer** — producing something thoughtful, measured, or self-aware. That is not LinkedIn Speak. The joke only works if you commit fully.

---

## 1. The seven cardinal sins (forward)

### 1.1 — Being too tasteful

**Wrong**:

> Had a tough day today. I think I'm going to take some time to reflect and maybe try a different approach tomorrow.

**Right**:

> I'm currently leaning into a powerful season of strategic recalibration. Today reinforced that the highest-leverage leaders don't just push through — they pivot with intention. Excited for what's next! #GrowthMindset #Resilience #Leadership

**Rule**: if the output could plausibly appear in a diary, you have failed. It must sound like a deck.

---

### 1.2 — Self-awareness / breaking character

**Wrong**:

> I know this sounds ridiculous, but I'm "thrilled to announce" that I ate a cookie today…

**Wrong** (trigger warning style):

> ⚠️ Translating this as LinkedIn Speak for humor purposes: I'm thrilled to share…

**Right**:

> I'm thrilled to share that I've just successfully completed the consumption of a high-quality, artisanal cookie. […]

**Rule**: Never wink. Never caveat. The character is perfectly sincere.

---

### 1.3 — Acknowledging the rawness of the input

**Wrong**:

> This is a difficult post to write, but I recently went through a painful firing…

**Right**:

> I'm excited to share a major pivot in my career journey. My time at my previous role has come to an unexpected end, and I'm choosing to see this as a tremendous opportunity for growth. […]

**Rule**: The LinkedIn voice has no memory of the raw being rough. The reframe is total.

---

### 1.4 — Skipping hashtags or misplacing the emoji tail

**Wrong**: output ends with a sentence and a period (no hashtags).

**Wrong**: hashtags with **no** emoji segment **between** the last body sentence and the first `#`.

**Wrong**: emoji **after** the last hashtag (`#Growth #Mindset 🚀`).

**Right**: every forward output ends with **body → 1–2 corporate-safe emoji → 3–7 hashtags** (CamelCase, space-separated). The emoji tail sits **after** the prose text and **before** the `#` block.

Hard rule — even a 1-sentence short output gets **emoji tail + hashtags**.

---

### 1.5 — Output language (forward)

**Wrong**: Chinese input → English output (register should match the user's language).

**Right**: Primarily **Chinese** input → **Chinese** LinkedIn Speak (same mechanical inflation, Chinese 职场正能量腔). **Other** languages → **English** LinkedIn Speak. Translate meaning first, then inflate.

Exception: **reverse mode** may output plain language in the register that best recovers meaning (often English for English posts; Chinese for Chinese posts).

---

### 1.6 — Generating a "decoded / reality" companion

**Wrong**:

> LinkedIn version: I'm thrilled to share…
> Reality: I got fired.

**Right**: Only the LinkedIn version. The user asked for one direction; deliver that one direction.

Reverse mode is a separate call (`/linkedin --reverse`). Never produce both in one output unless the user explicitly requests both.

---

### 1.7 — Being too smart / too specific

**Wrong** (too clever):

> This experience reminded me of Shannon's 1948 communication theory, which — while technically applicable here — also speaks to…

**Right** (on-brand bland):

> This experience reinforced the importance of alignment, agility, and radical ownership in today's fast-paced ecosystem.

**Rule**: the register trends toward **maximally generic** motivational-industrial complex phrases. Specificity beyond "what the raw said" dilutes the joke. If the output reads as *smart*, you have strayed — real LinkedIn Speak is closer to "it's not X; it's Y" padded with generic virtues.

---

### 1.8 — Fabricating facts

Don't invent:

- Company names not in the raw
- Percentages ("93% of top performers…")
- Named quotes ("So a CEO asked me…")
- Named people ("my mentor, Jane Smith, once told me…")

**OK** to inflate the **description** of something the raw mentioned:

- Raw: `I work at Google` → `contributing to such an innovative ecosystem` ✓
- Raw: `I fixed a bug` → `unlocked a high-leverage stability optimization` ✓

**Not OK** to invent:

- Raw: `I got fired` → `After 7 years at Tesla, I've decided to sunset…` ✗ (Tesla not in raw)

---

## 2. Reverse-mode anti-patterns

### 2.1 — Adding insults

**Wrong**: He got fired and nobody liked him anyway.

**Right**: He got fired.

Reverse strips the LinkedIn layer. It does not add a hostile layer.

---

### 2.2 — Inventing facts the post didn't imply

Only claim what the LinkedIn post gives you grounds to infer. "Started a new chapter" with no next company named → probably fired. "Started a new chapter at Google" → probably not fired.

---

### 2.3 — Being long

Reverse output is **one line**, optionally two. The whole joke is compression: the LinkedIn post is 200 words; the reality is 6.

---

## 3. Red-line refusals

This skill keeps a **minimal** safety net for three cases only. Everything else gets translated.

### 3.1 — Self-harm / suicide intent in the raw

Do NOT translate. Respond with a short line plus hotline info:

> This input reads like you're having thoughts of self-harm. This skill won't rewrite it. If you want to talk to someone right now: https://findahelpline.com/ — or, in mainland China: 北京心理危机研究与干预中心 010-82951332.

Heuristics (any one triggers refusal):

- "I want to kill myself" / "I want to die" / "想死" / "不想活了"
- "I'm going to end it" / "this is my last post"
- Detailed method description ("take all the pills", "jump off")

### 3.2 — Direct threat to a named real person

"I will kill [specific real name]" or equivalent. Do NOT translate. Briefly decline.

Generic / non-named venting and frustration is **fine** ("I want to scream at my manager in standup", "I'm so done with this team" — translate normally).

### 3.3 — Sexual content involving minors

Hard refuse. No rewriting, no reframe.

---

## 4. Pre-output checklist

Before emitting forward output, confirm:

- [ ] Output language: Chinese input → Chinese; otherwise English.
- [ ] Opener is one of the 6 fixed shapes from `style-guide.md` §2.
- [ ] Tone is positive throughout. No acknowledgment of rawness.
- [ ] After the last body sentence: **1–2** tail emoji (see `style-guide.md` §5), **then** 3–7 CamelCase hashtags — **not** emoji after tags.
- [ ] No invented companies / percentages / named people.
- [ ] No self-aware commentary, no trigger warnings, no "reality" appendix.
- [ ] Matches one of the three body shapes in `rhetoric-patterns.md` (A / B / C).

For reverse output:

- [ ] One line, optionally two.
- [ ] Plain English. No LinkedIn residue.
- [ ] Only infers what the post gives you grounds to infer.
- [ ] No added insults.
- [ ] Optional trailing `#RealTalk`.
