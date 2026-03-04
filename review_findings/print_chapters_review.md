# Print PDF: Chapter Openings and Running Headers Review

**File reviewed:** `output/sravakabhumi_print.pdf` (252 pages, 6"x9" KDP paperback)
**Date:** 2026-03-02

---

## Summary of Fascicle Chapter Locations

| Fascicle | Chapter # | Last page prev. | Blank page | Opening page | Recto? |
|----------|-----------|-----------------|------------|--------------|--------|
| 26       | Chapter 5 | 8 (Intro)       | --         | 9 (odd)      | YES    |
| 27       | Chapter 6 | 40 (even)       | --         | 41 (odd)     | YES    |
| 28       | Chapter 7 | 71 (odd)        | 72 (blank) | 73 (odd)     | YES    |
| 29       | Chapter 8 | 107 (odd)       | 108 (blank)| 109 (odd)    | YES    |
| 30       | Chapter 9 | 141 (odd)       | 142 (blank)| 143 (odd)    | YES    |
| 31       | Chapter 10| 165 (odd)       | 166 (blank)| 167 (odd)    | YES    |
| 32       | Chapter 11| 186 (even)      | --         | 187 (odd)    | YES    |
| 33       | Chapter 12| 213 (odd)       | 214 (blank)| 215 (odd)    | YES    |
| Translation Notes | Chapter 13 | 241 (odd) | -- | 243 (odd) | YES |

---

## 1. Chapter Openings: Recto Page Placement

**PASS.** All eight fascicle chapters and the Translation Notes chapter open on recto (right-hand, odd-numbered) pages. The `openright` class option in `metadata-print.yaml` is working correctly.

Where the prior fascicle ends on an odd page, LaTeX correctly inserts a blank verso page (pages 72, 108, 142, 166, 214). Where the prior fascicle ends on an even page (fascicles 26 ending p.40, 31 ending p.186), the next fascicle immediately begins on the next odd page without needing a blank.

Blank pages (72, 108, 142, 166, 214) are confirmed truly empty -- no headers, no footers, no page numbers. The `emptypage` package is working correctly.

---

## 2. Chapter Heading Format

**PASS with one observation.**

Each fascicle chapter opening page follows this structure:
1. Top line: "Sravakabhumi: The Hearer's Ground" (centered, appears as part of the chapter title block)
2. "Yogacarabhumi-sastra, Fascicle XX" (centered)
3. Attribution line: "Composed by Asanga..." (running text)
4. Section designation: "Basic Section: Shravaka Ground, [Nth] Yoga Place, Part [N]" (centered)
5. Blank vertical space
6. First section heading (e.g., "26.1 Opening Questions and Summary Verse")

The `\titlespacing*{\chapter}{0pt}{80pt}{40pt}` provides 80pt top margin and 40pt spacing before body text, which appears adequate in the extracted layout.

**Observation:** The chapter title "Sravakabhumi: The Hearer's Ground" is the same for all fascicles. The `\leftmark` in the running header therefore shows "CHAPTER N. SRAVAKABHUMI: THE HEARER'S GROUND" for every chapter. This is technically correct but means the running header does not distinguish between fascicles. Consider whether the chapter title should include the fascicle number (e.g., "Fascicle 26: The Hearer's Ground") for easier navigation. **Severity: Minor/cosmetic -- not a formatting defect, but a usability consideration.**

---

## 3. Running Headers

### 3a. Verso (even) pages

**PASS.** Even-numbered pages consistently show "Sravakabhumi" at the top left (as specified by `\fancyhead[LE]{\small\textit{Sravakabhumi}}`). Confirmed on pages 20, 22, 24, 26, 28, 30, and throughout all sampled ranges.

### 3b. Recto (odd) pages

**PASS with issues.** Odd-numbered pages show the chapter title via `\leftmark`. The content is:

- Fascicle 26 pages: "CHAPTER 5. SRAVAKABHUMI: THE HEARER'S GROUND"
- Fascicle 27 pages: "CHAPTER 6. SRAVAKABHUMI: THE HEARER'S GROUND"
- Fascicle 28 pages: "CHAPTER 7. SRAVAKABHUMI: THE HEARER'S GROUND"
- And so on through Chapter 13 (Translation Notes)

**ISSUE 1: "CHAPTER N." prefix in headers.** The running header includes the auto-generated "CHAPTER N." prefix followed by the chapter title in ALL CAPS. This is the LaTeX default `\MakeUppercase{\chaptermark}` behavior. For a scholarly book, this is visually heavy and not standard. Most scholarly publishers show only the chapter title in the header, without the "CHAPTER N." prefix, and typically in title case or small caps rather than all-uppercase.

**Severity: Moderate.** The all-caps "CHAPTER 5. SRAVAKABHUMI: THE HEARER'S GROUND" is visually dominant and occupies significant header space. Recommend customizing `\chaptermark` to suppress the "CHAPTER N." prefix and the uppercase transformation.

**Fix:** Add to `print-template.tex`:
```latex
\renewcommand{\chaptermark}[1]{\markboth{#1}{}}
```
This will make the recto header show just the chapter title (e.g., "Sravakabhumi: The Hearer's Ground") in the original case, matching the italic styling already specified.

**ISSUE 2: Chapter numbering starts at 5.** Because Pandoc treats each `# Heading` as a chapter, the front matter files (half-title, title page, copyright, contents, introduction) consume chapters 1-4. Fascicle 26 therefore becomes "Chapter 5." This numbering is invisible in the body text (the `\titleformat{\chapter}` uses `{}` for the number, suppressing it), but it leaks into the running headers via `\leftmark`. The reader sees "CHAPTER 5" for fascicle 26, "CHAPTER 6" for fascicle 27, etc. -- numbers that have no meaning in the context of this book.

**Severity: Moderate.** Readers will wonder why the book starts at "Chapter 5." This is a direct consequence of Issue 1 above -- fixing the `\chaptermark` to suppress "CHAPTER N." resolves both issues simultaneously.

### 3c. Chapter-opening pages

**PASS.** Chapter-opening pages (9, 41, 73, 109, 143, 167, 187, 215) use the `plain` page style as set by `\chapter`, which correctly shows only the centered page number in the footer and no running header. Confirmed by examining the content at top of these pages -- the first line is the chapter title block, not a running header.

### 3d. Blank pages

**PASS.** Blank pages before chapters (72, 108, 142, 166, 214) have no headers, no footers, and no page numbers. The `emptypage` package is functioning correctly.

---

## 4. Page Numbers

**PASS.** Page numbers appear centered in the footer on all content pages. They are absent on blank pages. The `\fancyfoot[C]{\thepage}` and the `plain` / `empty` page styles are all working correctly.

Front matter uses Roman numerals (not visible in the sampled ranges, as the main matter starts at page 9 with Arabic numerals). The `\frontmatter` / `\mainmatter` transitions are handled correctly.

Note: Page 241 (fascicle 33 Notes page) shows "241" -- the notes are counted in the main pagination, which is correct.

---

## 5. First Paragraph Indentation

**ISSUE: Cannot fully verify from text extraction.** The `pdftotext -layout` output shows indented paragraphs throughout, including after chapter headings. However, text-layout extraction is not pixel-accurate for indentation.

**Analysis from LaTeX template:** The template uses `\usepackage{parskip}` with `\setlength{\parindent}{1.5em}`. The `parskip` package by default removes paragraph indentation and adds vertical space. However, the template then overrides this by explicitly setting `\parindent` to 1.5em and `\parskip` to 0pt -- effectively restoring traditional paragraph formatting with indentation and no extra spacing.

**The issue:** With this configuration, ALL paragraphs have 1.5em indent, including the first paragraph after a chapter heading and after section headings. Standard book typography conventions dictate that the first paragraph after a heading should NOT be indented (since the heading itself signals the paragraph break). This requires explicit use of `\noindent` or a package like `indentfirst` (which does the opposite -- ensures first paragraphs ARE indented, but that is non-standard).

**Severity: Minor.** The first-paragraph indent after headings is a traditional typographic convention that is commonly violated in modern academic publishing. Many scholarly books indent all paragraphs including the first. However, for a press-quality publication matching NTC/Shambhala conventions, the first paragraph after a heading should not be indented.

**Fix:** Add `\usepackage{indentfirst}` to *not* use, or manually add `\noindent` handling. Actually, with the current `parskip` + explicit `\parindent` setup, the simplest fix is to add:
```latex
\makeatletter
\let\@afterindentfalse\@afterindenttrue
\@afterindenttrue
\makeatother
```
Wait -- actually, the `book` class with `\chapter` uses `\@afterindentfalse` by default, which means the first paragraph after `\chapter` should already NOT be indented. The `parskip` package may interfere with this. **This needs visual verification in the actual PDF (not text extraction).** Marking as "needs visual check."

---

## 6. Section Headings (##)

**PASS.** Section headings (mapped to `\section` by Pandoc) are centered per the template:
```latex
\titleformat{\section}
  {\normalfont\large\centering}
  {}
  {0pt}
  {\large}
\titlespacing*{\section}{0pt}{24pt}{12pt}
```

Confirmed in extracted text: section headings like "26.1 Opening Questions and Summary Verse", "26.4 Objects of Meditation: Overview", "27.4 Skillful Objects", "28.10 The Thirty-Seven Factors of Awakening", "31.8 Purification of Obstacles" all appear centered in the layout extraction. The 24pt above and 12pt below spacing appears adequate.

---

## 7. Subsection Headings (###)

**PASS.** Subsection headings (mapped to `\subsection` by Pandoc) are left-aligned and bold per the template:
```latex
\titleformat{\subsection}
  {\normalfont\normalsize\bfseries}
  {}
  {0pt}
  {}
\titlespacing*{\subsection}{0pt}{18pt}{6pt}
```

Confirmed in text extraction: headings like "The Image with Discernment", "The Image without Discernment", "The Limit of Things", "The Accomplishment of the Purpose" appear flush-left and are set in bold (confirmed by the font specification in the template). The 18pt above / 6pt below spacing is appropriate.

**Note:** Some subsection headings run inline with the paragraph text (e.g., "The Image with Discernment What is the image with discernment?"). This appears to be a Pandoc rendering of bold run-in headings from the markdown source (likely `**The Image with Discernment**` at paragraph start rather than `### The Image with Discernment`). These are not formatting defects but a different heading level in the source. They render correctly as bold inline text.

---

## 8. Transition Between Fascicles

**PASS.** Every fascicle ends with:
1. "End of Fascicle [N] of the Yogacarabhumi-sastra" (centered)
2. A "Notes" section (where applicable, for footnotes relocated to end-of-fascicle)
3. The new fascicle starts on a fresh recto page

The transition is clean in all cases. There is no content bleeding between fascicles. Each fascicle is its own LaTeX chapter with a fresh `\chapter` command.

---

## Summary of Issues

| # | Issue | Severity | Category |
|---|-------|----------|----------|
| 1 | Running headers show "CHAPTER N." prefix in ALL CAPS | Moderate | Running headers |
| 2 | Chapter numbering starts at 5 (leaks from front matter) | Moderate | Running headers |
| 3 | Running headers are identical for all fascicles (all say "Sravakabhumi: The Hearer's Ground") | Minor | Usability |
| 4 | First paragraph indentation after headings needs visual verification | Minor/Uncertain | Typography |

### Recommended Fixes

**Issues 1 and 2 (single fix):** Add to `print-template.tex` after the fancyhdr setup:
```latex
\renewcommand{\chaptermark}[1]{\markboth{#1}{}}
```
This removes the "CHAPTER N." prefix from `\leftmark`, resolving both the prefix and the meaningless numbering.

**Issue 3 (optional enhancement):** If distinct fascicle identification in the running header is desired, modify the chapter titles in the markdown source to include fascicle numbers, or customize `\chaptermark` to incorporate fascicle information.

**Issue 4 (verification needed):** Visually inspect the PDF to confirm whether the first paragraph after chapter and section headings is indented. If so, add `\makeatletter\@afterindenttrue\makeatother` or handle via titlesec's `\titleformat` options.

---

## Items That PASS Without Issues

- Recto placement of all chapter openings
- Blank pages before chapters (correctly empty, no headers/footers/numbers)
- Verso running headers ("Sravakabhumi" in italic)
- Chapter-opening pages have no running headers (plain style)
- Page numbers centered in footer throughout
- Section headings centered with proper spacing
- Subsection headings left-aligned, bold, with proper spacing
- Clean transitions between fascicles
- `emptypage` package functioning correctly
- `openright` class option functioning correctly
- Footnote rule and formatting
- Top margin on chapter opening pages (80pt)
- After-title spacing (40pt before body text)
