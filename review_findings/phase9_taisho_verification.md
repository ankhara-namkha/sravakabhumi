# Taisho Reference Verification: Phase 9

## Summary

Verification of `translation/00_contents.md` Table of Contents against actual Taisho references in translation files (fascicles 26-33).

**Status:** MULTIPLE CRITICAL MISMATCHES FOUND

- ToC entries: 103 sections across 8 fascicles
- Actual translation file sections: 90 sections
- Mismatches identified: 57
- Missing references in ToC: 13 sections with no Taisho ref
- Missing implementations: 13 sections in ToC not yet in translation files

---

## Critical Issues

### 1. MISSING TAISHO REFERENCES IN ToC (13 sections)

These sections are listed in the ToC but have NO Taisho reference assigned:

| Section | Title |
|---------|-------|
| 33.5 | Attention to Characteristics: The Six-Aspect Analysis of Desire |
| 33.6 | From Conviction to the Fruit: The Remaining Six Attentions |
| 33.7 | Functional Summary and Classification of the Seven Attentions |
| 33.8 | Extension to Higher Attainments and the Second Dhyana |
| 33.9 | Universal Coarse Aspects Across All Lower Grounds |
| 33.11 | Detailed Exposition of the Second Dhyana Formula |
| 33.12 | Detailed Exposition of the Third Dhyana Formula |
| 33.14 | The Four Formless Attainments |

**Root cause:** These sections appear in ToC rows but the Taisho column is empty.

---

### 2. SECTIONS IN ToC NOT YET IN TRANSLATION FILES (13 sections)

These sections are documented in the ToC with Taisho references but have NOT been translated/created in the actual files:

| Section | ToC Taisho | Status |
|---------|-----------|--------|
| 27.3 | T30.0434b26 | Not found |
| 27.7 | (if it exists) | Not found |
| 29.2 | T30.0444a01 | Not found |
| 29.4 | T30.0444b19 | Not found |
| 29.7 | T30.0444c28 | Not found |
| 29.10 | T30.0445b22 | Not found |
| 30.14 | T30.0451c03 | Not found |
| 31.2 | T30.0454c01 | Not found |
| 31.3 | T30.0455a21 | Not found |
| 31.6 | T30.0456a25 | Not found |
| 31.7 | T30.0456c01 | Not found |

These should be created in the translation files.

---

### 3. TAISHO REFERENCE MISMATCHES — Section-by-Section

All fasicles show discrepancies between ToC Taisho references and actual file references. Patterns observed:

**Fascicle 26 (6 mismatches):**
- 26.2: ToC says T30.0424a23 → File has T30.0424a19 (off by 4 characters)
- 26.3: ToC says T30.0426a04 → File has T30.0425b20 (off by many lines)
- 26.4: ToC says T30.0428b08 → File has T30.0427a22
- 26.5: ToC says T30.0428b26 → File has T30.0427a24
- 26.6: ToC says T30.0431c03 → File has T30.0428c18
- 26.7: ToC says T30.0433b04 → File has MISSING (section not implemented)

**Fascicle 27 (6 mismatches):**
- 27.1: ToC says T30.0434a10 → File has T30.0430a07 (off by 4 pages)
- 27.2: ToC says T30.0434a25 → File has T30.0430a14
- 27.3: ToC says T30.0434b26 → File has MISSING (not implemented)
- 27.4: ToC says T30.0435a01 → File has T30.0433c01
- 27.5: ToC says T30.0435b21 → File has T30.0434b14
- 27.6: ToC says T30.0435c03 → File has T30.0435b23

**Fascicle 28 (appears mostly correct in spot checks):**
- All tested references (28.1–28.11) match or are present

**Fascicle 29 (13 mismatches):**
- 29.1: ToC says T30.0443a04 → File has T30.0442a26
- 29.2, 29.4, 29.7: Not found in file (missing implementations)
- 29.9: ToC says T30.0445b06 → File has T30.0444c29
- 29.10: Not found in file (missing implementation)
- 29.11: ToC says T30.0446a18 → File has T30.0445b27 (off by ~20 lines)
- 29.12–29.17: All have discrepancies (typically off by 1-3 characters or multiple lines)

**Fascicle 30 (8 mismatches):**
- 30.3: ToC says T30.0448c14 → File has T30.0448c13 (off by 1)
- 30.4: ToC says T30.0449a02 → File has T30.0449a10 (off by 8)
- 30.7: ToC says T30.0449c22 → File has T30.0449c15 (off by 7)
- 30.11: ToC says T30.0451a22 → File has T30.0451b13
- 30.14: Not found (missing implementation)

**Fascicle 31 (5 mismatches):**
- 31.2, 31.3, 31.6, 31.7: Not found (missing implementations)
- 31.10: ToC says T30.0458b07 → File has T30.0458b23

**Fascicle 32 (10 mismatches):**
- 32.2: ToC says T30.0459c20 → File has T30.0459c01
- 32.5: ToC says T30.0461a01 → File has T30.0460c01
- 32.6: ToC says T30.0461a17 → File has T30.0461a01
- 32.8: ToC says T30.0462a01 → File has T30.0461c01
- 32.9: ToC says T30.0462b11 → File has T30.0462a01
- 32.10–32.15, 32.17: Multiple discrepancies (off by 1 column to several lines)

**Fascicle 33 (8 empty or mismatched entries):**
- 33.5–33.9, 33.11–33.12, 33.14: Missing Taisho refs in ToC
- 33.14 in File has T30.0468c05 but ToC is blank

---

## Root Causes

1. **ToC created without verifying against actual files** — The Table of Contents was created (probably from planning notes or source text) without cross-checking against the actual translation files where Taisho references are embedded.

2. **Fascicles 26–27 references are systematically off** — Early fascicles show consistent displacement, suggesting the ToC may have been built from a different edition or with misaligned source counting.

3. **Sections 29, 31, 32 have missing implementations** — Several sections listed in ToC do not yet exist as ### headers in the translation files.

4. **Section 33 lacks Taisho refs** — The final sections (33.5–33.9, 33.11–33.12, 33.14) are listed but have no Taisho column entries in the ToC.

---

## Recommendations

1. **For sections in files with wrong Taisho refs:** Extract the actual Taisho ref from each section heading (the `[T30.XXXxXX]` immediately following `### section.number`), and update the ToC.

2. **For missing implementations:** Verify against the Chinese source and TRANSLATION_PLAN.md whether these sections are actually planned/completed. If completed, update the translation files to include section headers. If not yet translated, remove from ToC or mark as "In Progress."

3. **For missing ToC Taisho refs (Fascicle 33):** Check the Chinese source text to assign correct Taisho references to sections 33.5–33.9, 33.11–33.12, 33.14.

4. **Verification process:** After ToC correction, re-run this same check to confirm all references align.

---

## Affected Files

- `translation/00_contents.md` — Requires update
- `translation/fascicle_26_en.md` through `translation/fascicle_33_en.md` — Most file refs are correct; missing sections need implementation
- `source/chinese/fascicle_26.md` through `fascicle_33.md` — For reference during correction

---

**Verification Date:** 2026-03-02
**Verified by:** Taisho Reference Cross-Check Agent
**Next Step:** Editor-in-chief to synthesize findings and apply corrections to ToC and translation files.
