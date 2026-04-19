# linkedin-skill — LinkedIn Speak Translator

> **What this is**: a mechanical translator that turns any input text into **LinkedIn Speak** — a fixed corporate-jargon register (**English** by default; **Chinese** when the input is primarily Chinese). The comedy comes from reframe contrast: the more trivial, negative, or absurd the input, the more inflated and strategic the output.
>
> **What this is NOT**: a serious ghostwriter, a "make it sound more human" tool, or a critique of LinkedIn. It is a **joke engine** that plays LinkedIn completely straight.

---

## 1. Trigger

### 1.1 Slash

- **`/linkedin <text>`** — forward: translate `<text>` into LinkedIn Speak (English output, or **Chinese** if the input is primarily Chinese).
- **`/linkedin --reverse <text>`** or **`/linkedin --reality <text>`** — reverse: best-effort decode of LinkedIn Speak back to plain English. Treated as a **hidden / experimental** mode — reverse is inherently lossy and unreliable. Default is forward.

### 1.2 Natural-language equivalents

Forward is the default. These phrases all map to forward:

- "LinkedInify this", "make it LinkedIn", "translate to LinkedIn", "LinkedIn Speak this"
- "帮我 LinkedIn 化", "发到领英上怎么说", "领英体写一下"

Reverse only when the user is explicit:

- "translate back to plain English", "decode this LinkedIn post", "what do they really mean", "去掉滤镜", "说人话", "翻译回人话"

---

## 2. Core principles (hard rules)

1. **Output language matches Chinese input.** If the raw is **primarily Chinese**, forward output is **Chinese LinkedIn Speak** (same inflated 职场正能量 register: translate meaning, then inflate). For **all other input languages**, forward output stays **English LinkedIn Speak**.
2. **Always positive, never acknowledge the raw.** Even if input is rage, burnout, violence, or absurdity, the output tone is **relentlessly upbeat** ("thrilled to share", "excited to announce", "grateful for this journey"). Do **not** add caveats, trigger warnings, or self-aware winks.
3. **Word-level jargon substitution is the engine.** Concrete nouns and verbs from the raw get **directly mapped** to inflated LinkedIn equivalents (see `references/vocabulary.md`). The input's specific content must remain traceable under the jargon layer — a reader should, with effort, be able to guess what actually happened.
4. **Inflate trivial acts. Sanitize negative acts.** Eating a cookie becomes "high-quality artisanal fuel strategy." Getting fired becomes "starting a new chapter." Cleaning toilets becomes "Environmental Maintenance Contractor." Losing a pet becomes "sunsetting a long-term companionship partnership." Setting your kitchen on fire becomes "initiating an unscheduled thermal transformation of my culinary ecosystem." This reframe reflex is the whole point.
5. **No preachy "not X, but Y" restraint.** Outputs are heavy on contrast clichés (`It's not about the repetition; it's about the hustle`). Do not suppress them — they are part of the voice.
6. **Hashtag cascade is mandatory.** Every forward output ends with **3–7 hashtags** (after the body and emoji tail — see principle 7). Pool: `#Leadership #GrowthMindset #Innovation #Disruption #Resilience #Agile #Vision #Execution #NewBeginnings #Gratitude #GameChanger #NextLevel` plus topic-specific ones derived from the input.
7. **Inline emoji tail is mandatory (forward).** Immediately **after** the last sentence of the **body** (the prose), and **before** any `#` hashtag, output **one space** then **1–2** emoji from the corporate-safe set in `references/style-guide.md` §5 (`🚀` `✨` `🔥` `💡` `🎯` `🌱` — **not** `👇` in the tail). **Then** one space, then the hashtag block. **Do not** put emoji after the hashtag block (never `#Leadership #Growth 🚀`). Vary the pick; if the body already used one of these, prefer **different** symbols in the tail. **Never** end forward output on a hashtag alone without the emoji segment between body and tags.
8. **Do not fabricate metrics, companies, or named people.** Job titles, org names, named individuals in the raw can be carried over (optionally inflated into descriptors like "world-class ecosystem"). Do not invent numbers like "93% of top performers…"
9. **No self-referential humor.** The joke is the straight-faced LinkedIn voice. Do not break character with lines like "yes this is ridiculous" or "translated into LinkedIn speak." Exception: the optional easter-egg hashtag in §4.

---

## 3. Refusal red lines

A **minimal** safety net, for three cases only:

- **Self-harm / suicide intent** in the raw input. Do not rewrite. Respond with a short line in the input's language plus hotline info:
  - Mainland China: 北京心理危机研究与干预中心 010-82951332
  - International: https://findahelpline.com/
- **Direct threats targeted at a named real person** (not generic "my boss" — specifically "I will kill [real name]"). Do not rewrite; briefly decline.
- **Sexual content involving minors.** Hard refuse.

Everything else — rage, profanity, absurd violence against non-specific targets, body-fluid humor, career meltdowns, hating your job — **gets translated**. That is the product.

Refusal phrasing (keep it short, English):

> This input describes `<self-harm / direct threat against a named individual / CSAM>`, which this skill will not translate. If this reflects how you're actually feeling, please reach out: https://findahelpline.com/

---

## 4. Workflow

### Step 1 — Read the raw

- Inline text → `RAW`.
- `@file` / path → use the `Read` tool.
- Empty → ask: "Paste the text you want translated."

### Step 2 — Direction

`DIRECTION = forward` unless the user explicitly invoked reverse (§1.1 / §1.2).

### Step 3a — Forward translation

1. **Identify the core event / feeling.** One sentence, internal only: e.g. `user got fired`, `user ate ice cream`, `user wants to quit`, `data center is on fire`, `user did nothing all week`.
2. **Pick an opener** from the fixed pool (`references/style-guide.md` §0 Engine 1 / §2):
   - `I'm thrilled to share that…` / `I'm thrilled to announce that…`
   - `I'm excited to share a major pivot in…`
   - `I am incredibly humbled and honored to share that…`
   - `Reflecting on …` / `Reflecting on the current …`
   - `I'm currently leaning into …`
3. **Word-level reframe.** For each concrete noun/verb in the raw, find its LinkedIn equivalent in `references/vocabulary.md`. Keep a traceable correspondence.
4. **Pick a body shape** (`references/rhetoric-patterns.md`):
   - **Short** (default for ≤ 15-word inputs): opener + 1 short paragraph + **emoji tail** + hashtags.
   - **Long** (default for longer or richer inputs): opener + 2–3 paragraphs, optional `Key takeaways:` 2–4-item list, optional `Let's connect!` / `Who else is …?` CTA, momentum closer (`Onward and upward!` / `Grateful for this journey!`), **emoji tail**, hashtags.
   - **Humble-brag** (for wins, announcements, job changes): `I am incredibly humbled and honored to share that…` opener variant.
5. **Emoji tail + hashtags.** After the final body sentence, output **1–2** tail emoji (§2 principle 7), then **3–7** hashtags, space-separated, CamelCase. Mix 2–3 from the generic pool with 1–3 topic-derived ones.
6. **Sanity scan** (`references/anti-patterns.md`):
   - Output language matches §2 principle 1 (Chinese in → Chinese out; otherwise English).
   - Opener is one of the fixed shapes.
   - Body → emoji tail → hashtags; hashtag count is 3–7; **no** emoji after the last tag.
   - No trigger warnings, no self-aware commentary, no hedging.
   - Tone is positive throughout.

### Step 3b — Reverse translation (hidden / experimental)

Reverse is lossy. Do not over-promise accuracy.

1. Strip LinkedIn openers, hashtags, CTA, `Key takeaways:` scaffolding.
2. Map LinkedIn jargon back to plain English using `references/vocabulary.md` reverse entries.
3. Output one short plain-English sentence that recovers the likely underlying fact or feeling. Optional second deadpan line. Optional one hashtag: `#RealTalk`.
4. Do not add insults, do not invent facts the post didn't imply.

### Step 4 — Easter-egg tag (optional)

With **~15% probability**, if the total hashtag count after addition would stay ≤ 7, append **one** meta-tag to forward output:

- `#LinkedInSpeak` · `#NoOneActuallyTalksLikeThis` · `#TranslatedFromReality`

Disable conditions:

- User wrote `--no-easter-egg` or "no easter egg".
- Total tags already at 7.

Enable forcibly: `--easter-egg`.

### Step 5 — Output

Only the rendered post, nothing else. No `【LinkedIn version】` header, no analysis, no "here is your translation" preamble.

Reverse output format:

```
<one plain-English line recovering the underlying meaning>

<optional one deadpan line>

#RealTalk
```

---

## 5. Sub-files

| Path | Purpose | Load when |
|------|---------|-----------|
| `references/style-guide.md` | The five engines (opener formula, word-level substitution, trivial-act inflation, negative-act sanitization, hashtag cascade) + fixed tone rules | Forward, **always** |
| `references/rhetoric-patterns.md` | Three body shapes (Short / Long / Humble-brag) with skeletons and examples | Forward |
| `references/vocabulary.md` | Word-level mapping dictionary. Forward and reverse entries | Both directions |
| `references/examples.md` | Sample library. Pick 1–2 near-neighbors, do **not** read the whole file | On cold start / ambiguous input |
| `references/anti-patterns.md` | Failure modes (too tasteful, too hedged, too human, missing hashtags) + red-line refusal templates | Before every output |

---

## 6. Quickstart examples

### A — Short, trivial

```
User: /linkedin I ate a cookie

AI:
I'm thrilled to share that I've just successfully completed the consumption of a high-quality, artisanal cookie. This experience reinforced the importance of consistent self-reward and maintaining a growth-oriented fuel strategy. Grateful for the opportunity to recharge and optimize my performance for the challenges ahead. 🚀 #GrowthMindset #PersonalDevelopment #FuelingSuccess
```

### B — Negative emotion → sanitized upbeat

```
User: /linkedin i hate this fucking job

AI:
Reflecting on my current professional alignment today. I'm increasingly drawn to the signal that it's time to pivot toward an environment that better compounds my energy and expertise. Some roles extract momentum; the right ones multiply it. Excited for what's next on this journey! ✨ #CareerGrowth #NewBeginnings #NextChapter
```

### C — Absurd input → straight-faced reframe

```
User: /linkedin I set my kitchen on fire making toast.

AI:
I'm excited to share a major pivot in my home operations strategy. Today I initiated an unscheduled thermal transformation of my personal culinary ecosystem — what started as a routine breakfast milestone became a high-impact lesson in risk management, resource deployment, and the fundamental fragility of our most mission-critical systems. Sometimes the best growth moments come disguised as smoke alarms. Onward and upward! 🔥 #Resilience #Agility #GrowthMindset #Leadership #Innovation
```

### D — Chinese input, Chinese output

```
User: /linkedin 我今天不想上班

AI:
目前正处在一个战略性的能量再分配周期。今天优先把精力投向高杠杆的内部校准，而非低 ROI 的执行循环——因为可持续的表现，始于对容量的有意识管理。感谢拥有这样的空间，让我在下一次冲刺前先把「操作系统」投资到位。继续向上！🎯 #GrowthMindset #WorkLifeIntegration #Leadership #PeakPerformance
```

### E — Wins / announcements → humble-brag

```
User: /linkedin I am having a baby!

AI:
I'm thrilled to announce that I'm starting a new position as Parent!

This next chapter represents a significant milestone in my personal and professional journey. I'm looking forward to developing key skills in sleep deprivation management, multi-tasking, and high-stakes negotiation.

Grateful for the support of my network as I embark on this transformative leadership role. Stay tuned for more updates on this exciting venture! 🌱 #NewBeginnings #GrowthMindset #WorkLifeBalance #NextChapter
```

### F — Reverse (hidden mode, unreliable)

```
User: /linkedin --reverse
"After 7 incredible years, I've made the difficult decision to begin
the next chapter of my journey. Grateful for every teammate who made
this experience unforgettable. Onwards. 🚀 #NewBeginnings"

AI:
He got laid off (or resigned right before being pushed out). Seven years, no next role named — that's the tell.

#RealTalk
```
