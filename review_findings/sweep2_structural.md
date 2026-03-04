# Structural Integrity Sweep — All Translation Files

Sweep date: 2026-03-03
Files checked: 00_copyright.md, 00_introduction.md, 00_abbreviations.md,
               fascicle_26_en.md through fascicle_33_en.md,
               00_methodology.md, 00_bibliography.md, build/metadata-print.yaml

---

## 1. HEADER HIERARCHY

### [Header-Skip] fascicle_26_en.md — Lines 310 and 432

Two locations jump from ### (level 3) directly to ##### (level 5), skipping #### entirely.

- Line 310: `### 26.5 Pervasive Objects of Meditation` → immediately `##### The Image with Discernment`
- Line 432: `### 26.6 Purifying-Conduct Objects: Impurity` → immediately `##### The Impurity Object`

**Impact:** Pandoc tolerates this but the HTML ToC and LaTeX hierarchy will reflect the gap. After build.py promotes all headings one level (### → ##, ##### → ####), the resulting ## → #### jump will still be one level too deep for strict accessibility conformance and EPUB navigation. Low severity for PDF; moderate for EPUB ToC.

### [Header-Skip] fascicle_27_en.md — Lines 42, 86, 268, 330, 422

Five locations jump from ### to #####, same pattern as fascicle_26.

- Line 42: `### 27.2 Element Differentiation` → `##### (1) The Earth Element`
- Line 86: `### 27.3 Mindfulness of Breathing` → `##### Types of Breath`
- Line 268: `### 27.4 Skillful Objects` → `##### (1) Skill in the Skandhas`
- Line 330: `### 27.5 Affliction-Purifying Objects` → `##### Worldly Path: Contemplation...`
- Line 422: `### 27.6 Four Types of Instruction` → `##### Instruction Replete with All Marks`

**Impact:** Same as fascicle_26 header issues above.

**Note:** Fascicles 28–33 use only levels 1, 2, 3 — no skips. The ### → ##### pattern is confined to fascicles 26–27 and appears to be a pre-existing structural decision (these subsections are named divisions within major sections). No action required if current rendering is acceptable; but a #### intermediate level per section would make the hierarchy valid.

---

## 2. FOOTNOTE REFERENCE / DEFINITION MATCHING

**All 8 fascicles: CLEAN — 1:1 match.**

| File | Unique refs | Unique defs | Status |
|------|-------------|-------------|--------|
| fascicle_26_en.md | 45 | 45 | OK |
| fascicle_27_en.md | 41 | 41 | OK |
| fascicle_28_en.md | 37 | 37 | OK |
| fascicle_29_en.md | 36 | 36 | OK |
| fascicle_30_en.md | 24 | 24 | OK |
| fascicle_31_en.md | 23 | 23 | OK |
| fascicle_32_en.md | 41 | 41 | OK |
| fascicle_33_en.md | 33 | 33 | OK |

No orphaned definitions and no references missing definitions across any file. No duplicate definitions found.

---

## 3. SECTION NUMBERING CONTINUITY

**All 8 fascicles: CLEAN — sequential, no gaps, no duplicates.**

| File | Range | Count |
|------|-------|-------|
| fascicle_26_en.md | 26.1–26.7 | 7 |
| fascicle_27_en.md | 27.1–27.6 | 6 |
| fascicle_28_en.md | 28.1–28.11 | 11 |
| fascicle_29_en.md | 29.1–29.17 | 17 |
| fascicle_30_en.md | 30.1–30.16 | 16 |
| fascicle_31_en.md | 31.1–31.11 | 11 |
| fascicle_32_en.md | 32.1–32.17 | 17 |
| fascicle_33_en.md | 33.1–33.18 | 18 |

---

## 4. HORIZONTAL RULE SEPARATORS

### [Missing-Sep] fascicle_28_en.md — Line 496

Section `### 28.11 The Four Foundations of Mindfulness` (line 496) is not preceded by a `---` separator. The `---` at line 480 is a mid-section break *within* 28.10, not a section terminator. Line 494 ends the 28.10 content; line 496 begins 28.11 with no intervening `---`.

**Context:**
```
494: (eightfold noble path list ends)
495: (blank)
496: ### 28.11 The Four Foundations of Mindfulness
```

**Impact:** In PDF output, build.py strips `---` from fascicle content, so this has no visual effect on print. In EPUB/HTML, pandoc uses `---` as `<hr>`, so 28.11 will lack the visual section break. Low severity for print; noticeable for digital.

All other `###` section boundaries across all 8 fascicles have correct `---` separators.

---

## 5. TAISHO REFERENCE FORMAT

**All Taisho references across all 8 fascicles: CORRECTLY FORMATTED.**

All `[T30.XXXXaXX]` references match the expected pattern `[T30.\d{4}[abc]\d{2}]`. No malformed references found.

### [Info] Taisho references absent from 31 section starts

The following sections do not begin with a Taisho reference — the text flows directly from the preceding section without a new page/column marker. This is not a formatting error (these sections continue within the same Taisho page/column as the preceding section), but is noted for completeness:

Fascicle 26: 26.7
Fascicle 27: 27.3
Fascicle 29: 29.2, 29.3, 29.4, 29.5, 29.6, 29.7, 29.8, 29.10
Fascicle 30: 30.11, 30.12, 30.14
Fascicle 31: 31.2, 31.3, 31.4, 31.6, 31.7, 31.10
Fascicle 32: 32.3, 32.13, 32.14, 32.15
Fascicle 33: 33.5, 33.6, 33.7, 33.8, 33.9, 33.11, 33.12, 33.14

No action required unless editorial policy requires a Taisho ref at every section break.

---

## 6. MARKDOWN SYNTAX

### [Clean] Bold markers (**): No unmatched pairs found in any file.
### [Clean] Italic markers (*): No unmatched pairs found in any file.
### [Clean] Footnote parentheses: All footnote definitions have balanced parentheses.
### [Clean] No stray backslashes detected.
### [Clean] No garbled encoding (replacement characters U+FFFD): All files are clean UTF-8.

Note: em-dash characters (U+2014, `—`) appear throughout, correctly encoded as UTF-8 bytes 0xE2 0x80 0x94. These displayed oddly in one terminal but are valid.

### [Info] HTML entity in 00_copyright.md — Line 3

`00_copyright.md` line 3 contains `&copy;` (HTML entity). This is benign: build.py replaces the entire copyright file with generated LaTeX for the print build, so `&copy;` never reaches XeLaTeX. For EPUB, pandoc renders `&copy;` correctly as ©. No action required.

---

## 7. EMPTY SECTIONS

**No empty sections found.** All `###` section headers have content before the next header or end of file.

---

## 8. VERSE FORMATTING (UDDANA BLOCKQUOTING)

All verse passages verified as correctly blockquoted with `>`.

- fascicle_26: The Opening Questions summary verse (section 26.1) is correctly blockquoted (line 27–30).
- fascicle_30: The Third Yoga Place uddana (section 30.1) is correctly blockquoted.
- fascicle_31: The Intermediate Summary Verse (section 31.10, `### 31.10 Intermediate Summary Verse`) is correctly blockquoted — the verse begins immediately with `>` at the first content line.
- fascicle_33: The Fourth Yoga Place uddana (section 33.1) is correctly blockquoted.

Fascicles 27–29 and 32 contain no standalone uddana verses and no "summary verse says" phrases. No unblockquoted verse content found.

---

## 9. TABLE FORMATTING

**The abbreviations table (00_abbreviations.md) is correctly formed.**

- Header row at line 5: `| Abbreviation | Full Title |`
- Separator at line 6: `|-------------|-----------|`
- 7 data rows (lines 7–13), all with consistent 2-column structure.

No table syntax errors detected.

---

## 10. BUILD METADATA

### metadata-print.yaml: All referenced assets verified as existing.

| Asset | Status |
|-------|--------|
| build/print-template.tex | EXISTS |
| build/metadata-print.yaml | EXISTS |
| build/metadata.yaml | EXISTS |
| build/epub.css | EXISTS |
| build/site-template.html | EXISTS |
| build/site-style.css | EXISTS |
| All 8 fascicle translation files | EXISTS |
| All 5 front matter files | EXISTS |
| All 3 back matter files | EXISTS |
| translation/00_glossary.md | EXISTS |

### Font availability

`metadata-print.yaml` specifies `mainfont: "EBGaramond"`. The font files `EBGaramond-Regular.ttf`, `EBGaramond-Bold.ttf`, `EBGaramond-BoldItalic.ttf`, `EBGaramond-Italic.ttf` are all present in `build/fonts/`. The print-template.tex correctly references EBGaramond via fontspec.

`CJKmainfont: "Microsoft YaHei"` is a system font (not a local file). It must be installed on the build machine. Not verifiable via file check alone — flag for deployment documentation.

### `\backmatter` macro

build.py injects `\backmatter` as raw LaTeX into the first back matter file (00_abbreviations.md). `\backmatter` is NOT defined in `print-template.tex` because it is a built-in command of the LaTeX `book` documentclass (specified in `metadata-print.yaml` as `documentclass: book`). This is correct and will function without issues.

---

## SUMMARY TABLE

| Check | Result |
|-------|--------|
| Header hierarchy | 7 skips (### → #####) in fascicles 26–27 only |
| Footnote ref/def matching | CLEAN — all 8 fascicles |
| Section numbering | CLEAN — all 8 fascicles |
| Horizontal rules | 1 missing: 28.11 in fascicle_28 |
| Taisho format | CLEAN — all correctly formatted |
| Bold/italic markers | CLEAN |
| Encoding/garbled chars | CLEAN |
| Empty sections | CLEAN |
| Verse blockquoting | CLEAN — all verified |
| Table syntax | CLEAN |
| Build file references | CLEAN — all files exist |

### Actionable issues (severity order):

1. **[Medium]** `fascicle_28_en.md` line 495: Missing `---` separator before `### 28.11`. Affects EPUB/HTML visual output. Add `---` between lines 495 and 496.

2. **[Low]** `fascicle_26_en.md` lines 310, 432 and `fascicle_27_en.md` lines 42, 86, 268, 330, 422: Header level skips from ### to #####. No build breakage, but technically invalid hierarchy. Consider adding `####` intermediate headers if EPUB accessibility compliance matters.

3. **[Info]** `CJKmainfont: "Microsoft YaHei"` requires the font to be installed as a system font on the build machine. Document this as a build prerequisite.

4. **[Info]** 31 sections lack Taisho references at their openings — these are continuation sections within the same Taisho page/column. No action required.
