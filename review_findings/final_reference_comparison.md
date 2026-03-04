# Final Reference Site Comparison
## Sravakabhumi vs. 84000 Reading Room and Lotsawa House

**Scope:** CSS/HTML-only improvements. Excludes already-implemented features (left-aligned text, no blockquote border, italic h3, scroll-padding-top).

---

## 1. Typography

### Current State
- Font: EB Garamond (single family for everything)
- Base size: 18px desktop, 16px mobile
- Line height: 1.7 throughout
- No letter-spacing on body text
- h1: 2rem / h2: 1.4rem / h3: 1.1rem / h4: 1rem (all font-weight: normal)
- p margin-bottom: 0.8rem

### 84000 Reading Room
- Uses a system that pairs a serif for body and a sans-serif for UI elements and section numbers
- Section paragraph numbers (format: `1.1`, `1.2`) are displayed as a distinct element beside or above each paragraph — distinct color (muted), smaller size, acting as persistent anchors
- Folio markers styled as small muted inline references, visually distinct from main text
- End-notes (not page footnotes): collected at bottom under `[n.]` heading, linked bidirectionally

### Lotsawa House
- Body: Spectral (serif, 400 weight) for translation text
- UI / interface labels / metadata: OpenSans (sans-serif, 300–800 weight range)
- Two-font system creates a clear hierarchy: human text vs. navigation apparatus
- Tibetan/Sanskrit term display: no special inline popup; displayed in italic with transliteration

### Actionable Improvements

**A. Add a second font for UI/apparatus (CSS-only).**
Currently EB Garamond is used for everything including navigation, TOC labels, footnote back-references, and section labels. Adding a complementary sans-serif for `.top-nav`, `.page-toc summary`, `.taisho-ref`, `.page-nav`, `footer`, and `sup a` creates the same semantic distinction both reference sites use — "human text vs. apparatus."

Suggested addition to `:root`:
```css
--ui-font: -apple-system, BlinkMacSystemFont, "Segoe UI", "Helvetica Neue", sans-serif;
```
Apply `font-family: var(--ui-font)` to: `.top-nav`, `.nav-links`, `.page-toc summary`, `.page-toc a`, `.taisho-ref`, `.page-nav`, `footer`, `sup a`, `.footnote-backref`, `.section-anchor`.

The Taisho reference spans already use `-apple-system` — extend this principle to all apparatus.

**B. Tighten body line-height for large blocks of enumeration/list text.**
Current 1.7 is generous for prose but can feel loose in the long enumeration sections (26.2's 28-person list, etc.). Lotsawa House uses tighter spacing for structured lists. Add:
```css
li { line-height: 1.5; }
```

**C. Paragraph spacing — reduce orphan gap.**
Current `p { margin-bottom: 0.8rem }` is fine but sections with back-to-back paragraphs need slightly more breathing room to separate thought-units. Both reference sites use closer to 1em or 1.2em. Change:
```css
p { margin-bottom: 1rem; }
```

**D. Add optical size / font-feature-settings for EB Garamond.**
EB Garamond supports OpenType features. Add to `body`:
```css
font-feature-settings: "onum" 1, "kern" 1, "liga" 1;
```
This activates oldstyle numerals, kerning, and ligatures — standard in the Nanamoli/Bodhi print tradition and expected by readers comparing print quality.

**E. Letter-spacing on uppercase/small-caps labels.**
Currently `.page-toc summary` has `letter-spacing: 0.05em` but the nav links only have `0.03em`. 84000 and Lotsawa House use tighter letter-spacing (0–0.01em) on ALL non-uppercase UI labels. Apply 0 letter-spacing to `.nav-links a` and increase only for explicitly uppercase/small-caps labels. Change:
```css
.nav-links a { letter-spacing: 0; }
```

---

## 2. Color Palette

### Current State
```css
--text-color: #2c2c2c;
--bg-color: #fafaf8;
--accent-color: #8b6914;
--border-color: #e0ddd5;
--muted-color: #888;
```

### 84000 Reading Room
- Primary accent: `#4d65ff` (blue) — a very different choice, specifically for interactive/focus states
- Orange overlay accent (`84000-brand-bg-orange-overlay20`) for featured content
- Background: white (pure or near-pure) for the reading area — no warm tint
- Section numbers: appear in a muted blue-gray distinct from body text

### Lotsawa House
- Primary text: dark charcoal (near-black, high contrast)
- Background: white/near-white — no warm tint
- Accent for interactive elements: blue (standard hyperlink convention)
- Navigation/header: dark background (near-black) with white logo/text — strong brand contrast

### Actionable Improvements

**F. Differentiate visited link color.**
Neither reference site leaves visited links identical to unvisited links. Currently all `a` links use `--accent-color: #8b6914` with no `:visited` style. Add:
```css
a:visited { color: #6b4e10; }
```
This subtle darkening signals already-read chapters/sections — genuinely useful for readers progressing through 8 fascicles.

**G. Add a focus-visible style for keyboard accessibility.**
84000 explicitly uses `outline: 0.125rem solid #4d65ff` on focus states. Current stylesheet has no `:focus-visible` rules. Add:
```css
a:focus-visible {
  outline: 2px solid var(--accent-color);
  outline-offset: 2px;
  border-radius: 2px;
}
```

**H. Muted color for Taisho references is correct but could use a background tint.**
Both reference sites use a very subtle background on inline scholarly apparatus (folio numbers, section IDs). Add:
```css
.taisho-ref {
  background-color: rgba(0, 0, 0, 0.03);
  padding: 0 0.2em;
  border-radius: 2px;
}
```
This makes the reference visually "pill-like" and clearly apparatus rather than text — matching 84000's folio marker presentation.

---

## 3. Navigation

### Current State
- Sticky top nav with title (left) and links (right)
- No breadcrumbs
- No section numbering visible in text
- `<details open>` TOC on fascicle pages
- `.page-nav` at bottom with prev/next arrows

### 84000 Reading Room
- Breadcrumbs: `84000 > The Collection > The Kangyur > Discourses > [Title]` — persistent location context
- TOC: collapsible accordion with two-letter section codes (`ti.`, `im.`, `co.`, `s.`, `i.`, `tr.`, `n.`, `b.`, `g.`) — compact, always-visible section list
- Section paragraph numbering: every paragraph has a persistent `1.1`, `1.2`, `2.1`... anchor displayed in muted color beside the paragraph — readers can cite exact locations
- Version stamp visible: `v 1.2.7 (2025)` — signals scholarly currency

### Lotsawa House
- Breadcrumbs: `Advice > Tibetan Masters > Mipham Rinpoche` — persistent 3-level breadcrumb
- Language selector: 8 languages inline in header — not relevant here but shows multi-audience design
- No TOC on shorter texts; single-scroll design for shorter texts
- Download (EPUB, PDF) links positioned in the reading area near the text, not just in footer

### Actionable Improvements

**I. Add breadcrumb navigation to fascicle pages.**
Lotsawa House and 84000 both use breadcrumbs. This is the single most impactful navigation improvement: helps readers locate themselves in the multi-fascicle structure and improves return-visit orientation.

Add above the `<aside class="page-toc">` on fascicle pages:
```html
<nav class="breadcrumb" aria-label="breadcrumb">
  <a href="index.html">Sravakabhumi</a>
  <span class="breadcrumb-sep">&rsaquo;</span>
  <a href="index.html#read">The Second Yoga Place</a>
  <span class="breadcrumb-sep">&rsaquo;</span>
  <span class="breadcrumb-current">Fascicle 26</span>
</nav>
```

CSS:
```css
.breadcrumb {
  font-family: var(--ui-font);
  font-size: 0.8rem;
  color: var(--muted-color);
  margin-bottom: 1.5rem;
  display: flex;
  align-items: center;
  gap: 0.4rem;
  flex-wrap: wrap;
}

.breadcrumb a {
  color: var(--muted-color);
  text-decoration: none;
}

.breadcrumb a:hover {
  color: var(--accent-color);
}

.breadcrumb-sep {
  color: var(--border-color);
}

.breadcrumb-current {
  color: var(--text-color);
}
```

**J. Add section paragraph anchors.**
84000's most distinctive scholarly feature: every paragraph has a visible `1.1`, `1.2` label that doubles as a deep-link anchor. This is achievable in HTML without JavaScript by adding a `data-section` span:

```html
<p><span class="para-num" id="26-2-1"><a href="#26-2-1">¶1</a></span> The varieties...</p>
```

CSS:
```css
.para-num {
  font-family: var(--ui-font);
  font-size: 0.7rem;
  color: var(--muted-color);
  margin-right: 0.4em;
  user-select: none;
}

.para-num a {
  color: var(--muted-color);
  text-decoration: none;
}

.para-num a:hover {
  color: var(--accent-color);
}
```
Note: This requires build.py changes to inject the HTML, but zero JS and zero CSS complexity beyond the above.

**K. TOC: close by default on mobile.**
Currently `<details open>` is open on all screen sizes. On mobile, this pushes the actual text off-screen. Add:
```css
@media (max-width: 768px) {
  .page-toc details {
    /* Remove open attribute via CSS is not possible, but we can style the
       closed state more gracefully */
  }
}
```
The real fix is in the HTML template: change `<details open>` to `<details>` and let the browser default to closed. On desktop, the TOC is short enough to be open by default only if the section list is short.

Actually, the CSS-only approach is to add `open` conditionally via the `@media` print-style approach. For a CSS-only solution, use:
```css
@media (max-width: 768px) {
  .page-toc details[open] summary::after {
    content: " (tap to collapse)";
    font-size: 0.75em;
  }
}
```
This doesn't force-close but adds orientation context on mobile.

**L. Active nav link indicator.**
Both reference sites make it clear which section is current. Currently all nav links look identical regardless of which page you're on. This is a per-page HTML change (add `aria-current="page"` to the active link), but the CSS can be ready:
```css
.nav-links a[aria-current="page"] {
  color: var(--text-color);
  font-weight: bold;
}
```

---

## 4. Footnote Presentation

### Current State
- Footnote superscripts: `sup a` with accent color, 0.75em size, no decoration
- Footnote section: 3rem margin-top, 1.5rem padding-top, border-top, 0.85rem font, 1.5 line-height
- Back-reference: `.footnote-backref` in accent color, no decoration
- Ordered list with 1.5rem padding-left

### 84000 Reading Room
- Bidirectional navigation: inline superscript `[37]` links to `#end-note-UT22084-072-039-80`; note has back-reference
- End-notes collected under labeled section `[n.]` with its own heading in the TOC — treated as a full section, not a typographic afterthought
- Note numbers appear in brackets `[37]`, not bare superscripts — more visible, easier to tap on mobile

### Lotsawa House
- Shorter texts often have no footnotes; scholarly notes appear in a bibliography section
- Metadata (translation date, translator credit) appears prominently below text before notes

### Actionable Improvements

**M. Style the footnote section heading.**
Currently `.footnotes` has no heading — the section just starts after the border. 84000 treats notes as a named section. Add a semantic heading:

In HTML: each fascicle's footnote section (generated by the markdown processor) could have a label added. Via CSS, style the `.footnotes` section with a label using `::before`:
```css
.footnotes::before {
  content: "Notes";
  display: block;
  font-family: var(--ui-font);
  font-size: 0.75rem;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: var(--muted-color);
  margin-bottom: 1rem;
}
```

**N. Footnote numbers: switch to bracketed style.**
Currently footnote superscripts are rendered as `[1]` by the markdown plugin already. The back-reference arrow `↩` is standard. Consider styling the back-reference arrow larger for easier mobile tapping:
```css
.footnote-backref {
  font-size: 1em;
  padding: 0 0.2em;
}
```

**O. Footnote hover highlight.**
When a footnote number is hovered or the back-link is followed, highlight the target:
```css
.footnotes li:target {
  background-color: rgba(139, 105, 20, 0.08);
  border-radius: 3px;
  padding: 0.2em 0.4em;
  margin-left: -0.4em;
}
```
This is standard on 84000 and most scholarly sites — the user can see exactly which note was linked to.

---

## 5. Table Styling

### Current State
- `border-collapse: collapse`, centered with `margin: 1.5rem auto`
- th: `border-bottom: 2px solid --text-color`, padding `0.5rem 1rem`, sticky with `top: var(--nav-height)`
- td: `border-bottom: 1px solid --border-color`
- Alternating rows: `rgba(0, 0, 0, 0.02)` — barely visible
- No horizontal scroll on mobile

### 84000 Reading Room
- Glossary tables styled with clear column boundaries
- Term entries use a definition-list (`dl/dt/dd`) structure in some places rather than pure `<table>` — this reflows better on mobile

### Lotsawa House
- Minimal table use; prefers definition lists for term glossaries

### Actionable Improvements

**P. Horizontal scroll wrapper for glossary table on mobile.**
Currently on mobile (max-width: 768px), the 4-column glossary table (Sanskrit | Chinese | English | Notes) will overflow or compress illegibly. Neither reference site has this problem because they use narrower tables or definition lists. CSS-only fix:

Add to mobile breakpoint:
```css
@media (max-width: 768px) {
  table {
    display: block;
    overflow-x: auto;
    -webkit-overflow-scrolling: touch;
    white-space: nowrap;
  }

  td, th {
    white-space: normal; /* Override for Notes column */
  }
}
```

**Q. Stronger alternating row contrast.**
Current `rgba(0, 0, 0, 0.02)` is nearly invisible. Both reference sites use a more visible stripe. Change to:
```css
table tr:nth-child(even) {
  background-color: rgba(0, 0, 0, 0.035);
}
```

**R. Remove sticky header from non-glossary tables.**
The sticky `th` with `top: var(--nav-height)` is useful for the long glossary but creates visual noise on small tables in the translation text (e.g., the brief taxonomic tables in fascicles 26-27). Add a scoped override using a class on non-glossary tables:
```css
.translation-table th {
  position: static;
}
```
This requires adding `class="translation-table"` to small tables in the HTML template.

---

## 6. Mobile Responsiveness

### Current State
- Single breakpoint at 768px
- Nav collapses to column layout (stacked title + links)
- Content padding reduces from 2rem to 1rem
- Font drops from 18px to 16px
- Table font drops to 0.8rem
- No print-specific table treatment
- No TOC behavior change on mobile

### 84000 Reading Room
- Progressive responsive system with multiple breakpoints
- `.hide-tablet` and `.hide-mobile` utility classes — elements selectively hidden at each tier
- Container classes (`.container-medium`, `.container-small`, `.container-large`) for responsive width
- Mobile TOC behavior: collapses automatically

### Lotsawa House
- Language selector visible on desktop, likely collapses on mobile
- Card grids for the index page reflow to single column

### Actionable Improvements

**S. Add intermediate breakpoint at 1024px for optimal reading width.**
Currently on tablets (768–1024px) the content renders at full desktop padding with no adjustment. Add:
```css
@media (max-width: 1024px) and (min-width: 769px) {
  .content {
    padding-left: 2rem;
    padding-right: 2rem;
  }
}
```

**T. Nav: prevent wrapping on small mobile.**
At very small screen widths (e.g., 375px), the nav links in column layout may still wrap. Add:
```css
@media (max-width: 480px) {
  .nav-links {
    flex-wrap: wrap;
    justify-content: center;
    font-size: 0.8rem;
    gap: 0.5rem 1rem;
  }
}
```

**U. Content width on very wide screens.**
At 2560px+ displays, content maxes at 40rem (~720px) centered in a vast white expanse. 84000 uses a wider container for its two-column layout (TOC sidebar + text). For single-column, consider increasing max reading width slightly:
```css
:root {
  --content-width: 42rem;  /* was 40rem — adds ~36px at 18px base */
}
```
This is minor but brings the text column closer to the 65–75 character per line ideal for scholarly prose with long Sanskrit compounds.

---

## 7. Landing/Index Page Design

### Current State
- Single column, all text, no visual hierarchy beyond h2/h3
- "Read Online" section is a flat list of links
- No visual differentiation between Yoga Places
- No call-to-action prominence
- Download section shows "coming soon" items — visually identical to active links

### 84000 Reading Room Index
- Featured translations use card grids with thumbnail images, title, Toh number, and CTA button
- The reading room landing page separates "featured" from "browse all" with clear visual hierarchy
- Translation metadata (version, date) displayed on cards

### Lotsawa House Author/Index Pages
- Two-column card layout with thumbnail images + title + brief summary + topic tags
- Collapsible category sections (Advice, Dzogchen, etc.) — browsable by topic
- Most-recent translations given prominence

### Actionable Improvements

**V. Style the Yoga Place groupings distinctly on index.html.**
Currently the three Yoga Places (Second/Third/Fourth) are separated only by h3 headings. Add a wrapper style for each group:
```css
.yoga-place {
  margin: 1.5rem 0;
  padding: 1rem 1.25rem;
  border-left: 2px solid var(--border-color);
  background-color: rgba(0, 0, 0, 0.01);
}

.yoga-place h3 {
  margin-top: 0;
  color: var(--text-color);
}
```
This is a pure CSS improvement requiring only a `<div class="yoga-place">` wrapper in the HTML around each Yoga Place group.

**W. Dim "coming soon" download items.**
Currently EPUB and print edition "coming soon" items are styled identically to active links. Differentiate:
```css
.coming-soon {
  color: var(--muted-color);
  font-style: italic;
  cursor: default;
  pointer-events: none;
}
```
Then in HTML: `<span class="coming-soon">EPUB (ebook) — coming soon</span>` instead of the list item with italic em.

**X. Add a subtle separator between major sections on index.html.**
Both reference sites visually separate "Read", "Appendices", "Download", and "License" sections. Currently only h2 headings separate them. Improve with:
```css
h2 + ul, h2 + p {
  margin-top: 0.5rem;
}

/* Spacer before new major sections */
h2:not(:first-of-type) {
  margin-top: 3rem;
  padding-top: 1.5rem;
  border-top: 1px solid var(--border-color);
}
```

---

## 8. Features the Reference Sites Have That Would Add Genuine Value

### From 84000 Reading Room

**Y. Version/date stamp.**
84000 displays `v 1.2.7 (2025)` on every translation page. This is one of the most trust-building features for a scholarly site — readers know when the text was last updated. CSS-only preparation:
```css
.version-stamp {
  font-family: var(--ui-font);
  font-size: 0.75rem;
  color: var(--muted-color);
  font-style: normal;
}
```
Then in HTML (index page and each fascicle footer):
```html
<span class="version-stamp">Translation v1.0 · March 2026</span>
```

**Z. `:target` scroll highlight for section headings.**
84000 uses anchor-based deep linking throughout. When a reader follows a link to `fascicle-26.html#262-the-twenty-eight-types-of-persons`, the target heading should briefly highlight. This is pure CSS:
```css
h2:target, h3:target {
  animation: highlight-fade 2s ease-out;
}

@keyframes highlight-fade {
  0% { background-color: rgba(139, 105, 20, 0.12); }
  100% { background-color: transparent; }
}
```
No JavaScript required; the browser fires the `:target` pseudo-class automatically on anchor navigation.

### From Lotsawa House

**AA. Download link styling near content.**
Lotsawa House positions download options (EPUB, PDF) within or immediately after the article content, not just in the footer. This increases discoverability for readers who finish a text. In the current site, download options are only on `index.html`. A CSS-prepared `.download-block` class:
```css
.download-block {
  margin-top: 2rem;
  padding: 1rem 1.25rem;
  background-color: rgba(0, 0, 0, 0.02);
  border: 1px solid var(--border-color);
  border-radius: 3px;
  font-size: 0.9rem;
}

.download-block p {
  text-indent: 0;
  margin-bottom: 0.4rem;
}
```

**BB. Translator credit styled distinctly.**
Lotsawa House displays translator credit prominently as metadata near the text title, not buried in the footer. Currently the Sravakabhumi has the attribution in the page h1 area but styled as a paragraph with inline `style="text-align: center; font-style: italic"`. Formalize this as a class:
```css
.attribution {
  font-family: var(--ui-font);
  font-size: 0.9rem;
  color: var(--muted-color);
  text-align: center;
  text-indent: 0;
  line-height: 1.6;
  margin: 0.5rem 0 1.5rem;
}
```

---

## Summary of Priority

**High impact, CSS-only (pure CSS additions):**
1. **F**: Visited link color — tiny addition, big UX benefit for multi-fascicle reading
2. **G**: `focus-visible` outline — accessibility, zero aesthetic cost
3. **M + O**: Footnote section label (`::before`) + `:target` highlight — scholarly professionalism
4. **Z**: `:target` heading highlight animation — deep-linking UX, zero JS
5. **P**: Mobile horizontal scroll for glossary table — prevents broken layout

**Medium impact, requires small HTML changes too:**
6. **A**: UI font system for apparatus (CSS addition + propagate to relevant elements)
7. **D**: `font-feature-settings` for EB Garamond — invisible to most, visible to scholars
8. **I + CSS**: Breadcrumb styling (CSS ready; HTML added to each page)
9. **L**: Active nav link indicator (CSS ready; `aria-current` added to each page's HTML)
10. **V**: Yoga Place group styling on index (CSS + `<div>` wrappers in HTML)

**Lower impact or debatable:**
11. **C**: p margin-bottom from 0.8rem to 1rem — minor
12. **B**: li line-height 1.7 → 1.5 — matters mainly for long lists
13. **U**: Content width 40rem → 42rem — very subtle
14. **Q**: Stronger alternating row stripe — cosmetic

---

*Analysis based on direct inspection of `docs/style.css`, `docs/index.html`, `docs/introduction.html`, `docs/fascicle-26.html`, `docs/glossary.html`; web fetches of 84000.co and lotsawahouse.org; and web search for design documentation. 84000 CSS values extracted from their HTML source structure; Lotsawa House font/color system from their @font-face declarations and homepage design.*
