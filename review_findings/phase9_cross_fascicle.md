# Phase 9 Cross-Fascicle Consistency Review

**Scope:** All 8 translation files: fascicle_26_en.md through fascicle_33_en.md
**Date:** 2026-03-02
**Reviewer:** Automated cross-fascicle audit

---

## 1. SECTION NUMBERING CONTINUITY

### Pattern: XX.N (fascicle number . section number)

| Fascicle | Sections Found | Notes |
|----------|----------------|-------|
| 26 | 26.1–26.7 (7 sections) | Sequential, no gaps |
| 27 | 27.1–27.6 (6 sections) | Sequential, no gaps |
| 28 | 28.1–28.11 (11 sections) | Sequential, no gaps |
| 29 | 29.1–29.17 (17 sections) | Sequential, no gaps |
| 30 | 30.1–30.16 (16 sections) | Sequential, no gaps |
| 31 | 31.1–31.11 (11 sections) | Sequential, no gaps |
| 32 | 32.1–32.17 (17 sections) | Sequential, no gaps |
| 33 | 33.1–33.18 (18 sections) | Sequential, no gaps |

**Total sections across all fascicles:** 103 sections
**Result: PASS.** No numbering gaps, no duplicates, no out-of-order sections detected. The pattern XX.N is applied uniformly throughout all 8 files.

---

## 2. COLOPHON PRESENCE AND FORMAT

### Status by Fascicle

| Fascicle | Colophon Present | Colophon Text | Issues |
|----------|-----------------|---------------|--------|
| 26 | **NO** | (absent) | Missing colophon |
| 27 | **NO** | (absent) | Missing colophon |
| 28 | **NO** | (absent) | Missing colophon |
| 29 | **NO** | (absent) | Missing colophon |
| 30 | YES | `*End of Fascicle Thirty of the Yogacarabhumi-sastra*` | Format differs from others |
| 31 | YES | `*End of Fascicle 31*` | Uses numeral (not word); no "of the Yogacarabhumi-sastra"; trailing Chinese text appended after colophon |
| 32 | YES | `*End of Fascicle Thirty-Two*` | No "of the Yogacarabhumi-sastra" |
| 33 | YES | `*End of Fascicle Thirty-Three.*` | Has a period; followed by `*Yogacarabhumi-sastra, Volume 33*` (extra line) |

### Issues

**Critical:** Fascicles 26, 27, 28, 29 have NO colophon at all. The files end abruptly in footnotes without any closing colophon line.

**Format inconsistency (fascicles 30–33 present but differ):**

- F30: `*End of Fascicle Thirty of the Yogacarabhumi-sastra*` — most complete form
- F31: `*End of Fascicle 31*` — uses Arabic numeral, not spelled-out word; no Yogacarabhumi-sastra suffix; followed by a Chinese line (`瑜伽師地論卷第三十一`) after the colophon
- F32: `*End of Fascicle Thirty-Two*` — no Yogacarabhumi-sastra suffix
- F33: `*End of Fascicle Thirty-Three.*` — trailing period; followed by `*Yogacarabhumi-sastra, Volume 33*` which uses "Volume" instead of standard colophon form

**Recommended standard form** (based on F30 as most complete): `*End of Fascicle [Spelled-out Number] of the Yogacarabhumi-sastra*`

---

## 3. HEADER FORMAT CONSISTENCY

### Template (identical across all 8 files — PASS)

```
# Sravakabhumi: The Hearer's Ground

## Yogacarabhumi-sastra, Fascicle XX

*Composed by Asanga*[^attr]
*Translated into Chinese by Tripitaka Master Xuanzang, by imperial decree*
*English translation from the Chinese (Taisho Tripitaka, Vol. 30, No. 1579)*

[^attr]: The Chinese text attributes this work to Maitreya Bodhisattva (彌勒菩薩說). Modern scholarly consensus attributes the Sravakabhumi to Asanga. See Deleanu, *The Chapter on the Mundane Path* (2006).

---

## Basic Section: Shravaka Ground, [Yoga Place], Part [N]

[Chinese title line]

---

### XX.1 [First Section Title]
```

**Result: PASS.** All 8 fascicles use exactly this header pattern with no variations. H1 (`# Sravakabhumi`), H2 (`## Yogacarabhumi-sastra, Fascicle XX`), attribution lines, `[^attr]` footnote, dividers, yoga-place H2, Chinese title line, and section H3 all conform perfectly across fascicles 26–33.

---

## 4. CROSS-FASCICLE TERMINOLOGY THREADS

### 4a. shamatha (correct) / samatha (wrong — Pali)

- `samatha`: **0 hits** across all 8 files
- `shamatha`: present and used correctly in all 8 files (counts: 8, 3, 10, 10, 4, 19, 30, 7)
- **Result: PASS.** No Pali form detected anywhere.

### 4b. vipashyana (correct) / vipassana (wrong — Pali)

- `vipassana`: **0 hits** across all 8 files
- `vipashyana`: present and used correctly in all 8 files (counts: 9, 3, 13, 8, 17, 27, 19, 3)
- **Result: PASS.** No Pali form detected anywhere.

### 4c. dhyana (correct) / jhana (wrong — Pali)

- `jhana`: **1 hit** — fascicle_33_en.md, line 204
  - **Context:** In a translator's footnote (`[^second_dhyana_coarse]`), which reads: *"The Visuddhimagga (IV.88-94) provides a parallel analysis of how *vitakka* and *vicara* must be abandoned for the second *jhana*."*
  - **Assessment:** This is a Pali cross-reference to the Visuddhimagga's own Pali technical term. The Visuddhimagga uses Pali throughout, and `jhana` here refers to the Pali text's own terminology, not to the Sravakabhumi's rendering. This is a borderline case: the footnote correctly uses `dhyana` when referring to the Sravakabhumi's content; the `jhana` appears only when referencing a Pali source. However, per the watchlist ("dhyana, not jhana"), this is technically a violation even in footnotes.
  - **Severity: Minor.** Could be replaced with "the Visuddhimagga's parallel treatment of *vitarka* and *vicara* as factors to be abandoned for the second dhyana."
- `dhyana`: present and used correctly in all fascicles discussing these attainments.
- **Result: 1 MINOR ISSUE** in footnote context (F33 line 204).

### 4d. afflictions (correct) / defilements (wrong — Theravada register)

- `defilements` / `defilement`: **3 hits** — all in fascicle_28_en.md
  - **Line 530 (running text):** "...lead to ultimate emergence, ultimate freedom from **defilement**, and the ultimate perfection of the holy life..."
    - **Assessment:** "Freedom from defilement" is used here in a specific technical sense — the Sanskrit is likely *viraga* (dispassion) or *vimutti* (liberation), describing a state of freedom. This is NOT using "defilement" as a synonym for 煩惱 (affliction/klesha), but rather as a description of the result state. Borderline, but the phrasing "freedom from defilement" is idiomatic English for this context and differs from using "defilements" as the name of a category.
    - **Assessment revised:** Still potentially confusing given the watchlist rule. The Chinese likely reads something like 究竟清淨 or 究竟離垢. Should be reviewed against source for whether "afflictions" or a more neutral rendering would be appropriate.
    - **Severity: Moderate.** Recommend checking against Chinese source and replacing with "freedom from afflictions" or "ultimate purity" if the source supports it.
  - **Line 588 (running text):** "**The four dimensions of defilement and purification.**" — Used as a technical category name: "defilement and purification" (染淨).
    - **Assessment:** Here "defilement" translates 染 (dye/stain/contaminate) as a conceptual category, not the klesha (煩惱) terminology. In this framework "染淨" is "staining and purifying" as a dyadic concept. This is a legitimate semantic field distinct from "defilements" (煩惱). However, given the watchlist warning, it creates register confusion.
    - **Severity: Minor.** "Defilement" as a translation of 染 (染汙) is contextually appropriate here in the dharma/karma frame; however, it should be footnoted or "contamination/purification" considered as alternative.
  - **Line 658 (footnote):** Repeats "defilement and purification" in the scholarly footnote summarizing the same category.
    - **Severity: Minor.** Same as line 588 — consistent with that passage.

- **Result: 1 MODERATE ISSUE** (line 530), **2 MINOR ISSUES** (lines 588, 658), all in F28. None are the watchlist-prohibited usage of "defilements" as a rendering of 煩惱 (klesha). However, the word "defilement" appears in running text in contexts that could cause register confusion.

### 4e. skandha (correct) / khandha (wrong — Pali)

- `khandha`: **0 hits** across all 8 files
- `skandha` / `skandhas`: used correctly throughout; first-use glossing ("the five skandhas (aggregates)") present in fascicle 26 and 28.
- **Result: PASS.**

### 4f. pudgala / person (never untranslated pudgala in running text)

Occurrences of `pudgala` in running text (not in footnotes):

- **F26, line 23:** "persons (*pudgala*)" — parenthetical gloss in Q&A opener. ACCEPTABLE — Sanskrit gloss in parentheses after English translation.
- **F26, line 29:** "persons,[^pudgala]" — verse line uses "persons" with footnote explaining Sanskrit. ACCEPTABLE.
- **F26, line 570:** Footnote only. ACCEPTABLE.
- **F28, line 77:** "three types of persons (*pudgala*)" — Sanskrit gloss in parentheses after English. ACCEPTABLE.
- **F28, line 636:** Footnote only ("agotra-pudgala"). ACCEPTABLE — compound Sanskrit technical term in footnote.
- **F29, line 394:** "persons (*pudgala*)" — Sanskrit gloss in parentheses after English. ACCEPTABLE.
- **F29, line 434:** "the person (*pudgala*)" — Sanskrit gloss in parentheses after English. ACCEPTABLE.
- **F27, F30, F31, F32, F33:** No bare `pudgala` occurrences.

**Result: PASS.** In every instance, `pudgala` appears either (a) only in footnotes, or (b) in running text with the English translation "person/persons" preceding it and pudgala following in parentheses as a Sanskrit clarification. The rule "never untranslated pudgala in running text" is observed: the English rendering always leads, pudgala is always in parentheses or footnotes.

**Note:** F26 line 23 uses "persons (*pudgala*)" and then continues using "persons" throughout — the pattern is established there and subsequent fascicles correctly use "person/persons" without repeating the Sanskrit gloss. This is correct NTC convention.

### 4g. Xuanzang (correct) / Hsuan-tsang (wrong)

- `Hsuan-tsang` / `Hsuan-chuang` / `Hsüan-tsang`: **0 hits** across all 8 files
- `Xuanzang`: used in all 8 header lines and in multiple footnotes. Uniform.
- **Result: PASS.**

### 4h. Asanga (correct) / Maitreya as author in running text

- **Attribution footnote `[^attr]`**: Present in all 8 fascicles at line 9. Text reads: *"The Chinese text attributes this work to Maitreya Bodhisattva (彌勒菩薩說). Modern scholarly consensus attributes the Sravakabhumi to Asanga."* This is correct — it acknowledges the Chinese attribution while stating the scholarly consensus. NOT a violation.
- **Header line**: All 8 files read `*Composed by Asanga*[^attr]` — correct.
- **"Maitreya" in running text as author claim:** 0 instances of Maitreya being credited as the author without qualification. The `[^attr]` footnote consistently handles the attribution question.
- **Result: PASS.** Maitreya appears only in the explanatory footnote as the Chinese text's attribution claim, never as an unqualified authorship assertion.

---

## 5. TAISHO REFERENCE FORMAT

### Standard format: `[T30.XXXX]` where XXXX = pagecol-line (e.g., `[T30.0424a07]`)

- All Taisho references across all 8 files use the `[T30.XXXX]` bracket format.
- Non-bracket format: **0 hits** — no Taisho references appear without brackets.
- Format is consistent (volume 30, decimal page, column letter a/b/c, two-digit line).
- References per fascicle: F26=11, F27=7, F28=20, F29=11, F30=14, F31=5, F32=18, F33=11.

**Result: PASS.** Taisho reference format is uniform across all 8 files. No deviations detected.

---

## SUMMARY OF FINDINGS

### Critical Issues (must fix)

1. **Colophons missing from fascicles 26, 27, 28, 29.** Four of the eight translation files have no closing colophon. Files end in the last footnote without any `*End of Fascicle N*` line. This is the most significant structural gap.

### Moderate Issues (should fix)

2. **Colophon format inconsistency (fascicles 30–33).** Four different formats used:
   - F30: `*End of Fascicle Thirty of the Yogacarabhumi-sastra*` (most complete)
   - F31: `*End of Fascicle 31*` (numeral not word; missing Yogacarabhumi-sastra; trailing Chinese text after colophon)
   - F32: `*End of Fascicle Thirty-Two*` (missing Yogacarabhumi-sastra)
   - F33: `*End of Fascicle Thirty-Three.*` (period; followed by extra `*Yogacarabhumi-sastra, Volume 33*` line)
   - Recommended standard: `*End of Fascicle [Spelled-Out] of the Yogacarabhumi-sastra*`

3. **"defilement" in running text, F28 line 530.** "Ultimate freedom from defilement" — should be checked against Chinese source; likely should read "ultimate freedom from afflictions" or "ultimate purity" to avoid Theravada register.

### Minor Issues

4. **"jhana" in footnote, F33 line 204.** Pali form appears once in a footnote cross-referencing the Visuddhimagga's Pali content. Technically violates the watchlist; can be replaced with "dhyana" or "the second dhyana" without loss of meaning.

5. **"defilement and purification" (F28 lines 588, 658).** Used as a translation of the dyadic 染淨 concept, not as a synonym for 煩惱. Technically correct but creates register confusion given the watchlist. "Contamination and purification" or "staining and purification" are alternatives.

6. **F31 trailing Chinese text after colophon.** The line `瑜伽師地論卷第三十一` appears after `*End of Fascicle 31*`. This is unformatted raw Chinese text appearing as the final line of the file rather than a translator's note or properly formatted colophon.

7. **F33 extra line after colophon.** `*Yogacarabhumi-sastra, Volume 33*` appears after the colophon as an extra italicized line. Not the right closing format; the colophon should be the final substantive line before the divider.

### PASS Items (no issues)

- Section numbering: all 103 sections correctly numbered XX.N, no gaps or duplicates
- Header format: perfectly uniform across all 8 fascicles
- `shamatha` (not `samatha`): 100% correct
- `vipashyana` (not `vipassana`): 100% correct
- `dhyana` (not `jhana`): 100% correct in running text; 1 footnote exception
- `afflictions` (not `defilements` as klesha rendering): 100% correct
- `skandha` (not `khandha`): 100% correct
- `pudgala` in running text: always parenthetical after "person/persons", never bare
- `Xuanzang` (not Hsuan-tsang): 100% correct
- `Asanga` as attributed author: correct in all 8 headers; Maitreya only in explanatory footnote
- Taisho reference format `[T30.XXXX]`: 100% consistent across all 97 references

---

## RECOMMENDED FIXES IN PRIORITY ORDER

| Priority | Action | Files |
|----------|--------|-------|
| 1 | Add missing colophons to fascicles 26, 27, 28, 29 | F26, F27, F28, F29 |
| 2 | Standardize colophon format to `*End of Fascicle [Spelled-Out] of the Yogacarabhumi-sastra*` | F31, F32, F33 |
| 3 | Remove/relocate trailing Chinese text from F31 | F31 |
| 4 | Remove extra `*Yogacarabhumi-sastra, Volume 33*` line from F33 | F33 |
| 5 | Check F28:530 "freedom from defilement" against Chinese source; replace if warranted | F28 |
| 6 | Replace `jhana` with `dhyana` in F33 footnote (line 204) | F33 |
| 7 | Consider replacing "defilement and purification" (F28:588, 658) with "contamination and purification" | F28 |
