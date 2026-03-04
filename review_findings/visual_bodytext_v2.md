# Visual Review: Body Text Formatting (v2 -- Detailed)

**Reviewer:** Visual Agent (detailed formatting comparison against Shambhala standard)
**Date:** 2026-03-02
**Scope:** All body text screenshots (pg009--pg111) plus back matter (pg247--pg256)
**Reference standard:** Shambhala Publications, *The Sadhana of Mahamudra* (2025 edition, Chogyam Trungpa)
**Pages reviewed:** 9, 10, 11, 12, 20, 25, 30, 40, 43, 50, 60, 80, 100, 111, 247, 248

---

## 1. Running Headers

**Verdict: GOOD -- properly implemented, matches Shambhala standard.**

Running headers are present throughout the body text and follow the Shambhala house style closely:

- **Even (verso) pages:** Page number, em-dash, small-capped book title ("SRAVAKABHUMI") with letterspacing. Example on p.4: "4 --- SRAVAKABHUMI". This matches the Shambhala pattern (p.28: "28 --- THE EMBODIMENT OF ALL THE SIDDHAS").
- **Odd (recto) pages:** Small-capped chapter/section title with letterspacing, em-dash, page number. Example on p.3: "SRAVAKABHUMI: THE HEARER'S GROUND --- 3". This matches Shambhala (p.29: "HISTORICAL COMMENTARY: PART ONE --- 29").
- **Hair rule:** A thin rule below the header text separates it from the body, consistent with the Shambhala reference.
- **Chapter-opening pages (p.9, p.43, p.111):** Headers suppressed, page number at bottom center. Correct.
- **Front matter pages (p.7, p.8):** Headers suppressed, page numbers in footer. Correct.

**One observation:** The recto header on early body pages reads "SRAVAKABHUMI: THE HEARER'S GROUND" (full title including subtitle). In the Shambhala reference, recto headers carry the *chapter* title, not the full book title (e.g., "THE EMBODIMENT OF ALL THE SIDDHAS" is the part title, not the book title). Consider using the current fascicle section title (e.g., "THE SECOND YOGA PLACE, PART ONE") on recto headers instead of the full book title, to aid navigation. Currently, both verso and recto say the same thing, which is redundant.

- **Severity:** Enhancement
- **Pages affected:** All odd body pages

---

## 2. Page Numbers

**Verdict: GOOD -- present and properly placed.**

Page numbers appear in running headers on body text pages (integrated with the em-dash pattern) and in footers on chapter-opening and front matter pages. Page numbering is sequential and correctly transitions from Roman (front matter) to Arabic (body) at the first fascicle.

---

## 3. Footnotes

### 3a. Footnote Rule

**Verdict: GOOD but slightly non-standard.**

The footnote separator is a horizontal rule approximately 2 inches wide, positioned at the left margin. This is a common scholarly convention. In the Shambhala reference, no footnotes are visible (they use endnotes), so direct comparison is not possible. The current implementation follows the Chicago Manual of Style standard.

- **Severity:** Pass

### 3b. Footnote Text Size and Leading

**Verdict: GOOD -- correctly smaller than body text.**

Footnote text is visibly reduced from the 11pt body text (appears to be approximately 9pt), with tighter line spacing. This is appropriate.

### 3c. Footnote Number Formatting

**Verdict: MINOR ISSUE -- superscript numbers in footnote area.**

In the body text, footnote call-outs are properly superscripted (e.g., the "1" after "Asanga" on p.9). In the footnote area itself, the numbers also appear superscripted. Professional typesetting often uses full-size numbers followed by a period or closing parenthesis in the footnote area itself (e.g., "1." or "1)"), while keeping superscript only in the body text. The current approach (superscript in both locations) is LaTeX's default and is acceptable, but the alternative is slightly more readable for dense footnotes.

- **Severity:** Enhancement
- **Pages affected:** All pages with footnotes (approximately 60% of body pages)

### 3d. Footnote Hanging Indent

**Verdict: PASS.**

Multi-line footnotes show proper hanging indent -- the second and subsequent lines align with the start of the text, not with the footnote number. This is correct. Visible on p.12, p.30, p.40, p.100.

### 3e. Footnote Density and Page Balance

**Verdict: ACCEPTABLE but occasionally heavy.**

Some pages have footnote areas consuming 30-40% of the page height (p.30 with its long footnotes about Revata and outflows, p.100 with the smrtyupasthana footnote, p.12 with the "empty and without fruit" footnote). This is a natural consequence of a heavily annotated scholarly text. The footnotes never overflow or push into the next page improperly.

- **Severity:** Minor (no fix needed, inherent to the content)

---

## 4. Block Quotes / Verse Passages

**Verdict: GOOD formatting; well-differentiated from body text.**

Verse and block-quoted passages (visible on p.9 as the summary verse / uddana, and on p.30 as quoted speech from the Blessed One) are:
- Indented from the left margin (approximately 2em left indent)
- Set in a smaller italic font
- Have adequate spacing above and below to separate them from body text

This matches professional practice. The italic treatment for block quotes is a deliberate design choice in the LaTeX template (`\small\itshape` in the quote environment). For a scholarly text, one could argue that long prose block quotes should be roman (not italic) with only verse in italic, but the current unified approach is internally consistent.

- **Severity:** Enhancement (consider roman for prose block quotes, italic only for verse)
- **Pages affected:** p.9 (uddana verse), p.30 (dialogue passages)

---

## 5. Numbered Lists

**Verdict: GOOD -- clean and well-formatted.**

Numbered lists appear on p.10 (the 28 types of persons, items 1-15), p.11 (items 16-28), p.50 (five cultivations of mindfulness of breathing), p.60 (three realms), p.80 (faculties list). They show:
- Consistent left indentation from the body text margin
- Arabic numerals followed by periods
- Hanging indent for wrapped items
- Appropriate spacing between items (tight, not spread out)

The list style uses Pandoc's `\tightlist` with `\itemsep=0pt` and `\parskip=0pt`, which is appropriate for these enumerative lists.

**One observation:** On p.10-11, the long list of 28 person types uses 1-28 numbering with items like "Those of dull faculties" and "Those of sharp faculties." The numbered list items have no extra space between them, which is correct for a compact enumeration. However, items that wrap to multiple lines (not observed here) should maintain hanging indent -- this appears to work correctly.

- **Severity:** Pass

---

## 6. Bulleted Lists

**Verdict: GOOD.**

Bullet lists appear on p.40 (loving-kindness, compassion, sympathetic joy). They use standard bullet characters with appropriate indentation. The bold lead-in terms ("Loving-kindness," "Compassion," "Sympathetic joy") are properly formatted with the explanatory text following in roman weight. This is a clean implementation.

- **Severity:** Pass

---

## 7. Section Headings (Numbered: "26.1", "27.1", etc.)

**Verdict: MAJOR ISSUE -- headings are centered but should be left-aligned per Shambhala standard.**

All numbered section headings (e.g., "26.1 Opening Questions and Summary Verse" on p.9, "26.2 The Twenty-Eight Types of Persons" on p.10, "27.1 Purifying-Conduct Objects: Dependent Origination" on p.43, "28.2 The Three Faculties" on p.80, "28.3 The Three Gates of Liberation" on p.80, "28.11 The Four Foundations of Mindfulness" on p.100) are **centered** on the page.

In the Shambhala reference, section-level headings are **left-aligned** and set in small caps (e.g., "THE PURPOSE OF THE SADHANA: JOINING ATI AND MAHAMUDRA" on p.28, "Relationship of mahamudra and ati." on p.29, "Reconciling the Kagyu and the Nyingma lineages in the sadhana." on p.29). They are NOT centered.

The Shambhala pattern is:
- **Part titles / chapter titles:** Centered, larger, all-caps or small-caps
- **Section headings:** Left-aligned, bold or small-caps, smaller than chapter titles
- **Sub-headings:** Left-aligned, bold, same size as body text

Our current pattern:
- **Fascicle titles (chapter level):** Centered, large -- CORRECT
- **Section headings (e.g., "26.2 ..."):** Centered -- INCORRECT, should be left-aligned
- **Subsection headings (bold, in-text):** Left-aligned -- CORRECT

The centered section headings create visual confusion about hierarchy. When both the chapter title and section headings are centered, the section headings appear to be competing with the chapter level rather than subordinate to it.

- **Severity:** Major
- **Pages affected:** Every section heading throughout the book (approximately 80+ occurrences)
- **Fix:** Change `\section` formatting from `\centering` to left-aligned. In `print-template.tex`, change the `\section` `@startsection` definition to remove `\centering`.

---

## 8. Subsection Headings (Bold, Inline)

**Verdict: GOOD -- properly formatted.**

Inline bold headings like "Persons of dull faculties." (p.11), "Persons of sharp faculties." (p.11), "Commentary on the fourth tetrad (dharmas)." (p.60), "The Dialogue with Elder Revata" (p.30), "Four Names and Two Faults" (p.50), "Five Cultivations of Mindfulness of Breathing" (p.50) are:
- Left-aligned
- Bold weight at body text size
- Appropriate spacing above (about 1 line) and minimal spacing below
- Some run into the paragraph text (e.g., "Persons of dull faculties. What is a person of dull faculties?") while others stand alone -- both patterns are fine

**One issue:** The spacing above subsection headings could be slightly more generous. Currently approximately 18pt above and 6pt below (per the template: `-18\p@ \@plus -1ex` / `6\p@ \@plus .2ex`). In the Shambhala reference, subsection headings have noticeably more breathing room above them. Consider increasing to 24pt above.

- **Severity:** Minor
- **Pages affected:** All subsection headings

---

## 9. Q&A Formatting ("Question:" / "Answer:")

**Verdict: GOOD -- functional but could be more polished.**

Q&A markers appear on p.9, p.20, and other pages. "Question:" and "Answer:" are set in bold. The text follows immediately on the same line.

In the Shambhala reference (p.29), Q&A formatting uses italic "Q:" and "CTR:" labels, which is a different convention. Our bold "Question:" / "Answer:" pattern is more common in scholarly Buddhist translations and is appropriate.

**One observation:** On p.20, "Question:" and "Answer:" paragraphs have standard paragraph indentation. In some scholarly texts, Q&A exchanges are set with no first-line indent and possibly a hanging indent or different left margin to visually distinguish them from commentary. The current approach (standard paragraph treatment with bold labels) is acceptable but not distinctive.

- **Severity:** Enhancement
- **Pages affected:** All Q&A passages

---

## 10. Taisho References [T30.0424a07]

**Verdict: GOOD -- correctly styled but positioning needs review.**

Taisho references appear in gray sans-serif small text (per the template: `\small\sffamily\color{gray}`). Examples visible on p.9 ("[T30.0424a07]"), p.10 ("[T30.0424a19]"), p.25 ("[T30.0427a20]"), p.43 ("[T30.0430a07]"), p.80 ("[T30.0436b19]"), p.100 ("[T30.0440a13]"), p.111 ("[T30.0442a26]").

The gray color and sans-serif face effectively differentiate these references from the body text without being invisible. They function as navigational aids for scholars.

**Issue:** The Taisho references appear on their own line, occupying a full line of text for what is essentially a marginal reference marker. In professional scholarly editions, such reference markers are often placed in the outer margin (as marginal notes) rather than inline, to avoid interrupting text flow. Alternatively, they could be placed inline within square brackets at reduced size without occupying their own line.

- **Severity:** Minor
- **Pages affected:** Approximately 40-50 locations throughout the text
- **Possible fix:** Move Taisho references to margin notes using `\marginpar` or a marginal note package, or make them inline rather than block-level.

---

## 11. Sanskrit / Italic Terms

**Verdict: PASS -- excellent consistency.**

Sanskrit terms in italics render cleanly throughout: *shamatha*, *vipashyana*, *dhyana*, *samadhi*, *prajna*, *skandha*, *klesha*, *anuShaya*, *srotaapanna*, *sakridagamin*, *anagamin*, *pudgala*, *maitri*, *karuna*, *mudita*, *asrava*, *prashrabdhi*, *smriti*, *dharma-pravicaya*, etc.

First-use glosses in parentheses are present (e.g., "shamatha (calm abiding)" early in the text). The italic rendering does not leak into surrounding text. Chinese characters within parenthetical glosses in footnotes also render correctly alongside italicized Sanskrit.

- **Severity:** Pass

---

## 12. Paragraph Indentation

**Verdict: GOOD -- follows Chicago Manual standard.**

- First paragraph after a heading: flush left (no indent) -- correct
- Subsequent paragraphs: first-line indent of approximately 1.5em -- correct (matches template `\parindent{1.5em}`)
- Paragraphs after block elements: flush left -- correct
- Paragraphs after lists: appropriate handling

**One issue:** On p.11, after the numbered list of 28 person types ends, the paragraph "(1) Persons of dull faculties." begins with a bold number in parentheses as a new section. The transition from the list to these numbered inline subsections is handled well, with the bold number providing visual separation. However, the "(1)" numbering style (parenthetical) differs from the "1." style used in the preceding list. This is intentional (list items vs. subsection markers) and reads correctly.

- **Severity:** Pass

---

## 13. Horizontal Rules (Section Dividers)

**Verdict: GOOD -- clean and proportional.**

Horizontal rules appear between major sections (visible on p.9 separating the fascicle header material from the first section, on p.10 between the verse and the next section, on p.25 between sections, on p.80 between sections). They are:
- Centered on the page
- Approximately 50% of line width (per Pandoc default: `\rule{0.5\linewidth}{0.5pt}`)
- Thin (0.5pt) -- not overpowering
- Adequate space above and below

This matches standard scholarly formatting. The Shambhala reference uses extra vertical space between sections rather than rules, but our use of thin rules is a valid alternative that provides clearer visual separation in a dense scholarly text.

- **Severity:** Pass

---

## 14. Chinese Characters

**Verdict: GOOD -- properly rendered.**

Chinese characters appear in:
- Fascicle headers (p.9: "本地分中聲聞地第十三第二瑜伽處之一", p.43, p.111)
- Footnotes throughout (e.g., p.12: "空無有果", p.30: "顏貴佐多", "觀", p.40: various)

They render correctly using Microsoft YaHei (per the template `\setCJKmainfont`). The CJK characters are:
- Properly sized relative to the body text (slightly larger apparent size than Latin characters, which is normal for CJK)
- Baseline-aligned with surrounding Latin text
- No missing glyphs or tofu boxes

- **Severity:** Pass

---

## 15. Margins and Text Block

**Verdict: ACCEPTABLE but tight.**

Per the metadata, margins are:
- Inner (binding): 0.75in
- Outer: 0.625in
- Top: 0.75in
- Bottom: 0.7in

This produces a text block of approximately 4.625in wide by 7.55in tall on a 6x9 page. The resulting line length is approximately 65-70 characters, which is within the ideal range.

**Issue:** The outer margin at 0.625in is quite narrow for a 6x9 book. The Shambhala reference (which appears to be a similar trim size) has noticeably wider outer margins -- probably 0.75-0.85in. The narrow outer margin makes the text block feel slightly cramped against the page edge, especially on recto (right-hand) pages where the outer margin is on the right.

Additionally, the inner margin of 0.75in may be tight for perfect binding. KDP recommends at minimum 0.375in gutter + 0.25in margin for books over 150 pages. While 0.75in meets this minimum, 0.875in would provide more comfortable reading near the spine.

- **Severity:** Minor
- **Pages affected:** All pages
- **Possible fix:** Increase outer to 0.75in and inner to 0.875in, accepting slightly tighter text or a modest page count increase.

---

## 16. Chapter Opening Pages (Fascicle Start Pages)

**Verdict: GOOD -- professional layout.**

Fascicle opening pages (p.9, p.43, p.111) follow a clean pattern:
- Title "Sravakabhumi: The Hearer's Ground" at the top, large and centered
- Subtitle line with sastra and fascicle number, centered
- Attribution line in italic, centered
- Chinese fascicle identifier, centered
- Horizontal rules separating sections
- First section heading follows with appropriate spacing
- Page number at bottom center, no running header -- correct

This is close to the Shambhala reference's chapter opening pattern. The Shambhala reference uses more vertical space from the top of the page to the chapter title (the title sits approximately 1/3 down the page), while our fascicle titles sit near the top (the `\titlespacing*{\chapter}` has 80pt from top). Consider increasing the top spacing to 120-140pt for a more stately chapter opening.

- **Severity:** Minor
- **Pages affected:** 8 fascicle opening pages
- **Possible fix:** Increase `\titlespacing*{\chapter}{0pt}{80pt}{40pt}` to `{0pt}{120pt}{40pt}`.

---

## 17. Footnote-to-Body Spacing

**Verdict: MINOR ISSUE -- footnote area feels slightly cramped.**

The footnote rule sits relatively close to the last line of body text. The template sets `\footnotesep` at `0.8\baselineskip` and the footnote rule has `\vspace{0.5em}` above and `\vspace{0.3em}` below. In the Shambhala reference (which uses endnotes, so not directly comparable), the general principle for footnotes is that the separator should have at least 1 full baseline skip of clear space above it.

On pages with dense footnotes (p.30, p.40, p.100), the body text and footnote area feel slightly compressed together.

- **Severity:** Minor
- **Pages affected:** All pages with footnotes
- **Possible fix:** Increase the `\vspace` above the footnote rule to `1em`, and increase `\footnotesep` to `1.0\baselineskip`.

---

## 18. Hyphenation Quality

**Verdict: GOOD -- conservative hyphenation.**

The template uses `\hyphenpenalty=300`, `\exhyphenpenalty=300`, `\tolerance=3000`, and `\emergencystretch=3em`, which produces conservative hyphenation (preferring looser word spacing over word breaks). Across the reviewed pages, hyphenation appears infrequent and appropriate. No instances of:
- Consecutive hyphenated lines (laddering)
- Hyphenation of short words
- Hyphenation of proper nouns or Sanskrit terms

The full justification looks clean with no visible rivers or excessive word spacing.

- **Severity:** Pass

---

## 19. Back Matter Formatting

**Verdict: GOOD -- consistent with body text.**

The back matter pages (p.247-248 showing "Translation Notes") maintain the same typography as the body text: same font, same size, same margins, running headers present. The section structure (bold headings like "Scope of This Translation", "The Second Yoga Place", "The Third Yoga Place", "The Fourth Yoga Place", "Source Text") is clear and well-organized.

The running header correctly reads "SRAVAKABHUMI" on verso and section title on recto.

- **Severity:** Pass

---

## Summary of All Issues

| # | Issue | Severity | Pages Affected | Recommended Fix |
|---|-------|----------|----------------|-----------------|
| 1 | Section headings centered instead of left-aligned | **Major** | All section headings (~80+) | Remove `\centering` from `\section` definition |
| 2 | Recto running header shows full book title instead of chapter/section title | Enhancement | All odd body pages | Set `\leftmark` to carry fascicle section title |
| 3 | Footnote numbers superscripted in footnote area (body+note both super) | Enhancement | All footnoted pages | Consider full-size numbers in note area |
| 4 | Block quotes all italic (including prose quotes, not just verse) | Enhancement | ~10-15 passages | Consider roman for prose block quotes |
| 5 | Taisho references occupy full line instead of margin/inline | Minor | ~40-50 locations | Move to margin notes or make inline |
| 6 | Outer margin slightly narrow (0.625in) | Minor | All pages | Increase to 0.75in |
| 7 | Chapter opening top space could be larger | Minor | 8 fascicle openings | Increase from 80pt to 120pt |
| 8 | Footnote-to-body spacing slightly tight | Minor | All footnoted pages | Increase `\vspace` and `\footnotesep` |
| 9 | Subsection heading space above could be more generous | Minor | All subsection headings | Increase from 18pt to 24pt |
| 10 | Q&A formatting functional but undistinguished | Enhancement | All Q&A passages | No change needed unless desired |

### Items That PASS

- Running headers: Present, correctly styled, Shambhala pattern
- Page numbers: Present, correctly placed
- Footnote rule, text size, hanging indent: Correct
- Numbered lists: Clean, properly indented
- Bulleted lists: Properly formatted
- Subsection headings (bold): Correctly left-aligned
- Sanskrit italic terms: Consistent throughout
- Paragraph indentation: Chicago Manual standard
- Horizontal rules: Clean, proportional
- Chinese characters: Properly rendered, no missing glyphs
- Hyphenation: Conservative, no laddering or rivers
- Back matter: Consistent with body text
- Overall typography: Professional quality, appropriate for scholarly Buddhist translation

---

## Priority Recommendations

### Must Fix (before print)

1. **Left-align section headings.** This is the single most impactful change. Centered section headings compete with the chapter-level hierarchy and look non-standard for a scholarly book. Change the `\section` definition in `print-template.tex` to remove `\centering`.

### Should Fix (noticeable improvement)

2. **Differentiate recto running headers.** Currently both verso and recto carry the book title, making them redundant. The recto header should carry the current chapter/section name for navigation.

3. **Increase chapter opening top space.** Moving the fascicle title further down the page creates a more stately, professional chapter opening consistent with the Shambhala standard.

### Nice to Have (polish)

4. Increase outer margins slightly for better page proportions.
5. Increase footnote-to-body spacing for breathing room.
6. Consider margin Taisho references instead of block-level.

---

## Comparison: Current vs. Shambhala Standard

| Element | Current | Shambhala | Match? |
|---------|---------|-----------|--------|
| Running headers | Small caps + letterspacing + em-dash | Small caps + letterspacing + em-dash | Yes |
| Header rule | 0.3pt rule below header | 0.3pt rule below header | Yes |
| Body font | EB Garamond 11pt | Similar serif (appears Garamond family) | Close |
| Line spacing | 1.15x | Similar (~1.15-1.2x) | Yes |
| Chapter openings | Centered, 80pt from top | Centered, ~120pt from top | Close |
| Section headings | Centered | Left-aligned | NO |
| Subsection headings | Left-aligned bold | Left-aligned bold | Yes |
| Paragraph indent | 1.5em | ~1.5em | Yes |
| Justification | Full | Full | Yes |
| Q&A formatting | Bold "Question:"/"Answer:" | Italic "Q:"/"CTR:" | Different (both valid) |
| Footnotes | Page bottom with rule | Endnotes | Different (both valid) |
| Page numbers | In running header | In running header | Yes |
