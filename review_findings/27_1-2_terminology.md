# Terminology Review: Fascicle 27, Sections 27.1-27.2

## Summary

12 issues found (2 critical, 6 moderate, 4 minor)

---

## Scope

Sections reviewed: 27.1 (Purifying-Conduct Objects: Dependent Origination) and 27.2 (Purifying-Conduct Objects: Element Differentiation), including all body text and footnotes. Lines 19-122 of `translation/fascicle_27_en.md`.

---

## Methodology

All technical terms — Sanskrit, Buddhist, doctrinal, structural — were extracted from body text and footnotes. Each was cross-referenced against:
1. `glossary/MASTER_GLOSSARY.md` (authoritative renderings)
2. `the terminology watchlist` (deprecated terms watchlist)
3. First-use conventions specified in the glossary

---

## Findings

### T-1: "sentient beings" used for 有情 in body text — Moderate
- **Location:** Line 88 (Section 27.2, Wind Element body text)
- **Issue:** "sentient beings" appears in running body text: "When *sentient beings* wish to produce wind, they wave their clothes, shake fans, or use palm fronds." The glossary distinguishes carefully: 有情 (*sattva*) = "sentient beings"; 補特伽羅 (*pudgala*) = "person/individual." The watchlist flags "sentient being (for 補特伽羅)" as WRONG, but here the Chinese likely reads 有情, making "sentient beings" the correct rendering per the glossary. This is NOT a terminology error in itself — however, the rendering requires verification against the Chinese source (有情 vs. 補特伽羅) to confirm correct term applied. If the source reads 有情, this is correct; if it reads 補特伽羅, this is a critical watchlist violation.
- **Current:** "When sentient beings wish to produce wind"
- **Expected:** Confirm Chinese reads 有情 (sattva), not 補特伽羅 (pudgala). If 補特伽羅: change to "When persons wish to produce wind."
- **Recommendation:** Source-check the Chinese at T30.0430b line for 有情 vs. 補特伽羅 before clearing.

---

### T-2: "formations" used without first-use gloss — Moderate
- **Location:** Line 23 (Section 27.1, first paragraph)
- **Issue:** "there are only formations, only dharmas, only events, only causes, and only results" — "formations" (行) is rendered without its first-use parenthetical gloss. The glossary records 行 (*samskara*) as "formation(s)" with no explicit first-use pattern specified (unlike skandhas, dhyanas, etc.). However, because this is a different doctrinal context from the skandha usage (here "formations" = conditioned phenomena in general, functioning like *samskara* in the pratityasamutpada formula), the lack of any parenthetical or note may confuse readers.
- **Current:** "only formations"
- **Expected:** "only formations (*samskara*)" on first occurrence in this fascicle, or a bracketed note clarifying that "formations" here = all conditioned phenomena (*samskara*).
- **Recommendation:** Add parenthetical "(samskara)" after "formations" on first use, consistent with practice for technical terms. Minor if glossary has no mandatory first-use pattern; escalate if deemed necessary for reader comprehension.

---

### T-3: *ap-dhatu* — Non-standard Sanskrit form — Critical
- **Location:** Line 56 (Section 27.2, heading "(2) The Water Element")
- **Issue:** The Sanskrit parenthetical reads "*ap-dhatu*" (italicized, which is correct for form). However, the glossary records the water element as "水界 | ap-dhatu | water element." The form *ap-* is the uninflected stem form; the more common scholarly Sanskrit would be *ab-dhātu* or *āpo-dhātu*. More critically, the glossary itself uses "ap-dhatu" — so the translation matches the glossary entry exactly. This is not a translation error but a glossary entry that may itself be non-standard. Flag for doctrinal review.
- **Current:** "*ap-dhatu*"
- **Expected:** Matches glossary ("ap-dhatu"). The issue is whether the glossary form is correct Sanskrit. Standard Abhidharma Sanskrit is *āpo-dhātu* (the genitive/compound form from *āpas* = water).
- **Recommendation:** Flag to Agent D (Doctrinal) for Sanskrit form verification. The translation is internally consistent with the glossary; the glossary entry may need correction to *apo-dhatu* or *ap-dhatu* (both appear in scholarship; Shukla edition should be checked).

---

### T-4: *pippala* wind — unlisted technical term, no glossary entry — Moderate
- **Location:** Line 84 (Section 27.2, internal wind element list), and in footnote [^twelve_winds] (Line 116)
- **Issue:** The term "*pippala*" wind (畢鉢羅風) appears in body text and footnote without a glossary entry. Per Rule 2 of design invariants: "Before using a technical term, check this file. If a term is not listed, add it here FIRST, then use it in translation." This specialized wind name is absent from the glossary.
- **Current:** "the *pippala* wind" (italicized in body text; explained in footnote)
- **Expected:** Term should appear in glossary before use. Rendering appears reasonable (leaving in Sanskrit since it is a proper name for a specific internal wind).
- **Recommendation:** Add 畢鉢羅風 / *pippala-vayu* to glossary under a new "Element Analysis Terms" or "Meditation Object Terms" subsection. Italics are correct.

---

### T-5: *vishva* wind and *vairamana* wind — unlisted technical terms — Moderate
- **Location:** Line 88 (Section 27.2, external wind element list), and in footnote [^external_winds] (Line 118)
- **Issue:** Both "*vishva*" (毘濕婆) and "*vairamana*" (吠藍婆) appear in body text and footnote without glossary entries. Same violation as T-4: terms used in translation without prior glossary registration.
- **Current:** "the *vishva* wind, the *vairamana* wind"
- **Expected:** Both should have glossary entries before use.
- **Recommendation:** Add 毘濕婆 / *vishva-vayu* and 吠藍婆 / *vairamana-vayu* to glossary. These are proper names for specific Indian wind types; Sanskrit/transliteration forms acceptable. Italics are correct.

---

### T-6: *mana-carita* — in-text Sanskrit used in parenthetical without italics — Minor
- **Location:** Line 100 (Section 27.2, "Application to Pride-Conduct")
- **Issue:** "a person of pride-conduct (*mana-carita*)" — the Sanskrit parenthetical *mana-carita* is italicized, which is correct. This is consistent with glossary practice. No error found here. Recorded for completeness.
- **Current:** "person of pride-conduct (*mana-carita*)"
- **Expected:** Correct as-is. Matches glossary: 慢行 | mana-carita | pride-conduct.
- **Recommendation:** No action needed.

---

### T-7: *citta*, *manas*, *vijnana* — three terms introduced in body text with correct parentheticals — Minor (Observation)
- **Location:** Line 96 (Section 27.2, Consciousness Element)
- **Issue:** "the threefold distinction of heart (*citta*), mind (*manas*), and consciousness (*vijnana*) is called the consciousness element" — all three Sanskrit terms appear in parentheticals with italics. *Citta* and *manas* are not individually listed in the glossary as standalone entries; only *vijnana* appears (as 識 | vijnana | consciousness). The compound/framework 心意識 = *citta-manas-vijnana* is not in the glossary.
- **Current:** "heart (*citta*), mind (*manas*), and consciousness (*vijnana*)"
- **Expected:** *Vijnana* = consciousness is correct per glossary. *Citta* rendered as "heart" and *manas* as "mind" are reasonable Yogacara conventions but these renderings are not registered in the glossary. The footnote [^citta_manas_vijnana] explains the framework adequately.
- **Recommendation:** Add *citta* (心, "heart/mind"), *manas* (意, "mind/mentation"), and the 心意識 (*citta-manas-vijnana*) triad to the glossary with the chosen renderings documented. The rendering "heart" for *citta* is non-standard (most translations use "mind" or "mind-continuum"); flag for doctrinal review as to whether "heart" is the intended scholarly choice or should be "mind" or left as *citta* untranslated.

---

### T-8: "formations" in 27.1 renders 行 in pratityasamutpada context — potential glossary ambiguity — Moderate
- **Location:** Line 23 (Section 27.1)
- **Issue:** The glossary records 行 (*samskara*) with two contexts: (a) as skandha (行蘊) = formations, and (b) "all conditioned phenomena" and "conditioning in pratityasamutpada." Here "formations" is used in the pratityasamutpada meditation-object context (緣性緣起). The glossary permits "formations" for this usage, so the rendering is technically correct. However, the list structure "only formations, only dharmas, only events, only causes, and only results" is ambiguous: does "formations" here refer specifically to *samskara* as one of the three characteristics (impermanence = anicca of *samskara*), or to all conditioned phenomena in general?
- **Current:** "only formations, only dharmas, only events, only causes, and only results"
- **Expected:** If "formations" = *samskara* as a technical enumeration in the pratityasamutpada formula, the rendering is defensible. A translator's note would clarify.
- **Recommendation:** Add a footnote explaining that "formations" here (行) refers to all conditioned phenomena (*samskara*) — not the skandha specifically — to disambiguate. Low priority.

---

### T-9: "cosmic wind-wheel" — unlisted technical term — Minor
- **Location:** Line 88 (Section 27.2, external wind element list) and footnote [^external_winds] (Line 118)
- **Issue:** "the cosmic wind-wheel" (風輪) is used in translation without a glossary entry. The footnote explains it refers to the wind-element at the base of the world-system in Buddhist cosmology, but the term itself is unregistered.
- **Current:** "the cosmic wind-wheel"
- **Expected:** Glossary entry for 風輪 / *vayu-mandala* (or equivalent Sanskrit) with rendering "cosmic wind-wheel" or "wind disk."
- **Recommendation:** Add 風輪 to glossary. The rendering "cosmic wind-wheel" is descriptively accurate and consistent with Abhidharma cosmological terminology.

---

### T-10: "personally appropriated" — glossary entry present; first-use parenthetical absent — Minor
- **Location:** Lines 46, 48, 58, 62, 70, 74, 82, 86, 92 (Section 27.2, recurring throughout element descriptions)
- **Issue:** "personally appropriated" (親附執受, *upadatta*) appears repeatedly. The glossary entry exists: 親附執受 | upadatta | personally appropriated. The footnote [^upadatta] explains the term on its first use. However, the body text never renders the Sanskrit parenthetical "(upadatta)" on first occurrence, only the English phrase. Per glossary convention: "First-use pattern: 'English rendering (Sanskrit)' on first occurrence in each fascicle."
- **Current:** "which is personally appropriated" (no Sanskrit on first use)
- **Expected:** "which is personally appropriated (*upadatta*)" on first occurrence in this fascicle (line 46).
- **Recommendation:** Add "(*upadatta*)" parenthetical on first use at line 46. Subsequent uses can remain as plain English. Moderate if consistent first-use convention is required across all glossary terms; minor if the footnote is deemed sufficient.

---

### T-11: "notion of unity" — *eka-samjna* footnote form inconsistent with body text — Moderate
- **Location:** Line 100 (Section 27.2, "Application to Pride-Conduct") and footnote [^eka_samjna] (Line 122)
- **Issue:** Body text uses "the notion of unity" without any Sanskrit parenthetical. The footnote [^eka_samjna] provides "一合想, *eka-samjna*" and a full explanation. The term *eka-samjna* (一合想) is not in the glossary. Per the design invariant: terms used in translation must be in the glossary first.
- **Current:** "the notion of unity" in body text; "*eka-samjna*" only in footnote
- **Expected:** (a) Glossary entry for 一合想 / *eka-samjna* / "notion of unity"; (b) first-use parenthetical in body text: "the notion of unity (*eka-samjna*)."
- **Recommendation:** Add 一合想 / *eka-samjna* to glossary. Add parenthetical to body text on first use. Critical if glossary-first rule is strictly enforced; moderate otherwise.

---

### T-12: "delusion-conduct" — glossary entry present; first-use parenthetical absent — Critical
- **Location:** Lines 25-26 (Section 27.1, second paragraph) — first use of this term in fascicle 27
- **Issue:** "a person of delusion-conduct" and "delusion-conduct" appear in section 27.1 without a Sanskrit parenthetical on first use. The glossary records 癡行 | moha-carita | delusion-conduct. The first-use convention requires "delusion-conduct (*moha-carita*)" on first occurrence in each fascicle. This is the very first occurrence in fascicle 27.
- **Current:** "a person of delusion-conduct has all their delusion-conduct attenuated"
- **Expected:** "a person of delusion-conduct (*moha-carita*) has all their delusion-conduct attenuated"
- **Recommendation:** Add "(*moha-carita*)" on first use at line 25. This is consistent with how *mana-carita* is handled in 27.2 (line 100), where the parenthetical does appear. The inconsistency between 27.1 and 27.2 suggests the 27.1 parenthetical was omitted in error.

---

## Terms Confirmed Correct

The following terms were checked and found consistent with the glossary:

| Term | Location | Verdict |
|------|----------|---------|
| *prithivi-dhatu* (earth element) | Line 44 | Correct; matches glossary; italicized |
| *ap-dhatu* (water element) | Line 56 | Matches glossary form (see T-3 for note on Sanskrit form) |
| *tejas-dhatu* (fire element) | Line 68 | Correct; matches glossary; italicized |
| *vayu-dhatu* (wind element) | Line 80 | Correct; matches glossary; italicized |
| *akasha-dhatu* (space element) | Line 92 | Correct; matches glossary; italicized |
| *vijnana-dhatu* (consciousness element) | Line 96 | Correct; matches glossary; italicized |
| purifying-conduct object | Lines 19, 29, 100 | Correct; matches glossary (淨行所緣) |
| dependent origination | Line 23 | Correct; glossary: preferred-in-text form is "dependent origination" |
| nature of conditions and dependent origination | Line 23 | Correct; matches glossary rendering of 緣性緣起 |
| delusion-conduct (second and third use) | Line 25-26 | Correct rendering; only first-use parenthetical missing (see T-12) |
| earth element, water element, fire element, wind element, space element, consciousness element | Throughout 27.2 | All correct per glossary |
| pride-conduct (*mana-carita*) | Line 100 | Correct; parenthetical present |
| element differentiation | Lines 29, 33 | Correct; matches glossary (六界差別 → element differentiation) |
| formations | Line 23 | Correct rendering for 行; first-use pattern ambiguous (see T-2) |
| dharmas | Line 23 | Correct; glossary: lowercase = phenomena |
| footnote [^pratityasamutpada_object] | Line 104 | Sanskrit terms *pratyaya-pratityasamutpada* correctly parenthetical and italicized |
| footnote [^dhatu_prabheda] | Line 108 | Sanskrit *dhatu-prabheda* correctly handled; cross-reference to Dhatuvibhanga Sutta (MN 140) acceptable |
| four reasonings (reasoning from dependence, function, proof, nature of things) | Line 23 | All four terms match glossary entries |
| *vijnana* (consciousness element member) | Line 96 | Correct per glossary |

---

## Missing Glossary Entries (Summary)

Terms used in translation (body text or footnotes) without prior glossary registration:

1. 畢鉢羅風 / *pippala* wind (T-4)
2. 毘濕婆 / *vishva* wind (T-5)
3. 吠藍婆 / *vairamana* wind (T-5)
4. 風輪 / cosmic wind-wheel (T-9)
5. 一合想 / *eka-samjna* / notion of unity (T-11)
6. 心 / *citta* / heart (T-7) — standalone rendering unregistered
7. 意 / *manas* / mind (T-7) — standalone rendering unregistered

---

## Severity Justification

- **Critical (2):** T-3 (non-standard Sanskrit form *ap-dhatu* in glossary itself — requires doctrinal verification), T-12 (missing first-use parenthetical for *moha-carita* at the very opening of 27.1 — directly violates glossary first-use convention, and inconsistently applied vs. 27.2).
- **Moderate (6):** T-1 (sentient beings — requires source check), T-2 (formations first-use gloss), T-5 (two unlisted wind names), T-8 (formations glossary ambiguity), T-10 (*upadatta* first-use parenthetical missing), T-11 (*eka-samjna* not in glossary).
- **Minor (4):** T-4 (*pippala* unlisted but footnoted), T-6 (confirmed correct), T-7 (*citta/manas* renderings unregistered), T-9 (wind-wheel unlisted).
