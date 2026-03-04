# Final Source Verification Report
Date: 2026-03-03

## 1. Footnote Count

| File | Definitions |
|------|-------------|
| fascicle_26_en.md | 35 |
| fascicle_27_en.md | 38 |
| fascicle_28_en.md | 33 |
| fascicle_29_en.md | 35 |
| fascicle_30_en.md | 15 |
| fascicle_31_en.md | 13 |
| fascicle_32_en.md | 24 |
| fascicle_33_en.md | 25 |
| **TOTAL** | **218** |

PASS. Total matches expected count of 218.

## 2. Orphaned Footnotes

Checked all 8 fascicle files for:
- Footnote definitions `[^name]:` with no corresponding body reference `[^name]`
- Body references `[^name]` with no corresponding definition

Result: **No orphaned footnotes found.** All 218 definitions are referenced; all references have definitions.

## 3. Deprecated Terms

Searched all fascicle_*_en.md files for the full deprecated term list.

### Clean (zero matches):
- "defilements" — NONE
- "mental quiescence" — NONE
- "special insight" — NONE
- "Hsuan-tsang" / "Hsuan-chuang" — NONE
- "vipassana" — NONE
- "samatha" (standalone) — NONE
- "jhana" — NONE
- "nibbana" — NONE

### Requires review:

**"absorptions"** — 6 occurrences across fascicle_28_en.md and fascicle_33_en.md. Verdict:
- fascicle_28, line 27: "meditative attainments and absorptions (*samapatti*)" — legitimate: gloss of Sanskrit *samapatti*, not standalone rendering of 靜慮 (dhyana). PASS.
- fascicle_33, lines 23, 30, 326, 336: all refer to "two absorptions without mind" (*acitta-samapatti* = 無心定/無想定/滅盡定) — a technically distinct category from the four dhyanas (靜慮). PASS. These are correct: the referent is *samapatti*, not dhyana.

Conclusion: No deprecated "absorptions" usage found. All occurrences refer to *samapatti* (meditative attainments), not to 靜慮 (dhyanas). The watchlist rule applies to 靜慮 rendered as "absorptions"; none present.

**"Maitreya"** — 1 occurrence in fascicle_26_en.md, line 9:
> [^attr]: The Chinese text attributes this work to Maitreya Bodhisattva (彌勒菩薩說). Modern scholarly consensus attributes the Sravakabhumi to Asanga.

Verdict: PASS. This is a footnote explicitly noting and correcting the Chinese attribution. Maitreya is not used as the author in the translation; the footnote itself redirects to Asanga. The usage conforms to the watchlist intent.

## 4. Methodology Footnote Count

translation/00_methodology.md, line 51:
> "218 scholarly footnotes providing doctrinal context and cross-references"

PASS. Correctly states 218.

## 5. README Footnote Count

README.md, line 13:
> "103 sections, with 218 scholarly footnotes providing doctrinal context, cross-references, and canonical parallels"

PASS. Correctly states 218.

## 6. Turqoisehex References

Searched translation/ and README.md for "turqoisehex".

Result: **Zero matches.** PASS.

---

## Summary

| Check | Result |
|-------|--------|
| Footnote count (218) | PASS |
| Orphaned footnotes | PASS — none |
| Deprecated terms | PASS — none in active translation text |
| Methodology "218" | PASS |
| README "218" | PASS |
| Turqoisehex | PASS — zero |

**All checks pass.** Translation source files are consistent and clean.
