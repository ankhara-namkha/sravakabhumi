# Back Matter Formatting Review (Pages 222-252)

Reviewed: Pages 222-252 of `output/sravakabhumi_print.pdf` (252-page KDP 6x9 paperback)

---

## 1. Back Matter Chapter Openings

### Translation Notes (page 243)
- **Starts on a new page: YES** -- page 243, which is a recto (odd) page. Good.
- However, there is a problem. Pages 241-242 are wasteful:
  - **Page 241**: Contains only the word "Notes" in the upper left, with the rest of the page completely blank. This appears to be a LaTeX-generated endnotes page that is empty because all footnotes are rendered at the bottom of their respective pages. This is a **CRITICAL defect** -- a nearly blank page with just "Notes" printed on it serves no purpose and looks like a production error. The running header still says "CHAPTER 12. SRAVAKABHUMI: THE HEARER'S GROUND" which is also wrong for what should be back matter.
  - **Page 242**: Completely blank (verso before the Translation Notes chapter opening). This is expected behavior for `\cleardoublepage` before a chapter, but only acceptable if page 241 is removed.

### Abbreviations and Conventions (page 249)
- **Starts on a new page: YES** -- page 249, which is a recto (odd) page. Good.
- Chapter title is properly centered and sized (large font, display style). Matches the Translation Notes chapter opening style.

### Bibliography (page 251)
- **Starts on a new page: YES** -- page 251, which is a recto (odd) page. Good.
- Chapter title is properly centered and sized, matching the other back matter chapters.

**Verdict on chapter openings:** All three back matter sections start on recto pages, which is correct for a professional book. The orphan "Notes" page (241) is a significant defect.

---

## 2. Section Heading Hierarchy

### Section headings (## level) -- e.g., "Scope of This Translation" (p.243), "Source Text" (p.244), "Terminology" (p.245), "The Translation Process" (p.245)
- Rendered as **centered, slightly larger font** (large size). Properly differentiated from body text.
- Consistent styling across all section headings in Translation Notes.
- Section headings in Abbreviations and Conventions ("Canonical Text Abbreviations," "Taisho Reference Format," "Romanization and Diacritics," "Translation Conventions") -- all centered, same style. Consistent.

### Subsection headings (### level) -- e.g., "The Challenge" (p.245), "The Approach" (p.246), "The Register Standard" (p.247), "Limitations and Hopes" (p.247), "Acknowledgments" (p.248)
- Rendered as **left-aligned, bold, normal size**. Properly differentiated from section headings (which are centered and larger).
- Clear visual hierarchy: chapter title (very large, centered) > section (large, centered) > subsection (normal, bold, left-aligned).

### Bibliography subsections -- "Primary Sources" (p.251), "Secondary Sources" (p.251), "Reference Library" (p.251)
- These appear as **centered, slightly larger** -- looks like they are rendered as section-level (##), not subsection-level (###). This is fine for the bibliography structure but differs from the Translation Notes subsections. Acceptable because bibliography sections are distinct categorical divisions.

**Verdict:** Heading hierarchy is well-differentiated and consistent within each back matter chapter. Minor inconsistency in bibliography sub-headings vs. Translation Notes sub-headings, but not a defect.

---

## 3. Four-Reviewer Bullet List (Translation Notes, "The Approach," p.246)

- **Bullet points are properly formatted:** Each of the four reviewer descriptions is a distinct bullet item with adequate inter-item spacing.
- **Bold labels: NO** -- The labels "A terminological reviewer," "A doctrinal reviewer," "A readability reviewer," and "A source fidelity reviewer" are **not bolded**. They appear in regular roman text, beginning each bullet with "A [type] reviewer..." This is a **MODERATE defect**. In professional typesetting, lead-in phrases in a descriptive bullet list should be bolded or italicized to help the reader scan. The current rendering makes the four roles harder to distinguish at a glance.
- **Bullet symbol:** Standard bullet (filled circle). Appropriate.
- **Indentation:** Properly indented from the left margin. Continuation lines wrap correctly within the indented block.
- **Spacing:** Adequate vertical space between bullets. The list is readable.

**Verdict:** Functionally correct but would benefit from bold lead-in phrases for each reviewer type.

---

## 4. Tables in Abbreviations (p.249)

- **Table is properly formatted:** The abbreviation table on page 249 uses proper LaTeX `booktabs`-style horizontal rules (top rule, header separator, bottom rule).
- **Column alignment:** "Abbreviation" column is left-aligned; "Full Title" column is left-aligned. Both are properly spaced with generous row height (the `\arraystretch{1.4}` from the template is working).
- **Readability:** Excellent. Clean two-column layout. Each abbreviation (AN, DN, MN, SN, T, Vism) is clearly paired with its full title.
- **Header row:** "Abbreviation" and "Full Title" column headers are present and visually separated from the data rows by a horizontal rule.

**Verdict:** Table formatting is clean and professional. No issues.

---

## 5. Taisho Reference Format Example (p.249)

- The blockquote example renders as:
  - **[T30.0424a07]** = *Taisho volume 30, page 0424, column a, line 07*
- The reference is in **bold brackets**, and the expansion is in **italics**. This is rendered as a blockquote (indented, smaller font, italic per the template's quote environment).
- Properly set off from the surrounding body text.

**Verdict:** Well rendered. The bold + italic combination clearly distinguishes the example from running text.

---

## 6. Bibliography Entries (pp.251-252)

### Primary Sources (p.251)
- **Asanga entry:** Author in roman. Title *Yogacarabhumi-sastra* followed by Chinese characters in brackets. Publication details follow standard format. The Chinese characters render correctly.
- **Shukla entry:** Properly indented as a continuation. Author, title in italics, series information, publication details. Standard bibliographic format.

### Secondary Sources (p.251)
- **Deleanu entry:** Author, title in italics, subtitle, volume count, series information. Properly formatted.

### Reference Library (pp.251-252)
- All nine reference translations are listed.
- **Titles are italicized: YES** -- *Mindfulness of Breathing*, *Satipatthana*, *In the Buddha's Words*, *The Path of Purification*, *Stages of Meditation*, *A Manual of Insight*, *Gateway to Knowledge*, *The Path of Individual Liberation*, *The Great Treatise on the Stages of the Path to Enlightenment*. All correctly italicized.
- **Hanging indent: PARTIALLY** -- The entries use a paragraph-indentation style where the first line is flush left and continuation lines are indented by approximately 1.5em (the standard `\parindent`). However, this is **not a true hanging indent** -- it appears to be standard paragraph indentation applied to continuation lines rather than a dedicated hanging indent (`\hangindent`). The visual effect is similar but not identical to Chicago Manual of Style bibliography format.
  - **MODERATE issue:** For a bibliography, a true hanging indent (first line flush, subsequent lines indented ~2em) would be more conventional. The current formatting works but is slightly informal.
- **Consistent style: YES** -- All entries follow the same pattern: Author. *Title*. Translator/Editor info. Place: Publisher, Year.
- **Line breaks between entries:** There appear to be small gaps between entries, but some entries (especially on p.251-252) appear to run close together. The Analayo and Bodhi entries on p.251 have visible spacing; the entries on p.252 are more tightly packed.

**Verdict:** Bibliography is functional and readable. Titles properly italicized, entries consistently styled. The hanging indent could be more pronounced for strict Chicago style, but this is a minor issue. Some entries on p.252 could use slightly more inter-entry spacing.

---

## 7. Overall Consistency with Body Text

- **Font:** Body text and back matter use the same EB Garamond font throughout. Consistent.
- **Font size:** Back matter body text matches the 11pt body text of the main translation. Consistent.
- **Line spacing:** Back matter matches the body text line spacing (set by `\linestretch` in the template). Consistent.
- **Margins:** Same KDP 6x9 geometry throughout. Consistent.
- **Footnotes:** The footnotes in the body text (pp.222-240) appear at the bottom of each page with proper footnote rules. The back matter (pp.243-252) has no footnotes, which is appropriate.
- **Paragraph indentation:** Back matter uses the same 1.5em paragraph indentation as body text. Consistent.

**Verdict:** Visual consistency between body text and back matter is excellent. The back matter does not look like a different document.

---

## 8. Running Headers

### Body text pages (222-240)
- **Even pages (verso):** "Sravakabhumi" in small italic. Correct.
- **Odd pages (recto):** "CHAPTER 12. SRAVAKABHUMI: THE HEARER'S GROUND" in small italic caps. Correct -- this is the `\leftmark` from the chapter title.

### Page 241 ("Notes" page)
- **Running header: "CHAPTER 12. SRAVAKABHUMI: THE HEARER'S GROUND"** -- This is **WRONG**. This page is technically part of the back matter endnotes; it should not carry the Chapter 12 running header. However, this is moot if the page is removed (see item 1).

### Translation Notes (pp.243-248)
- **Page 243 (chapter opening):** No running header, only page number at bottom center. Correct (plain style for chapter openings).
- **Page 244 (verso):** "Sravakabhumi" in italic. Correct.
- **Page 245 (recto):** "CHAPTER 13. TRANSLATION NOTES" in small italic caps. Correct.
- **Page 246 (verso):** "Sravakabhumi" in italic. Correct.
- **Page 247 (recto):** "CHAPTER 13. TRANSLATION NOTES" in small italic caps. Correct.
- **Page 248 (verso):** "Sravakabhumi" in italic. Correct.

### Abbreviations and Conventions (pp.249-250)
- **Page 249 (chapter opening/recto):** No running header, page number at bottom center. Correct.
- **Page 250 (verso):** "Sravakabhumi" in italic. Correct.

### Bibliography (pp.251-252)
- **Page 251 (chapter opening/recto):** No running header, page number at bottom center. Correct.
- **Page 252 (verso):** "Sravakabhumi" in italic. Correct.

**Note on chapter numbering:** Translation Notes is labeled "CHAPTER 13" in the running header. This implies it was set up as a numbered chapter in the LaTeX structure rather than an unnumbered back-matter section. For a back matter section, it would be more conventional to have just "TRANSLATION NOTES" without a chapter number. Similarly, "Abbreviations and Conventions" would be its own unnumbered chapter. This is a **MINOR issue** -- the numbering is not visible in the chapter title itself (which just says "Translation Notes"), only in the running header. But a careful reader may wonder why the back matter has chapter numbers.

**Verdict:** Running headers are correctly formatted and consistent, with the exception of the orphan "Notes" page (241) and the chapter-number artifact in running headers for back matter.

---

## 9. Final Page

- **Page 252** is the last page of the book.
- Content: Final bibliography entries (Buddhaghosa through Tsongkhapa/Lamrim Chenmo Translation Committee).
- The last entry is the Tsongkhapa entry, which ends cleanly about 60% down the page.
- Page number "252" appears at the bottom center.
- No dangling content, no orphaned lines, no blank trailing pages.
- The book ends on a verso (even) page. For KDP, this is acceptable -- KDP adds blank pages as needed to reach an even page count. However, ending on a verso means the last printed content faces a blank recto, which is slightly unusual. Ideally the book would end on a recto, but this depends on content length and is not a defect.

**Verdict:** Clean ending. No issues.

---

## 10. Translation Notes Content Quality

### Scope of This Translation (pp.243-244)
- Well-structured overview of the three Yoga Places covered (fascicles 26-29, 30-32, 33).
- Each section is described with appropriate technical detail -- key topics, Sanskrit terms with transliteration, and structural relationships.
- The note about what is NOT included (the supramundane path beyond fascicle 33) is important and well-placed.
- Reads naturally and informatively. No issues.

### Source Text (p.244)
- Clear identification of primary source (Xuanzang's Chinese, T1579, Vol. 30).
- Appropriate mention of Sanskrit (Shukla 1973) and Tibetan as secondary references.
- Clear statement of policy: Chinese is followed when sources diverge, with divergence noted.
- Taisho reference format explained.
- Reads well. No issues.

### Terminology (p.245)
- Concise explanation of the NTC register convention (Sanskrit preservation for common dharma-English terms).
- List of preserved Sanskrit terms is appropriate.
- Points reader to the glossary appendix and Abbreviations and Conventions for details.
- Reads well. No issues.

### The Translation Process (pp.245-248)

#### The Challenge (p.245)
- Honest framing of why no English translation exists (scale, technical density, specialized source language).
- Names the standard-setters (NTC, Padmakara) to establish the benchmark.
- Lists the convergence of expertise required.
- Well-written, appropriately humble without being self-deprecating.

#### The Approach (pp.246-247)
- Clear description of the computational multi-stage process.
- The four-reviewer descriptions are well-written and accurately describe each role.
- The priority hierarchy (source fidelity > doctrinal accuracy > terminological consistency > readability) is clearly stated.
- Statistics given (46 prose register rewrites, 329 footnotes) add credibility.

#### The Register Standard (p.247)
- Names the three benchmark translations (Nanamoli, Bodhi, Lamrim Chenmo Translation Committee).
- Clearly describes the target audience (80/20 practitioner/scholar).
- Distinguishes between taxonomic and practice-instruction registers.
- Well-written.

#### Limitations and Hopes (pp.247-248)
- Honest disclosure: "This is a machine translation, and it would be dishonest to present it as anything else."
- Balanced: acknowledges limitations while describing what the process offers beyond typical machine translation.
- Appropriate hope for future human revision.
- Mention of Creative Commons license and version-controlled repository is important.

#### Acknowledgments (p.248)
- Appropriate acknowledgment of Xuanzang, Shukla, reference translations, and the broader translation community.
- "Whatever merit this work may have belongs to that lineage of effort; its shortcomings are entirely its own." -- Good closing.

**Verdict on Translation Notes content:** Excellent. Well-structured, honest, appropriately detailed. Reads as a professional translator's note. No content issues found.

---

## Summary of Findings

### Critical (must fix)
1. **Orphan "Notes" page (p.241):** Nearly blank page with only "Notes" header. Appears to be an empty LaTeX endnotes section. Must be removed or suppressed.

### Moderate (should fix)
2. **Four-reviewer bullet labels not bolded (p.246):** "A terminological reviewer," "A doctrinal reviewer," etc. should have bold lead-in phrases for scannability.
3. **Bibliography hanging indent (pp.251-252):** Uses standard paragraph indentation rather than a true bibliographic hanging indent. Consider `\hangindent` formatting.
4. **Back matter chapter numbers in running headers:** "CHAPTER 13. TRANSLATION NOTES" appears in running headers -- the "CHAPTER 13" prefix is unconventional for unnumbered back matter sections.

### Minor (consider fixing)
5. **Bibliography inter-entry spacing (p.252):** Entries on the final page are somewhat tightly packed compared to p.251.
6. **Book ends on verso (p.252):** Not a defect per se, but ending on recto would be slightly more conventional.

### No issues found
- Back matter chapter openings all start on recto pages
- Section/subsection heading hierarchy is properly differentiated
- Abbreviation table is clean and professional
- Taisho reference blockquote is well-rendered
- Bibliography titles properly italicized, entries consistently styled
- Visual consistency with body text is excellent
- Running headers (apart from items 1 and 4) are correct
- Book ends cleanly without dangling content
- Translation Notes content is well-written and professional
