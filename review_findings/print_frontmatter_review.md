# Print PDF Front Matter Review

Reviewed: `output/sravakabhumi_print.pdf`, pages 1-20
PDF specs: 432 x 648 pts (6" x 9"), 252 pages total, EB Garamond 11pt

---

## 1. Page Order

**Expected:** half-title (recto) -> blank (verso) -> title page (recto) -> copyright (verso) -> contents (recto) -> introduction (recto)

**Actual:**
- Page 1 (recto): Half-title "The Hearer's Ground" -- CORRECT
- Page 2 (verso): Blank -- CORRECT
- Page 3 (recto): Combined title page + copyright -- BUG
- Page 4 (verso): Blank -- stale blank
- Page 5 (recto): Contents -- CORRECT placement
- Page 6 (verso): Contents continued -- CORRECT
- Page 7 (recto): Translator's Introduction -- CORRECT placement
- Page 9 (recto): Fascicle 26 opening -- CORRECT placement

**CRITICAL -- Title page and copyright page are merged (page 3).** The title ("Sravakabhumi: The Hearer's Ground") appears at the top, followed immediately by the subtitle, translator credit, copyright notice, CC license, Taisho source info, and Asanga attribution -- all on one page. Standard book convention requires:
- Page 3 (recto): Title page only (title, subtitle, author/translator)
- Page 4 (verso): Copyright page (copyright, license, ISBN, edition info)

The copyright material is currently presented as left-aligned body text rather than in the conventional copyright-page style (typically small type, bottom-of-page or vertically centered, with line breaks between elements).

Additionally, the LaTeX template does not use `\frontmatter` properly for the half-title and title page. Looking at the source, `00_titlepage.md` and `00_copyright.md` are separate files, but the build concatenates them as continuous markdown processed by pandoc. The copyright file lacks a heading (`#`), so it flows directly beneath the title page content without a page break.

## 2. Recto/Verso Placement

- Half-title on page 1 (recto) -- CORRECT
- Contents on page 5 (recto) -- CORRECT
- Introduction on page 7 (recto) -- CORRECT
- Fascicle 26 on page 9 (recto) -- CORRECT
- Blank pages (2, 4) have no headers/footers -- CORRECT

No issues with chapter-opening recto placement.

## 3. Alignment

### Title (page 3)
The main title "Sravakabhumi: The Hearer's Ground" is roughly centered (center offset +4.5pts from page center at 216pt). This is acceptable.

### Title page body text (page 3)
**BUG: Title page metadata is left-aligned, not centered.** The subtitle "From the Yogacarabhumi-sastra of Asanga" starts at x=53 (left margin) and all subsequent lines start at x=70. A proper title page should have all elements centered. Currently only the main title is centered; everything below it (subtitle, translator, copyright) is left-aligned body text with paragraph indentation. This looks like a regular text page, not a title page.

The "Licensed under Creative Commons..." line is broken across two lines with full justification, creating ugly spacing ("Licensed under Creative Commons Attribution-NonCommercial-" with large inter-word gaps). This would be better as ragged-right small type on a dedicated copyright page.

### Contents (page 5)
The "Contents" heading and yoga-place subheadings ("The Second Yoga Place", etc.) are centered -- CORRECT. Fascicle entries are left-aligned at x=54 -- CORRECT and consistent.

### Contents page formatting
**BUG: Bold formatting lost on fascicle names.** The source markdown uses `**Fascicle 26 -- Part One**` (bold), but the PDF renders all fascicle names in regular weight (EBGaramond-Regular, flags=4). The bold variant may not be loading correctly, or the EB Garamond variable font bold axis is not being activated properly. This makes it harder to visually distinguish fascicle names from their content descriptions.

## 4. Spacing

### Contents page
Spacing between fascicle entries is adequate (~28pts between groups). The yoga-place subheadings have good separation from surrounding entries (~38pts above). Overall the Contents page reads well.

### Introduction (page 7)
The section heading "Translator's Introduction" has proper top spacing (~80pts from page top to heading). The subheading "The Sravakabhumi in Context" has adequate spacing below (~12pts to first paragraph). The second subheading "Significance of This Translation" on the same page also has proper spacing.

### Body text (pages 9+)
Section headings (e.g., "26.1 Opening Questions and Summary Verse", "26.2 The Twenty-Eight Types of Persons") have adequate spacing. Taisho references in LMSans10 at 10pt are visually distinct. Footnotes are well-separated from body text with a proper rule.

## 5. Indentation

### First paragraphs after headings
- Page 7 (Introduction): First paragraph after "The Sravakabhumi in Context" starts at x=53 (flush left) -- CORRECT (no indent after heading)
- Page 7: Second paragraph starts at x=70 (indented) -- CORRECT
- Page 10: First paragraph after "26.2 The Twenty-Eight Types of Persons" starts at x=61 (indented 16pts) -- CORRECT (paragraph indent after section heading)

Indentation appears consistent throughout: `\parindent = 1.5em` (~16.5pts at 11pt).

### Contents page
The `\setlength{\parindent}{0pt}` command in the contents source is rendered as literal LaTeX in the output -- need to verify this. Looking at the PDF, the contents entries all start at x=54 (left margin), so the indentation reset appears to have worked. But the raw LaTeX command may be visible as text in some renderers.

## 6. Running Headers

### Front matter (pages 1-8)
- Pages 1, 3, 5, 7 (recto, with headings): No running header -- CORRECT (plain style suppresses header on chapter-opening pages)
- Pages 2, 4 (blank): No running header -- CORRECT
- Page 6 (verso, contents continued): "Sravakabhumi" (italic, 10pt) in left header -- CORRECT
- Page 8 (verso, introduction continued): "Sravakabhumi" (italic, 10pt) in left header -- CORRECT

### Body text (pages 9-20)
- Even pages (10, 12, 14, 16, 18, 20): "Sravakabhumi" in left header -- CORRECT
- Page 9 (chapter opening): No header -- CORRECT (plain style)
- Odd pages (11, 13, 15, 17, 19): **"CHAPTER 5. SRAVAKABHUMI: THE HEARER'S GROUND"** in right header

**BUG: Running header on recto pages shows "CHAPTER 5. SRAVAKABHUMI: THE HEARER'S GROUND" in all-caps italic.** This is the LaTeX `\leftmark` which captures the chapter title from `\chapter{}`. Problems:
1. The "CHAPTER 5." prefix is ugly and unnecessary -- standard book headers show just the chapter title.
2. The full text "CHAPTER 5. SRAVAKABHUMI: THE HEARER'S GROUND" is very long for a header -- it runs from x=136 to x=387, nearly the full text width.
3. The all-caps rendering appears to come from LaTeX's default `\MakeUppercase` on `\leftmark`. The template should override this.
4. The "5" is wrong -- this is the only chapter in the book (or rather, it should not have a chapter number at all since each fascicle is a section within a single work).
5. **Ideally the recto header should show the current fascicle or section name** (e.g., "Fascicle 26" or the section title), not the overall chapter title repeated on every page.

## 7. Page Numbers

### Front matter
- Page 1: "1" (Arabic) -- **BUG: Front matter should use Roman numerals (i, ii, iii...) or no visible page numbers.** The `\frontmatter` command in the template should switch to Roman numerals, but the PDF shows Arabic "1" on the half-title.
- Page 3: "3" (Arabic) -- Same issue.
- Page 5: "5" (Arabic) -- Same issue.
- Page 7: "7" (Arabic) -- Same issue.
- Page 8: "8" (Arabic) -- Same issue.

**BUG: All front matter pages show Arabic numerals instead of Roman numerals.** The template has `\frontmatter` and `\mainmatter` guards, but they may not be activating correctly via pandoc's `has-frontmatter` variable. If `has-frontmatter` is not set in the metadata, the `\frontmatter`/`\mainmatter` commands are never issued.

### Body text
- Page 9 onwards: Arabic numerals (9, 10, 11...) -- these continue from the front matter numbering rather than restarting at 1.

**BUG: Body text page numbers should restart at 1 (or at an appropriate number if front matter uses Roman).** Currently page 9 (Fascicle 26 opening) is numbered "9" instead of "1". This is because `\mainmatter` is either not being called or the front matter is not using `\frontmatter` properly.

### Placement
All page numbers are centered in the footer at y=621 -- CORRECT placement.

## 8. Typography

### Hyphenation
The template sets `\hyphenpenalty=300` and `\emergencystretch=2em`, which is reasonable. Spot-checking:
- Page 10: "skill-/ful" across lines in Contents -- acceptable
- Page 11: Normal hyphenation density in body text
- No excessive hyphenation observed in the sampled pages

### Justification issues
- Page 3 (title/copyright): "Licensed under Creative Commons Attribution-NonCommercial-" has visibly stretched inter-word spacing due to full justification of a long compound word. This line should be on a copyright page with ragged-right alignment.
- Page 11 (line at y=277): "who possesses dull faculties and functions sluggishly and feebly with respect to" -- normal spacing
- Page 12 (y=230): "manifestsinaccordancewiththoseobjects" -- **BUG: Missing inter-word spaces.** The text "manifests in accordance with those objects" is rendered with no spaces between words. This is likely a PDF rendering/extraction artifact of very tight justification, but it should be checked in the actual printed output. Same issue on page 12 at y=308.

Checking additional pages:
- Page 9 (y=472): "presentedand elucidated" -- missing space between "presented" and "and"
- Page 9 (y=472): "are ableto realize" -- missing space
- Page 13 (y=308): "structionandguidance, upondirectlyrealizingoneoftheshramanafruits" -- severe word-spacing collapse
- Page 15 (y=152): "Thosewhoattainparinirvanawithexertion" -- complete word-spacing collapse

**CRITICAL: Multiple lines throughout the body text show collapsed inter-word spacing (words running together).** This appears to be a typesetting bug where XeLaTeX is producing overfull lines with zero inter-word space rather than hyphenating or loosening the line. The `\tolerance=1500` and `\emergencystretch=2em` settings should normally prevent this. The issue may be related to EB Garamond's metrics or the variable font configuration. These lines would be unreadable in print.

### Orphaned headings
No orphaned headings observed in the first 20 pages.

### Widows/orphans
The template has `\widowpenalty=10000` and `\clubpenalty=10000` -- should prevent widows and orphans. No violations observed.

## 9. Title Page

**Current state (page 3):** The title "Sravakabhumi: The Hearer's Ground" is centered in 17.2pt EBGaramond at y=162 (about 2.25" from the top). Below it, left-aligned body text lists the subtitle, translator, editor, copyright, license, source, and attribution.

**Problems:**
1. Not a proper title page -- it is a combined title+copyright dump.
2. Subtitle and attribution info is left-aligned rather than centered.
3. No visual hierarchy between title, subtitle, translator, and copyright info -- everything is the same 10.9pt body font.
4. The title should be higher on the page (centered vertically in the upper third).
5. Missing: "Translated from the Chinese of Xuanzang" should be in a different size/style to create hierarchy.
6. A professional title page would show: Title (large), Subtitle (medium, italic), Author/Translator block (medium), Publisher info (small, bottom). Copyright belongs on the verso.

## 10. Copyright Page

**The copyright page does not exist as a separate page.** The copyright information (copyright notice, CC license, Taisho source info) appears on page 3 as a continuation of the title page. It should be on page 4 (verso of the title page).

**Missing standard copyright page elements:**
- ISBN (noted as placeholder in source -- acceptable for now)
- Edition statement (e.g., "First edition, 2026")
- "Printed in [country]" (required for KDP)
- Publisher or self-publishing attribution
- The CC license should have its own line with proper formatting
- Copyright page text is typically set in a smaller font (9-10pt), not body text size

---

## Summary of Issues by Severity

### Critical (must fix before print)
1. **Collapsed word spacing** -- Multiple body text lines show words running together with no spaces. This is a typesetting engine issue that would make the book unreadable.
2. **Title page / copyright page merged** -- No separate copyright page. The combined page looks unprofessional and violates standard book conventions.
3. **Arabic page numbers in front matter** -- Front matter shows "1, 3, 5, 7, 8" instead of Roman numerals. Body text continues at "9" rather than restarting at "1".

### Major (should fix)
4. **Running header text** -- Recto pages show "CHAPTER 5. SRAVAKABHUMI: THE HEARER'S GROUND" in all-caps. Should show fascicle title or a shorter descriptor without the "CHAPTER 5." prefix.
5. **Title page layout** -- Subtitle and metadata are left-aligned instead of centered. No typographic hierarchy. Does not look like a professional title page.
6. **Bold lost on Contents** -- Fascicle names render in regular weight despite bold markup in source. Makes the ToC harder to scan.

### Minor (nice to fix)
7. **Contents page: no page numbers** -- A standard ToC has dot leaders and page numbers for each entry. The current Contents is a descriptive overview (which is a valid design choice) but may frustrate readers looking for specific fascicles.
8. **Title page justification** -- The CC license line has stretched spacing due to full justification of a long compound word.
9. **Half-title page number** -- Page 1 shows "1" in the footer. Convention is no page number on the half-title.

---

## Recommended Fix Priority

1. Fix the word-spacing collapse (investigate EB Garamond variable font metrics with XeLaTeX; consider using static .otf files instead of .ttf variable fonts).
2. Split title page and copyright page into separate pages with `\newpage` or `\cleardoublepage` in the markdown/template.
3. Add `has-frontmatter: true` to `metadata-print.yaml` to activate `\frontmatter`/`\mainmatter` for proper page numbering.
4. Fix the running header by overriding `\chaptermark` to suppress "CHAPTER N." prefix and suppress `\MakeUppercase`.
5. Center all title page elements and add typographic hierarchy (larger subtitle, different styles for translator vs. copyright info).
6. Investigate bold rendering for EB Garamond -- the `BoldFeatures = {RawFeature={+axis={wght=700}}}` may not be working correctly.
