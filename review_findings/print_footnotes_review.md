# Print PDF Footnote/Endnote Formatting Review

File reviewed: `output/sravakabhumi_print.pdf` (252 pages, 8 fascicles)

---

## 1. Footnote Location: Page-Bottom, Not Endnotes

**Finding: Footnotes appear at the BOTTOM of each page where they are referenced, not collected as endnotes at fascicle ends.**

The build script (`build/build.py`, lines 107-167) relocates footnote definitions to the end of each fascicle in the markdown source. However, pandoc converts these to standard LaTeX `\footnote{}` commands, which render at the bottom of the page where the reference marker appears. The LaTeX template (`build/print-template.tex`, lines 87-95) explicitly acknowledges this:

> "The build script has already relocated footnote definitions to the end of each fascicle in the markdown, but pandoc still renders them at point of reference. This is actually the standard scholarly convention and works well for a text with moderate footnote density (avg ~40 per fascicle)."

The template uses `\usepackage[bottom]{footmisc}` to pin footnotes to the page bottom.

**Verdict: This is correct behavior for a scholarly translation of this type.** Page-bottom footnotes are the standard for academic/scholarly Buddhist translations (Nanamoli, Bodhi, etc.). The build script's relocation step is not wasted -- it serves to namespace footnote IDs with fascicle prefixes (e.g., `f27_1`) to avoid collisions when pandoc processes all fascicles in a single pass.

---

## 2. Footnote Numbering: Restarts at 1 Per Fascicle

**Finding: Footnote numbering correctly restarts at 1 for each fascicle.**

Verified across all eight fascicles:

| Fascicle | Start Page | First FN# | Last FN# (approx) |
|----------|-----------|-----------|-------------------|
| 26 | 9 | 1 | 53 |
| 27 | 41 | 1 | ~48 |
| 28 | 73 | 1 | ~43 |
| 29 | 109 | 1 | ~40 |
| 30 | 143 | 1 | ~28 |
| 31 | 167 | 1 | ~27 |
| 32 | 187 | 1 | ~51 |
| 33 | 215 | 1 | ~38 |

**Verdict: Correct.** The per-fascicle restart is achieved by the build script's prefixing scheme (e.g., `f26_1`, `f27_1`) which pandoc interprets as separate numbering sequences.

---

## 3. Footnote Markers in Body Text

**Finding: Markers are rendered as superscript numbers, correctly positioned.**

Analysis of body text pages (25-35) confirms:
- Footnote reference markers in body text: **size 8.0pt, EBGaramond-Regular, flags=5 (superscript)**
- Body text: **size 10.9pt, EBGaramond-Regular, flags=4**
- The superscript markers are visually distinct and properly elevated above the baseline

Example from page 25: The marker "17" appears at y=261 (superscript baseline) while body text sits at y=265 -- a 4pt elevation consistent with standard superscript positioning.

Placement after punctuation was verified on multiple pages. Markers appear correctly after periods and closing parentheses (e.g., "alambana-vastu).^17" on page 25).

**Verdict: Correct formatting.**

---

## 4. "Notes" Heading Sections: Empty Vestigial Headings

**ISSUE (Moderate): Every fascicle ends with a "Notes" heading that contains no endnote content.**

The build script injects a `### Notes` heading at the end of each fascicle's markdown, intending it to introduce collected endnotes. But since pandoc renders footnotes at point of reference (page bottom), the "Notes" section heading appears empty -- just the word "Notes" followed by blank space to the bottom of the page.

Pages with empty "Notes" headings:

| Page | Fascicle | Content Below "Notes" |
|------|----------|----------------------|
| 40 | 26 | One footnote (fn 53) at page bottom -- but this is a page-bottom footnote for a marker on the same page, not an endnote |
| 71 | 27 | Empty |
| 107 | 28 | Empty |
| 141 | 29 | Empty |
| 165 | 30 | Empty |
| 186 | 31 | Empty |
| 213 | 32 | Empty |
| 241 | 33 | Empty (only "Notes" heading plus page number) |

On page 40, footnote 53 text does appear at the very bottom (y=568-605), but this is the standard page-bottom footnote for marker 53 which appears in the body text on the same page (y=128). It is NOT an endnote under the "Notes" heading. The "Notes" heading sits at y=259 with nothing between it and the footnote separator line at y=556.

**Verdict: The "Notes" headings are vestigial artifacts of the build script's relocation logic and should be removed from the print output.** They serve no purpose since pandoc renders footnotes at page bottom. On page 241 (fascicle 33), the "Notes" heading is the ONLY body content on the entire page, making it especially conspicuous.

**Recommendation:** Either (a) remove the `### Notes` heading injection from the `relocate_footnotes()` function in `build.py` for print builds, or (b) add a LaTeX filter to suppress the heading.

---

## 5. Footnote Text Formatting

**Finding: Footnote text is well-formatted and readable.**

Font characteristics of footnote text at page bottom:
- Footnote number: **size 6.0pt** (smaller than body superscript markers)
- Footnote body text: **size 9.0pt, EBGaramond-Regular** (vs. 10.9pt body text)
- Italic text (Sanskrit terms, etc.): **size 9.0pt, EBGaramond-Italic**
- Chinese characters in footnotes: **size 9.0pt, MicrosoftYaHei** (CJK font fallback working correctly)

The 9.0pt footnote text on the 6x9 page is a readable size -- proportionate to the 10.9pt body text (approximately 82% of body size, within the standard 75-85% range for academic footnotes).

No truncation was observed. Long footnotes (e.g., footnote 27 on pages 53-54 about the sixteen victory practices) span multiple lines and even continue across pages as expected with LaTeX footnote handling.

**Verdict: Correct and readable.**

---

## 6. Cross-References: Markers Match Definitions

**Finding: Footnote numbers in body text match their definitions at page bottom.**

Verified on sampled pages:
- Page 25: Body marker "17" (superscript) -> bottom-of-page definition beginning with "17" followed by explanatory text about the four types of objects of meditation
- Page 26: Body marker "18" -> definition about the image with discernment; marker "19" -> definition about the compound for loving-kindness
- Page 27: Body marker "20" -> definition about nine stages; marker "21" -> definition about eight alternative names; marker "22" -> definition about the limit of things
- Page 40: Body marker "53" -> definition about "attenuated" at page bottom

All sampled markers correctly correspond to their definitions. No mismatches found.

**Verdict: Correct.**

---

## 7. Footnote Separator Rule

**Finding: A horizontal rule separates footnotes from body text.**

The LaTeX template defines:
```latex
\renewcommand{\footnoterule}{\vspace{0.5em}\noindent\rule{2in}{0.4pt}\vspace{0.3em}}
```

Confirmed in the PDF: horizontal lines appear at the footnote separation point. On page 25, a line at y=534 (about 82% down the 648pt page) separates body text from footnote content. The line extends 144pt (2 inches), consistent with the template specification.

On pages with multiple horizontal rules in the body (Taisho reference markers rendered as centered rules), the footnote rule is visually distinguishable: it is left-aligned and narrower (2 inches vs. the 0.5\linewidth body rules).

**Verdict: Correct.**

---

## 8. Blank Pages After Fascicle Ends

**Finding: Blank verso pages appear after each fascicle ending, before the next fascicle's title page.**

Blank pages detected at: 72, 108, 142, 166, 214, 242. These are standard recto-starting chapter behavior in book typesetting (the `book` documentclass with `openright` default). Each new fascicle chapter begins on a recto (odd/right) page.

The `emptypage` package is loaded in the template, which correctly suppresses headers/footers on these blank pages.

**Verdict: Correct book typesetting behavior.**

---

## Summary of Issues

| # | Severity | Issue | Recommendation |
|---|----------|-------|----------------|
| 1 | **Moderate** | Empty "Notes" headings appear at the end of every fascicle (8 occurrences) with no endnote content below them | Remove the `### Notes` heading from `relocate_footnotes()` in `build.py`, or suppress it in the LaTeX template |
| 2 | None | All other footnote formatting aspects are correct | -- |

### What Is Working Well

- Page-bottom footnotes are the correct scholarly convention for this type of text
- Per-fascicle numbering restart works correctly across all 8 fascicles
- Superscript markers are properly sized and positioned
- Footnote text is readable (9.0pt on 6x9 page)
- Chinese characters render correctly in footnotes via CJK font fallback
- Footnote separator rule is properly formatted
- Cross-references between markers and definitions are accurate
- Blank recto-start pages are handled correctly with suppressed headers
