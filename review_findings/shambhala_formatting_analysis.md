# Shambhala Formatting Analysis

Comprehensive comparison: *The Sadhana of Mahamudra* (Shambhala Publications, 2025 edition) vs. current Sravakabhumi print PDF. With concrete LaTeX implementation recommendations.

Reference photos: 7 images of the Shambhala book (cover, title page, copyright/contents spread, contents/foreword spread, body text Q&A spread, close-up of verso header + section heading, close-up of recto header + Q&A formatting).

---

## 1. Running Headers

### What Shambhala Does

**Verso (left/even) pages:**
- Page number flush left, followed by an em-dash, then chapter/section title in LETTERSPACED SMALL CAPS
- Example: `28 — THE EMBODIMENT OF ALL THE SIDDHAS`
- A thin horizontal rule runs the full text width BELOW the header line
- The text is all small caps (not italic), letterspaced

**Recto (right/odd) pages:**
- Section/subsection title in LETTERSPACED SMALL CAPS, followed by an em-dash, then page number flush right
- Example: `HISTORICAL COMMENTARY: PART ONE — 29`
- Same thin rule below the header line
- The content is the current subsection or a more specific section identifier than the verso

**Chapter-opening pages:**
- No running header (suppressed), page number centered at bottom in roman numeral for front matter, arabic for body

### What We Currently Do

```latex
\fancyhead[LE]{\small\textit{Sravakabhumi}}
\fancyhead[RO]{\small\textit{\leftmark}}
\fancyfoot[C]{\thepage}
\renewcommand{\headrulewidth}{0pt}
```

- Verso: "Sravakabhumi" in small italic, no page number in header
- Recto: Chapter title in small italic, no page number in header
- Page number centered in footer on all pages
- No rule under header
- No em-dash separator
- No small caps — uses italic instead

### Recommended Changes

```latex
% === Headers and Footers ===
\usepackage{fancyhdr}

\pagestyle{fancy}
\fancyhf{}
% Verso: page number — BOOK TITLE in small caps
\fancyhead[LE]{\small\thepage\enspace\textemdash\enspace\textsc{\addfontfeatures{LetterSpace=8}Sravakabhumi}}
% Recto: SECTION TITLE in small caps — page number
\fancyhead[RO]{\small\textsc{\addfontfeatures{LetterSpace=8}\leftmark}\enspace\textemdash\enspace\thepage}
% Thin rule under header (Shambhala uses approx 0.3pt)
\renewcommand{\headrulewidth}{0.3pt}

% Strip "CHAPTER N." prefix from running headers
\renewcommand{\chaptermark}[1]{\markboth{\MakeUppercase{#1}}{}}
\renewcommand{\sectionmark}[1]{\markright{\MakeUppercase{#1}}}

% Plain style for chapter openings — page number bottom center only
\fancypagestyle{plain}{
  \fancyhf{}
  \fancyfoot[C]{\small\thepage}
  \renewcommand{\headrulewidth}{0pt}
}

% Empty style for blank pages
\fancypagestyle{empty}{
  \fancyhf{}
  \renewcommand{\headrulewidth}{0pt}
}
```

**Key differences:** Page number moves from footer to header (integrated with running head), small caps replace italic, em-dash separators, thin rule appears below header. The `\addfontfeatures{LetterSpace=8}` adds the characteristic Shambhala letterspacing for small caps headers.

**Note on \textsc with fontspec:** EB Garamond includes small caps glyphs. The `\textsc` command with fontspec will use the font's actual small cap glyphs via the `smcp` OpenType feature. If the build has issues, add `SmallCapsFont` to the font definition or use `\addfontfeatures{Letters=SmallCaps}` instead.

---

## 2. Title Page

### What Shambhala Does

- Title positioned in the upper third of the page, centered
- Title in large-ish serif, mixed case with key nouns capitalized: "The Sadhana of Mahamudra"
- Subtitle in italic below: "Teachings on Devotion and Crazy Wisdom"
- A short thin horizontal rule (about 2 inches) centered, separating title from author
- Author name below rule in regular weight: "Chogyam Trungpa"
- "FOREWORDS BY" in small caps, then names below
- Publisher logo (Shambhala emblem) centered at page bottom
- "SHAMBHALA" in letterspaced small caps below the logo
- Very generous white space — the page breathes

### What We Currently Do

Page 3 of our PDF shows:
- Title "Sravakabhumi: The Hearer's Ground" centered, large, but in the default `\LARGE` size from the chapter title format
- Subtitle information left-aligned: "*From the Yogacarabhumi-sastra of Asanga*", "Fascicles 26-33", "Translated from the Chinese of Xuanzang (T1579)", "English translation edited by Ankhara"
- The subtitle block is left-aligned, not centered
- No horizontal rule separating title from credits
- No publisher attribution at bottom
- The layout reads like the beginning of a chapter rather than a dedicated title page

### Recommended Changes

Rewrite `translation/00_titlepage.md` and add LaTeX raw blocks:

```markdown
\thispagestyle{empty}

\begin{center}

\vspace*{2.5in}

{\Large\textit{Sravakabhumi}}

\vspace{0.3em}

{\LARGE The Hearer's Ground}

\vspace{1em}

{\normalsize\textit{From the Yogacarabhumi-sastra of Asanga}}

\vspace{2em}

\rule{2in}{0.4pt}

\vspace{2em}

{\normalsize Translated from the Chinese of Xuanzang}

\vspace{0.5em}

{\small\textsc{English translation edited by}}\\
{\normalsize Ankhara}

\vfill

\end{center}

\newpage
```

**Key changes:** Everything centered. Sanskrit title in large italic above the English title. Short horizontal rule separating title block from attribution. Generous vertical spacing. `\vfill` pushes content upward from center rather than being anchored to top. The hierarchy is: Sanskrit title (italic) > English title (largest) > source attribution (italic) > rule > translator credit.

---

## 3. Copyright Page

### What Shambhala Does

- Text positioned at TOP of page, flush left
- Publisher address block at top: company name, street, city/state/zip, URL
- Small font throughout (approximately 8-9pt)
- Copyright notices with standard (c) symbol and years
- Source attributions in regular text with italic for book titles
- "Cover art" and "Cover design" credits
- "All rights reserved" notice
- Print number line (9 8 7 6 5 4 3 2 1)
- "Printed in the United States of America"
- Paper/distribution statement
- LIBRARY OF CONGRESS header in letterspaced small caps
- LOC cataloging data in even smaller font
- No decorative elements whatsoever — purely informational

### What We Currently Do

Page 4 of our PDF shows:
- Copyright text in regular body font (11pt — same as body text, too large)
- Standard paragraph formatting with indent
- Content is adequate but visually the font is too large and has paragraph indents (copyright pages never use paragraph indents)

### Recommended Changes

Rewrite `translation/00_copyright.md` with LaTeX:

```markdown
\thispagestyle{empty}

\begin{flushleft}
{\footnotesize

English translation copyright \textcopyright{} 2025--2026 Ankhara

\vspace{0.5em}

Licensed under Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0)

\vspace{1em}

English translation from the \textit{Taisho Shinshu Daizokyo}, Vol.\ 30, No.\ 1579

Chinese translation by Xuanzang, 648 CE

Original composition attributed to Asanga (c.\ late 4th--early 5th century CE)

\vspace{1em}

% ISBN placeholder — print edition\\
% ISBN placeholder — ebook edition

}
\end{flushleft}

\newpage
```

**Key changes:** `\footnotesize` (approx 9pt at 11pt base) for the entire copyright page. Flush left, no paragraph indent. Short `\vspace` gaps between logical blocks instead of full paragraph spacing. This is the standard scholarly/trade book copyright page layout.

**Template-level support:** Add to print-template.tex to suppress indent on copyright page:

```latex
% Copyright page helper — no indent
\newenvironment{copyrightpage}{%
  \thispagestyle{empty}%
  \footnotesize%
  \setlength{\parindent}{0pt}%
  \setlength{\parskip}{0.5em}%
}{\newpage}
```

---

## 4. Table of Contents

### What Shambhala Does

- "CONTENTS" as heading in LETTERSPACED SMALL CAPS, centered, with generous space below (approximately the same as a chapter title)
- Front matter entries (Foreword, Introduction) listed with page numbers in lowercase roman numerals, right-aligned
- NO dot leaders — clean white space between entry and page number
- Part titles in italic: "*Part One: The Embodiment of All the Siddhas*"
- Chapter numbers and titles in regular weight, indented slightly from the part titles
- Back matter entries (Afterword, Appendices, Glossary, Index) at same indent as chapters
- Sub-entries under "Appendices" indented further, with SMALL CAPS for "HUM:" label
- Page numbers right-flush, in regular weight, aligned in a clean column
- Generous vertical spacing between parts; tighter spacing between chapters within a part
- The overall effect is airy, elegant, and easy to scan

### What We Currently Do

Page 5 of our PDF shows:
- "Contents" centered in the standard chapter title format (not small caps)
- "The Second Yoga Place" as a centered section heading (like a chapter sub-section)
- Fascicle entries as bold left-aligned subsection headings: **Fascicle 26 — Part One**
- Content descriptions as regular body text paragraphs below each fascicle heading
- NO page numbers at all — this is a manual ToC, not a LaTeX-generated one
- No dot leaders, no right-aligned page numbers
- The ToC looks like a descriptive overview rather than a navigable table of contents

### Recommended Changes

This requires the most significant structural change. The current approach of a manually-composed markdown ToC without page numbers is not functional for a print book. Two options:

**Option A: Use LaTeX auto-generated ToC (preferred for accurate page numbers)**

Replace the contents markdown entirely and use `\tableofcontents` in the template with custom formatting:

```latex
% === Table of Contents ===
\usepackage{tocloft}

% "CONTENTS" heading in letterspaced small caps
\renewcommand{\contentsname}{\hfill\textsc{\addfontfeatures{LetterSpace=10}Contents}\hfill}
\renewcommand{\cftaftertoctitle}{\hfill}

% No dot leaders
\renewcommand{\cftdot}{}
\renewcommand{\cftchapdotsep}{\cftnodots}
\renewcommand{\cftsecdotsep}{\cftnodots}

% Chapter entries: regular weight, not bold
\renewcommand{\cftchapfont}{\normalfont}
\renewcommand{\cftchappagefont}{\normalfont}

% Section entries: indented
\setlength{\cftsecindent}{1.5em}
\setlength{\cftsubsecindent}{3em}

% Vertical spacing
\setlength{\cftbeforechapskip}{0.5em}
\setlength{\cftbeforesecskip}{0.2em}
```

**Option B: Enhanced manual ToC with page number placeholders (if page stability is wanted)**

Keep the manual ToC but add right-aligned page numbers with `\dotfill` or clean spacing, and structure it to match the Shambhala style. This requires manual page number updates after each build — fragile and not recommended.

**Recommendation:** Option A is strongly preferred. It requires the chapter/section headings in the fascicle files to be properly structured so LaTeX can auto-generate entries. The descriptive content summaries currently in the ToC would be lost, but those summaries are better suited for a separate "Overview" page or the introduction.

---

## 5. Chapter Openings

### What Shambhala Does

- "FOREWORD" in LARGE LETTERSPACED SMALL CAPS, centered, positioned about 1/3 down the page from top
- Generous drop from page top to title — approximately 2.5-3 inches of white space above
- No chapter number visible (the word "FOREWORD" IS the chapter indicator)
- Body text begins after approximately 1.5 inches of space below the title
- First paragraph: NO indent (standard typographic convention for paragraphs following a heading)
- Subsequent paragraphs: standard indent (~1.5em)
- No decorative elements (no ornamental rules, no drop caps in this edition)
- The simplicity is the design — the white space does the work

### What We Currently Do

Page 9 (our first fascicle page) shows:
- "Sravakabhumi: The Hearer's Ground" as a large chapter title
- "Yogacarabhumi-sastra, Fascicle 26" as subtitle
- Then a block of italicized source attribution text
- Then "Basic Section: Shravaka Ground, Second Yoga Place, Part One"
- Then Chinese characters
- Then a section heading "26.1 Opening Questions and Summary Verse"
- Then Taisho reference
- Then "Question:" bold label followed by text

The chapter opening is VERY dense — it packs title, attribution, Chinese, section heading, and body text all into the first page. There is minimal breathing room.

**Spacing values from template:**
```latex
\titlespacing*{\chapter}{0pt}{80pt}{40pt}
```
80pt above + 40pt below = adequate but the content below fills it immediately.

### Recommended Changes

```latex
% Chapter title: letterspaced small caps, centered, generous top drop
\titleformat{\chapter}[display]
  {\normalfont\centering}
  {}
  {0pt}
  {\Large\textsc{\addfontfeatures{LetterSpace=6}}}
\titlespacing*{\chapter}{0pt}{100pt}{50pt}

% Suppress first paragraph indent after chapter/section headings
\usepackage{indentfirst}  % Remove this if present — we want NO indent after headings
% Instead:
\makeatletter
\let\@afterindentfalse\@afterindenttrue
\@afterindentfalse
\makeatother
```

**Alternative approach for first-paragraph suppression** (simpler, using titlesec):

```latex
% titlesec already loaded — add [indentafter] option or handle manually
% The cleanest approach: redefine \chapter to suppress indent on first para
\usepackage{etoolbox}
\apptocmd{\@afterheading}{\@afterindentfalse}{}{}
```

**Note:** The current fascicle opening pages are very dense because they include source attribution, Chinese characters, and section numbering all on the first page. Consider moving the Chinese-text citation and source attribution to a separate, quieter title page for each fascicle, then starting the translation text on the following recto page. This would more closely match Shambhala's generous chapter openings.

---

## 6. Body Text

### What Shambhala Does

- Serif font — appears to be a Garamond variant (possibly Adobe Garamond Pro or similar), very close to what EB Garamond provides
- Size approximately 10.5-11pt
- Leading (line spacing) approximately 13-14pt — about 1.25-1.3x the font size
- Paragraph indent approximately 1-1.2em (relatively modest)
- Full justification with good word spacing (minimal rivers)
- Line length approximately 27-30 characters per line on a 5-inch text block — well within the 60-75 characters per line ideal
- Text block appears to be approximately 4.0-4.25 inches wide

### What We Currently Do

- EB Garamond at 11pt — good choice, similar to Shambhala's font
- Line stretch 1.15 — slightly tight compared to Shambhala's more generous leading
- Paragraph indent 1.5em — slightly larger than Shambhala
- Geometry: inner 0.75in, outer 0.625in on a 6in page = text width of 4.625in
- This gives a slightly wider text block than Shambhala, potentially pushing line lengths to 70+ characters

### Recommended Changes

```yaml
# metadata-print.yaml adjustments
linestretch: 1.2     # Was 1.15 — more generous leading, closer to Shambhala
```

```latex
% print-template.tex adjustments
\setlength{\parindent}{1.2em}  % Was 1.5em — slightly more modest indent
```

**Margin adjustment for narrower text block:**

```yaml
geometry:
  - paperwidth=6in
  - paperheight=9in
  - inner=0.8in      # Was 0.75in — slightly more inner gutter
  - outer=0.7in       # Was 0.625in — more generous outer margin
  - top=0.7in         # Was 0.6in — room for the running head
  - bottom=0.7in      # Was 0.6in — more breathing room
```

This would give a text width of 4.5in (down from 4.625in) and text height of 7.6in (down from 7.8in). This is a modest tightening that brings line lengths and vertical density closer to the Shambhala standard.

**Note:** The current text block is not dramatically different. The main visual difference between our body text and Shambhala's is the leading (1.15 vs ~1.25) and the margin proportions, not the font choice.

---

## 7. Section Headings Within Chapters

### What Shambhala Does

- **Major section headings:** Bold, small caps, mixed-case, left-aligned, with generous space above (~18pt) and modest space below (~8pt)
  - Example: "THE PURPOSE OF THE SADHANA: JOINING ATI AND MAHAMUDRA" — bold small caps, left-aligned
- **Sub-sections:** Bold, title-case, regular caps (not small caps), same size as body text
  - Example: "Relationship of mahamudra and ati." — bold, regular case, followed by a period, text continues on same line or next line
- **Minor headings:** Sometimes italic or bold in the flow of text
- No numbering visible — Shambhala prefers descriptive headings without numerical prefixes

### What We Currently Do

```latex
\titleformat{\section}
  {\normalfont\large\centering}
  {} {0pt} {\large}
\titlespacing*{\section}{0pt}{24pt}{12pt}

\titleformat{\subsection}
  {\normalfont\normalsize\bfseries}
  {} {0pt} {}
\titlespacing*{\subsection}{0pt}{18pt}{6pt}
```

- Sections: large, centered, regular weight — reads like a subtitle rather than a section heading
- Subsections: bold, left-aligned, normal size — this is actually close to Shambhala's sub-section style

Looking at page 12 of our PDF: "26.2 The Twenty-Eight Types of Persons" — bold, left-aligned, with a Taisho ref on its own line above. This is similar in spirit to Shambhala but we have the numbered prefix "26.2" which Shambhala would not use.

### Recommended Changes

```latex
% Section headings: bold small caps, left-aligned, generous spacing
\titleformat{\section}
  {\normalfont\normalsize\bfseries\scshape}
  {}
  {0pt}
  {}
\titlespacing*{\section}{0pt}{28pt}{10pt}

% Subsection headings: bold, left-aligned, normal size
% (current is already close — adjust spacing only)
\titleformat{\subsection}
  {\normalfont\normalsize\bfseries}
  {}
  {0pt}
  {}
\titlespacing*{\subsection}{0pt}{20pt}{8pt}
```

**Note on section numbering:** Shambhala does not use numbered sections (26.1, 26.2, etc.). Our project uses these for scholarly traceability to the Chinese source, which is a different convention from Shambhala's trade-book approach. Keep the numbers for our project since this is a scholarly translation — they serve a functional purpose (cross-referencing with the Taisho). But consider making the number less prominent:

```latex
% If section numbers are rendered by the heading format:
% De-emphasize the number while keeping the descriptive title prominent
\titleformat{\section}
  {\normalfont\normalsize\bfseries\scshape}
  {\normalfont\small\thesection\enspace}
  {0pt}
  {}
```

---

## 8. Q&A Formatting

### What Shambhala Does

This is one of the most distinctive elements in the Shambhala book:

- **Questions:** Prefixed with italic "*Q:*" (or italic "*Q.*"), followed by the question text in italic. The Q and the text are both italic.
  - The question text wraps normally with standard indent for continuation lines
  - Questions are often full paragraphs

- **Responses:** Prefixed with italic "*CTR:*" (Chogyam Trungpa Rinpoche), followed by the response text in regular roman. Only the "CTR:" label is italic.

- **Indentation:** The Q&A block appears to use the same paragraph indent as regular body text. The Q:/CTR: labels sit at the start of the paragraph where the indent would be.

- **Spacing:** Standard paragraph spacing between Q and A, and between Q&A pairs. No extra space — the italic Q: and roman CTR: labels provide sufficient visual differentiation.

- **Block-level treatment:** Q&A sections are set off from surrounding text by a bold subheading (e.g., "Discussion") and standard paragraph spacing. They are NOT indented as block quotes.

### What We Currently Do

Looking at our PDF (pages 9-10), the Q&A structure uses:
- "**Question:**" as a bold label inline, followed by text
- Answers appear as regular paragraphs
- No special Q/A prefix or italic treatment

This is functional but less visually distinctive than Shambhala's approach.

### Recommended Changes

This is primarily a markdown/content change rather than a template change. In the translation files, Q&A passages would need to be formatted as:

```markdown
*Q:* What are the objects of meditation?

It is as follows: the objects of meditation are of four types...
```

For template-level support, if we want to define custom environments:

```latex
% Q&A formatting
\newcommand{\questionlabel}{\textit{Q:\enspace}}
\newcommand{\answerlabel}{}  % No label for answers in our context

% Or for the Sravakabhumi's structural Q&A:
\newcommand{\sravQ}[1]{\par\noindent\textit{Q:\enspace #1}\par}
```

**However:** The Sravakabhumi's Q&A structure is different from the Shambhala book's interview format. Asanga uses a formal scholastic structure: "What is X? (云何X)" followed by "That is to say: (謂...)" — this is not a conversational Q&A. The current bold "Question:" / "Answer:" treatment may actually be more appropriate for our text. The Shambhala Q&A style is specifically for interview/teaching transcripts.

**Recommendation:** Keep the current bold-label approach for the formal Q&A structure. If desired, make the question text italic to set it apart more visually, matching the Shambhala convention that questions get italic treatment:

```latex
% Custom environment for Sravakabhumi Q&A
\newenvironment{sravakaqa}{%
  \par\vspace{0.5em}\noindent\textbf{Question:}\enspace\itshape
}{%
  \par\upshape\vspace{0.3em}
}
```

---

## 9. Page Numbers

### What Shambhala Does

- **Body pages:** Page number INTEGRATED into the running header
  - Verso: flush left, as part of "28 — THE EMBODIMENT..."
  - Recto: flush right, as part of "...PART ONE — 29"
  - NO page number in footer
- **Chapter-opening pages:** Page number centered at bottom (footer), lowercase roman for front matter, arabic for body
- **Front matter:** Lowercase roman numerals (vii, viii, ix, etc.)
- **Body:** Arabic numerals starting from 1

### What We Currently Do

- All page numbers centered in footer (`\fancyfoot[C]{\thepage}`)
- Front matter in roman, body in arabic (correctly implemented via `\frontmatter`/`\mainmatter`)
- Page number never appears in header

### Recommended Changes

See Section 1 (Running Headers) — the page number integration is part of the header redesign. The key change:

```latex
% Remove footer page numbers on normal pages
% (they move to the header)
% Keep footer page numbers ONLY on chapter-opening (plain) pages
\fancyfoot{}  % Clear all footer content for fancy style
```

The `plain` pagestyle already puts the number in the footer for chapter openings:
```latex
\fancypagestyle{plain}{
  \fancyhf{}
  \fancyfoot[C]{\small\thepage}
  \renewcommand{\headrulewidth}{0pt}
}
```

---

## 10. Margins

### What Shambhala Does

The Shambhala book appears to be a standard trade paperback, likely 5.5" x 8.5" or 6" x 9":
- **Inner (gutter) margin:** Approximately 0.85-0.9 inches — generous for binding
- **Outer margin:** Approximately 0.65-0.75 inches
- **Top margin:** Approximately 0.7-0.8 inches (to the header rule)
- **Bottom margin:** Approximately 0.8-0.9 inches (from last text line to page bottom)
- **Text block:** Approximately 4.0-4.25 inches wide, 6.5-6.8 inches tall
- **Header space:** The running header sits above the text block with the thin rule providing a visual boundary

The ratio of inner:outer is approximately 1.2:1 — the inner margin is larger, which is standard for perfect-bound books.

### What We Currently Do

```yaml
geometry:
  - paperwidth=6in
  - paperheight=9in
  - inner=0.75in
  - outer=0.625in
  - top=0.6in
  - bottom=0.6in
```

Text block: 4.625in wide x 7.8in tall.
Inner:outer ratio = 1.2:1 (matches Shambhala convention).

**Issues:**
- Top margin (0.6in) is very tight for a running header — the header text sits very close to the page edge
- Bottom margin (0.6in) is tight — less breathing room than Shambhala
- Text block is slightly wide (4.625in vs Shambhala's ~4.1in)

### Recommended Changes

```yaml
geometry:
  - paperwidth=6in
  - paperheight=9in
  - inner=0.85in       # Was 0.75in — more gutter for binding
  - outer=0.7in        # Was 0.625in — more thumb space
  - top=0.75in         # Was 0.6in — room for running head + rule
  - bottom=0.75in      # Was 0.6in — breathing room
  - headsep=0.25in     # Explicit: space between header rule and text
  - headheight=14pt    # Explicit: height of header line
```

This gives a text block of 4.45in wide x 7.5in tall — still generous but with proportions closer to Shambhala's.

**KDP consideration:** KDP requires minimum 0.375in outer margins and gutter based on page count. For a ~250 page book at 6x9, minimum gutter is ~0.5in. Our proposed 0.85in inner is well above minimum and appropriate for a quality printing.

---

## 11. Footnotes

### What Shambhala Does

The Shambhala book does not have extensive footnotes visible in the photographed pages. The "Notes" section in the back matter (listed in the Contents at page 209) suggests they use endnotes, not footnotes.

This is typical of Shambhala trade publications — they prefer clean pages without footnote clutter, relocating notes to the back of the book.

### What We Currently Do

Our PDF (pages 20-24 visible) shows:
- Page-bottom footnotes with a 2-inch rule separating them from body text
- Footnotes in smaller font
- Superscript reference numbers in text
- Footnotes are dense and scholarly — some pages have 3-4 footnotes taking up 30-40% of the page
- The footnote rule and spacing appear clean and well-formatted

```latex
\usepackage[bottom]{footmisc}
\setlength{\footnotesep}{0.8\baselineskip}
\renewcommand{\footnoterule}{\vspace{0.5em}\noindent\rule{2in}{0.4pt}\vspace{0.3em}}
```

### Recommendation

**Keep page-bottom footnotes.** While Shambhala uses endnotes for trade books, our project is a scholarly translation. Page-bottom footnotes are the standard for scholarly translations (Nanamoli's Visuddhimagga, Bodhi's translations, etc.) because they allow the reader to check references without flipping to the back. This is the correct choice for our audience.

**Minor refinements:**

```latex
% Slightly shorter rule (Shambhala-inspired subtlety)
\renewcommand{\footnoterule}{%
  \vspace{0.6em}%
  \noindent\rule{1.5in}{0.3pt}%  % Was 2in/0.4pt — slightly more subtle
  \vspace{0.4em}%
}

% Footnote text size — ensure it's noticeably smaller than body
\renewcommand{\footnotesize}{\fontsize{9pt}{11pt}\selectfont}
```

---

## 12. Additional Observations

### Half-Title Page

**Shambhala:** Not photographed, but standard practice is a simple centered title in regular or italic, no subtitle, no author — just the book title.

**Our current (page 1):** "The Hearer's Ground" centered — this is correct and matches the convention.

**Improvement:** Consider using the Sanskrit title:

```markdown
\thispagestyle{empty}
\vspace*{3in}
\begin{center}
{\Large\textit{Sravakabhumi}}
\end{center}
\newpage
```

### Overall Typography Philosophy

The Shambhala house style embodies:
1. **Restraint** — small caps for headers, no bold in headers, minimal decoration
2. **White space as design element** — generous margins, leading, chapter drops
3. **Small caps as the workhorse** — used for headers, contents heading, section titles, labels
4. **Thin rules sparingly** — under headers, between title/author on title page, nowhere else
5. **Consistent hierarchy** — title > section > subsection, each with distinct treatment but all harmonious

Our current template is functional but reads as "LaTeX default with minor customizations" rather than "deliberately designed scholarly book." The changes above would move it significantly toward the Shambhala standard while retaining the scholarly apparatus (footnotes, section numbers, Taisho references) that our text requires.

### Font Note

EB Garamond is an excellent choice and close to what Shambhala likely uses (Adobe Garamond Pro or similar). No font change is needed. However, confirm that EB Garamond's small caps glyphs render correctly in XeLaTeX — if not, the `fontspec` font definition may need:

```latex
\setmainfont{EBGaramond}[
  ...existing options...,
  SmallCapsFeatures = {Letters=SmallCaps},
]
```

---

## Summary of All Recommended Changes

### Template Changes (print-template.tex)

1. **Running headers:** Small caps with letterspaced headers, page numbers in header, em-dash separators, thin rule below
2. **Chapter format:** Small caps title, more generous top spacing, suppress first paragraph indent
3. **Section format:** Bold small caps for sections, keep bold for subsections
4. **Footnote rule:** Slightly shorter and thinner
5. **Line spacing:** 1.2 (from 1.15)
6. **Paragraph indent:** 1.2em (from 1.5em)

### Metadata Changes (metadata-print.yaml)

7. **Margins:** inner 0.85, outer 0.7, top 0.75, bottom 0.75 (from 0.75/0.625/0.6/0.6)
8. **Line stretch:** 1.2 (from 1.15)

### Content Changes (translation/ markdown files)

9. **Title page:** Full redesign with centered layout, horizontal rule, hierarchy
10. **Copyright page:** Smaller font, flush left, no paragraph indent
11. **Half-title:** Consider using Sanskrit title in italic
12. **Contents:** Strongly consider switching to auto-generated ToC with small-caps heading and no dot leaders

### Priority Order

| Priority | Change | Impact | Effort |
|----------|--------|--------|--------|
| 1 | Running headers (small caps + page number + rule) | High — most visible change | Medium |
| 2 | Margins and line spacing | High — affects every page | Low |
| 3 | Title page redesign | High — first impression | Low |
| 4 | Chapter opening spacing | Medium — sets the tone | Low |
| 5 | Section heading small caps | Medium — visual hierarchy | Low |
| 6 | Copyright page | Low — one page | Low |
| 7 | ToC auto-generation | High — functional (page numbers!) | High |
| 8 | Footnote rule refinement | Low — minor polish | Low |

---

*Analysis based on 7 photographs of The Sadhana of Mahamudra (Shambhala Publications, 2025) and 13 rendered pages of the current Sravakabhumi print PDF.*
