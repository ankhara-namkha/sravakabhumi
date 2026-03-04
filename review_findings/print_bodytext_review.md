# Print Body Text Formatting Review

**PDF:** `output/sravakabhumi_print.pdf` (252 pages, 6"x9" KDP paperback)
**Pages reviewed:** 30-50 (fascicle 26), 80-100 (fascicle 28), 145-165 (fascicle 30)
**Font:** EB Garamond 11pt body, 9pt footnotes, 8pt superscript note markers, 10pt chapter headers (italic), 10pt Taisho refs (LM Sans, gray)
**Date:** 2026-03-02

---

## 1. Hyphenation

**Overall assessment: ACCEPTABLE with minor concerns.**

Hyphenation is present throughout and generally well-managed by the LaTeX engine. Most pages have 1-5 hyphenated line endings, which is normal for justified text at this measure.

**Pages with highest hyphenation density (6+ breaks per page):**
- Page 30: 9 hyphenated lines (highest in sample)
- Page 157: 9 hyphenated lines
- Page 93: 8 hyphenated lines
- Pages 32, 42, 80, 94, 149, 156: 7 each
- Pages 39, 46, 99, 100, 158: 6 each

**Consecutive hyphenation runs (3+ in a row):**
- Page 42: 3 consecutive lines ending in hyphens (near "...pride-conduct, and (5) mindful-")
- Page 149: 3 consecutive lines (near "...shila-samvara) dwells in non-")
- Page 157: Three separate runs of 2 consecutive hyphens

These are borderline but not severe. No runs of 4+ consecutive were found.

**Notable ugly breaks:**
- Page 30: "Sravakab-humi's" (splitting a proper name across lines in footnote)
- Page 157: "samyak-" and "cor-" in consecutive lines (compound Sanskrit term split awkwardly)
- Page 157: "charya-" / "-ana" run (Sanskrit compound broken at unhelpful points)
- Multiple pages: Sanskrit compound terms broken mid-word (e.g., "kavadikara-bhojana", "tathagata-garbha") -- these are actually acceptable since the hyphen falls at a morpheme boundary

**Recommendation:** The hyphenation is within acceptable range for scholarly typesetting. Two pages (30, 157) are at the upper limit. Consider adding `\hyphenpenalty` adjustments or manual `\mbox{}` for the worst cases, particularly page 157 which has three runs of consecutive hyphens.

---

## 2. Margins

**Overall assessment: GOOD -- meets KDP requirements.**

**Measurements (from text bounding box analysis):**

| Page | Side | Gutter (spine) | Outside | Top | Bottom |
|------|------|---------------|---------|-----|--------|
| 30 | Even/verso | 0.729in | 0.620in | 0.136in* | 0.175in* |
| 31 | Odd/recto | 0.745in | 0.604in | 0.136in* | 0.175in* |
| 80 | Even/verso | 0.729in | 0.620in | 0.136in* | 0.175in* |
| 81 | Odd/recto | 0.745in | 0.604in | 0.136in* | 0.175in* |
| 145 | Odd/recto | 0.750in | 0.604in | 0.136in* | 0.175in* |
| 146 | Even/verso | 0.732in | 0.620in | 0.136in* | 0.175in* |

*Top/bottom measurements include running headers and page numbers, not just body text.

**KDP requirements for 252 pages:** 0.625in gutter minimum, 0.25in outside minimum.
- Gutter: 0.729-0.750in -- PASSES (comfortable margin above 0.625in minimum)
- Outside: 0.604-0.620in -- PASSES (well above 0.25in minimum)
- Text width: consistently 4.65in across all pages -- CONSISTENT

**Margin alternation:** Even/verso pages have wider right margin (gutter side); odd/recto pages have wider left margin (gutter side). The alternation is correctly implemented for two-sided printing.

**No text hits edges.** All content stays well within safe print area.

---

## 3. Paragraph Formatting

**Overall assessment: GOOD.**

- **Indentation:** First-line indent is consistent. Body text lines typically start at x=45pt (even pages) or x=54pt (odd pages). Indented paragraph openings start at x=61pt (even) or x=70pt (odd), giving approximately a 16pt (1.5em at 11pt) first-line indent. This is consistent across all three page ranges.
- **Paragraph spacing:** No extra space between paragraphs within the same section. Block-style (first-line indent only) is consistently used. Slight additional space appears before section headings.
- **Justification:** Text is fully justified throughout. No visible rivers or excessive word spacing noted in the rendered pages.
- **Consistency:** The formatting pattern is identical across fascicles 26, 28, and 30.

---

## 4. Footnotes

**Overall assessment: GOOD with one observation.**

- **Position:** Footnotes appear at the bottom of each page, below a horizontal separator rule.
- **Separator rule:** Present on all pages with footnotes. Consistently 144pt long (~2in), left-aligned to the text margin. Properly positioned.
- **Numbering:** Superscript numbers in body text (8pt, EBGaramond-Regular) link to footnotes below. Numbering appears sequential and correct.
- **Font size:** Footnote text is 9pt EBGaramond-Regular, clearly smaller than 10.9pt body text. Readable.
- **Chinese characters:** Microsoft YaHei at 9pt used for inline Chinese in footnotes. Renders correctly (visible on pages 30, 35, 45, etc.).
- **Footnote density:** Some pages are heavily footnoted (page 45 has 58 footnote-size spans, page 35 has 40). The footnotes can consume up to half the page in dense sections (particularly element differentiation in fascicle 27 and the Four Yogas in fascicle 28).

**One observation:** Some pages have centered horizontal lines that are section-break ornaments (166pt, centered), distinct from left-aligned footnote separators (144pt). These appear on pages 34, 38, 40, 41, 42, 45, 81, 82, 84, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 99, 100, 145, 146, 149, 150, 152, 154, 155, 156, 157, 159, 163, 165. These are Taisho reference section markers and are correctly distinguished from footnote rules by being centered and slightly longer.

---

## 5. Blockquotes/Verse

**Overall assessment: GOOD.**

Verse passages (uddana/verse summaries) are present on pages 33, 49, 86, and 92 within the sampled ranges.

**Page 33 verse formatting (representative):**
- Two verse passages identified ("First Verse and Commentary" and "Second Verse and Commentary")
- Verse text is in EBGaramond-Italic at 10.0pt (slightly smaller than 10.9pt body)
- Indented: verse lines start at x=75-76pt vs body text at x=54pt (approximately 21pt additional indent)
- Both visual inspection and font analysis confirm italic styling
- Clear visual distinction from surrounding body prose

The verse passages are properly set off from body text with:
1. Italic face (10pt vs 10.9pt regular body)
2. Additional left indentation (~0.3in beyond body indent)
3. Adequate whitespace before and after

---

## 6. Bold Text

**Overall assessment: CONCERN -- no bold text found.**

No EBGaramond-Bold font was detected on any of the 63 pages sampled. Q&A markers ("What is...", "Question:", "Answer:") are all set in EBGaramond-Regular at the same size as body text.

**Observed Q&A formatting:**
- "What is X?" questions begin paragraphs in regular weight
- "Question:" and "Answer:" markers are in regular weight
- Section sub-headings (e.g., "27.2 Purifying-Conduct Objects: Element Differentiation") appear in regular weight

**Impact:** The Q&A structure is still discernible through paragraph structure and the question-word pattern, but bold markers would improve scanability. This is a design choice rather than a defect -- many scholarly translations use this approach -- but if bold Q&A markers were intended, they are missing.

**Inline section headers** like "(5) The Space Element" and "Application to Pride-Conduct" on page 45 appear as inline bold-like labels within body text, but the font data shows EBGaramond-Regular. Some of these labels may be achieving visual weight through the surrounding whitespace rather than font weight.

---

## 7. Tables

**Overall assessment: N/A -- no tables found.**

No table structures (grid lines, vertical rules) were detected in any of the 63 sampled pages. The text uses numbered lists and prose enumerations instead of tabular layouts, which is appropriate for this content type.

---

## 8. Taisho References

**Overall assessment: EXCELLENT.**

Taisho references are consistently formatted across all three page ranges:
- **Font:** LMSans10-Regular (Latin Modern Sans) at 10pt -- distinct from body text's EB Garamond
- **Color:** RGB (127, 128, 127) -- medium gray, subtle but readable
- **Format:** Consistently `[T30.XXXXxNN]` pattern
- **Frequency:** Appear at major section breaks throughout (33 instances across sampled pages)
- **Placement:** Typically on their own line or at the start of a section, preceded by a centered horizontal rule

The sans-serif gray treatment effectively distinguishes these scholarly apparatus markers from the body text without being obtrusive. This is well-executed.

---

## 9. Orphans/Widows

**Overall assessment: MINOR ISSUES found.**

**Potential orphans (paragraph starting at page bottom with insufficient continuation):**
- **Page 40:** "Notes" label appears alone at bottom of page with large whitespace above. The actual footnote content is below the separator. This is a fascicle-end page with "End of Fascicle Twenty-Six" centered above, so the layout is intentional but the "Notes" heading with vast empty space looks unusual.
- **Page 146:** "30.5 The Four-Fold Investigation" appears as a section heading near the bottom of the page. The section content begins on the next page. This is acceptable -- section headings at the bottom with content following on the next page is standard.
- **Page 165:** "Notes" label at bottom of fascicle-end page, same pattern as page 40.

**Potential widows (single continuation line at page top):**
- **Page 82:** "10. The perception of death" -- this is actually a list item wrapping to the top of the page, not a true widow. The list continues below it.
- **Page 85:** "Permanent destruction of yoga refers to a person without lineage..." -- starts a new paragraph, not a continuation. Not a widow.

**Fascicle-end pages (40, 165):** These pages have body text ending in the upper quarter, followed by the centered "End of Fascicle" marker, decorative rules, and a "Notes" heading with the final footnotes at the very bottom. The large whitespace is by design but could look better if the footnotes were moved closer to the "Notes" heading rather than being pushed to the page bottom.

**LaTeX widow/orphan control** appears to be active -- very few genuine orphans or widows were found across 63 pages, suggesting `\widowpenalty` and `\clubpenalty` are set appropriately.

---

## 10. Lists

**Overall assessment: GOOD with one alignment inconsistency.**

Numbered lists are present on pages 80-82, 90-91, 145, 155, 158, and 160.

**Formatting:**
- Single-digit items (1-9): consistently indented, left-aligned
- List items are not hanging-indent style; they appear as regular indented paragraphs with the number
- Multi-line list items wrap correctly

**Alignment inconsistency between single-digit and double-digit numbers:**
- Items 1-8 on page 80: x=59.1pt
- Items 9 on page 81: x=68.1pt (shifted right by ~9pt)
- Items 10-11 on page 81: x=62.8pt (different from both)
- Second list items 1-9 on page 81: x=68.1pt
- Item 10 on page 82: x=53.8pt (shifted left compared to 1-9)

This means lists that span single and double-digit numbers have inconsistent left alignment. The numbers are not right-aligned to a fixed decimal point, nor are the text bodies consistently aligned. Items 10+ shift left (the "1" in "10" occupies the space where single-digit numbers were), but the text after the period does not line up with the text after the period in single-digit items.

**Recommendation:** Consider using a list environment with fixed-width number column (e.g., `\begin{enumerate}` with `\labelwidth` adjustment, or a custom list with `\settowidth` for double-digit numbers). This would ensure "1." and "10." produce text starting at the same horizontal position.

---

## 11. Overall Readability

**Overall assessment: PROFESSIONAL quality.**

**Line length:** Text width is consistently 4.65in (334pt), yielding approximately 73-84 characters per line depending on the content. This is within the ideal range (65-75 characters per line is often cited, but 80-85 is acceptable for scholarly text with justified alignment). The EB Garamond typeface at 11pt in this measure produces comfortable reading.

**Line spacing:** Body text line spacing measures approximately 15.5-15.6pt consistently, which at 10.9pt body size gives a ratio of about 1.43 (leading/font-size). This is slightly more generous than the stated 1.15 line-spacing specification, suggesting the 1.15 may refer to the LaTeX `\baselinestretch` factor applied to the default leading. The actual result is comfortable and readable.

**Visual texture:** The justified text blocks are even without visible rivers. EB Garamond's proportional character set works well at this measure.

**Page density:** Body text pages are well-filled. Footnote-heavy pages (e.g., pages 45, 87, 95) can have footnotes consuming 40-50% of the page, but the footnote text at 9pt remains readable and the separation from body text is clear.

**Running headers:** Present at top of pages in italic, alternating between book title (verso) and chapter title (recto). Small caps for "SRAVAKABHUMI: THE HEARER'S GROUND" on recto pages. These are well-positioned and unobtrusive.

**Page numbers:** Centered at bottom. Consistent across all pages.

**Fascicle transition pages (40, 165):** The "End of Fascicle" markers use centered italic text with decorative horizontal rules above and below. These are elegant and appropriate.

---

## Summary of Issues by Severity

### Should Fix (before print)
1. **List number alignment** (pp. 80-82, likely elsewhere): Single-digit and double-digit numbered items have inconsistent left-margin alignment. Fix with proper list environment configuration.

### Consider Fixing
2. **High hyphenation pages** (pp. 30, 157): These pages have 9 hyphenated lines each, with page 157 having three runs of consecutive hyphens. Consider manual intervention (rewording or `\mbox{}`) for the worst cases.
3. **Page 42 consecutive hyphens**: 3 consecutive hyphenated line endings. Borderline but visible.
4. **Fascicle-end page whitespace** (pp. 40, 165): The "Notes" heading sits alone with large whitespace above. The footnotes are pushed to the page bottom by the footnote mechanism. Consider whether an endnote approach or manual page break adjustment would look cleaner.

### Design Decisions (not defects)
5. **No bold for Q&A markers**: All Q&A text is in regular weight. If bold was intended, it is missing everywhere. If this is a design choice, it is consistent.
6. **Footnote density**: Some pages (particularly fascicle 27 element differentiation and fascicle 28 four yogas) have very dense footnotes. This is inherent to the scholarly content and managed well.

### No Issues Found
- Margins: All meet KDP requirements with comfortable clearance
- Paragraph formatting: Consistent and correct
- Footnote formatting: Professional, properly separated, readable
- Verse/blockquote styling: Correctly italicized and indented
- Taisho references: Excellent subtle gray sans-serif treatment
- Tables: None present (appropriate for this content)
- Orphans/widows: Very few, well-controlled by LaTeX
- Overall readability: Professional scholarly typesetting
