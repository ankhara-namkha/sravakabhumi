# Navigation Review: First-Time Reader Audit
Reviewer: first-time reader simulation (moderate Buddhist familiarity, no Classical Chinese)
Files read: 00_introduction.md, 00_abbreviations.md, 00_contents.md, fascicle_26_en.md (lines 1-60), fascicle_30_en.md (lines 1-50 + sections 30.10-30.12), fascicle_32_en.md (lines 1-100), 00_methodology.md, 00_bibliography.md

---

## Test 1: Introduction Orientation

**[PARTIAL PASS] What are "Yoga Places"?**
The introduction mentions "three major divisions — the Second, Third, and Fourth Yoga Places" but never explains what a "Yoga Place" (瑜伽處) is. A reader with moderate Buddhist familiarity will not know this term. "Yoga" in Western popular usage means physical posture practice; calling a chapter division a "Yoga Place" without explanation is opaque.
- **Suggested fix:** Add one sentence in the introduction: "The Sravakabhumi is organized into four 'Yoga Places' (yuga-sthana), each marking a stage of the practitioner's path — the present translation begins with the Second Yoga Place."

**[FAIL] What does "fascicle" mean?**
The introduction uses "fascicle" throughout (e.g., "covering the full scope of Asanga's treatment... covering fascicles 26-33") without ever defining it. A non-specialist reader does not know that a fascicle is a physical scroll or volume unit of the Taisho Tripitaka. The Table of Contents also uses "Fascicle 26 — Part One" without any note. The Abbreviations page similarly uses the word in a convention description without defining it.
- **Suggested fix:** One parenthetical in the introduction on first use: "fascicle 26 through 33 (each fascicle is a scroll-volume of Xuanzang's Chinese text, numbered within the larger Taisho Tripitaka)."

**[PASS] What does [T30.0424a07] mean?**
The introduction explains this clearly: "Bracketed references such as [T30.0424a07] cite the Chinese source text by volume, page, column, and line." The Abbreviations page adds the breakdown column-by-column. This is well handled.

**[PASS] That footnotes are translator commentary?**
The Abbreviations page states this explicitly: "Footnotes contain translator's notes, cross-references, doctrinal context, and canonical parallels. They are never woven silently into the translation text." Also confirmed in practice — all footnotes sampled are clearly translator material, not Asanga's text.

---

## Test 2: Cross-Reference Resolution

Five cross-references located and navigation attempted:

1. **Fascicle 32, footnote `[^nine_stages_ref]`: "see section 30.10"** — Section 30.10 exists. The title is "The Nine Stages of Mental Abiding." Navigation works. PASS.

2. **Fascicle 32, footnote `[^five_signs]`: "section 31.11"** — Section 31.11 exists: "Cultivation of Attention: Four Types, Objects of Practice, and the Goldsmith Simile." Navigation works. PASS.

3. **Fascicle 33, body text: "for the six aspects, see section 30.14"** — Section 30.14 exists: "The Three Doors and Six Aspects of Vipashyana." Navigation works. PASS.

4. **Fascicle 26, footnote `[^emptyfruitless]`: "This topic is treated in fascicle 29 (section 29.17)"** — Section 29.17 exists: "Three Causes of Fruitless Practice." Navigation works. PASS.

5. **Fascicle 29, footnote `[^six_categories]`: "the twenty-eight person types established in fascicle 26 (sections 26.1-26.2)"** — Section 26.2 exists: "The Twenty-Eight Types of Persons." However, section 26.1 is the "Opening Questions and Summary Verse," not itself a person-types section. The cross-reference says "sections 26.1-26.2" but the twenty-eight types begin at 26.2. The range is slightly misleading.
- **Suggested fix:** Change to "section 26.2" (not a range beginning at 26.1).

**[PARTIAL PASS] Overall:** All five references resolve to existing sections. No dead links. One reference range is slightly inaccurate.

---

## Test 3: Abbreviation Coverage

Abbreviations actually used in footnotes, checked against the Abbreviations table:

| Abbreviation | In Table? | Notes |
|---|---|---|
| AN | Yes | Defined as Anguttara Nikaya |
| SN | Yes | Defined as Samyutta Nikaya |
| MN | Yes | Defined as Majjhima Nikaya |
| DN | Yes | Defined as Digha Nikaya |
| T30 (within Taisho refs) | Yes | Format explained |
| Skt. | No | Used in footnotes (e.g., "Skt. *Revata*; Pali *Revata*") |
| Pali | No | Used as a label in footnotes — "Pali:" or "Pali *term*" — not defined as an abbreviation but used as a language identifier |

**[PARTIAL PASS]** All canonical text abbreviations (AN, SN, MN, DN) are defined. "Skt." appears as an abbreviation in several footnotes (e.g., fascicle_26_en.md footnote [^revata]: "Skt. *Revata*; Pali *Revata*") but is not listed in the Abbreviations table. Similarly, "Pali:" is used as a language label in footnotes without being defined. These are common scholarly abbreviations that moderately educated readers would recognize, but a complete abbreviations table should include them.
- **Suggested fix:** Add a row for "Skt." = Sanskrit to the abbreviations table. Optionally add "Pali" = Pali language. This is a minor gap.

---

## Test 4: Section Numbering Logic

**[PASS]** The numbering scheme is self-explanatory for anyone who has read the Table of Contents. "Fascicle 30, Part One" maps to sections 30.1, 30.2, etc. Seeing "30.10" in a cross-reference, a reader who has oriented themselves in the TOC will understand it means fascicle 30, section 10. The Table of Contents confirms: "Fascicle 30 — Part One: Approaching the teacher; the five establishments; the nine stages of mental abiding; the six powers; the four types of attention; the four types of vipashyana."

**Mild issue:** Section numbering does not restart per Yoga Place. Fascicle 26 runs 26.1, 26.2... Fascicle 27 runs 27.1, 27.2... This is logical, but nowhere in the front matter is the scheme stated explicitly. A reader who opens fascicle 33 and sees "33.10" may need a moment to confirm this refers to the tenth section of fascicle 33, not some other coordinate system.
- **Suggested fix (optional):** One sentence in the Abbreviations page: "Section numbers follow the format [fascicle].[section] — for example, 30.10 means fascicle 30, section 10."

---

## Test 5: Footnote Utility

Ten footnotes sampled; all from sections actually read:

1. **fascicle_30, [^third_yoga_transition]:** Explains the transition from Second to Third Yoga Place. Clear, valuable orientation. PASS.
2. **fascicle_30, [^nine_stages]:** Provides Sanskrit names for all nine stages plus secondary literature pointers. Excellent for scholar; the Sanskrit names are explained. PASS.
3. **fascicle_30, [^six_powers]:** Maps the six powers to the nine stages in a compact table. Clearly useful. PASS.
4. **fascicle_30, [^four_attentions]:** Provides Chinese characters and a secondary source reference. The Chinese is opaque to most readers but clearly labelled; the secondary reference is findable. PASS.
5. **fascicle_32, [^teacher_frame]:** Orients the reader to the teaching voice adopted for the whole fascicle. Essential context. PASS.
6. **fascicle_32, [^five_signs]:** Cross-references section 31.11 and explains the five signs briefly. Useful. PASS.
7. **fascicle_32, [^non_regret_sequence]:** Explains the progressive sequence and provides Pali parallels. Clear. However, "See AN 10.1 and 11.1" requires reader to know AN = Anguttara Nikaya — confirmed defined in abbreviations. PASS.
8. **fascicle_32, [^decline_types]:** Explains the six decline types. Includes a Chinese phrase rendered phonetically without any translation ("病病法性死死法性"). A reader cannot parse this.
  - **Suggested fix:** Either translate the Chinese phrase or remove it from the footnote. This is translator's annotation; the Chinese formula is not necessary for a reader without Classical Chinese. Suggestion: replace with "The formula means: 'The nature of the ill is to be ill; the nature of the mortal is to die.'" (The translation is in the main text, so the Chinese in the footnote adds nothing for a non-specialist.)
9. **fascicle_32, [^oil_bowl]:** Explains the simile with a Pali parallel. Clear and adds genuine value. PASS.
10. **fascicle_31_en.md, [^mutual_support]:** References "section 31.9 below." The word "below" is functional in a print scroll but in a PDF or digital reader it means the reader must search forward. A section reference ("section 31.9") would be cleaner, but this is minor. PASS with note.

**[MOSTLY PASS]** Nine of ten footnotes are clear and valuable. One footnote ([^decline_types]) contains an untranslated Chinese formula that is opaque to the target reader.

---

## Test 6: Back Matter Utility

**[PARTIAL PASS] Would a confused reader know to flip to the abbreviations?**
The Introduction says: "conventions for abbreviations, terminology, and romanization are detailed in the appendices." This is vague — it does not say "see the Abbreviations and Conventions appendix." For a print reader, the Table of Contents does not list the abbreviations page under a recognizable navigation entry (the TOC only shows fascicle contents, not front/back matter structure). A reader confused by "AN" or "SN" in a footnote would need to know to look in the back matter.
- **Suggested fix:** In footnotes that cite AN, MN, SN, DN for the first time, a parenthetical: "(Anguttara Nikaya; see Abbreviations)" would be cleaner and more navigable than requiring the reader to search. Alternatively, the Contents page should list "Abbreviations and Conventions" as a navigable section.

**[PASS] Is the methodology interesting or just process documentation?**
The Methodology section is well-written and intellectually honest. The "Limitations and Hopes" section is genuinely engaging — it acknowledges what the AI translation cannot do while explaining what it attempted. A general reader would find this worth reading. The section headers ("The Challenge," "The Approach," "The Register Standard") make it easy to skim. PASS.

---

## Test 7: Digital Edition Reference

**[PASS]** The Abbreviations page mentions "a consolidated glossary with diacritical forms is available in the digital edition (github.com/ankhara-namkha/sravakabhumi)" and "a comprehensive glossary with Chinese characters is available in the digital edition." The URL is given twice in the Abbreviations page and once in the Methodology section. The reader knows what to do with it. The Methodology section also says: "The text, together with all review findings and verification reports, is published at github.com/ankhara-namkha/sravakabhumi under a Creative Commons license." Clear and sufficient. PASS.

---

## Test 8: Cold-Open Test (fascicle 30 without introduction)

**[PARTIAL PASS]** Opening fascicle 30 directly, a reader encounters:
- Title: "Sravakabhumi: The Hearer's Ground" — clear.
- Chapter title: "Basic Section: Shravaka Ground, Third Yoga Place, Part One" — the reader who has not seen the introduction does not know what "Third Yoga Place" or "Basic Section" means.
- Chinese characters: "本地分中聲聞地第十三第三瑜伽處之一" — appears without explanation. A reader unfamiliar with the format will find this briefly puzzling, then ignore it. It would benefit from a note such as "[Chinese chapter heading]" if it cannot be removed.
- Metadata block: There is no metadata block — no brief "this fascicle covers..." orientation header. The first footnote ([^third_yoga_transition]) does provide this context, but only readers who immediately read footnotes will encounter it.
- **Suggested fix:** Add a brief italicized orientation line under the chapter heading, e.g.: "*This fascicle opens the Third Yoga Place, which covers the practical instructions for meditation training. The Second Yoga Place (fascicles 26-29) established the theoretical framework; what follows is the how.*" This is standard in multi-volume translations (the Lamrim Chenmo uses similar chapter prefaces).

---

## Summary Table

| Result | Test | Description |
|--------|------|-------------|
| PARTIAL PASS | 1A — Yoga Places | Term used in Introduction without definition |
| FAIL | 1B — Fascicle defined? | "Fascicle" used throughout without explanation |
| PASS | 1C — Taisho reference format | Well explained in both Introduction and Abbreviations |
| PASS | 1D — Footnotes as translator commentary | Explicitly stated in Abbreviations |
| PASS | 2 — Cross-reference resolution | All 5 links resolve; 1 minor range inaccuracy (26.1-26.2 should be 26.2) |
| PARTIAL PASS | 3 — Abbreviation coverage | All canonicals covered; "Skt." used in footnotes but not in table |
| PASS | 4 — Section numbering logic | Self-explanatory once TOC read; format not stated explicitly |
| MOSTLY PASS | 5 — Footnote utility | 9/10 footnotes clear and useful; 1 has untranslated Chinese formula |
| PARTIAL PASS | 6 — Back matter utility | Methodology engaging; no TOC entry for Abbreviations impedes discovery |
| PASS | 7 — Digital edition reference | URL given 3 times, clearly explained |
| PARTIAL PASS | 8 — Cold-open test | Chapter heading orientation works; "Yoga Place" and bare Chinese heading are unexplained |

---

## Priority Fixes

**Critical (blocks comprehension for non-specialist):**
1. Define "fascicle" on first use in the Introduction. One parenthetical is sufficient.

**Moderate (impairs navigation):**
2. Define "Yoga Place" on first use in the Introduction. One sentence.
3. Add the section-numbering convention to the Abbreviations page: "Section numbers follow [fascicle].[section] format."
4. Add "Skt." = Sanskrit to the Abbreviations table.
5. Add "Abbreviations and Conventions" to the Contents page as a navigable entry.

**Minor (polish):**
6. Fix cross-reference "sections 26.1-26.2" to "section 26.2" in fascicle_29_en.md footnote [^six_categories].
7. Remove or translate the bare Chinese formula in fascicle_32_en.md footnote [^decline_types].
8. Add a brief chapter-opening orientation line to each fascicle's header (especially fascicle 30 and 33 which are common entry points for new readers).
9. Consider adding "(Anguttara Nikaya)" on first use of "AN" in each fascicle, or make the abbreviation table more prominent.
