# Structural and Navigational Review: Sravakabhumi Print PDF (v2)

Reviewer: Structural Review Agent
Date: 2026-03-02
Reference standard: Shambhala Publications (Sadhana of Mahamudra, 2025 edition)
PDF: 256 pages, 6"x9" trim

---

## 1. PAGE NUMBERING SEQUENCE

### Front Matter (Roman numerals)

The front matter uses lowercase Roman numerals, which is correct. The sequence observed:

| Physical page | Content | Folio number |
|---|---|---|
| 1 | Half-title | (no number visible, `\thispagestyle{empty}`) |
| 2 | Blank verso | (no number visible) |
| 3 | Title page | (no number visible) |
| 4 | Copyright page | (no number visible) |
| 5 | Contents p.1 | **v** |
| 6 | Contents p.2 | **vi** |
| 7 | Introduction p.1 | **vii** |
| 8 | Introduction p.2 | **viii** |

**Assessment:** The Roman numerals start at "v" on the first Contents page (physical page 5). This is CORRECT. In standard book typesetting, the half-title is page i, its verso is ii, the title page is iii, the copyright is iv — all with page numbers suppressed. The Contents then correctly shows "v". The Shambhala reference confirms this convention: their Contents page shows "v" as well (visible in PXL_20260303_024525316.jpg). **No fix needed.**

**Severity:** N/A — Correctly implemented.

### Main Body (Arabic numerals)

- Page 9 (first body page, Fascicle 26 chapter opening) shows Arabic numeral **1** at bottom center. This is correct — `\mainmatter` resets the counter to 1 with Arabic numerals.
- Page 10 shows **2** in the running header (left/verso position). Correct.
- Page 11 shows **3** in the running header (right/recto position). Correct.
- The sequence continues consistently through the body pages sampled: 12, 17, 22, 32, 35, 42, 52, 72, 92, 103.

**Assessment:** Arabic numbering starts at 1 with `\mainmatter`, no gaps observed in sampled pages. The transition from Roman to Arabic is clean.

**Severity:** N/A — Correctly implemented.

### Back Matter (Arabic continued)

- Page 247 (Translation Notes) shows **239** at bottom center (chapter opening, plain style). This confirms back matter continues Arabic numbering without reset, which is correct (`\backmatter` does not restart page numbers).
- Pages 248-256 continue the Arabic sequence: 240, 241, 242, 243, 244, 245, 246, 247, 248.

**Assessment:** Correct. The back matter continues the Arabic sequence from the body.

**Severity:** N/A — Correctly implemented.

---

## 2. RUNNING HEADERS

### Format

- **Verso (even/left):** `2 — sravakabhumi` — page number, em-dash, book title in letterspaced small caps. Correct Shambhala style.
- **Recto (odd/right):** `sravakabhumi: the hearer's ground — 3` — chapter title in letterspaced small caps, em-dash, page number. Correct Shambhala style.
- **Header rule:** Thin 0.3pt rule below the header. Present and consistent.

The Shambhala reference (PXL_20260303_024551357.jpg, PXL_20260303_024556966.jpg, PXL_20260303_024600355.jpg) shows:
- Verso: `28 — the embodiment of all the siddhas` (page number — section title, small caps)
- Recto: `historical commentary: part one — 29` (chapter title — page number, small caps)

Our PDF matches this pattern exactly.

### Suppression on Chapter Openings

- pg009 (Fascicle 26 chapter opening): No running header, page number at bottom center. **Correct** — `plain` pagestyle applied.
- pg043 (Fascicle 27 chapter opening, pg 35): No running header visible, page number at bottom center. **Correct.**
- pg111 (Fascicle 29 chapter opening, pg 103): No running header, page number at bottom center. **Correct.**
- pg247 (Translation Notes chapter opening, pg 239): No running header, page number at bottom center. **Correct.**
- pg253 (Abbreviations chapter opening, pg 245): No running header, page number at bottom center. **Correct.**
- pg255 (Bibliography chapter opening, pg 247): No running header, page number at bottom center. **Correct.**

### Suppression on Front Matter

- Pages 1-4 (half-title through copyright): No headers or footers visible on pages 1-3. Page 4 (copyright) has no visible header. **Correct** — `\thispagestyle{empty}` on half-title, and `\fancyhead{}` clears headers for front matter.
- Pages 5-8 (Contents and Introduction): Footer page numbers (v, vi, vii, viii) centered at bottom. No running headers. **Correct** — front matter suppresses headers, shows only footer page numbers.

### Suppression on Blank Pages

- pg002 (blank verso after half-title): Completely blank, no page number, no header. **Correct** — `emptypage` package suppresses all content on blank pages before chapters.

### Running Header Content Accuracy

**Issue found:** The recto (odd) running header shows the BOOK TITLE ("sravakabhumi: the hearer's ground") rather than the CHAPTER/FASCICLE title. Looking at pages 3 (pg011), 17 (pg025), and other recto pages — they all show the full book title.

Compare to Shambhala: the recto header shows the CHAPTER title ("historical commentary: part one"), while the verso shows the SECTION title ("the embodiment of all the siddhas"). This creates useful wayfinding — you know which chapter and which section you are in.

In our PDF, BOTH headers essentially show the book title:
- Verso: `sravakabhumi` (the main title)
- Recto: `sravakabhumi: the hearer's ground` (the full title with subtitle)

This means the headers provide NO navigational value for locating yourself within the 240-page body. A reader flipping through cannot tell whether they are in Fascicle 26 or Fascicle 33.

**Root cause:** The `\chaptermark` is being set to the `\leftmark`, which captures the chapter title. Since each fascicle opens with a chapter command whose title is "Sravakabhumi: The Hearer's Ground" (the full title used in the markdown `#` heading), that is what appears in the running header.

**Recommendation:** The recto running header should show the fascicle/section identifier — e.g., "the second yoga place, part one" or "fascicle 26" — something that differentiates where the reader is. This requires either changing the chapter titles in the markdown or customizing `\chaptermark` to extract a shorter form.

**Severity: MAJOR** — Headers provide zero navigational value for a 240-page body text. A reader cannot orient themselves by glancing at the top of any page. This is the single most important structural deficiency.

---

## 3. CHAPTER OPENINGS

### Recto (Right/Odd) Start

- Fascicle 26 (pg009, body p.1): Opens on a recto page. **Correct.**
- Fascicle 27 (pg043, body p.35): Opens on a recto page. **Correct.**
- Fascicle 29 (pg111, body p.103): Opens on a recto page. **Correct.**
- Translation Notes (pg247, body p.239): Opens on a recto page. **Correct.**
- Abbreviations (pg253, body p.245): Opens on a recto page. **Correct.**
- Bibliography (pg255, body p.247): Opens on a recto page. **Correct.**

The `openright` class option ensures all `\chapter` commands force a recto start. Working correctly.

### Drop (Top Spacing)

- All chapter openings show approximately 80pt of blank space above the chapter title, consistent with `\titlespacing*{\chapter}{0pt}{80pt}{40pt}`. This is consistent across all observed chapter openings.
- The Shambhala reference shows a similar generous drop before chapter titles.

**Assessment:** Consistent and professional.

### Blank Pages Before Chapters

- pg002 (before title page): Blank, no page number. **Correct.**
- Any blank verso before a fascicle that forces a recto opening would be fully blank per the `emptypage` package. Not directly observable from the screenshot set since we do not have screenshots of every page, but the LaTeX configuration is correct.

**Severity:** N/A — Correctly implemented.

---

## 4. FASCICLE TRANSITIONS

### Visual Structure at Fascicle Openings

Each fascicle starts a new `\chapter`, which means:
1. It forces a recto (odd) page start via `openright`
2. It shows the main title centered at the top (after 80pt drop): "Sravakabhumi: The Hearer's Ground"
3. Below: centered subtitle "Yogacarabhumi-sastra, Fascicle XX"
4. Below: italicized attribution line
5. Below: horizontal rule
6. Below: "Basic Section" designation with yoga place identifier
7. Below: Chinese title
8. Below: horizontal rule
9. Below: First section heading

This is a clear, dignified fascicle opening that provides strong visual differentiation. Observed on pg009 (Fascicle 26), pg043 (Fascicle 27), and pg111 (Fascicle 29).

### Consistency

All observed fascicle openings follow the same template. The spacing, centering, rule weight, and element ordering are consistent.

### Within-Fascicle Section Breaks

- Sections (e.g., "26.2 The Twenty-Eight Types of Persons" on pg010/p.2) are formatted with centered headings, preceded by a horizontal rule. Clean and consistent.
- Subsections (e.g., "Commentary on the fourth tetrad" on pg060/p.52) use bold left-aligned headings. Consistent.

**Assessment:** Fascicle transitions are strong and professional.

**Severity:** N/A — Well implemented.

---

## 5. TABLE OF CONTENTS

### Structure and Hierarchy

The ToC occupies two pages (pp. v-vi). It is organized by Yoga Place (centered, larger text) with fascicle entries below (bold "Fascicle XX — Part N" headings with descriptive text).

Hierarchy:
1. **Yoga Place** (centered section header): "The Second Yoga Place", "The Third Yoga Place", "The Fourth Yoga Place"
2. **Fascicle** (bold heading with part number): "Fascicle 26 — Part One"
3. **Content summary** (regular text below each fascicle heading)

### Missing Elements

**CRITICAL: No page numbers in the ToC.** The Table of Contents lists fascicles and their content summaries but provides NO page numbers. A reader cannot use the ToC to navigate to any specific fascicle or section. They must flip through the book to find content.

Compare to the Shambhala reference (PXL_20260303_024525316.jpg): every ToC entry has right-aligned page numbers with dot leaders connecting the entry text to the number. This is the universal convention for print books.

**Root cause:** The ToC is hand-crafted in `00_contents.md` as a styled markdown document rather than being auto-generated by LaTeX's `\tableofcontents`. The hand-crafted ToC has no mechanism to look up page numbers — it is just descriptive text.

**Recommendation:** Either (a) switch to LaTeX's auto-generated `\tableofcontents` which will include page numbers, or (b) add page numbers manually after a build pass (fragile and unmaintainable), or (c) use a hybrid approach where the markdown is processed to inject LaTeX `\ref{}` commands that resolve to page numbers.

**Severity: CRITICAL** — A Table of Contents without page numbers is functionally useless for navigation. This is arguably the single highest-priority fix.

### Section-Level Detail

The ToC currently shows only fascicle-level entries with content summaries. It does NOT list individual section headings (e.g., "26.2 The Twenty-Eight Types of Persons", "28.11 The Four Foundations of Mindfulness"). For a 240-page scholarly translation with dozens of sections, this level of granularity is insufficient.

The Shambhala reference shows both chapters AND subsections in the ToC with page numbers for each.

**Recommendation:** Include section-level (h2) entries in the ToC with page numbers. This would significantly improve the book's usability as a reference work.

**Severity: Major** — Scholarly translations require section-level navigation. The current ToC provides only fascicle-level orientation, forcing readers to search for specific topics.

---

## 6. BACK MATTER

### Structure (pp. 239-248)

The back matter consists of three sections:
1. **Translation Notes** (pp. 239-244): Scope, source text, terminology, translation process, approach, register standard, limitations, acknowledgments
2. **Abbreviations and Conventions** (pp. 245-246): Text abbreviation table, Taisho reference format, romanization/diacritics, translation conventions
3. **Bibliography** (pp. 247-248): Primary sources, secondary sources, reference library

### Assessment

**Translation Notes (pp. 239-244):** Well-structured with clear subheadings. The section progresses logically from scope through methodology to acknowledgments. Running headers show "translation notes" in small caps — correct for a chapter-level back matter section. Content is appropriate for a scholarly translation.

**Abbreviations and Conventions (p. 245-246):** The abbreviation table (AN, DN, MN, SN, T, Vism) is well-formatted with horizontal rules separating header and body. Taisho reference format is clearly explained with a bold example. Translation conventions are presented as a bulleted list. Clean and functional.

**Bibliography (pp. 247-248):** Organized into Primary Sources, Secondary Sources, and Reference Library subsections. Proper bibliographic formatting with italicized titles. The final page (248) has content ending approximately mid-page, followed by blank space — acceptable for a final page.

### Missing Back Matter Elements

**No Index.** Scholarly translations of this nature typically include a subject index, a Sanskrit term index, or both. The Shambhala reference includes a "Notes" section, "Resources" section, "Glossary", and "Index" (visible in PXL_20260303_024534650.jpg). However, an index is a significant undertaking and may be intentionally deferred.

**No Glossary in Print.** The build script explicitly excludes `00_glossary.md` from the print edition (`include_glossary=False`). The Abbreviations page mentions "A consolidated glossary is provided as an appendix" — but this appendix is not present in the print PDF. This is a contradiction: the text promises a glossary that does not exist in the print edition.

**Recommendation:** Either (a) include the glossary in the print edition, or (b) change the Abbreviations text to say the glossary is available in the digital/online edition only.

**Severity: Major** — The text promises a glossary appendix that is missing from the print edition. This is a factual error in the published text.

---

## 7. CONSISTENCY

### Heading Formatting

- **Chapter titles** (h1): Large, centered, consistent across all fascicle openings and back matter sections. Consistent.
- **Section titles** (h2, e.g., "26.2 The Twenty-Eight Types of Persons"): Centered, regular size. Consistent across sampled pages.
- **Subsection titles** (h3, e.g., "Commentary on the fourth tetrad"): Left-aligned, bold, regular size. Consistent.
- **Inline bold headers** (e.g., "(1) Persons of dull faculties."): Bold inline at start of paragraph. Consistent.

### Margins and Text Block

- Inner margin: 0.75in (gutter side). Consistent.
- Outer margin: 0.625in. Consistent.
- Top/bottom margins: 0.75in/0.7in. Consistent.
- The text block position appears stable across all sampled pages.

### Font Usage

- Body text: EB Garamond throughout. Consistent.
- Running headers: Small caps, letterspaced. Consistent.
- Footnotes: Smaller size, separated by a 2-inch rule. Consistent.
- Taisho references: Sans-serif, gray. Consistent.
- Chinese characters: Microsoft YaHei. Appears in fascicle openings and occasional inline citations. Consistent.

### Footnote Treatment

- Footnotes appear at page bottom with superscript reference numbers.
- Footnote text is in a smaller font.
- A 2-inch horizontal rule separates footnotes from body text.
- Footnote spacing appears consistent.
- Footnote numbering is per-fascicle (prefixed to avoid collision), which means numbers restart with each fascicle. This is appropriate for a fascicle-based text.

### Horizontal Rules

- Section separators within fascicles: Centered, approximately half-linewidth. Consistent.
- Fascicle opening decorative rules: Full-width or near-full-width. Consistent.

**Severity:** N/A — Formatting is consistent throughout.

---

## 8. OVERALL PAGE COUNT AND STRUCTURE

### Page Accounting

| Section | Physical pages | Folio range |
|---|---|---|
| Half-title | 1 | i (suppressed) |
| Blank verso | 1 | ii (suppressed) |
| Title page | 1 | iii (suppressed) |
| Copyright | 1 | iv (suppressed) |
| Contents | 2 | v-vi |
| Introduction | 2 | vii-viii |
| **Front matter total** | **8** | **i-viii** |
| Body (Fascicles 26-33) | ~238 | 1-238 |
| Translation Notes | ~6 | 239-244 |
| Abbreviations | ~2 | 245-246 |
| Bibliography | ~2 | 247-248 |
| **Back matter total** | **~10** | **239-248** |
| **Grand total** | **~256** | — |

The book structure is sound: 8 pages front matter + 238 body + 10 back matter = 256 physical pages. For a 6"x9" scholarly translation, this is a reasonable and professional length.

### Structural Oddities

**None observed.** The front matter flows naturally from half-title through introduction. The body proceeds through fascicles in order. The back matter provides the expected scholarly apparatus (though with the missing glossary noted above).

---

## SUMMARY OF FINDINGS

### Critical (must fix before publication)

1. **ToC has no page numbers** — The hand-crafted Table of Contents provides no page references. A reader cannot navigate the book from the ToC. This defeats the purpose of a ToC entirely.

### Major (should fix before publication)

2. **Running headers have no navigational value** — Both verso and recto headers show variants of the book title. Neither shows the fascicle number or section, so a reader flipping through a 240-page body text cannot orient themselves. Recto headers should show the current fascicle/yoga place.
3. **ToC lacks section-level entries** — Only fascicle-level entries appear. For a scholarly reference work with dozens of sections, individual section headings with page numbers are expected.
4. **Glossary promised but missing in print** — The Abbreviations page states "A consolidated glossary is provided as an appendix" but the glossary is excluded from the print build. This is a factual error in the published text.

### Minor

5. **No index** — Scholarly translations typically include at least a basic subject/term index. This is a significant value-add for a reference work but understandable to defer.

### Enhancement (nice to have)

6. **ToC could use dot leaders** — If page numbers are added, connecting them to entry text with dot leaders (as in the Shambhala reference) would improve readability.
7. **Chapter titles could be more specific** — Currently every fascicle opens with "Sravakabhumi: The Hearer's Ground" as the chapter title. More specific titles (e.g., "The Second Yoga Place, Part One" or even just "Fascicle 26") would improve both the running headers and the chapter openings themselves.

### Working Well (no changes needed)

- Roman numeral sequence in front matter (correctly starts at v on Contents page)
- Arabic numeral sequence in body (correctly starts at 1)
- Back matter numbering (correctly continues Arabic, no reset)
- Running header suppression on chapter openings, front matter, and blank pages
- Chapter openings consistently on recto pages with proper drop spacing
- Fascicle transition pages are dignified and well-structured
- Heading hierarchy is consistent throughout
- Margins and text block position are stable
- Font usage is consistent and appropriate
- Footnote treatment is professional
- Back matter content (Translation Notes, Abbreviations, Bibliography) is well-organized
- Overall page count and structure are sound
