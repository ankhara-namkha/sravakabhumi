# Terminology Review: Fascicle 33, Sections 33.10–33.18
**Agent T (Terminology) — Review Batch EF (Updated)**
**Sections:** 33.10 First Dhyana Formula Commentary, 33.11 Second Dhyana Formula, 33.12 Third Dhyana Formula, 33.13 Fourth Dhyana Formula, 33.14 Four Formless Attainments, 33.15 Two Absorptions Without Mind, 33.16 Five Superknowledges and Twelve Perceptions, 33.17 Rebirth Destinations, 33.18 Characteristics of the Desire-Free Person
**Lines reviewed:** 220–449 of `translation/fascicle_33_en.md`
**Note:** This updated version supersedes the earlier draft. Additional findings added after full re-read against glossary lines 1–623 and watchlist.

---

## Summary Table

| Severity | Count |
|----------|-------|
| Critical | 1 |
| Moderate | 4 |
| Minor | 5 |
| **Total** | **10** |

---

## CRITICAL FINDINGS

### C-1 — Missing glossary entries: five key terms used in 33.16 without glossary coverage

**Severity:** Critical
**Location:** Section 33.16; footnotes [^five_superknowledges] and [^liberation_mastery]
**Issue:** Four terms introduced and used with Sanskrit equivalents in sections 33.16 and its footnotes are absent from `glossary/MASTER_GLOSSARY.md`:

1. **no-contention knowledge** (*arana-jnana*, 無諍) — line 394, running text
2. **power of aspiration** (*pranidhi-jnana*, 願智) — line 394, running text
3. **four analytical knowledges** (*pratisam-vid*, 四無礙解/四無礙辯) — line 394, running text
4. **twelve perceptions** (*dvadasha-samjna*) — used as a technical set label throughout 33.16

Additionally:
5. **bases of mastery** (*abhibhv-ayatana*, 勝處) — mentioned in footnote [^liberation_mastery] (line 402) and section 33.16 body (line 394) — not in glossary.

The glossary has `ashta-vimoksha` (eight liberations) and the `samahita-bhumi` reference, but none of these five terms appear. Since `glossary/MASTER_GLOSSARY.md` is the sole authority and terms must be added before use, these are glossary gaps.

**Action required:** Add all five terms to the glossary before marking the section complete.

---

## MODERATE FINDINGS

### M-1 — `priti` rendered as "joy" throughout, but glossary notes "rapture" in dhyana context

**Severity:** Moderate
**Location:** Sections 33.10–33.13; lines 236, 262, 272–280, 296, 300
**Issue:** The glossary entry for 喜 / priti (line 598) reads:
> "joy, rapture | joy | Dhyana factor distinct from pramodya (gladness); 'rapture' in dhyana context per Nanamoli"

The translation consistently renders priti as "joy" in the dhyana formula commentaries (33.10–33.13). This is the preferred form per the glossary ("joy"), so it does not violate the preferred rendering. However, the note suggests "rapture" for the dhyana context per the Nanamoli standard. This creates a minor inconsistency with the reference library register — not a hard violation but worth flagging for editorial consideration.

**Note:** The full compound formula phrases are correctly rendered: "joy and bliss born of separation" (離生喜樂 = glossary entry 612) and "joy and bliss born of concentration" (定生喜樂 = glossary entry 613). These match.

**Action:** Editorial judgment. The current rendering is permitted by the glossary. No change required unless editorial policy aligns with Nanamoli's "rapture."

---

### M-2 — `parishuddha` introduced in running text without glossary entry

**Severity:** Moderate
**Location:** Section 33.13, line 300
**Issue:** The text uses:
> "equanimity and mindfulness here are pure and radiant (*parishuddha*)"

The Sanskrit *parishuddha* is introduced in parentheses in running text (the standard first-use gloss pattern), but there is no glossary entry for this term. The Chinese source likely uses 清淨鮮白 (literally "clear, pure, bright, white" — confirmed in footnote [^four_cessations] at line 360). The footnote explains this but the glossary lacks the term.

**Action required:** Add *parishuddha* / 清淨鮮白 to the glossary with rendering "pure and radiant."

---

### M-3 — `acitta-samapatti` (two absorptions without mind) partially in glossary — rendered form inconsistent

**Severity:** Moderate
**Location:** Section 33.15 heading and line 342
**Issue:** The heading uses "Two Absorptions Without Mind" and the text uses "two absorptions without mind (*acitta-samapatti*)." The glossary contains:
- `無想定` / `asamjni-samapatti` = "attainment of non-perception" (line 609) ✓
- `滅受想定` / `samjna-vedayita-nirodha` = "cessation of perception and feeling" (line 155) ✓

However, the collective term "two absorptions without mind" (*acitta-samapatti*, 二無心定) is not in the glossary as a standalone entry. The footnote [^two_absorptions] (line 354) correctly identifies the individual terms (`citta-caitta` = mind and mental factors) but the collective compound is unattested in the glossary.

Additionally, the footnote uses `citta-caitta` (mind and mental factors) — the glossary has `caitta` (mental factors) as a standalone entry, and `citta` as heart/mind, but not the compound `citta-caitta`. This is a minor gap.

**Action required:** Add `acitta-samapatti` / 二無心定 as a collective term entry. Add `citta-caitta` note linking to existing `citta` and `caitta` entries.

---

### M-4 — Five pure abodes Sanskrit name variants inconsistent with existing glossary entry

**Severity:** Moderate
**Location:** Section 33.17 footnote [^rebirth_destinations], line 424
**Issue:** The footnote gives the five pure abodes as:
> "Avrha (無煩), Atapa (無熱), Sudrsha (善現), Sudarsana (善見), and Akanishtha (色究竟)"

The glossary has only Akanishtha (line 124, with Chinese 色究竟天). The Sanskrit forms of the other four pure abodes — Avrha, Atapa, Sudrsha (should be Sudrsha or Sudarsha?), Sudarsana — appear only in the footnote and are not in the glossary. The term `shuddhavasika` (pure abodes collective) is also used in this footnote but is absent from the glossary.

**Specific concern:** "Sudrsha" (善現) — the standard Sanskrit is Sudrishya or Sudrsha (Pali: Sudassa). The footnote uses "Sudrsha" which is an acceptable transliteration but should be verified against the Sanskrit and confirmed in the glossary. The Pali parallels (Avihā, Atappā, Sudassā, Sudassī, Akaniṭṭhā) are not being used, which is correct per NTC convention.

**Action required:** Add the five pure abodes as named entries, verify Sanskrit forms, and add `shuddhavasika` collective entry.

---

## MINOR FINDINGS

### m-1 — `abhibhv-ayatana` typo in footnote

**Severity:** Minor
**Location:** Footnote [^liberation_mastery], line 402
**Issue:** The footnote uses `abhibhv-ayatana` for the Sanskrit of 勝處 (bases of mastery). This appears to be a typographic abbreviation or error — the standard Sanskrit is `abhibhv-ayatana` (where "abhibhv" is an unusual abbreviation of *abhibhu* or *abhibhavana*). The standard rendering in Abhidharma literature is *abhibhv-ayatana* (as it appears here) but more commonly written *abhibhavayatana* or *abhibhu-ayatana*. The internal form is inconsistent with normal Sanskrit romanization.

**Action:** Verify the standard Sanskrit form and correct the footnote accordingly. The rendering "bases of mastery" is not in the glossary (see C-1 above).

---

### m-2 — First-use gloss pattern for `prashrabdhi` — acceptable but note for consistency

**Severity:** Minor
**Location:** Section 33.10, line 236
**Issue:** "vast pliancy (*prashrabdhi*)" — this follows the correct first-use pattern (English + Sanskrit in parentheses). The glossary entry (line 91) gives "pliancy, ease | pliancy" as the correct rendering. This is correct.

However, in 33.12 and 33.13, pliancy appears again (lines 280, 294) without the Sanskrit parenthetical, which is appropriate per the "first-use only" convention. No issue.

**Status:** Correct. Noted for confirmation.

---

### m-3 — `dutula` (cotton variety) — no glossary entry, no explanation

**Severity:** Minor
**Location:** Section 33.16, line 372
**Issue:** "*dutula* cotton" is used as a comparison term (like a kind of cotton). This is a Sanskrit/Pali term for a type of cotton or cottonwood. It appears untranslated (rendered as the Sanskrit form in italics) but without any gloss or footnote explaining what it is. It is not in the glossary.

**Action:** Either add a brief parenthetical gloss ("*dutula* cotton [a fine, light variety]") or add to glossary with note that it is a type of lightweight cotton used in similes. Minor omission, but unexplained Sanskrit terms should be flagged per rule (5).

---

### m-4 — `samahita-bhumi` cross-reference rendered correctly but inconsistently capitalized

**Severity:** Minor
**Location:** Section 33.16, line 394
**Issue:** "the concentrated ground (*samahita-bhumi*)" — the glossary entry (line 104) gives "ground of meditative equipoise" as the English rendering and "meditative equipoise" as preferred. The translation uses "concentrated ground" here, which is a slight deviation from the glossary's "ground of meditative equipoise."

**Note:** This section is a cross-reference pointing back to an earlier section of the Yogacarabhumi. Using "concentrated ground" versus "ground of meditative equipoise" is a rendering inconsistency. The glossary form should be preferred.

**Action:** Consider changing to "the ground of meditative equipoise (*samahita-bhumi*)" for consistency.

---

### m-5 — `shuddhavasika` used in footnote without glossary entry

**Severity:** Minor (overlaps with M-4 above)
**Location:** Footnote [^rebirth_destinations], line 424
**Issue:** "*shuddhavasika*" is the Sanskrit used parenthetically for "five pure abodes" in the footnote. This term does not appear in the glossary. (Covered in M-4 above but listed here for completeness as a first-use gloss without backing glossary entry.)

---

## TERMS VERIFIED AS CORRECT

The following terms appear in sections 33.10–33.18 and have been cross-checked against the glossary. All are correctly rendered:

| Term in Translation | Glossary Entry | Status |
|--------------------|----------------|--------|
| examination (*vitarka*) | glossary line 97/607: examination | CORRECT |
| analysis (*vicara*) | glossary line 99/608: analysis | CORRECT |
| inner clarity (*adhyatma-samprasada*) | glossary line 611: inner clarity | CORRECT |
| equanimity (*upeksha*) | glossary line 90: equanimity | CORRECT |
| pliancy (*prashrabdhi*) | glossary line 91: pliancy | CORRECT |
| joy and bliss born of separation | glossary line 612 | CORRECT |
| joy and bliss born of concentration | glossary line 613 | CORRECT |
| dhyana | glossary line 25: dhyana | CORRECT |
| samadhi | glossary line 26/27 | CORRECT |
| afflictions | glossary line 21: afflictions (not "defilements") | CORRECT |
| affliction-desire (*klesha-kama*) | glossary line 22 | CORRECT |
| object-desire (*vastu-kama*) | glossary line 23 | CORRECT |
| sphere of infinite space (*akashanantya-ayatana*) | glossary line 616 | CORRECT |
| sphere of infinite consciousness (*vijnanananty-ayatana*) | glossary line 617 | CORRECT |
| sphere of nothingness (*akimcanya-ayatana*) | glossary line 618 | CORRECT |
| sphere of neither-perception-nor-non-perception (*naiva-samjna-nasamjna-ayatana*) | glossary line 619 | CORRECT |
| provisional conviction (*parikalpita-adhimoksha*) | adhimoksha = glossary line 96: resolute confidence/conviction | CORRECT (conviction applied; parikalpita gloss appropriate) |
| shamatha | glossary line 28: shamatha | CORRECT (no Pali form used) |
| attainment of non-perception (*asamjni-samapatti*) | glossary line 609 | CORRECT |
| cessation attainment (*nirodha-samapatti*) | glossary line 155 (cross-reference) | CORRECT |
| learner (*shaiksha*) | glossary line 230/394 | CORRECT |
| arhat | glossary line 66 | CORRECT |
| ordinary being(s) | glossary line 78 (prithagjana) | CORRECT |
| noble one(s) | glossary line 77 (arya) | CORRECT |
| superknowledge / superknowledges | glossary line 610: superknowledge (NOT "supernatural power") | CORRECT |
| magical display (*rddhi-abhijna*) | glossary line 610 (five types listed) | CORRECT |
| recollection of past lives (*purvanivasanusmrti*) | glossary line 610 | CORRECT |
| divine ear (*divya-shrotra*) | glossary line 610 | CORRECT |
| knowledge of death and rebirth (*cyuty-upapatti-jnana*) | glossary line 610 | CORRECT |
| knowledge of others' minds (*para-citta-jnana*) | glossary lines 512, 610 | CORRECT |
| non-returner (*anagamin*) | glossary line 69 | CORRECT |
| universal purity (*subhakrtsna*) | glossary line 620 | CORRECT |
| vast fruit (*brhatphala*) | glossary line 621 | CORRECT |
| Akanishtha | glossary line 124 | CORRECT |
| in-and-out breathing (*anapana*) | glossary line 113 | CORRECT |
| attention of completed application | glossary line 423 | CORRECT |
| attention to the fruit of completed application | glossary line 424 | CORRECT |
| secondary afflictions | glossary line 110 (upaklesha) | CORRECT |
| eight liberations (*vimoksha*) | glossary line 150 (ashta-vimoksha) | CORRECT |
| ground of meditative equipoise (*samahita-bhumi*) | glossary line 104 [see m-4 for deviation] | NEAR-CORRECT |
| five branches (*pañcāṅga*) | glossary line 615 | CORRECT |
| mental one-pointedness (*ekagrata*) | glossary line 229 | CORRECT — full phrase used, not abbreviation |
| five pure abodes | glossary line 124 (Akanishtha entry notes) | PARTIAL — collective term missing (see M-4) |
| Blessed One | glossary line 83 | CORRECT (NOT "World-Honored One") |
| sentient beings | glossary line 182 (sattva, 有情) | CORRECT in context — 33.16 and 33.17 use for 有情/sattva not 補特伽羅 |

---

## WATCHLIST CHECK (`the terminology watchlist`)

All watchlist items checked against sections 33.10–33.18:

| Watchlist Item | Status |
|---|---|
| Hsuan-tsang / Hsuan-chuang | NOT present — PASS |
| Maitreya as author | NOT present — PASS |
| pudgala untranslated in running text | NOT present — PASS |
| sentient being for 補特伽羅 | NOT an issue — "sentient being" used correctly for sattva contexts |
| vipassana (Pali) | NOT present — PASS |
| samatha (Pali) | NOT present — PASS |
| jhana (Pali) | NOT present — PASS |
| sutta (Pali) | NOT present — PASS |
| nibbana (Pali) | NOT present — PASS |
| khandha (Pali) | NOT present — PASS |
| defilements for 煩惱 | NOT present — "afflictions" used throughout — PASS |
| mental quiescence | NOT present — PASS |
| special insight | NOT present — PASS |
| aggregates without context | NOT present — PASS |
| absorptions for 靜慮 (dhyanas) | The word "absorptions" appears in the section heading "Two Absorptions Without Mind" (33.15) and body — but this refers to the 二無心定 (two mindless attainments), NOT 靜慮 (dhyanas). Correct usage; not a violation. PASS |
| one-pointedness abbreviation | "mental one-pointedness" used correctly in footnote line 174 — PASS |
| concentration for 三摩地 standalone | Line 258: **"Concentration"** is used as a formula-term heading for the second dhyana formula factor. This is quoting the formula word (定 = specific state), not 三摩地 standalone. The glossary (line 27) allows "concentration" for 定 when = specific state. The full compound "born of concentration" matches glossary line 613. PASS — not a violation. |

---

## SUMMARY OF REQUIRED ACTIONS

**Must fix before completion:**
1. **C-1**: Add five missing terms to glossary: *arana-jnana* (no-contention knowledge), *pranidhi-jnana* (power of aspiration), *pratisam-vid* (four analytical knowledges), *dvadasha-samjna* (twelve perceptions), *abhibhv-ayatana* (bases of mastery).

**Should fix:**
2. **M-2**: Add *parishuddha* / 清淨鮮白 to glossary as "pure and radiant."
3. **M-3**: Add `acitta-samapatti` / 二無心定 as collective entry; add note on `citta-caitta`.
4. **M-4**: Add five pure abode names with verified Sanskrit forms; add `shuddhavasika` collective entry.
5. **m-1**: Verify and correct `abhibhv-ayatana` Sanskrit form in footnote.
6. **m-3**: Add brief gloss for *dutula* or add to glossary.
7. **m-4**: Change "the concentrated ground (*samahita-bhumi*)" to "the ground of meditative equipoise (*samahita-bhumi*)" for glossary consistency.

**Editorial discretion:**
8. **M-1**: Consider whether *priti* in dhyana context should be "rapture" per Nanamoli standard, or whether "joy" is the project preference. Current rendering is not a violation.

---

## ADDITIONAL FINDINGS (Updated Re-Read)

### M-5 — "purified divine eye" — Rendering inconsistency within the section

**Severity:** Moderate
**Location:** Section 33.16, line 390
**Issue:** The body text at line 390 reads: "one achieves the knowledge of death and rebirth — the purified divine eye." The appositive "purified divine eye" is a different rendering from the established glossary term "knowledge of death and rebirth (*cyuty-upapatti-jnana*)" (glossary line 610, confirmed as the correct rendering for 死生智通). The footnote [^five_superknowledges] at line 400 correctly gives "knowledge of death and rebirth (*cyuty-upapatti-jnana-abhijna*, 死生智通)." The body text's appositional phrase "the purified divine eye" introduces "divine eye" (*divya-cakshus*, 天眼) as an alternative label — which, while found in some Abhidharma traditions, is not the registered rendering and is not in the glossary.

**Action required:** Either (a) remove the appositive "the purified divine eye" from the body text so it reads "one achieves the knowledge of death and rebirth — whereby one sees sentient beings dying and being reborn in states fortunate and unfortunate," or (b) add a footnote explaining that "purified divine eye" is the Chinese 清淨天眼 (if that is the Chinese source), add *divya-cakshus* to the glossary, and reconcile with the footnote's rendering. The current state creates a within-section inconsistency.

---

### M-6 — Three "supreme holy superknowledges" lack Sanskrit

**Severity:** Moderate
**Location:** Section 33.16, line 394
**Issue:** "the power of transforming things, the power of creating things, and the power of conviction" — these three are listed as "supreme holy superknowledges" without any Sanskrit parentheticals, even though the immediately following terms (*arana-jnana*, *pranidhi-jnana*, *pratisam-vid*) do have them. These likely correspond to *riddhi-vibhavana* (power of transformation), *nirmana-rddhi* (power of creation), and *adhimoksha-bala* or similar (power of conviction). Without Sanskrit, these three unnamed powers cannot be traced or verified against the Chinese source.

**Action required:** Identify the Chinese source for these three powers in T30.0470a (around the corresponding Taisho passage for 33.16) and supply appropriate Sanskrit or at minimum Chinese character glosses. Add to glossary if they prove to be technical terms.

---

### m-6 — `vijnanananty-ayatana` triple-n form — Internal note

**Severity:** Minor (documentation)
**Location:** Section 33.14, line 316 and glossary line 617
**Issue:** Both glossary and translation use *vijnanananty-ayatana* (triple-n). The standard Sanskrit for this term is *vijñānānantya-āyatana* (from vijñāna + ānantya). In simplified romanization without diacriticals, this would be *vijnanantya-ayatana* (double-n), not triple-n. The triple-n appears to be a consistent project-wide convention (glossary line 617 matches the translation), so this is internally consistent. However, a scholar comparing against Shukla's Sanskrit edition or Lévi's edition would expect double-n.

**Action:** No change needed for internal consistency, but recommend adding a note to the glossary entry: "Romanization: *vijnanananty* reflects Xuanzang's Chinese 識無邊 (vijnana + ananta/anantya); scholarly editions use *vijñānānantya* (double-n after vijnana)."

---

### m-7 — *pañca-abhijña* vs. *abhijna* diacritical inconsistency

**Severity:** Minor
**Location:** Footnote [^five_superknowledges], line 400: `(*pañca-abhijña*)` vs. body text and glossary using `*abhijna*`
**Issue:** The footnote uses the diacritical form *abhijña* (with ñ) while the glossary (line 610) and all body-text uses employ *abhijna* (without diacritical). Internal inconsistency.

**Action:** Standardize footnote to *abhijna* (the established project-wide romanization convention for this term).

---

### m-8 — *samjña-vedayita-nirodha* vs. *samjna-vedayita-nirodha* diacritical inconsistency

**Severity:** Minor
**Location:** Footnote [^two_absorptions], line 354: `(*samjña-vedayita-nirodha*)` vs. glossary line 155: `samjna-vedayita-nirodha`
**Issue:** The footnote uses *samjña* (with diacritical ñ) while the glossary uses *samjna*. Same issue as m-7: the project's romanization convention drops diacriticals (*samjna*, not *samjña*).

**Action:** Change footnote to *samjna-vedayita-nirodha* per glossary convention.

---

## CONSOLIDATED PRIORITY ACTION LIST (All findings combined)

### Critical / Must fix before marking complete:
1. **C-1** Add five missing terms to glossary: *arana-jnana*, *pranidhi-jnana*, *pratisam-vid*, *dvadasha-samjna*, *abhibhv-ayatana* (bases of mastery). These appear in 33.16 running text or footnotes without glossary backing.

### Moderate / Should fix:
2. **M-2** Add *parishuddha* / 清淨鮮白 to glossary as "pure and radiant."
3. **M-3** Add collective entry *acitta-samapatti* / 二無心定 to glossary; add note on *citta-caitta*.
4. **M-4** Add five pure abode names (Avrha, Atapa, Sudrsha, Sudarsana, Akanishtha already present) with verified Sanskrit forms; add *shuddhavasika* collective entry.
5. **M-5** Resolve "purified divine eye" / "knowledge of death and rebirth" inconsistency at line 390.
6. **M-6** Supply Sanskrit or Chinese glosses for "power of transforming things, creating things, power of conviction" at line 394.

### Minor / Fix if quick:
7. **m-1** Verify and correct *abhibhv-ayatana* Sanskrit form in footnote [^liberation_mastery].
8. **m-3** Add brief gloss for *dutula* ("a fine, light variety of Indian cotton") — either parenthetical or footnote.
9. **m-4** Change "concentrated ground (*samahita-bhumi*)" to "ground of meditative equipoise (*samahita-bhumi*)" for glossary consistency (line 394).
10. **m-7** Standardize *abhijña* → *abhijna* in footnote [^five_superknowledges].
11. **m-8** Standardize *samjña* → *samjna* in footnote [^two_absorptions].

### Editorial discretion:
12. **M-1** Consider *priti* as "rapture" vs. "joy" in dhyana context (Nanamoli standard vs. project preference). Current rendering not a violation.
