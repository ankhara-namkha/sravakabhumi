# Final Terminology Review — All 8 Fascicles + Front/Back Matter

**Reviewer role:** Terminology Agent (Agent T)
**Scope:** translation/fascicle_26_en.md through fascicle_33_en.md; translation/00_introduction.md, 00_methodology.md, 00_bibliography.md, 00_abbreviations.md
**Reference files:** glossary/MASTER_GLOSSARY.md, the terminology watchlist, translation/00_abbreviations.md

---

## Summary of Severity Counts

| Severity | Count |
|----------|-------|
| Critical (C) | 3 |
| Moderate (M) | 7 |
| Minor (m) | 9 |
| **Total** | **19** |

---

## Findings

### CRITICAL — Deprecated or Wrong Term in Active Text

**[C] [Fascicle 26, 28, 31] [Vism] — Forbidden abbreviation "Vism" used for Visuddhimagga in footnotes.**

The abbreviation table does not list "Vism" (it was removed per prior audit). Three footnotes use it:

- `translation/fascicle_26_en.md` line 562 (`[^corpse_stages]`): `Visuddhimagga's tenfold *asubha* (Vism ch. VI)`
- `translation/fascicle_28_en.md` line 610 (`[^gradual_path]`): `(cf. AN 11.1–2, Kimatthiya Sutta; DN 34; MN 70; Vism I.1-8)`
- `translation/fascicle_31_en.md` line 350 (`[^signless_beginner]`): `specific meditation object (Vism III.104 ff.)`

All three must be expanded to "Visuddhimagga" (e.g., "Visuddhimagga ch. VI", "Visuddhimagga I.1-8", "Visuddhimagga III.104 ff.").

---

**[C] [Fascicle 28] [adhicitta-shiksha] — Footnote mislabels second training as "concentration" instead of "mind".**

Footnote `[^three_trainings]` at `translation/fascicle_28_en.md` line 606 reads:
> "The three superior trainings (*tri-shiksha*) — discipline, **concentration**, and wisdom"

The body text throughout fascicle 28 (lines 23, 27, 41, 55, 61, 65, 67, etc.) consistently and correctly calls it **"superior training in mind" (*adhicitta-shiksha*)**. The glossary entry for `tri-shiksha` (line 261) reads "three trainings in discipline, **mind**, and prajna." Using "concentration" for the second training is wrong — that shorthand belongs to popular usage, not to this text's own technical vocabulary, and contradicts the glossary. The footnote should read: "The three superior trainings (*tri-shiksha*) — discipline, mind, and prajna."

---

**[C] [Fascicle 29] [adhicitta-shiksha] — Body text inconsistently labels second training as "training of samadhi".**

`translation/fascicle_29_en.md` line 254:
> "right mindfulness and right samadhi belong to the **training of samadhi**"

This is the eightfold path section where the Chinese text assigns the right mindfulness and right samadhi factors to the *adhicitta-shiksha*. The Sravakabhumi's own terminology throughout (fascicle 28 passim; fascicle 29 line 171) calls this the "superior training in mind," not the "training of samadhi." Using "training of samadhi" here introduces an unlisted term and directly contradicts the glossary. Should read: "training of mind" or "superior training in mind."

Note: the footnote `[^eightfold_path]` (line 565) correctly uses "samadhi training" as a shorthand when discussing the *Pali tradition's* name for this training, which is acceptable in that comparative context. The problem is the body text's primary label.

---

### MODERATE — Inconsistent Rendering of Same Term

**[M] [Fascicles 26, 32] [asubha vs. ashubha] — Pali form "asubha" used in place of Sanskrit "ashubha" in footnotes.**

The Sanskrit form is *ashubha*; the Pali form is *asubha*. The glossary and the body text consistently use *ashubha*. However, several footnotes in fascicle 26 and fascicle 32 use the Pali form:

- `translation/fascicle_26_en.md` line 562: `Visuddhimagga's tenfold *asubha* (Vism ch. VI)` — here used as part of a Visuddhimagga citation (where Pali form is acceptable as the text's own term), but the inconsistency with surrounding footnotes that use *ashubha* should be noted.
- `translation/fascicle_32_en.md` lines 173, 195, 203, 247: footnotes use "asubha" without italics or Sanskrit parenthetical, while the body text and other footnotes in the same fascicle use "ashubha." For example, line 193 (`[^asubha_ref]`) immediately uses `(*ashubha*)` in the Sanskrit parenthetical, establishing *ashubha* as the form, yet lines 195, 203, 247 then use bare "asubha."

The pattern in fascicle 32 is inconsistent within the same footnote sequence. Footnotes that are discussing the text's own contemplation should use *ashubha*; footnotes comparing with the Visuddhimagga may use *asubha* when quoting the Pali text's terminology, but should label it as such.

---

**[M] [Fascicles 28, 29] [riddhipada vs. rddhipada] — Two Sanskrit spellings for the same term.**

The glossary at line 200 gives: `riddhipada`. The fascicle 28 body text (lines 478, 486) uses `*riddhipada*`. However, fascicle 29 consistently uses `*rddhipada*` throughout (lines 161, 165, 167, 545 note, 553 note). These are two romanizations of the same Sanskrit term. The glossary form (*riddhipada*) should be used throughout. Fascicle 29's `*rddhipada*` should be normalized to `*riddhipada*`.

---

**[M] [Fascicle 26] [ashraya-paravritti vs. ashraya-paravrtti] — Spelling variant not matching glossary.**

The glossary gives: `ashraya-paravrtti` (single terminal -i). Fascicle 26 body text (line 340) and its footnote (line 534) use `ashraya-paravritti` (double -tti). Fascicle 31 (lines 271, 283, 346) correctly uses `ashraya-paravrtti`. The fascicle 26 spelling should be normalized to `ashraya-paravrtti`.

---

**[M] [Fascicle 26] [asubha vs. ashubha in Vism citation] — See above under [asubha/ashubha]; listed separately here for the Vism citation context.**

`translation/fascicle_26_en.md` line 562: "Visuddhimagga's tenfold *asubha* (Vism ch. VI)." When citing the Visuddhimagga's own term, the Pali *asubha* is defensible since the source text is Pali. But when talking about the Sravakabhumi's own teaching, all instances should use the Sanskrit *ashubha*. The citation context suggests this is the Visuddhimagga's Pali term, which may be intentional; however, it is inconsistent with the practice elsewhere and should either add a parenthetical "(Pali: *asubha*; Sanskrit: *ashubha*)" or normalize to *ashubha*.

---

**[M] [Fascicle 27, 32] [anapanasati (Pali) vs. anapanasmriti (Sanskrit)] — Pali form used in footnote labels.**

The correct Sanskrit form is *anapanasmriti*; the Pali form is *anapanasati*. The glossary entry (line 28) gives *anapanasmriti*. However:

- `translation/fascicle_27_en.md` line 456 footnote label `[^anapanasati_object]` uses the Pali form in the footnote name.
- `translation/fascicle_27_en.md` line 456 footnote text uses *anapanasmriti* correctly.
- `translation/fascicle_27_en.md` footnote cross-references use "anapanasati" in the Pali text references (MN 118 references are to the Anapanasati Sutta, where Pali is appropriate for the sutta title).
- `translation/fascicle_32_en.md` line 421 footnote label `[^satipatthana_formula]` uses Pali *satipatthana* as the footnote identifier.

The footnote labels are internal markup and do not appear in the rendered text, so these are minor in practical terms. However, the pattern of using Pali forms in footnote labels while using Sanskrit forms in the text creates inconsistency. The more substantive issue is in the footnote text itself — no instances found where Pali forms replace Sanskrit forms in running footnote prose when discussing the Sravakabhumi's own teaching.

---

**[M] [Multiple fascicles] [Visuddhimagga citation format inconsistency] — Some citations use "Visuddhimagga (chapter)" while others use "Visuddhimagga chapter.verse".**

Citation formats vary:
- "Visuddhimagga (III.74-103)" — parenthetical (fascicle 26 line 272)
- "Visuddhimagga XI.74-78" — no parenthetical (fascicle 27 line 444)
- "Visuddhimagga (VIII.145-244)" — parenthetical (fascicle 27 line 456)
- "Visuddhimagga (IV.88-94)" — parenthetical (fascicle 33 line 200)
- "Visuddhimagga (IV.139)" — parenthetical (fascicle 33 line 260)

Not a terminology error per se, but inconsistent citation style within footnotes. The most common pattern (parenthetical) should be used throughout.

---

**[M] [Bibliography] [Tsongkhapa citation incomplete] — Bibliography lists Vols. 1–3 but not Vol. 3 alone.**

`translation/00_bibliography.md` line 39: "Vols. 1–3. Translated by the Lamrim Chenmo Translation Committee. Ithaca: Snow Lion Publications, 2000–2004." Several footnotes (fascicles 30, 31, 32) cite "Vol. 3" specifically. The bibliography entry is adequate as a collective reference but lacks a specific Vol. 3 publication year (2004). Minor bibliographic incompleteness, not a terminology error.

---

### MINOR — First-Use Gloss Missing or Inconsistent

**[m] [Fascicle 27] [shamatha, vipashyana] — First use in fascicle 27 lacks gloss.**

The first use of *shamatha* in fascicle 27 (line 236) appears without an English gloss. The convention (per 00_abbreviations.md) is "shamatha (calm abiding)" on first occurrence in each fascicle. Similarly, *vipashyana* at line 236 has no "(insight)" gloss. Fascicles 28, 30, 32 do provide these glosses on first use. Fascicle 27 and fascicle 29 first uses lack them.

- Fascicle 27 line 236: "one practiced the yoga of shamatha" — needs "(calm abiding)".
- Fascicle 29 line 77: "cultivation of shamatha one-pointedness" — needs "(calm abiding)".
- Fascicle 29 line 77 (or the first explicit vipashyana use): needs "(insight)" gloss.
- Fascicle 31 first use of shamatha (line 23): no gloss.
- Fascicle 33 first use (line 44): no gloss.

The pattern is inconsistent: fascicles 26, 28, 30, 32 provide the gloss; fascicles 27, 29, 31, 33 do not.

---

**[m] [Fascicle 26, 27, 29, 33] [dhyana first-use gloss absent in some fascicles] — Inconsistent first-use gloss.**

The convention calls for "dhyana (meditative absorption)" on first use in each fascicle. First-use glosses are present in fascicles 26 (line 119), 28 (line 27), and 33 (line 158 and footnote 170). However:

- Fascicle 27 first use (line 100): "beings in the fourth dhyana" — no gloss.
- Fascicle 29 first use (line 205): "the four dhyanas" — no gloss.
- Fascicle 30 first use (line 76): "accomplishes dhyana" — no gloss.
- Fascicle 31 first use (line 225, a contextual reference): "the other dhyanas" — no gloss.
- Fascicle 32 first contextual appearance (line 89): "working in shamatha" (vipashyana gets gloss but dhyana is used without it through the fascicle).

The glosses are present where it matters most (fascicle 26 entry point, fascicle 28 superior training section, fascicle 33 dhyana formula). The missing glosses in intermediate fascicles are minor since the term is well-established by the time the reader reaches them.

---

**[m] [Fascicle 26, 27, 29] [samadhi first-use gloss status] — Gloss present in fascicles 28 and 29 but absent in 26 first use.**

Fascicle 26 introduces *samadhi* early (lines as "sign of samadhi," etc.) without the "(meditative concentration)" gloss; it appears first with a gloss at fascicle 28 line 39. The abbreviations convention calls for this on first use per fascicle. Given that fascicle 26 handles *samadhi* primarily in compound forms and as a topic title (*samadhi-avarana*, *maula-dhyana vs. samadhi*), the absence is minor but technically non-compliant.

---

**[m] [Fascicle 26] [pudgala in parenthetical in body text] — "persons (*pudgala*)" pattern breaks watchlist rule.**

`translation/fascicle_26_en.md` line 23 contains: "How many types of persons (*pudgala*) are able to realize renunciation?" The watchlist says "pudgala (untranslated, in running text)" is WRONG. However, this instance shows *pudgala* as a parenthetical gloss after the correct English rendering "persons," not as a standalone untranslated term. This is the first-use introduction pattern and is consistent with glossary convention: first use introduces the Sanskrit form in parentheses. This is technically correct and not an error.

Similarly at fascicle 28 line 77: "three types of persons (*pudgala*)" and fascicle 29 line 396: "alternative designations for persons (*pudgala*)." These are first-use-style reintroductions and are acceptable. No violation found.

---

**[m] [Fascicle 32] [satipatthana Pali form in footnote label and prose] — Pali technical term in footnote prose.**

`translation/fascicle_32_en.md` line 421 footnote `[^satipatthana_formula]` text: "This is the standard satipatthana formula." The Sanskrit equivalent is *smrityupasthana*. Since the footnote is explicitly discussing the Pali Satipatthana Sutta formula, using the Pali term here to identify the formula-type is defensible as a cross-textual reference. However, it would be more consistent to write "This is the standard foundation-of-mindfulness (*smrityupasthana*) formula, rendered here following the Pali Satipatthana Sutta (MN 10)." As currently written, it is borderline: not a watchlist violation (which targets the running translation), but inconsistent with the convention of using Sanskrit forms throughout.

---

**[m] [Front matter: 00_bibliography.md] [Vipassana Dipani subtitle contains Pali term] — Pali "Vipassana" in reference title.**

`translation/00_bibliography.md` line 27: `*A Manual of Insight (Vipassana Dipani)*`. The subtitle "Vipassana Dipani" is the Pali title of Ledi Sayadaw's work. Since this is a proper title, the Pali form is correct and required. This is NOT an error — it is a proper noun. Listed for completeness only.

---

**[m] [Front matter: 00_bibliography.md] [Satipatthana title] — Pali "Satipatthana" in book title.**

`translation/00_bibliography.md` line 19: `*Satipatthana: The Direct Path to Realization*`. This is Analayo's book title in Pali. As a proper title, the Pali form is correct and required. NOT an error.

---

**[m] [Fascicle 28] [Three trainings footnote — "concentration" vs. "mind"] — See Critical finding [C] above; this minor note adds that the footnote would benefit from an explanatory note that "mind" (*adhicitta*) is the text's own term while "concentration" is the common shorthand in other traditions.**

---

**[m] [Multiple fascicles] [ekagrata first-use gloss] — Inconsistent.**

The first use of *ekagrata* with its gloss "(mental one-pointedness)" appears at fascicle 28 line 39 and 428. However:

- Fascicle 27 line 152 uses "mental one-pointedness" (no *ekagrata* parenthetical yet — this is the first use of the English rendering).
- Fascicle 29 lines 113, 115 use "mental one-pointedness" without *ekagrata* parenthetical.
- Fascicle 30 line 230 uses "mental one-pointedness" without *ekagrata* parenthetical until the footnote (line 496) reintroduces it.
- Fascicle 31 line 231 uses "*ekagrata*" parenthetical correctly.
- Fascicle 33 footnote line 170 correctly uses "(*ekagrata*, 心一境性)."

The pattern is acceptable: the English rendering "mental one-pointedness" appears consistently and the Sanskrit is introduced at first use in fascicle 28 and reinstructed at key structural points thereafter.

---

## Summary of Required Fixes (by priority)

### Must Fix (Critical):

1. **Fascicle 26 line 562, Fascicle 28 line 610, Fascicle 31 line 350** — Replace "Vism" with "Visuddhimagga" (3 instances).

2. **Fascicle 28 line 606** `[^three_trainings]` — Replace "discipline, concentration, and wisdom" with "discipline, mind, and prajna" (or "superior training in discipline, mind, and prajna").

3. **Fascicle 29 line 254** — Replace "belong to the training of samadhi" with "belong to the training of mind" (or "belong to the superior training in mind").

### Should Fix (Moderate):

4. **Fascicle 29 throughout** — Replace `*rddhipada*` with `*riddhipada*` to match glossary form.

5. **Fascicle 26 lines 340, 534** — Replace `ashraya-paravritti` with `ashraya-paravrtti` to match glossary form.

6. **Fascicle 32 footnotes lines 173, 195, 203, 247** — Normalize "asubha" to "ashubha" where discussing the Sravakabhumi's own contemplation practice (as distinct from citing the Pali Visuddhimagga's terminology).

7. **Fascicle 27 line 236 and Fascicle 29 line 77** — Add "(calm abiding)" gloss to first use of *shamatha*, and "(insight)" to first use of *vipashyana*, to match the convention established in fascicles 26, 28, 30, 32.

### May Fix (Minor):

8. Dhyana first-use glosses in fascicles 27, 29, 30 (minor, given established context).
9. Visuddhimagga citation format normalization (parenthetical vs. inline).
10. Fascicle 32 satipatthana footnote: clarify that "satipatthana" is the Pali formula name.

---

## Watchlist Checklist (per the terminology watchlist)

| Check | Status |
|-------|--------|
| Hsuan-tsang / Hsuan-chuang | CLEAR — only "Xuanzang" found |
| Maitreya as author | CLEAR — correctly noted as traditional attribution in fn. |
| pudgala untranslated in running text | CLEAR — parenthetical introductions only |
| sentient being for 補特伽羅 | CLEAR — "sentient being" only used for *sattva* |
| vipassana (Pali) | CLEAR — not found in body text |
| samatha (Pali) | CLEAR — not found |
| jhana (Pali) | CLEAR — not found |
| sutta (Pali) | CLEAR — only appears in proper sutta titles |
| nibbana (Pali) | CLEAR — not found |
| khandha (Pali) | CLEAR — not found |
| defilements for 煩惱 | CLEAR — "afflictions" used throughout |
| mental quiescence | CLEAR — not found |
| special insight | CLEAR — not found |
| aggregates without context | CLEAR — always "skandhas (aggregates)" on first use |
| absorptions for 靜慮 | CLEAR — "dhyanas (meditative absorptions)" used |
| hearer in title | CLEAR — title uses "The Hearer's Ground" (acceptable subtitle) |
| one-pointedness abbreviated | CLEAR — full phrase used throughout |
| concentration for standalone 三摩地 | MODERATE — see Critical finding #2 and #3 above |
| The Mind Illuminated | CLEAR — not cited anywhere |
| Vism abbreviation | VIOLATION — 3 instances (Critical finding #1) |

---

*File written by Terminology Agent (T) — final review pass, all 8 fascicles + front/back matter.*
