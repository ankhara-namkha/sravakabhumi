# Terminology Review — Fascicle 31, Sections 31.5–31.7
## Agent T (Terminology) Findings

**Scope:** Section 31.5 ("Furthermore, there are nine approaches...") through section 31.7 conclusion ("This constitutes the teaching on mental one-pointedness")
**Reviewer role:** Systematic cross-reference of all technical terms against MASTER_GLOSSARY.md and the terminology watchlist watchlist.

---

## CRITICAL FLAG (Category 2): Term Rendered Differently from Glossary

### 1. "desire-conduct" vs. glossary "greed-conduct" — SEVERITY: CRITICAL

**Location:** Section 31.5, first paragraph of approach (1) Appropriate Practice:
> "If one is of the **desire-conduct** type, one settles the mind on impurity."

**Glossary entry:**
| 貪行 | raga-carita | **greed-conduct** | greed-conduct |

**Watchlist status:** Not listed in watchlist explicitly, but the rendering conflict is unambiguous.

**Cross-fascicle evidence:** All other fascicles consistently use "greed-conduct":
- Fascicle 26: "greed-conduct (*raga-carita*)" — multiple instances
- Fascicle 27: footnote at 27:482 explicitly enumerates "(1) **greed**-conduct, (2) aversion-conduct, (3) delusion-conduct..."
- Fascicle 30: "Those of **greed**-conduct (*raga-carita*)..."

**Problem:** "desire-conduct" is a translation of 欲行 (desire/kama), not 貪行 (greed/raga). These are distinct concepts in the Yogacara framework. Using "desire" for 貪 introduces a doctrinal error, conflating two different Chinese/Sanskrit terms.

**Required fix:** Change "desire-conduct" → "greed-conduct" in section 31.5.

---

## FLAG (Category 2): Term Rendered Differently from Glossary

### 2. "yogachara teachers" vs. glossary "yogin" — SEVERITY: MODERATE

**Location:** Section 31.5, approach (3) Non-inverted Practice:
> "One follows the instruction of accomplished **yogachara** teachers..."

**Glossary entry:**
| 瑜伽師 | yogin / yogacara | **yogin**, practitioner | **yogin** |

The "Preferred in text" column specifies **yogin**, not "yogachara." The term "yogachara" is also used in footnotes (e.g., fn [^no_agent]: "core **Yogacara** thesis") and in fn [^painter]: "**Yogacara** system" — those are acceptable as proper-noun references to the philosophical school. But 瑜伽師 in running text should render as "yogin" per the glossary.

**Required fix:** "accomplished yogachara teachers" → "accomplished yogin teachers" or "accomplished yogins" per context.

---

## FLAG (Category 1): Term Not in Glossary

### 3. "tranquil concentration" — SEVERITY: MODERATE

**Location:** Section 31.7, approach (7) Insatiable Practice:
> "never resting content with a small measure of **tranquil concentration** and losing heart midway"

**Glossary search:** No entry for "tranquil concentration" as a compound. The underlying Chinese is likely 三摩地 (samadhi) or possibly 奢摩他 (shamatha). The glossary mandates "samadhi" for 三摩地 (and the watchlist flags "concentration (for 三摩地 standalone)" → must use samadhi). If the Chinese here is 三摩地, this rendering violates the watchlist.

**Note:** The phrase may be intentionally paraphrastic (i.e., "a small measure of tranquil concentration" as a descriptive rendering). However, if the underlying term is 三摩地 or 定, it should be rendered as "samadhi" per glossary. Flagged for source fidelity agent to verify the Chinese term.

**Possible required fix:** "tranquil concentration" → "samadhi" (if underlying Chinese is 三摩地 or 定).

### 4. "sign-following mode," "investigation-following mode," "examination-following mode," "vipashyana mode" — SEVERITY: MINOR

**Location:** Section 31.7, approach (9) Correct Practice:
> "Through the **sign-following mode**, the **investigation-following mode**, the **examination-following mode**, and the **vipashyana mode**."

**Glossary search:** No entries found for these four mode-names as a compound set. The glossary has:
- 四種慧行 | "four modes of wisdom-practice" (but names the four as: correct discernment, thorough discernment, comprehensive investigation, comprehensive examination)
- Individual entries: 尋 = vitarka / examination; 伺 = vichara / investigation; 相 = nimitta / sign

The four mode-names in section 31.7 ("sign-following," "investigation-following," "examination-following," "vipashyana") do not match the glossary's four modes of wisdom-practice. Either these are a different fourfold set requiring their own glossary entry, or there is a translation inconsistency. The glossary entry 四種慧行 lists four modes by their function (discernment, investigation, examination) — the present translation labels them by what is "followed" (sign, investigation, examination, vipashyana). These may be distinct frameworks, but neither the glossary nor a footnote clarifies this.

**Action:** Flagged for doctrinal/source review. If these four modes are the same as 四種慧行, the names should be harmonized with the glossary rendering. If a distinct set, add to glossary.

### 5. "five types of clearing" terminology — SEVERITY: MINOR

**Location:** Section 31.7, approach (9) Correct Practice:
> "(1) internally collecting the mind, (2) non-attending attention, (3) redirected attention, (4) antidote attention, and (5) signless-realm attention"

**Glossary search:** None of these five terms appear in the glossary. These are technical terms in the Yogacara meditation system and should be glossary entries with their Chinese source terms. Particularly "signless-realm attention" (likely 無相界作意) and "non-attending attention" (likely 不作意) are standard technical terms. Their absence from the glossary is a gap.

**Action:** Add these five terms to the glossary with Chinese source terms and Sanskrit equivalents where available.

---

## FLAG (Category 5): Missing First-Use Glosses

### 6. *adhimoksha* — first use in section 31.7, no English gloss

**Location:** Section 31.7, approach (9) Correct Practice:
> "One repeatedly generates resolute confidence (*adhimoksha*) toward the object..."

**Glossary entry:** 勝解 | adhimoksha | **resolute confidence, conviction** | resolute confidence

The text provides the Sanskrit in parentheses but not the English gloss. The standard first-use pattern per the glossary conventions is "English rendering (Sanskrit)". Here the pattern is inverted: the Sanskrit is provided but the English is already in front of it ("resolute confidence (*adhimoksha*)"), which actually satisfies the spirit of the convention. However, the glossary specifies "English rendering (Sanskrit)" — the current usage is compliant.

**Status:** ACCEPTABLE — the English "resolute confidence" precedes the Sanskrit parenthetical. No fix needed.

### 7. *ekagrата* — rendering in conclusion, potential Unicode corruption

**Location:** Section 31.7 conclusion:
> "This constitutes the teaching on mental one-pointedness (*ekagrата*)."

**Glossary entry:** 一境性 | ekagrata | one-pointedness / mental one-pointedness | mental one-pointedness

**Issue:** The italicized Sanskrit "*ekagrата*" appears to contain a Cyrillic "т" (U+0442) rather than a Latin "t". This is likely a Unicode corruption artifact in the file — "*ekagrата*" should be "*ekagrata*". This is a typographic/encoding error that should be corrected.

**Required fix:** Correct "*ekagrата*" → "*ekagrata*" (ensure all characters are Latin).

---

## FLAG (Category 3): Watchlist Check — Deprecated Terms

**All watchlist terms checked against sections 31.5–31.7:**

| Watchlist Term | Status in 31.5–31.7 |
|---|---|
| Hsuan-tsang | Not present |
| Maitreya (as author) | Not present |
| pudgala (untranslated) | Not present |
| sentient being (for 補特伽羅) | Not present |
| vipassana (Pali) | Not present |
| samatha (Pali) | Not present |
| jhana (Pali) | Not present |
| sutta (Pali) | Present in footnote — see below |
| nibbana (Pali) | Not present |
| khandha (Pali) | Not present |
| defilements | Not present |
| mental quiescence | Not present |
| special insight | Not present |
| aggregates (without context) | Not present |
| absorptions (for 靜慮) | Not present |
| one-pointedness (standalone) | Present — see below |
| concentration (for 三摩地 standalone) | Possible issue — see flag #3 |

### Watchlist Item A: "sutta" (Pali form) in footnote — SEVERITY: MINOR

**Location:** Footnote [^urgency] in section 31.5:
> "The same countdown structure appears in the **Pali suttas** (e.g., AN 6.19–20)."

**Watchlist:** "sutta (Pali form)" → should be "sutra" per NTC convention.

**Note:** This is a footnote reference to Pali canonical texts, not a translation of a Chinese term. There is an argument that "Pali suttas" correctly identifies the textual tradition being cited (they ARE Pali suttas, not Sanskrit sutras). However, the watchlist is categorical: the project uses Sanskrit forms. "Pali sutras" would be technically awkward.

**Recommendation:** Either (a) change "Pali suttas" → "Pali sutras" for strict watchlist compliance, or (b) add a project-level exception for citations to Pali canonical literature. Currently flagged as a watchlist violation requiring editorial decision.

### Watchlist Item B: "one-pointedness" (standalone, abbreviated form) — SEVERITY: MINOR

**Location:** Section 31.7, footnote [^yoke]:
> "keep the mind tethered to **one-pointedness**."

**Watchlist:** "one-pointedness (for 心一境性)" → must use "one-pointed mind / mental one-pointedness" (full phrase).

In the main text conclusion, the full phrase is used correctly: "the teaching on **mental one-pointedness** (*ekagrata*)". But the footnote uses the abbreviated "one-pointedness" alone.

**Required fix:** Footnote [^yoke]: "one-pointedness" → "mental one-pointedness" or "one-pointed mind."

---

## FLAG (Category 4): Pali Forms Used Instead of Sanskrit

### 8. "Pali suttas" — see Watchlist Item A above.

No other Pali forms detected in sections 31.5–31.7.

---

## Terms Verified as Correctly Rendered

The following terms were checked and found to match the glossary:

| Term Used | Glossary Entry | Status |
|---|---|---|
| shamatha | shamatha | CORRECT |
| vipashyana | vipashyana | CORRECT |
| samadhi | samadhi | CORRECT |
| bright category | shukla-paksha / bright category | CORRECT |
| dark category | krishna-paksha / dark category | CORRECT |
| bhikshus | bhikshu | CORRECT |
| bhikshunis | bhikshuni | CORRECT |
| upasakas | upasaka | CORRECT |
| aversion-conduct | dvesha-carita | CORRECT |
| delusion-conduct | moha-carita | CORRECT |
| pride-conduct | mana-carita | CORRECT |
| discursive-thought-conduct | vitarka-carita | CORRECT |
| thin-dust type | manda-rajas | CORRECT |
| nine stages of mental abiding | navavidha-citta-sthiti | CORRECT |
| resolute confidence (*adhimoksha*) | adhimoksha | CORRECT |
| sense restraint | indriya-samvara | CORRECT (in footnote [^yoke]) |
| mental one-pointedness | ekagrata | CORRECT (main text) |
| life faculty (*jivitindriya*) | jivitindriya | CORRECT (section 31.3, prior to scope) |
| appropriate practice | 相應加行 | CORRECT |
| habituated practice | 串習加行 | CORRECT |
| non-inverted practice | 無倒加行 | CORRECT |
| unslackened practice | 不緩加行 | CORRECT |
| timely practice | 應時加行 | CORRECT |
| comprehending practice | 解了加行 | CORRECT |
| insatiable practice | 無厭足加行 | CORRECT |
| not-abandoning-the-yoke practice | 不捨軛加行 | CORRECT |
| correct practice | 正加行 | CORRECT |
| pliancy | prashrabdhi | CORRECT (section 31.6/31.7) |
| discursive thought | vitarka | CORRECT |

---

## Summary of Issues

| # | Issue | Category | Severity | Action |
|---|---|---|---|---|
| 1 | "desire-conduct" should be "greed-conduct" (raga-carita) | (2) Wrong rendering | CRITICAL | Fix immediately |
| 2 | "yogachara teachers" should be "yogin teachers" per glossary preferred form | (2) Wrong rendering | MODERATE | Fix |
| 3 | "tranquil concentration" — possibly rendering 三摩地 as "concentration" against watchlist | (1) Not in glossary / watchlist risk | MODERATE | Verify Chinese; fix if 三摩地 |
| 4 | Sign-following / investigation-following / examination-following / vipashyana modes — no glossary entries; possible conflict with 四種慧行 | (1) Not in glossary | MINOR | Add to glossary; verify alignment with 四種慧行 |
| 5 | Five types of clearing — no glossary entries for any of the five terms | (1) Not in glossary | MINOR | Add to glossary |
| 6 | *ekagrата* — Cyrillic "т" in Sanskrit italics (Unicode corruption) | Typographic error | MODERATE | Fix encoding |
| A | "Pali suttas" in footnote — watchlist mandates "sutra" not "sutta" | (3) Deprecated/watchlist | MINOR | Editorial decision required |
| B | "one-pointedness" (standalone) in footnote [^yoke] — should be "mental one-pointedness" | (3) Watchlist abbreviated form | MINOR | Fix footnote |
