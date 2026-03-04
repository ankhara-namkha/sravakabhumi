# Final Navigation Verification — docs/

Date: 2026-03-03

## 1. Navigation Chain

The prev/next chain is **complete and correct** across all 13 pages.

| Page | Prev | Next |
|---|---|---|
| introduction.html | (none) | fascicle-26.html |
| fascicle-26.html | introduction.html | fascicle-27.html |
| fascicle-27.html | fascicle-26.html | fascicle-28.html |
| fascicle-28.html | fascicle-27.html | fascicle-29.html |
| fascicle-29.html | fascicle-28.html | fascicle-30.html |
| fascicle-30.html | fascicle-29.html | fascicle-31.html |
| fascicle-31.html | fascicle-30.html | fascicle-32.html |
| fascicle-32.html | fascicle-31.html | fascicle-33.html |
| fascicle-33.html | fascicle-32.html | methodology.html |
| methodology.html | fascicle-33.html | abbreviations.html |
| abbreviations.html | methodology.html | glossary.html |
| glossary.html | abbreviations.html | bibliography.html |
| bibliography.html | glossary.html | (none) |

**Finding:** PASS. Unbroken chain in expected order. bibliography.html correctly has no "next" link.

---

## 2. Top Nav Consistency

All 14 HTML files (including index.html) have identical top nav:

```html
<a href="introduction.html">Introduction</a>
<a href="index.html#read">Read</a>
<a href="glossary.html">Glossary</a>
<a href="methodology.html">About</a>
```

**Finding:** PASS. All 4 links present with correct hrefs on every page.

---

## 3. Footer Consistency

All 14 HTML files have identical footer:

```html
<footer>
  <p>Sravakabhumi: The Hearer's Ground &middot; From the Yogacarabhumi-sastra of Asanga</p>
  <p>English translation from the Chinese of Xuanzang (T1579) &middot; CC BY-NC-SA 4.0</p>
</footer>
```

**Finding:** PASS. 100% identical across all pages.

---

## 4. Stale Content Checks

### 4a. Footnote count in index.html
index.html contains **no footnote count text at all** — no reference to "218", "284", or "280". The page is a table of contents only. No issue.

### 4b. Footnote count in methodology.html
methodology.html line 62 reads: **"218 scholarly footnotes"** — correct.

Actual footnote item counts per fascicle (verified by counting `class="footnote-item"` entries):
- fascicle-26.html: 35
- fascicle-27.html: 38
- fascicle-28.html: 33
- fascicle-29.html: 35
- fascicle-30.html: 15
- fascicle-31.html: 13
- fascicle-32.html: 24
- fascicle-33.html: 25
- **Total: 218** — matches the claim exactly.

**Finding:** PASS.

### 4c. turqoisehex / ankhara-namkha references
No file references "turqoisehex" or "turquoisehex". All GitHub URL references correctly use "ankhara-namkha":
- abbreviations.html (2 occurrences)
- methodology.html (1 occurrence)

**Finding:** PASS.

### 4d. bibliography.html — raw {#anchor} tags
Zero occurrences of `{#` in bibliography.html. The Markdown-style anchor tags (`{#primary-sources}`, etc.) are absent; the page uses proper `id=` attributes on heading elements.

**Finding:** PASS.

### 4e. glossary.html — raw pipe characters
Zero lines with raw ` | ` characters outside HTML markup. The glossary table is fully rendered as `<table>/<tr>/<td>` HTML.

**Finding:** PASS.

---

## 5. Google Fonts — EB Garamond

All 14 HTML files load EB Garamond from Google Fonts. Each contains exactly one reference to `EB+Garamond` in a `<link href="https://fonts.googleapis.com/css2?family=EB+Garamond...">` tag.

**Finding:** PASS.

---

## 6. Section Heading Counts (h2 + h3 per fascicle)

Each fascicle page has 2 h2 headings (the page/yogaplace title + "Fascicle N" title) plus h3 section headings.

| Page | h2 | h3 | Total | h3 Section Titles |
|---|---|---|---|---|
| fascicle-26.html | 2 | 7 | 9 | 26.1–26.7 |
| fascicle-27.html | 2 | 6 | 8 | 27.1–27.6 |
| fascicle-28.html | 2 | 11 | 13 | 28.1–28.11 |
| fascicle-29.html | 2 | 17 | 19 | 29.1–29.17 |
| fascicle-30.html | 2 | 16 | 18 | 30.1–30.16 |
| fascicle-31.html | 2 | 11 | 13 | 31.1–31.11 |
| fascicle-32.html | 2 | 17 | 19 | 32.1–32.17 |
| fascicle-33.html | 2 | 18 | 20 | 33.1–33.18 |

**Total h3 sections across all fascicles: 103**
**Total headings (all levels) across all fascicles: 119**

### Detailed h3 listings:

**Fascicle 26 (7 sections):** 26.1 Opening Questions and Summary Verse · 26.2 The Twenty-Eight Types of Persons · 26.3 Establishment of Persons: The Eleven Criteria · 26.4 Objects of Meditation: Overview · 26.5 Pervasive Objects of Meditation · 26.6 Purifying-Conduct Objects: Impurity · 26.7 Purifying-Conduct Objects: Loving-Kindness and Compassion

**Fascicle 27 (6 sections):** 27.1 Purifying-Conduct Objects: Dependent Origination · 27.2 Purifying-Conduct Objects: Element Differentiation · 27.3 Purifying-Conduct Objects: Mindfulness of Breathing · 27.4 Skillful Objects · 27.5 Affliction-Purifying Objects · 27.6 Four Types of Instruction

**Fascicle 28 (11 sections):** 28.1 The Three Superior Trainings · 28.2 The Three Faculties · 28.3 The Three Gates of Liberation · 28.4 Factors Opposing and According with Training · 28.5 Four Types of Yoga Failure · 28.6 The Four Yogas · 28.7 Types of Attention · 28.8 Yogic Activities and Three Types of Yogin · 28.9 Two Types of Cultivation · 28.10 The Thirty-Seven Factors of Awakening · 28.11 The Four Foundations of Mindfulness

**Fascicle 29 (17 sections):** 29.1 The Four Right Efforts · 29.2 The Four Samadhis · 29.3 The Eight Abandonment Factors · 29.4 The Bases of Supernatural Power · 29.5 The Five Faculties · 29.6 The Five Powers · 29.7 Correlation of Faculties and Powers with Other Groups · 29.8 The Four Wholesome Roots · 29.9 The Seven Factors of Awakening · 29.10 The Noble Eightfold Path · 29.11 Summary of the Thirty-Seven Factors · 29.12 The Four Shramana Fruits · 29.13 Person Typology: Behavioral Types and the Thin-Dust Person · 29.14 Six Categories of Persons · 29.15 Eight Types of Persons by Capacity · 29.16 Four Maras and Mara's Activities · 29.17 Three Causes of Fruitless Practice

**Fascicle 30 (16 sections):** 30.1 Transition and Summary Verse · 30.2 Approaching the Teacher · 30.3 The Teacher's Encouragement · 30.4 The Four Inquiry Points · 30.5 The Four-Fold Investigation · 30.6 The Five Establishments — Overview · 30.7 The First Establishment: Guarding the Samadhi Resources · 30.8 The Second Establishment: Seclusion · 30.9 The Third Establishment: One-Pointed Mind · 30.10 The Nine Stages of Mental Abiding · 30.11 The Six Powers · 30.12 The Four Types of Attention · 30.13 The Four Types of Vipashyana · 30.14 The Three Doors and Six Aspects of Vipashyana · 30.15 Vipashyana Applied to the Contemplation of Impurity · 30.16 Vipashyana Applied to the Contemplation of Loving-Kindness

**Fascicle 31 (11 sections):** 31.1 Vipashyana Applied to the Contemplation of Dependent Origination · 31.2 Vipashyana Applied to the Contemplation of Element Differentiation · 31.3 Vipashyana Applied to the Contemplation of Mindfulness of Breathing · 31.4 Shamatha and Vipashyana in Mutual Support · 31.5 The Nine Practice Approaches — Introduction and Approaches 1-4 · 31.6 The Nine Practice Approaches — Approach 5: Timely Practice · 31.7 The Nine Practice Approaches — Approaches 6-9 and Conclusion · 31.8 Purification of Obstacles · 31.9 Shamatha and Vipashyana: Mutual Growth, Completion Criteria, and Paired Operation · 31.10 Intermediate Summary Verse · 31.11 Cultivation of Attention: Four Types, Objects of Practice, and the Goldsmith Simile

**Fascicle 32 (17 sections):** 32.1 The Five Signs: Framework for the Beginner · 32.2 The Sign of Disenchantment — Instruction for the Greedy Temperament · 32.3 The Sign of Delight · 32.4 The Sign of Danger and Entry into Shamatha · 32.5 The Sign of Luminosity and Entering Practice · 32.6 The Oil-Bowl Simile · 32.7 Decoding the Simile; Alternating Shamatha and Vipashyana · 32.8 Graduated Contemplation: From One to the Limitless · 32.9 Light-Perception Applied; Entering the Foundations of Mindfulness · 32.10 The Four Foundations via Asubha: External Body; Feeling, Mind, and Dharmas · 32.11 Conduct Between Sessions; The Fire-Drill Simile · 32.12 The Remaining Four Objects; Loving-Kindness Contemplation · 32.13 Dependent Origination Contemplation · 32.14 Element Differentiation Contemplation · 32.15 Mindfulness of Breathing Contemplation · 32.16 Universal Shamatha Practice and Pliancy Attainment · 32.17 Attainment of the Status "Possessed of Attention"

**Fascicle 33 (18 sections):** 33.1 Uddana Verse for the Fourth Yoga Place · 33.2 Two Paths After Attaining "Possessed of Attention" · 33.3 Four Types of Persons Pursuing the Worldly Path · 33.4 The Seven Attentions for Abandoning Desire · 33.5 Attention to Characteristics: The Six-Aspect Analysis of Desire · 33.6 From Conviction to the Fruit: The Remaining Six Attentions · 33.7 Functional Summary and Classification of the Seven Attentions · 33.8 Extension to Higher Attainments and the Second Dhyana · 33.9 Universal Coarse Aspects Across All Lower Grounds · 33.10 Detailed Exposition of the First Dhyana Formula · 33.11 Detailed Exposition of the Second Dhyana Formula · 33.12 Detailed Exposition of the Third Dhyana Formula · 33.13 Detailed Exposition of the Fourth Dhyana Formula · 33.14 The Four Formless Attainments · 33.15 Two Absorptions Without Mind · 33.16 Five Superknowledges and the Twelve Perceptions · 33.17 Rebirth Destinations According to Attainment · 33.18 Characteristics of the Person Free from Desire

---

## Summary

All checks pass. Navigation chain is unbroken across all 13 pages in the correct order. Top nav is identical on all 14 pages with correct hrefs. Footer is identical on all 14 pages. No stale content: index.html has no footnote count (not an issue), methodology.html correctly states 218 footnotes (verified against actual page counts totaling 218). No turqoisehex references. No raw {#anchor} tags in bibliography.html. No raw pipe characters in glossary.html. All 14 pages load EB Garamond from Google Fonts. Total h3 section headings across fascicles: 103.
