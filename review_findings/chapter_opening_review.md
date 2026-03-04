# Chapter Opening Design Review
*Sravakabhumi Print PDF — Shambhala/Wisdom Publications Standard*

---

## 1. Chapter Titles

**Current titles:**
- The Second Yoga Place, Part One
- The Second Yoga Place, Part Two
- The Second Yoga Place, Part Three
- The Second Yoga Place, Part Four
- The Third Yoga Place, Part One
- The Third Yoga Place, Part Two
- The Third Yoga Place, Part Three
- The Fourth Yoga Place

**Assessment: Acceptable but borderline for running headers.**

The chapter titles are structurally sound and editorially honest — they reflect the text's own organization (瑜伽處). The Shambhala model (e.g., *Stages of Meditation*, *The Jewel Ornament of Liberation*) tends to use chapter titles that are thematically distinctive, not just positional labels. These titles are positional labels only, which works for a scholastic text but feels thin for a chapter opening that must carry the weight of a major section break.

**Running header problem:** The recto header renders the chapter title in letterspaced small caps:
```
\textsc{\MakeLowercase{\leftmark}}
```
"The Second Yoga Place, Part One" becomes "the second yoga place, part one" in small caps — 35 characters plus spaces, pushing the limit before it crowds the page number with the em-dash separator. At 11pt on a 6"×9" page with standard inner/outer margins, this is workable but tight. "The Third Yoga Place, Part Three" (33 chars) is similarly marginal. No overflow expected at standard trim, but test carefully.

**Recommendation:** Consider shortened header-only versions via `\chaptermark` override, or use abbreviated forms: "Second Yoga Place I," "Second Yoga Place II," etc. The chapter opening page can retain the full title; the running header uses the short form. This is standard Wisdom Publications practice (e.g., the Lamrim Chenmo volumes use abbreviated running headers for long chapter names).

---

## 2. Metadata Block — Full vs. Slim Attribution

**Current design:**
- Fascicle 26 (first): full four-line attribution block — work title, Asanga credit (with scholarly footnote), Xuanzang credit, Taisho source, plus Chinese structural ID.
- Fascicles 27–33: slim — just "Fascicle XX" in italic + Chinese structural ID.

**Assessment: The balance is correct in principle; execution has one flaw.**

The decision to front-load full attribution on fascicle 26 and suppress repetition thereafter is editorially sound — it mirrors Shambhala/Wisdom house practice, where full bibliographic apparatus appears once (either on the copyright page or the first chapter opening) and is not repeated chapter by chapter. The Bodhi anthologies, Nanamoli's Visuddhimagga, and the Lamrim Chenmo all follow this pattern.

**The flaw:** The slim block for fascicles 27–33 reduces to only two lines of centered italic:
```
\textit{Fascicle 27}
[Chinese structural ID]
```
This is starkly minimal — more austere than even the sparsest Wisdom Publications chapter opening. The Chinese ID line (`本地分中聲聞地第十三第二瑜伽處之二`) provides scholarly grounding but no English content for the general reader. A practitioner opening to fascicle 29 mid-book sees only a fascicle number and an untranslated Chinese line before the horizontal rule and body text begin. No structural orientation ("This fascicle continues the Second Yoga Place...") is offered.

**Recommendation:** Add one English descriptor line to the slim block — the English equivalent of the structural title already present in the source markdown ("Basic Section: Shravaka Ground, Second Yoga Place, Part Two"). This does not repeat the full attribution but gives the reader a chapter-level anchor. Revised slim block:
```
\textit{Fascicle 27}
\textit{Basic Section: Shravaka Ground, Second Yoga Place, Part Two}
[Chinese ID line]
```
The source markdown already contains this text as an h2 heading ("## Basic Section: Shravaka Ground, Second Yoga Place, Part Two"); it is currently consumed entirely by the `metadata_re` regex and replaced rather than surfaced in the slim rendering. A one-line change to `metadata_replacement` when `not is_first` would include it.

---

## 3. Chapter Drop — 120pt from Top

**Current setting:**
```latex
\titlespacing*{\chapter}{0pt}{120pt}{40pt}
```

**Assessment: Slightly generous but defensible; could be refined.**

Standard Shambhala/Wisdom chapter drop on 6"×9" trim is typically 1.75–2.25 inches (126–162pt). At 120pt, this design sits just below the lower bound — slightly tighter than Shambhala standard, slightly more open than utilitarian academic typesetting. For a text with a metadata block below the chapter title (which adds ~3–5 lines of centered italic before the first body paragraph), the 120pt drop is appropriate: the chapter title + metadata + rule + first body paragraph will together occupy roughly the upper third of the page, which looks balanced.

If the metadata block is reduced (per recommendation above), the total drop-to-body distance shrinks and 120pt may feel a little cramped. In that case, consider increasing to 130–140pt.

The 40pt below-chapter spacing (space between chapter title and metadata block) is standard.

**Verdict:** Accept as-is if metadata block retains its current depth. Reconsider if metadata is trimmed.

---

## 4. Chapter Page Style — Bottom-Center Page Number, No Header

**Current setting (plain style):**
```latex
\fancypagestyle{plain}{
  \fancyhf{}
  \fancyfoot[C]{\small\thepage}
  \renewcommand{\headrulewidth}{0pt}
}
```

**Assessment: Exactly correct.**

Bottom-center page number with no running header on chapter opening pages is the universal Shambhala/Wisdom standard. Nanamoli's Visuddhimagga, Bodhi's anthologies, the Lamrim Chenmo volumes — all follow this convention. The implementation is clean. The `\small` sizing is appropriate (matches header page number size). No issues.

---

## 5. Transition from Metadata to Body — Horizontal Rule

**Current design:** A `---` (horizontal rule) appears after the metadata block and before the first section heading. The pandoc/LaTeX rendering produces:
```latex
\begin{center}\rule{0.5\linewidth}{0.5pt}\end{center}
```

**Assessment: Functional but visually weak.**

A centered half-line rule at 0.5pt is the default pandoc output and is thinner and shorter than the Shambhala/Wisdom convention. Shambhala titles typically use a full-width or 2–3 inch ornamental rule (sometimes a fleuron or typographic ornament) to mark the transition from chapter apparatus to body text. The Visuddhimagga uses no rule at all, relying on whitespace. The Lamrim Chenmo uses a short centered rule approximately 1.5–2 inches wide at ~0.8pt.

The 0.5\linewidth width (approximately 2.1 inches on a 6"×9" page with standard margins) is reasonable, but 0.5pt weight is visually insubstantial in Garamond at 11pt. Increasing rule weight to 0.4pt (the same as the footnote rule already defined) or 0.6pt would add presence without heaviness.

There is also a structural ambiguity: the rule after the metadata block is generated from a `---` in the markdown, but `---` also appears between sections within the body. The visual treatment is currently identical. Readers cannot distinguish the chapter-opening separator from mid-section breaks by appearance alone.

**Recommendation:** Override the chapter-opening rule in LaTeX to a distinct style — either slightly heavier weight, a different width (e.g., `\rule{1.5in}{0.6pt}` centered), or replace with a typographic ornament (❧ or ✦). The body `---` separators can remain as-is. This requires injecting a custom LaTeX command in `_restructure_fascicle_headings` where the `---` following the metadata block is emitted, replacing it with `\begin{center}\rule{1.5in}{0.6pt}\end{center}` or equivalent.

---

## 6. Title Type Setting

**Current setting:**
```latex
\titleformat{\chapter}[display]
  {\normalfont\Large\centering}
  {}
  {0pt}
  {\LARGE}
```

**Assessment: One concern.**

The two-size split (`\Large` for the format command, `\LARGE` for the title text itself) is a pandoc/titlesec idiom that produces centered `\LARGE` chapter titles with no chapter number. `\LARGE` at 11pt base = approximately 14.4pt displayed text. This is on the small side for a Shambhala chapter title — Wisdom Publications chapter titles typically run 16–18pt, sometimes with generous tracking.

More significantly: the `[display]` format places the label (empty here, since `secnumdepth=-1`) on one line and the title on the next. For short chapter titles like "The Fourth Yoga Place" this is fine. For "The Second Yoga Place, Part One," a single-line title at `\LARGE` on a 6"×9" page will typically fit, but it is close. Verify no line-breaking occurs in the chapter title for any of the eight titles.

**Recommendation:** Consider bumping to 14pt base or using `{\fontsize{16}{19}\selectfont}` for the chapter title specifically. This is a minor refinement, not a defect.

---

## 7. Font Choice — EB Garamond

**Assessment: Excellent.**

EB Garamond is a strong choice for this context — open-source, authentic Garamond revival, excellent CJK coexistence via xeCJK, and well-regarded in academic Buddhist publishing contexts (the BDRC digital publications use Garamond variants). The italic weight reads well for the metadata block. The static TTF approach (rather than variable font) is technically sound for XeLaTeX/HarfBuzz.

---

## Summary of Issues

| # | Issue | Severity | Recommended Action |
|---|-------|----------|--------------------|
| 1 | Chapter titles for running headers borderline long | Minor | Add `\chaptermark` shortened form for headers |
| 2 | Slim metadata block (fascicles 27–33) lacks English structural label | Moderate | Surface "Basic Section: X" line in slim rendering |
| 3 | Chapter-opening rule (0.5pt) too thin; visually identical to body section breaks | Moderate | Use distinct rule style for chapter-opening separator |
| 4 | Chapter title point size (`\LARGE` at 11pt base) slightly small for Shambhala register | Minor | Consider 14–16pt explicit sizing |
| 5 | Chapter drop (120pt) acceptable; monitor if metadata block changes | Watch | Adjust to 130–140pt if metadata block is trimmed |

Issues 2 and 3 are the strongest recommendations. Issue 2 is a reader-experience problem; issue 3 is a visual coherence problem. Both are localized code changes in `build.py` (`_restructure_fascicle_headings`).
