# Chicago Manual of Style (17th Edition) & Shambhala House Style Review

**Reviewer:** Scholarly book design specialist
**Date:** 2026-03-02
**Files reviewed:** `print-template.tex`, `build.py`, `metadata-print.yaml`, all front/back matter source files
**Reference standards:** Chicago Manual of Style, 17th ed. (2017); Shambhala Publications house style; University of Chicago Press scholarly monograph conventions; Amazon KDP 6"x9" trim specifications

---

## 1. Front Matter Sequence

**Chicago 17th (1.4):** Half title > series title or blank > title page > copyright > dedication > epigraph > table of contents > list of illustrations > list of tables > foreword > preface > acknowledgments > introduction (if part of front matter) > abbreviations

**Current sequence in `build.py`:**
1. `00_halftitle.md` (half title)
2. `00_titlepage.md` (title page -- replaced with LaTeX in `_print_titlepage()`)
3. `00_copyright.md` (copyright -- replaced with LaTeX in `_print_copyright()`)
4. `00_contents.md` (table of contents -- replaced with `\tableofcontents`)
5. `00_introduction.md` (translator's introduction)

### Assessment

**Correct:** The sequence half title -> title page -> copyright -> contents -> introduction is standard Chicago. The half title page properly starts the front matter.

**Issue 1 (Minor): No blank verso after half title.** Chicago 1.4 specifies that the verso (back) of the half title page is traditionally blank, or carries a series title or frontispiece. Currently, `build.py` does not inject a `\cleardoublepage` or blank page after the half title. The `_print_titlepage()` function begins with `\cleardoublepage`, which should force the title page to a recto -- but only if the half title is processed as a normal page. The half title uses `\chapter*{The Hearer's Ground}` which will start on a recto, then the title page's `\cleardoublepage` should leave the verso blank. **This is likely correct in practice** but depends on the `openright` class option being active (which it is, per `metadata-print.yaml`).

**Verdict:** Sequence is correct per Chicago. The `openright` option handles the blank verso. No change needed.

---

## 2. Page Geometry

**Current settings (from `metadata-print.yaml`):**
- Paper: 6" x 9" (KDP standard trim)
- Inner margin: 0.75"
- Outer margin: 0.75"
- Top margin: 0.75"
- Bottom margin: 0.7"
- Head height: 14pt
- Head sep: 18pt

**KDP Requirements (6"x9"):** Minimum margins are 0.375" (top/bottom/outer), with inner margin dependent on page count (0.375" + gutter allowance). For a book of ~400-500 pages, KDP recommends at least 0.875" inner gutter.

### Assessment

**Issue 2 (Major): Inner margin is too narrow for a bound book.** At 0.75" inner, text will disappear into the gutter on a 400+ page perfect-bound paperback. KDP itself calculates minimum inner margins based on page count:
- 150-400 pages: ~0.75" minimum (borderline)
- 400-600 pages: ~0.875" minimum
- 600+ pages: ~1.0" minimum

For a scholarly translation of 8 fascicles with front/back matter, the page count will likely land in the 350-500 range. **0.75" inner is the absolute KDP minimum and will feel tight.** Chicago does not mandate specific margins but assumes adequate gutter for comfortable reading.

**Recommendation:** Increase inner margin to 0.875" or even 1.0". Reduce outer to 0.625" or accept a slightly narrower text block. Shambhala trade paperbacks typically use approximately 0.875"-1.0" inner, 0.625"-0.75" outer for 6"x9".

**Issue 3 (Minor): Equal inner/outer margins.** In twoside/openright book design, inner margins should be larger than outer to compensate for binding. Equal margins (0.75"/0.75") are atypical. Chicago 17th does not prescribe specific dimensions but the convention is well established in book design.

**Issue 4 (Minor): Top/bottom margins.** 0.75"/0.7" is acceptable but tight. With the running header (14pt headheight + 18pt headsep = ~32pt consumed from the top margin), the effective space above the header is small. This is within acceptable range but leaves minimal breathing room. Shambhala typically uses 0.8"-0.9" top.

**Recommended geometry:**
```yaml
geometry:
  - paperwidth=6in
  - paperheight=9in
  - inner=0.9in
  - outer=0.65in
  - top=0.8in
  - bottom=0.7in
  - headheight=14pt
  - headsep=18pt
```

---

## 3. Running Headers

**Current setup:**
- Verso (even/left): `pagenumber -- SRAVAKABHUMI` (letterspaced small caps)
- Recto (odd/right): `CHAPTER TITLE -- pagenumber` (letterspaced small caps)
- Em-dash separator between page number and title
- 0.3pt header rule
- Plain style on chapter openings (page number bottom center)
- Empty style on blank pages (via `emptypage` package)

**Chicago 17th (1.10-1.14):** Running heads typically contain book title on verso, chapter title on recto. Page numbers may be in the header (outer corners) or at the foot. The convention of page number in the header with a separator is acceptable but less common than outer-corner placement.

### Assessment

**Correct:** The verso = book title, recto = chapter title convention follows Chicago. The letterspaced small caps are elegant and match Shambhala house style. The `emptypage` package correctly suppresses headers on blank pages.

**Issue 5 (Moderate): Page number placement.** The current design places the page number adjacent to the title with an em-dash separator. This is a valid design choice (seen in some Shambhala/Wisdom Publications titles) but differs from the more conventional approach where page numbers sit at the outer margin corner, with the running head centered or in the inner position. The em-dash style is acceptable but less traditional.

**More conventional alternative:**
```latex
\fancyhead[LE]{\small\thepage}
\fancyhead[CE]{\small\addfontfeatures{LetterSpace=8}\textsc{sravakabhumi}}
\fancyhead[RO]{\small\thepage}
\fancyhead[CO]{\small\addfontfeatures{LetterSpace=8}\textsc{\MakeLowercase{\leftmark}}}
```

**Issue 6 (Minor): Header rule.** A 0.3pt header rule is present. Many Shambhala titles omit the rule entirely for a cleaner look. Some academic presses retain it. This is a legitimate design choice. If the goal is specifically Shambhala house style, consider removing it (`\renewcommand{\headrulewidth}{0pt}`).

**Issue 7 (Minor): `\MakeLowercase{\leftmark}` in recto header.** This lowercases the chapter title for small caps rendering. Works correctly for English text but may produce unexpected results if chapter marks contain LaTeX commands, Sanskrit diacritics, or special characters. Given the chapter titles ("The Second Yoga Place, Part One" etc.), this should be fine. No action needed.

**Verdict:** Running headers are well-designed. The em-dash style is a valid but non-standard choice. Consider whether the header rule matches the desired aesthetic.

---

## 4. Chapter Openings

**Current setup:**
```latex
\titleformat{\chapter}[display]
  {\normalfont\Large\centering}
  {}
  {0pt}
  {\LARGE}
\titlespacing*{\chapter}{0pt}{120pt}{40pt}
```

- Display format (title on its own line)
- Centered, `\LARGE` size (~20pt at 11pt base)
- 120pt top space (drop), 40pt below title
- No chapter number (secnumdepth = -1)
- Plain page style on chapter openings (page number at foot center)

**Chicago 17th (1.49-1.55):** Chapter openings traditionally begin lower on the page (a "sink" or "drop"). The chapter title should be visually distinct. Page numbers on chapter-opening pages typically appear at the foot, centered.

### Assessment

**Correct:** The 120pt drop is generous and appropriate for a 9" page -- roughly 1.67", which places the title at about the upper third of the text block. This matches Shambhala's clean, spacious chapter openings. The centered format, unnumbered chapters, and foot-center page number all follow Chicago.

**Issue 8 (Minor): Chapter title size hierarchy.** The format specifier uses `\Large` for the format and `\LARGE` for the title itself. Since `\Large` applies to the prefix (which is empty -- no chapter number) and `\LARGE` to the title, the effective title size is `\LARGE` (~20pt). This is appropriate. However, the `\Large` in the format declaration has no visible effect since the prefix is empty. This is cosmetically harmless but slightly unclear.

**Issue 9 (Minor): No ornament or rule below chapter title.** Some Shambhala titles use a small ornament or thin rule below the chapter title to separate it from the body text. The current design relies solely on 40pt spacing. Both approaches are valid. A short centered rule (similar to the one on the title page) could enhance the visual weight of the opening.

**Verdict:** Chapter openings are well-configured. The drop, centering, and page style all follow Chicago and Shambhala conventions.

---

## 5. Section Headings

**Current setup:**
```latex
\renewcommand\section{...}
  % 24pt above, 12pt below, \large\bfseries, left-aligned
\renewcommand\subsection{...}
  % 24pt above, 6pt below, \normalsize\bfseries, left-aligned
```
- `\needspace{6\baselineskip}` for sections, `\needspace{4\baselineskip}` for subsections
- Uses `\@startsection` instead of `titlesec` for sections/subsections (to avoid fancyhdr interaction)
- Heading levels are promoted in `_restructure_fascicle_headings()`: `###` -> `##`, `####` -> `###`

**Chicago 17th (1.56-1.58):** Subheadings should be clearly hierarchical. A-heads (sections) are typically bold, larger; B-heads (subsections) are bold, same size. Left alignment is standard for academic texts. Adequate space above and below is required.

### Assessment

**Correct:** The heading hierarchy is clear. The spacing (24pt/12pt for sections, 24pt/6pt for subsections) provides adequate visual separation. The `\needspace` commands properly prevent headings from appearing at the page bottom without following text (Chicago 1.80). The use of `\@startsection` to avoid titlesec/fancyhdr conflicts is a sound engineering decision.

**Issue 10 (Minor): Section above-spacing is asymmetric.** The negative value `-24\p@` for the before-skip in `\@startsection` signals that the heading should suppress the paragraph indent of the following paragraph. The absolute value 24pt is the actual space. This is standard LaTeX convention and correct.

**Issue 11 (Minor): No run-in or italic heading level.** For a three-level hierarchy (chapter > section > subsection), the current setup works. If a fourth level is needed (paragraph-level headings), there is no definition. The heading promotion in `_restructure_fascicle_headings` pushes `#####` to `####`, but no `\paragraph` style is defined. If any `#####` headings exist in the source, they will use LaTeX defaults. Check whether this level is used in any fascicle.

**Verdict:** Section headings are well-designed and technically sound. The `\needspace` approach is good practice.

---

## 6. Footnotes

**Current setup:**
```latex
\usepackage[bottom]{footmisc}
\setlength{\footnotesep}{0.8\baselineskip}
\renewcommand{\footnoterule}{\vspace{0.8em}\noindent\rule{2in}{0.4pt}\vspace{0.4em}}
```
- `[bottom]` option: forces footnotes to page bottom (not float up on short pages)
- Footnote separator: 2-inch rule, 0.4pt thick, with 0.8em above and 0.4em below
- Footnote IDs are prefixed per fascicle in `relocate_footnotes()` to avoid collisions
- `\footnotesep` at 0.8\baselineskip gives moderate spacing between footnotes

### Assessment

**Correct:** The `[bottom]` option is essential for scholarly texts (Chicago 14.38). The 2-inch rule is standard (Chicago uses a short rule, typically 1-2 inches). The footnote collision prevention via prefixing is a sound engineering solution.

**Issue 12 (Minor): Footnote text size.** No explicit size is set for footnote text. LaTeX default for the `book` class at 11pt is `\footnotesize` (~9pt). This is appropriate -- Chicago recommends footnotes be 1-2 points smaller than body text.

**Issue 13 (Minor): Footnote rule indentation.** The rule uses `\noindent` to start flush left. This is standard. Some presses indent the footnote rule or omit it entirely. The current approach is correct per Chicago.

**Issue 14 (Minor): Footnote paragraph indent.** No explicit `\footnotemargin` or `\hangfootparindent` is set. LaTeX defaults will apply. For multi-line footnotes, the default hanging indent is appropriate. If footnotes have continuation paragraphs, verify they indent correctly.

**Verdict:** Footnote configuration is solid and follows Chicago conventions.

---

## 7. Typography

**Font:** EB Garamond (static TTF instances, loaded via fontspec with HarfBuzz renderer)
**Size:** 11pt base
**Line spacing:** 1.15 (via setspace)
**Paragraph indent:** 1.5em
**Paragraph skip:** 0pt
**Microtype:** enabled

### Assessment

**Correct:** EB Garamond is an excellent choice for a scholarly Buddhist translation. It is a faithful digitization of Claude Garamond's types with strong coverage of Latin diacritics (important for Sanskrit romanization). The 11pt size is standard for 6"x9" trade paperbacks. Shambhala uses various Garamond-family fonts; EB Garamond is in the right family.

**Issue 15 (Minor): Line spacing 1.15.** This is slightly above single-spacing (1.0) and below the 1.2 sometimes used for heavily annotated texts. For a 6"x9" text block with moderate footnote density, 1.15 is appropriate. However, at 11pt with EB Garamond (which has relatively tall ascenders/descenders), 1.2 might give marginally better readability. This is a judgment call -- 1.15 is acceptable.

**Issue 16 (Minor): Paragraph indent.** 1.5em (~16.5pt at 11pt) is standard. Chicago recommends 1-1.5em. This is at the upper end but acceptable. Some presses use 1em for a tighter look.

**Issue 17 (Informational): The `parskip` package.** Loading `parskip` and then overriding both `\parindent` (1.5em) and `\parskip` (0pt) effectively negates the package's purpose. The package is designed to set `\parskip` to a positive value and `\parindent` to 0. Loading it and then resetting both values is harmless but unnecessary. Consider removing `\usepackage{parskip}` and setting the lengths directly, which is cleaner.

**Issue 18 (Good): Microtype is enabled.** `\usepackage{microtype}` provides character protrusion and font expansion, improving line breaks and reducing hyphenation. This is excellent practice for any quality typeset book.

**Verdict:** Typography choices are appropriate for the genre. EB Garamond at 11pt with 1.15 spacing is a solid foundation.

---

## 8. Table of Contents

**Current setup:**
```latex
\usepackage{tocloft}
\setcounter{tocdepth}{1}  % chapters + sections
\renewcommand{\cftchapfont}{\normalfont\bfseries}
\renewcommand{\cftchappagefont}{\normalfont\bfseries}
\renewcommand{\cftchapleader}{\cftdotfill{\cftdotsep}}
\renewcommand{\cftsecfont}{\normalfont}
\renewcommand{\cftsecpagefont}{\normalfont}
\renewcommand{\cftdot}{.}
\renewcommand{\cftdotsep}{2}
\setlength{\cftsecindent}{1.5em}
\setlength{\cftbeforechapskip}{0.8em}
\setlength{\cftbeforesecskip}{0.1em}
```

In `build.py`, the hand-crafted markdown ToC (`00_contents.md`) is replaced with `\tableofcontents` for print. The markdown ToC contains descriptive subtitles under each fascicle entry.

**Chicago 17th (1.38-1.42):** The ToC should list chapter titles and first-level subheads. Dot leaders are conventional. Bold for chapter entries, roman for subentries. Page numbers right-aligned.

### Assessment

**Correct:** The tocloft configuration follows Chicago conventions. Bold chapters with dot leaders, roman sections, appropriate indentation and spacing. The tocdepth of 1 (chapters + sections) is appropriate -- deeper would produce an unwieldy ToC for this text.

**Issue 19 (Moderate): Loss of descriptive content from hand-crafted ToC.** The markdown `00_contents.md` contains valuable descriptive subtitles under each fascicle (e.g., "Types of persons; objects of meditation; purifying-conduct objects..."). When `build.py` replaces this with `\tableofcontents`, these descriptions are lost. The auto-generated ToC will list only chapter titles and section headings. For a scholarly translation, these synoptic descriptions are valuable -- they tell the reader what each fascicle contains before they navigate to it.

**Recommendation:** Consider a hybrid approach: keep the auto-generated ToC for accurate page numbers, but add the descriptive content as a separate "Summary of Contents" or "Analytical Contents" page. Alternatively, use `\addtocontents` commands to inject the descriptive lines into the auto-generated ToC. Chicago 1.38 permits both a brief ToC and an expanded analytical ToC.

**Issue 20 (Minor): ToC title.** The default `\tableofcontents` title is "Contents" (for the `book` class). The hand-crafted version uses "# Contents" which would produce the same. This is correct per Chicago.

**Verdict:** ToC is well-configured but loses valuable descriptive content from the hand-crafted version.

---

## 9. Title Page

**Current LaTeX output (`_print_titlepage()`):**
```
[cleardoublepage, empty page style]
[1.5" vertical space]
SRAVAKABHUMI (large small caps)
The Hearer's Ground (large)
From the Yogacarabhumi-sastra of Asanga (italic)
Fascicles 26-33
[2-inch rule]
Translated from the Chinese of Xuanzang
(Taisho Tripitaka, Vol. 30, No. 1579) (small)
English translation edited by Ankhara
[vfill]
First English Translation from the Chinese (small italic, at bottom)
```

**Chicago 17th (1.17-1.22):** Title page should include: full title and subtitle, author name, publisher name and location, possibly edition statement. For translations: original author, translator, and original-language information.

### Assessment

**Issue 21 (Moderate): No publisher imprint.** The title page lacks a publisher name or imprint. For a KDP self-published title, this is common but weakens the professional appearance. Consider adding a line such as "Independently Published" or creating a simple imprint name. Chicago expects a publisher identification.

**Issue 22 (Minor): "English translation edited by Ankhara" phrasing.** The role "edited by" is ambiguous for a work that is both translated and edited by the same person. Standard phrasing for a translation would be "Translated by [Name]" or "A New Translation by [Name]." If the AI translation aspect is to be acknowledged, "Translation edited by Ankhara" is acceptable, but "Translated and edited by Ankhara" would be more complete. Current phrasing could imply someone else did the translation.

**Issue 23 (Minor): "First English Translation from the Chinese" at bottom.** This is a strong selling point and appropriate for the title page. Its placement at the vfill bottom is effective. However, "First English Translation from the Chinese" could be read as "first translation specifically from Chinese" (implying others exist from Sanskrit/Tibetan). Consider "First Complete English Translation" if that is more accurate.

**Issue 24 (Minor): Title spacing.** The 1.5" top space places the title at roughly 1/6 of the page from the top. This is within the conventional range (some presses use 1/3 page drop, some use 1/4). The current placement is adequate.

**Verdict:** Title page is functional and reasonably balanced. Adding a publisher line and clarifying the translator credit would strengthen it.

---

## 10. Copyright Page

**Current LaTeX output (`_print_copyright()`):**
```
[empty page style]
[vfill -- pushes content to bottom]
English translation copyright (c) 2025-2026 Ankhara
Licensed under CC BY-NC-SA 4.0
[brief license description]
English translation from the Taisho Shinshu Daizokyo, Vol. 30, No. 1579
Chinese translation by Xuanzang, 648 CE
Original composition attributed to Asanga (c. late 4th-early 5th century CE)
Typeset in EB Garamond
First edition, 2026
```

**Chicago 17th (1.23-1.36):** Copyright page should include: copyright notice, rights statement, publication history, CIP data or ISBN, publisher address, printing history, paper/production statement, credits.

### Assessment

**Issue 25 (Moderate): Missing ISBN.** The markdown source has `<!-- ISBN placeholder -->` comments but the LaTeX generator does not include them. Before publishing on KDP, ISBNs must be added. KDP provides a free ISBN or you can purchase your own. This is a placeholder issue but should not be forgotten.

**Issue 26 (Minor): Missing "All rights reserved" or equivalent.** While the CC license serves this purpose, traditional copyright pages include "All rights reserved" or the specific license terms more prominently. The current layout handles this adequately with the CC description.

**Issue 27 (Minor): No Library of Congress / CIP data.** Self-published titles typically lack CIP data, which is acceptable. However, if the work is intended for library acquisition, obtaining an LCCN would be valuable.

**Issue 28 (Minor): No country of printing.** Chicago recommends "Printed in [country]." For KDP print-on-demand, "Printed in the United States of America" (or wherever KDP prints) is conventional.

**Issue 29 (Good): "Typeset in EB Garamond" and "First edition, 2026."** These are appropriate colophon details. The edition statement is required by Chicago.

**Issue 30 (Minor): Position.** The `\vfill` pushes content to the page bottom, which is the standard position for copyright information. Correct per Chicago 1.23.

**Verdict:** Copyright page covers essentials but needs ISBN before publication. Consider adding country of printing.

---

## 11. Orphan/Widow Control

**Current setup:**
```latex
\widowpenalty=10000
\clubpenalty=10000
\hyphenpenalty=300
\exhyphenpenalty=300
\tolerance=3000
\emergencystretch=3em
```

**Chicago 17th (2.113):** Widows (last line of paragraph at top of page) and orphans (first line of paragraph at bottom of page) should be avoided.

### Assessment

**Correct:** `\widowpenalty=10000` and `\clubpenalty=10000` effectively prohibit widows and orphans (10000 is the maximum penalty, treated as "infinite" by TeX). This is the standard approach and follows Chicago.

**Issue 31 (Good): Hyphenation settings.** `\hyphenpenalty=300` moderately discourages hyphenation, `\tolerance=3000` allows looser line spacing to compensate, and `\emergencystretch=3em` provides a generous emergency stretch. This combination reduces hyphenation while avoiding overfull boxes. The values are well-balanced -- aggressive enough to reduce ugly breaks but not so strict as to cause rivers of white space.

**Issue 32 (Minor): No `\brokenpenalty`.** `\brokenpenalty` penalizes page breaks after a hyphenated line. Setting `\brokenpenalty=10000` would prevent a page from breaking immediately after a hyphenated last line -- a nice refinement. Currently unset (LaTeX default is 100).

**Verdict:** Orphan/widow control is excellent. Consider adding `\brokenpenalty`.

---

## 12. Back Matter

**Current sequence in `build.py`:**
1. `00_methodology.md` (Translation Notes) -- first back matter file, gets `\backmatter`
2. `00_abbreviations.md` (Abbreviations and Conventions)
3. `00_bibliography.md` (Bibliography)
4. Glossary excluded from print (`include_glossary=False`)

**Chicago 17th (1.4, 1.61-1.63):** Back matter typically includes: appendix(es), notes, glossary, bibliography, index. The `\backmatter` command switches page numbering and heading behavior appropriately.

### Assessment

**Issue 33 (Moderate): Back matter sequence.** Chicago prefers: appendixes > glossary > bibliography > index. The current sequence (Translation Notes > Abbreviations > Bibliography) is reasonable but places the abbreviations after the methodology. Since abbreviations are a reference tool that readers consult while reading the main text, they arguably belong either in the front matter (Chicago 1.44) or at the very beginning of the back matter.

**Recommendation:** Consider moving abbreviations to front matter (before the introduction, per Chicago 1.44: "A list of abbreviations... may appear in the front matter if it is essential for the reader before encountering the text"). Alternatively, keep it as the first back matter item.

**Issue 34 (Minor): Glossary excluded from print.** The decision to exclude the glossary from print (keeping it digital-only) is pragmatic -- glossaries can add significant page count and cost. However, for a scholarly translation, a print glossary is expected. Consider including an abridged glossary of key terms (50-100 entries) in the print edition.

**Issue 35 (Minor): No index.** A scholarly translation of this scope would normally include an index. Chicago strongly recommends indexes for academic books (chapter 16). For a Buddhist text, a subject index and a Sanskrit term index would be valuable. This is a significant undertaking and may be beyond the current project scope, but its absence should be noted.

**Issue 36 (Minor): Back matter `\backmatter` placement.** The `\backmatter` command is injected before the first back matter file. This correctly switches from Arabic numbering and disables chapter numbering. However, back matter items still appear as chapters (h1 headings). Verify that back matter chapters do not receive numbered treatment in the ToC (they should not, since `secnumdepth` is -1).

**Verdict:** Back matter is functional. Consider the abbreviations placement and the absence of index/glossary in print.

---

## 13. Additional Observations

### 13.1 Build Script Architecture

**Observation:** The `build.py` script handles preprocessing that would typically be done in LaTeX. This includes:
- Replacing markdown front matter files with raw LaTeX (`_print_titlepage()`, `_print_copyright()`)
- Injecting `\frontmatter`, `\mainmatter`, `\backmatter` transitions
- Restructuring heading levels (`_restructure_fascicle_headings()`)
- Relocating footnotes (`relocate_footnotes()`)
- Managing fancyhdr state transitions between front/main matter

This approach is pragmatic for a pandoc-based pipeline but creates tight coupling between the build script and the template. Any future changes to the template's page style management must be synchronized with the Python code.

### 13.2 The titlesec/fancyhdr Interaction

The codebase includes extensive comments about the titlesec/fancyhdr interaction bug. The solution (using `\@startsection` for sections/subsections, titlesec only for chapters, never using `\pagestyle{plain}`) is technically sound and well-documented. The header state management via `\fancyhead{}` toggling rather than `\pagestyle` switching is the correct workaround.

### 13.3 Font Loading

The static font instances (generated from variable fonts) with HarfBuzz renderer is a robust approach for XeLaTeX. The comment about "axis parsing issues" suggests previous problems with variable font instances, which are known to cause issues with older XeLaTeX/fontspec combinations. The static approach is more portable.

### 13.4 Verse/Blockquote Styling

```latex
\renewenvironment{quote}
  {\list{}{\leftmargin=2em\rightmargin=1em}\item\relax\small\itshape}
  {\endlist}
```

This renders blockquotes (used for verse passages) in small italic with 2em left indent and 1em right indent. This is appropriate for verse passages (uddana) in the Sravakabhumi. However, if blockquotes are also used for non-verse material (long quotations), the italic might be inappropriate. Verify that all blockquote usage is for verse.

### 13.5 Taisho Reference Styling

```latex
\newcommand{\taishoref}[1]{{\small\sffamily\color{gray}{#1}}}
```

Taisho references are rendered in small sans-serif gray. This is a good visual distinction -- they are reference apparatus, not running text. The gray color (0.5) may be too light for print, however. Print tends to reproduce lighter than screen. Consider a darker gray (0.35-0.4) or using a lighter weight of the main font instead of sans-serif.

### 13.6 The `parskip` Package Issue

As noted in section 7, `\usepackage{parskip}` is loaded but then both `\parindent` and `\parskip` are manually overridden. The `parskip` package modifies list spacing and other internal parameters beyond just `\parindent` and `\parskip`. Some of these modifications may be desirable (tighter list spacing) or undesirable (altered footnote spacing). Either commit to the `parskip` paradigm (block paragraphs) or remove the package and set values manually, ensuring list spacing is acceptable.

---

## Summary of Issues by Priority

### Must Fix Before Publication
| # | Issue | Section |
|---|-------|---------|
| 2 | Inner margin too narrow (0.75") for bound book -- increase to 0.875"-1.0" | Geometry |
| 25 | ISBN missing (placeholder exists but not in LaTeX output) | Copyright |

### Should Fix (Professional Quality)
| # | Issue | Section |
|---|-------|---------|
| 3 | Equal inner/outer margins -- inner should exceed outer | Geometry |
| 19 | Auto-generated ToC loses descriptive fascicle summaries | ToC |
| 21 | No publisher/imprint on title page | Title Page |
| 33 | Abbreviations placement -- consider front matter per Chicago 1.44 | Back Matter |

### Consider (Polish)
| # | Issue | Section |
|---|-------|---------|
| 4 | Top margin tight (0.75") -- consider 0.8" | Geometry |
| 6 | Header rule may not match Shambhala aesthetic (they often omit it) | Headers |
| 9 | No ornament or rule below chapter title | Chapters |
| 17 | `parskip` package loaded but overridden -- remove or commit | Typography |
| 22 | "Edited by" ambiguous for translator credit | Title Page |
| 28 | No "Printed in [country]" on copyright page | Copyright |
| 32 | No `\brokenpenalty` set | Orphan/Widow |
| 34 | No glossary in print edition | Back Matter |
| 35 | No index (significant for scholarly work) | Back Matter |

### No Action Needed
| # | Issue | Section |
|---|-------|---------|
| 1 | Half title verso blank handling -- `openright` handles correctly | Front Matter |
| 5 | Em-dash page number style -- valid design choice | Headers |
| 7, 8, 10, 11, 12, 13, 14, 15, 16 | Various minor observations -- all acceptable | Multiple |
| 20, 23, 24, 26, 27, 29, 30, 31, 36 | Informational notes -- current approach is valid | Multiple |

---

## Overall Assessment

The template and build system represent solid, professional-quality book design. The core Chicago conventions are followed correctly: front matter sequence, chapter opening treatment, footnote placement, orphan/widow prevention, ToC formatting, and running header content. The EB Garamond font at 11pt with 1.15 line spacing is well-suited to the genre.

The two items requiring attention before publication are the inner margin (which will cause gutter problems on a bound 400+ page book) and the ISBN. Beyond those, the improvements are matters of polish -- the descriptive ToC, publisher line, and abbreviations placement would bring the book closer to a press-published scholarly translation.

The build pipeline architecture (Python preprocessing + pandoc + XeLaTeX) is well-engineered, with careful handling of the titlesec/fancyhdr interaction and footnote namespace collisions. The extensive inline documentation in both the template and build script demonstrates awareness of the technical pitfalls.

Grade: **B+** -- Solid scholarly book design with correct Chicago fundamentals. The geometry issue prevents an A; fixing the inner margin and adding the missing publication metadata would bring it to professional press quality.
