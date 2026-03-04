# Terminology Review: Fascicle 33, Sections 33.6–33.9

**Agent T (Terminology)**
**Scope:** `translation/fascicle_33_en.md` lines 142–216 (sections 33.6, 33.7, 33.8, 33.9)
**Date:** 2026-03-02

---

## Summary Table

| Severity | Count |
|----------|-------|
| Critical | 0 |
| Moderate | 3 |
| Minor | 5 |
| **Total** | **8** |

---

## Findings

### MODERATE — M1: `panchangika` variant spelling (line 174, footnote)

**Location:** `[^five_branches]`: "The five branches (*panchangika*, 五支)"

**Issue:** The Sanskrit `panchangika` is not in the glossary under any entry. The correct Sanskrit for "five branches/limbs" is typically `pancanga` or `pañcāṅga`. The spelling `panchangika` is a non-standard form (likely an adjectivized form). More importantly, this term is not registered in the glossary at all, which is a protocol violation (all technical terms used must be in the glossary before use). No entry exists for this compound Sanskrit term describing the five factors of the first dhyana.

**Action:** Add `panchangika` (or the normalized form `pancanga`) to the glossary with the rendering "five-branched / five-factor." Also verify the correct Sanskrit form against a reference edition.

---

### MODERATE — M2: `citta-ekagrya` vs. glossary `ekagrata` (line 174, footnote)

**Location:** `[^five_branches]`: "one-pointed mind (*citta-ekagrya*, 心一境性)"

**Issue:** The glossary entry for 一境性 (line 229) gives the Sanskrit as `ekagrata` and specifies the rendering "mental one-pointedness" (full phrase, per watchlist). The translation footnote uses the Sanskrit form `citta-ekagrya` (which is a compound = "one-pointedness of mind"), which is not the form registered in the glossary. The glossary renders 心一境性 as "mental one-pointedness" (preferred) or "one-pointedness / mental one-pointedness." The in-text rendering here is "one-pointed mind (*citta-ekagrya*, 心一境性)" — which is close in meaning but differs in form from the glossary's preferred "mental one-pointedness."

**Sub-issues:**
- The Sanskrit form `citta-ekagrya` is not in the glossary (the glossary has `ekagrata` for 一境性).
- The in-text English rendering "one-pointed mind" is an acceptable variant, but the watchlist explicitly mandates "one-pointed mind / mental one-pointedness" as the full phrase, not an abbreviation — so "one-pointed mind" without "mental" is borderline.

**Action:** Either (a) use "mental one-pointedness (*ekagrata*, 心一境性)" to align with the glossary, or (b) add `citta-ekagrya` as an alternate Sanskrit compound to the glossary entry. The English rendering should be "one-pointed mind" — which is acceptable per the glossary — but the Sanskrit should match the glossary's registered form.

---

### MODERATE — M3: `samuccheda-prahana` not in glossary (line 170, footnote)

**Location:** `[^temporary_suppression]`: "permanently destroy (*samuccheda-prahana*) the seeds of affliction"

**Issue:** The Sanskrit technical term `samuccheda-prahana` ("eradication-abandonment" / "cutting off completely") is used in a footnote but is not registered in the glossary. It is a doctrinal distinction from the Abhidharma tradition: temporary suppression (伏斷) vs. complete eradication (samuccheda). Since footnotes introduce technical Sanskrit terms parenthetically, this should be glossary-registered.

**Action:** Add `samuccheda-prahana` to the glossary with the rendering "complete eradication / eradication abandonment" and note: "Contrasted with temporary suppression (伏斷); only the supramundane path achieves samuccheda."

---

### MINOR — Mi1: `viveka-ja priti-sukha` not in glossary (line 172, footnote)

**Location:** `[^progressive_joy]`: "joy and bliss born of separation (*viveka-ja priti-sukha*, 離生喜樂)"

**Issue:** The compound `viveka-ja priti-sukha` ("joy and bliss born of seclusion/separation") is used parenthetically in the footnote but has no glossary entry. The Chinese 離生喜樂 is the standard formula for the first dhyana quality. The rendering "joy and bliss born of separation" is doctrinally sound and consistent with usage throughout sections 33.6–33.9 in the main text, but the term is unregistered.

**Action:** Add `viveka-ja priti-sukha` (or the Chinese 離生喜樂) to the glossary. Recommended rendering: "joy and bliss born of separation" consistent with current usage.

---

### MINOR — Mi2: `styana-middha` rendering vs. glossary (line 166, footnote)

**Location:** `[^joyful_engagement]`: "torpor and drowsiness (*styana-middha*, 惛沈睡眠)"

**Issue:** The glossary entry (line 221) gives `styana-middha` with the rendering "torpor and drowsiness." The footnote matches the glossary exactly: "torpor and drowsiness (*styana-middha*, 惛沈睡眠)." This is correct. However, the main text of section 33.6 (line 148) uses the phrase "in order to dispel torpor, drowsiness, excitement, and the like" without giving the Sanskrit parenthetical — which is appropriate for running text (the gloss is in the footnote). **No issue in this occurrence.** Noting as verified.

*No action required.*

---

### MINOR — Mi3: `auddhatya` vs. `agitation` rendering check (line 166, footnote)

**Location:** `[^joyful_engagement]`: "excitement (*auddhatya*, 掉舉)"

**Issue:** The glossary (line 556) renders `auddhatya` as "agitation" (preferred form: "agitation"). The footnote uses "excitement" for 掉舉 (*auddhatya*). These are inconsistent: the glossary specifies "agitation" as the rendering for 掉舉 standalone, while "restlessness" is reserved for the compound 掉舉惡作. The running text at line 148 also uses "excitement" ("in order to dispel torpor, drowsiness, excitement").

**Action:** Replace "excitement" with "agitation" for 掉舉 (*auddhatya*) in both the running text (line 148) and the footnote (line 166), consistent with the glossary's specified rendering. Using "excitement" diverges from the established rendering.

---

### MINOR — Mi4: `adhimana` first-use gloss placement

**Location:** Line 180 (section 33.7): "enables the mind to abide free from overestimation (*adhimana*) regarding what has been attained."

**Issue:** `adhimana` / overestimation is given its Sanskrit parenthetical in the running text of 33.7. The glossary entry (line 409) registers `adhimana` → "overestimation." This is correct. However, `adhimana` was already introduced with Sanskrit gloss in earlier sections of fascicle 33 (section 33.6, footnote line 168: "overestimation (*adhimana*)"). So the re-parenthesization in 33.7 running text is technically a repeat. Per the glossary convention: "First-use pattern: 'English rendering (Sanskrit)' on first occurrence in each fascicle. Thereafter, either English or Sanskrit per the 'Preferred in text' column." The glossary does not specify a "preferred in text" form for adhimana. Repeated parenthetical glossing is a minor stylistic inconsistency rather than an error.

**Action:** Minor only — consider removing the Sanskrit parenthetical in 33.7 since it was already introduced in 33.6's footnote. Not an error, but redundant.

---

### MINOR — Mi5: `dharmata` in footnote vs. glossary form

**Location:** Line 168, footnote `[^investigation_test]`: "genuinely transformed through insight into the nature of things (*dharmata*)"

**Issue:** The glossary (line 601) lists `dharmata` → "the nature of things, natural order" with preferred in-text form "dharmata." The footnote uses `dharmata` parenthetically with the English gloss "the nature of things" — this is fully consistent with the glossary. **No error.** Verified.

*No action required.*

---

## Terms Verified as Correct

The following terms were checked against the glossary and found correctly rendered and consistent:

| Term used in text | Glossary entry | Status |
|---|---|---|
| shamatha | 奢摩他 / shamatha | Correct |
| vipashyana | 毘鉢舍那 / vipashyana | Correct |
| dhyana (first, second, etc.) | 靜慮 / dhyana | Correct |
| samadhi | 三摩地 / samadhi | Correct |
| afflictions | 煩惱 / klesha / afflictions | Correct |
| latent tendencies (*anushaya*) | 隨眠 / anushaya / latent tendency | Correct |
| overestimation (*adhimana*) | 增上慢 / adhimana / overestimation | Correct |
| attention to characteristics | 了相作意 / attention to characteristics | Correct |
| attention of conviction | 勝解作意 / attention of conviction | Correct (context 2 per glossary note) |
| attention of separation | 遠離作意 / attention of separation | Correct |
| attention of joyful engagement | 攝樂作意 / attention of joyful engagement | Correct |
| attention of investigation | 觀察作意 / attention of investigation | Correct |
| attention of completed application | 加行究竟作意 / attention of completed application | Correct |
| attention to the fruit of completed application | 加行究竟果作意 / attention to the fruit of completed application | Correct |
| dausthulya (coarseness and heaviness) | 麁重 / dausthulya / heaviness, coarseness | Correct |
| examination (*vitarka*) | 尋 / vitarka / examination | Correct (dhyana-factor context) |
| analysis (*vicara*) | 伺 / vicara / analysis | Correct (dhyana-factor context) |
| upper-grade (*adhimatra*) | glossary footnote context | Correct |
| middle (*madhya*) / lower (*mrdu*) | glossary footnote context | Correct |
| joy (*priti*) | 喜 / priti / joy | Correct |
| bliss (*sukha*) | 樂 / sukha / correct general rendering | Correct |
| dark category | 黑品 / krishna-paksha / dark category | Correct |
| worldly path | 世俗道 / samvriti-marga / worldly path | Correct |
| supramundane path | 出世間道 / lokottara-marga / supramundane path | Correct |
| four noble truths | 四聖諦 / four noble truths | Correct |
| torpor and drowsiness (*styana-middha*) | 惛沈睡眠 / styana-middha / torpor and drowsiness | Correct |
| dharmata | 法爾 / dharmata / the nature of things | Correct |
| formations (*samskara*) | 行 / samskara / formations | Correct (line 154: "constrained by formations") |
| yogin | 瑜伽師 / yogin | Correct |
| sphere of infinite space / infinite consciousness / nothingness / neither-perception-nor-non-perception | standard formless-realm terminology | Correct (no Sanskrit glosses needed for these well-established terms) |
| Nikayas/Agamas (footnote cross-reference) | N/A — scholarly reference, not a technical term | Acceptable |
| Visuddhimagga (footnote cross-reference) | N/A — title reference | Acceptable |
| Abhidharmasamuccaya (footnote cross-reference) | N/A — title reference | Acceptable |

---

## Watchlist Check

All watchlist items reviewed:

| Watchlist item | Present in 33.6–33.9? | Status |
|---|---|---|
| Hsuan-tsang / Hsuan-chuang | No | Clear |
| Maitreya as author | No | Clear |
| pudgala (untranslated in running text) | No | Clear |
| sentient being (for 補特伽羅) | No | Clear |
| vipassana (Pali) | No | Clear |
| samatha (Pali) | No | Clear |
| jhana (Pali) | No — "dhyana" used correctly | Clear |
| sutta (Pali) | No | Clear |
| nibbana (Pali) | No | Clear |
| khandha (Pali) | No | Clear |
| defilements (for 煩惱) | No — "afflictions" used | Clear |
| mental quiescence | No | Clear |
| special insight | No | Clear |
| aggregates without context | No | Clear |
| absorptions (for 靜慮) | Line 25 (uddana): "Two absorptions" — but this is in the uddana summary (outside 33.6–33.9 scope) | Out of scope |
| one-pointedness (abbreviation) | One occurrence: "one-pointed mind" in footnote fn5 — see M2 above | Near-miss, see M2 |
| concentration (for 三摩地 standalone) | Line 196: "ground of concentration" — 定 here likely = "samadhi" or "concentration" in context. The phrase "ground of concentration" (定) is contextually appropriate. | Acceptable |
| The Mind Illuminated | No | Clear |

---

## Priority Action Summary

| ID | Severity | Issue | Fix |
|----|----------|-------|-----|
| M1 | Moderate | `panchangika` not in glossary | Add to glossary; verify Sanskrit form |
| M2 | Moderate | `citta-ekagrya` not in glossary; diverges from registered `ekagrata` | Align Sanskrit to glossary or add `citta-ekagrya` as compound form |
| M3 | Moderate | `samuccheda-prahana` not in glossary | Add to glossary |
| Mi1 | Minor | `viveka-ja priti-sukha` not in glossary | Add to glossary |
| Mi3 | Minor | "excitement" used for 掉舉 (*auddhatya*) — glossary says "agitation" | Replace "excitement" with "agitation" in lines 148 and 166 |
| Mi4 | Minor | Redundant Sanskrit parenthetical for `adhimana` in 33.7 | Optional: remove redundant gloss |
| Mi2, Mi5 | Minor | Verified correct (styana-middha, dharmata) | No action |
