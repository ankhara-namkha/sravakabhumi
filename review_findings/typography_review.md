# Typography Review: Print PDF (6"x9" KDP)

Source files reviewed:
- `build/print-template.tex`
- `build/metadata-print.yaml`

Assessment against professional book design standards for a scholarly translation.

---

## 1. Font: EB Garamond at 11pt

**Current:** `EBGaramond` via HarfBuzz renderer, static TTF instances, 11pt.

**Assessment:** Excellent choice. EB Garamond is a high-quality open-source revival of the Garamond tradition, appropriate for scholarly translations of classical religious texts. The NTC (Lamrim Chenmo) and similar projects use Garamond-family faces. HarfBuzz renderer is correct for OpenType feature support. Static TTF instances are a reasonable workaround for variable-font axis parsing issues in XeLaTeX.

**Size:** 11pt is within the professional range for 6"x9" scholarly books. Garamond reads slightly small at equivalent point sizes compared to transitional faces (Times, Palatino) due to its smaller x-height — 11pt EB Garamond sits approximately where 10.5pt Palatino would. For a text with extensive Sanskrit terms and dense doctrinal prose, 11pt is appropriate: large enough for comfortable reading, small enough to fit reasonable line counts per page. 10pt would be marginal; 12pt would feel padded.

**Recommendation:** No change needed. The HarfBuzz + static-instance approach is correct and well-documented in the template comments.

---

## 2. Line Spacing: 1.15

**Current:** `\setstretch{1.15}` (linestretch: 1.15 in metadata).

**Assessment:** Slightly tight for book typography. Professional book design for body text typically targets 1.2–1.4x the point size (in absolute terms), which translates to roughly 1.2–1.3 linestretch for a 11pt Garamond. At 11pt, a leading of approximately 14–15pt is standard. `1.15` gives roughly 12.65pt leading — closer to tightly-leaded magazine columns than book paragraphs.

The tight leading compounds with Garamond's smaller x-height: the interline space feels more compressed than the number suggests because Garamond's ascenders and descenders are proportionally taller. For a scholarly translation where readers are working through dense material, slightly more breathing room aids comprehension.

**Recommendation:** Increase to `1.2` or `1.25`. At 1.2, the leading becomes ~13.2pt, within the acceptable range. At 1.25, it reaches ~13.75pt — comfortable for sustained reading. Either is an improvement. `1.25` is the safer scholarly convention.

---

## 3. Margins: inner=0.75in, outer=0.75in, top=0.75in, bottom=0.7in

**Current:** All four margins set to approximately 0.75in (bottom slightly less at 0.7in), symmetric inner/outer.

**Assessment:** These margins are too tight on multiple grounds:

**Binding (inner margin):** KDP's minimum inner margin requirements for books over 100 pages are 0.5in (small page count) rising to 0.875in (for 300–600 page books). A scholarly translation of 8 fascicles will easily exceed 300 pages. At 0.75in inner margin, text will ride uncomfortably close to the gutter after binding, requiring the reader to strain the spine open to read line beginnings. Professional scholarly books at 6"x9" use 1.0–1.25in inner margins.

**Outer margin:** 0.75in is tight for a twoside layout. The outer margin is where readers rest their thumbs; it also provides visual breathing room. Standard for scholarly 6"x9" is 0.875–1.0in outer. The current outer=inner=0.75in creates a uniform, cramped frame with no recto/verso visual asymmetry — the classic book proportion (inner:outer approximately 1:1.6) is lost.

**Top/bottom:** 0.75in top and 0.7in bottom are minimal. Note that `headheight=14pt` and `headsep=18pt` are consumed from the top margin, so the actual text-to-header clearance is further reduced. Standard scholarly practice: 0.875in–1.0in top, 1.0in bottom (bottom margins traditionally run slightly larger than top to give the text block a stable, grounded feel on the page).

**Recommended revision:**
```
inner=1.0in
outer=0.875in
top=0.875in
bottom=1.0in
headheight=14pt
headsep=20pt
```
This gives KDP-safe gutter clearance, proper visual asymmetry on twoside layouts, and comfortable top/bottom breathing room. It will slightly reduce lines per page but improve readability and print-safety.

**Alternative (wider outer margin for scholar annotations):**
```
inner=1.0in
outer=1.125in
top=0.875in
bottom=1.0in
```
Some academic translations provide a slightly wider outer margin for marginalia/annotation. Not required, but worth considering.

---

## 4. Paragraph Formatting: 1.5em indent, 0pt parskip

**Current:** `\parindent=1.5em`, `\parskip=0pt`.

**Assessment:** Correct and professional. This is the standard book typesetting convention: paragraphs are separated by indentation, not vertical space. A 0pt parskip with indented paragraphs is the norm for Garamond-set scholarly books (Chicago Manual of Style §1.43, common in Shambhala and Wisdom Publications books).

1.5em indent is slightly generous — 1.0–1.2em is the more common standard — but not wrong. At 11pt Garamond, 1.5em ≈ 16.5pt, which is a clearly visible indent without being distracting.

**The parskip package** is loaded (`\usepackage{parskip}`) but then overridden with `\setlength{\parskip}{0pt}`. This is a known anti-pattern: the parskip package sets `\parskip` to a positive value on load, then you manually reset it to 0pt. This should work correctly but is fragile — any package loaded after parskip that resets paragraph spacing may interact unpredictably. Consider removing the `\usepackage{parskip}` line entirely and setting `\setlength{\parindent}{1.5em}` directly, which is cleaner.

**Recommendation:** Minor improvement — remove the parskip package and set indentation directly. Current values (1.5em, 0pt) are acceptable as-is.

---

## 5. Header Design: Letterspaced small caps with em-dash separator

**Current:**
```
Verso: \thepage — SRAVAKABHUMI (letterspaced small caps)
Recto: CHAPTER TITLE (letterspaced small caps) — \thepage
```
With 0.3pt header rule.

**Assessment:** Professional and well-executed. This is the standard scholarly/literary book header convention: page number flanked by title/chapter in small caps. The em-dash separator (rather than a pipe or comma) is elegant and consistent with Shambhala/Wisdom house style. Letterspacing at 8 units (LetterSpace=8 in addfontfeatures) is appropriate for small caps — tighter than display, looser than body. The \small size is correct for running headers.

The `\MakeLowercase{\leftmark}` on the recto is essential for proper small-caps rendering — well done.

The 0.3pt header rule is conservative; some designers prefer 0.5pt for visibility. Either is acceptable.

The plain pagestyle (bottom center, no header, no rule) for chapter openings is standard scholarly convention.

**Recommendation:** No change needed. This is a clean, professional header implementation.

---

## 6. Heading Hierarchy: Chapter (LARGE centered) → Section (large bold left) → Subsection (normalsize bold left)

**Current:**
```
\chapter: \normalfont\Large\centering label + \LARGE title, 120pt top / 40pt bottom spacing
\section: \large\bfseries, 24pt above / 12pt below
\subsection: \normalsize\bfseries, 24pt above / 6pt below
```
Unnumbered sections (secnumdepth=-1).

**Assessment:**

**Chapter formatting:** The display format (label on one line, title on the next) is appropriate. `\Large` for the label and `\LARGE` for the title gives clear hierarchy. 120pt top spacing (≈1.67in) provides the traditional "chapter drop" — the vertical space before a new chapter that signals a major structural division. This is correct scholarly/literary convention. 40pt bottom spacing before body text is fine.

**Section formatting:** `\large\bfseries` (≈13.2pt bold at 11pt base) with 24pt above / 12pt below is workable. However, for a Garamond text, bold sections can feel slightly heavy. Many scholarly translations use small caps or italic for section headings to stay within the Garamond register rather than jumping to bold. This is a stylistic choice, not an error.

**Subsection:** `\normalsize\bfseries` (11pt bold) with only 6pt below is quite tight. This makes the subsection heading appear close to the following text, which can make it look more like a run-in than a standalone heading. 8–10pt below would be clearer.

**Unnumbered sections** (secnumdepth=-1): Appropriate for a classical text translation where the Chinese source has no numbered sections.

**Needspace guards:** `\needspace{6\baselineskip}` for sections and `4\baselineskip` for subsections are correct — prevents headings from being stranded at the bottom of a page without following text.

**Recommendation:**
- Subsection: Increase bottom spacing from 6pt to 8–10pt.
- Optional: Consider small caps for section headings (`\large\scshape`) instead of bold, for a more Garamond-consistent visual register. Not required.

---

## 7. Footnotes: footmisc[bottom], 2in rule, 0.8\baselineskip separation

**Current:**
```
\usepackage[bottom]{footmisc}
\footnotesep=0.8\baselineskip
\footnoterule: 0.8em vspace, 2in rule (0.4pt), 0.4em vspace
```

**Assessment:** Standard scholarly convention and well-executed.

`[bottom]` option: Correct — forces footnotes to the true page bottom rather than floating above the last line of text. Essential for scholarly books where footnote/text spatial relationship is semantically meaningful.

**Footnote rule:** 2 inches is the traditional length (1/3 of text width at 6"x9" with these margins). Correct. 0.4pt thickness is appropriate — thin enough to be unobtrusive, visible enough to separate zones.

**Separator:** 0.8\baselineskip between footnotes is reasonable. Standard ranges from 0.5–1.0\baselineskip. Given the expected density (~40 footnotes per fascicle), 0.8 is a good balance between compactness and readability.

**Missing:** Footnote font size is not explicitly set. LaTeX defaults footnotes to `\footnotesize` (9pt at 11pt base) — this is correct, but worth confirming. Some scholarly publications use 10pt footnotes; at 6"x9" with tight margins, the default is fine.

**Recommendation:** No change needed. Consider adding `\renewcommand\footnotesize{\small}` if footnotes read too small in review PDFs, but default is acceptable.

---

## 8. Hyphenation: hyphenpenalty=300, tolerance=3000, emergencystretch=3em

**Current:**
```
\hyphenpenalty=300
\exhyphenpenalty=300
\tolerance=3000
\emergencystretch=3em
```

**Assessment:** This is a reasonable but somewhat loose hyphenation setup. Analyzing each parameter:

**hyphenpenalty=300:** Standard LaTeX default is 50; this value raises the cost of hyphenation by 6x, strongly discouraging breaks. For a scholarly translation with long Sanskrit compounds (shamatha, vipashyana, yogacarabhumi, satipatthana), this is sensible — these terms should not be broken.

**exhyphenpenalty=300:** Matching hyphenpenalty is correct. This governs breaks at explicit hyphens (compound words). Matching values are standard.

**tolerance=3000:** This is very high. LaTeX default is 200; the practical upper bound for acceptable output is typically 800–1200. At 3000, TeX will accept quite poor inter-word spacing before giving up. Combined with emergencystretch=3em, this means TeX will stretch word spacing substantially rather than hyphenate. The risk: loose lines with visibly uneven spacing, particularly in narrow columns or passages with long Sanskrit terms.

**emergencystretch=3em:** This is a large emergency stretch allowance (3em ≈ 33pt at 11pt). This is the "last resort" parameter — when TeX cannot meet tolerance, it applies up to 3em of additional stretch. At 3em, some lines may appear noticeably looser than adjacent lines.

**The tradeoff:** The current settings prioritize avoiding hyphenation at the cost of potentially loose word spacing. For a 6"x9" book with a 4.5in text width (approximately, at current margins), this tradeoff is more pronounced than in wider formats.

**Recommended revision:**
```
\hyphenpenalty=200        % Still discourages but allows necessary breaks
\exhyphenpenalty=200
\tolerance=1500           % More reasonable; prevents worst spacing
\emergencystretch=1.5em   % Reduced; tighter final resort
```
This reduces hyphenation without tolerating severely loose lines.

**Alternative:** If the goal is specifically to protect Sanskrit compound terms from mid-word breaks, add `\lccode` adjustments or use the `hyphenat` package's `\nohyphens{}` macro around specific terms rather than globally loosening all hyphenation.

---

## 9. Orphan/Widow Penalties: 10000

**Current:**
```
\widowpenalty=10000
\clubpenalty=10000
```

**Assessment:** Standard and correct. The value 10000 is the LaTeX maximum — effectively prohibiting widows and orphans absolutely. This is the professional book standard; single lines stranded at the top or bottom of a page are considered serious typographic defects in scholarly publishing.

Note that these penalties interact with `\emergencystretch` and `\tolerance`: TeX will stretch/compress pages to avoid violating these penalties. With the current high tolerance and large emergencystretch, TeX has many tools available to avoid widows/orphans, which is good.

One known issue: absolute widow/orphan penalties can occasionally cause page-length inconsistencies (pages that are one or two lines shorter than the target to avoid a widow). With microtype enabled (which expands the solution space), this is less likely to be visible.

**Recommendation:** No change needed. 10000 is the correct value.

---

## 10. Blockquotes/Verse: 2em left, 1em right, small italic

**Current:**
```
\renewenvironment{quote}
  {\list{}{\leftmargin=2em\rightmargin=1em}\item\relax\small\itshape}
  {\endlist}
```

**Assessment:** Workable but has potential issues for uddana verses specifically.

**Indentation:** 2em left / 1em right is asymmetric, which is reasonable for prose quotations. For verse (udddanas), symmetric indentation or pure left-indentation with preserved line breaks is more conventional. If the markdown blockquote is used for both prose quotations and verse, the same environment handles both — which is a constraint to be aware of.

**Size:** `\small` (≈9.5pt at 11pt base) for verse is appropriate — uddana verses in Tibetan/Chinese Buddhist texts are traditionally set slightly smaller than the body to signal their structural distinctiveness.

**Italic:** `\itshape` for verse is correct literary convention. Garamond's italic is elegant and well-suited for this purpose.

**Missing:** No `\setlength{\parsep}{}` or `\setlength{\itemsep}{}` within the list environment. The default list spacing may add unwanted vertical space between verse lines if each line is a separate paragraph. For verse, you typically want lines to flow with minimal inter-line space. Consider:
```latex
{\list{}{\leftmargin=2em\rightmargin=1em\parsep=0pt\itemsep=0pt}\item\relax\small\itshape}
```

**Recommendation:** Add `\parsep=0pt\itemsep=0pt` to prevent unwanted inter-line spacing in verse passages. Consider whether prose blockquotes and verse need separate environments — if yes, define a `\verse` environment distinct from `quote`.

---

## 11. Table Formatting: booktabs, arraystretch=1.4

**Current:**
```
\usepackage{booktabs}
\renewcommand{\arraystretch}{1.4}
```

**Assessment:** Correct and professional.

**booktabs:** The standard for scholarly typeset tables. Provides `\toprule`, `\midrule`, `\bottomrule` with proper spacing, eliminating vertical rules which are considered poor table design (Chicago Manual, Tufte). Essential for the glossary and comparison tables in a scholarly translation.

**arraystretch=1.4:** This applies globally to all tables (and also affects the CJK character rows). 1.4 is on the generous side but appropriate for tables containing Tibetan or Chinese characters (which need more vertical clearance) and for bilingual/trilingual tables that need breathing room. For a pure English table (e.g., a term list), 1.2–1.3 would be more compact; 1.4 for mixed-script tables is a reasonable default.

**The `\newcounter{none}` workaround** for Pandoc 3.9's `\def\LTcaptype{none}` is a known compatibility fix — correctly documented and handled.

**Recommendation:** No change needed. If pure-English tables look too spacious, consider `\renewcommand{\arraystretch}{1.3}` and adding a local override for mixed-script tables. As-is, 1.4 is defensible.

---

## 12. Microtype: Enabled

**Current:** `\usepackage{microtype}` (default options).

**Assessment:** Correct and essential. Microtype enables:
- **Character protrusion:** Punctuation and certain glyphs extend slightly into the margin, making the text block appear more evenly aligned.
- **Font expansion:** Glyphs are subtly compressed or expanded (typically ±2%) to improve line-breaking without perceptible distortion.

For a scholarly translation being prepared as a final production PDF, microtype is standard and should always be enabled. It significantly reduces the number of overfull/underfull hboxes and improves the overall color of the text block.

**With XeLaTeX/fontspec:** Microtype in XeLaTeX mode has reduced capabilities compared to pdfLaTeX — character protrusion is supported, but some expansion features may be limited depending on the font and TeX engine version. This is a known limitation, not a fixable issue.

**Default options:** Loading microtype without options applies reasonable defaults (protrusion=true, expansion=true, tracking=false). For production, consider:
```latex
\usepackage[protrusion=true, expansion=true, tracking=false, kerning=true]{microtype}
```
This makes the intent explicit and enables kerning optimization.

**Recommendation:** No change required. Optionally, make options explicit as above for documentation clarity.

---

## Summary of Priority Issues

| Priority | Issue | Recommendation |
|----------|-------|----------------|
| **HIGH** | Inner margin 0.75in too tight for binding | Increase to 1.0in; outer to 0.875in |
| **HIGH** | Bottom margin 0.7in too small | Increase to 1.0in |
| **MEDIUM** | Line spacing 1.15 too tight for sustained reading | Increase to 1.25 |
| **MEDIUM** | hyphenation tolerance=3000 too loose | Reduce to 1500; emergencystretch to 1.5em |
| **LOW** | `\usepackage{parskip}` loaded then overridden | Remove parskip package; set \parindent directly |
| **LOW** | Blockquote/verse: no parsep/itemsep control | Add \parsep=0pt\itemsep=0pt to quote environment |
| **LOW** | Subsection bottom spacing 6pt too tight | Increase to 8–10pt |
| **LOW** | Microtype options implicit | Make explicit for documentation clarity |

**No changes needed:** Font (EB Garamond 11pt), paragraph formatting values (1.5em/0pt), header design, chapter drop spacing, footnote configuration, orphan/widow penalties, table formatting (booktabs/1.4), microtype (enabled).

---

*Review completed 2026-03-02. Findings are typographer's assessment against professional book design standards; all changes require build/review cycle before adoption.*
