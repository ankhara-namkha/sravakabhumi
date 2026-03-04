# Final Footnote Verification Report

Generated: 2026-03-03

## fascicle-26.html

**Status: PASS**

- Footnote references in body: 38 (35 unique footnotes; 3 cited more than once: [3, 6, 23])
- Footnote definitions (li#fnN): 35
- Backref links: 38 total (35 unique footnote numbers)
- `<hr class="footnotes-sep">` present: True
- `<section class="footnotes">` present: True
- Raw markdown `[^` syntax: 0 occurrences
- Footnote range: fn1 to fn35

## fascicle-27.html

**Status: PASS**

- Footnote references in body: 38 (38 unique footnotes; 0 cited more than once: none)
- Footnote definitions (li#fnN): 38
- Backref links: 38 total (38 unique footnote numbers)
- `<hr class="footnotes-sep">` present: True
- `<section class="footnotes">` present: True
- Raw markdown `[^` syntax: 0 occurrences
- Footnote range: fn1 to fn38

## fascicle-28.html

**Status: PASS**

- Footnote references in body: 33 (33 unique footnotes; 0 cited more than once: none)
- Footnote definitions (li#fnN): 33
- Backref links: 33 total (33 unique footnote numbers)
- `<hr class="footnotes-sep">` present: True
- `<section class="footnotes">` present: True
- Raw markdown `[^` syntax: 0 occurrences
- Footnote range: fn1 to fn33

## fascicle-29.html

**Status: PASS**

- Footnote references in body: 35 (35 unique footnotes; 0 cited more than once: none)
- Footnote definitions (li#fnN): 35
- Backref links: 35 total (35 unique footnote numbers)
- `<hr class="footnotes-sep">` present: True
- `<section class="footnotes">` present: True
- Raw markdown `[^` syntax: 0 occurrences
- Footnote range: fn1 to fn35

## fascicle-30.html

**Status: PASS**

- Footnote references in body: 15 (15 unique footnotes; 0 cited more than once: none)
- Footnote definitions (li#fnN): 15
- Backref links: 15 total (15 unique footnote numbers)
- `<hr class="footnotes-sep">` present: True
- `<section class="footnotes">` present: True
- Raw markdown `[^` syntax: 0 occurrences
- Footnote range: fn1 to fn15

## fascicle-31.html

**Status: PASS**

- Footnote references in body: 13 (13 unique footnotes; 0 cited more than once: none)
- Footnote definitions (li#fnN): 13
- Backref links: 13 total (13 unique footnote numbers)
- `<hr class="footnotes-sep">` present: True
- `<section class="footnotes">` present: True
- Raw markdown `[^` syntax: 0 occurrences
- Footnote range: fn1 to fn13

## fascicle-32.html

**Status: PASS**

- Footnote references in body: 24 (24 unique footnotes; 0 cited more than once: none)
- Footnote definitions (li#fnN): 24
- Backref links: 24 total (24 unique footnote numbers)
- `<hr class="footnotes-sep">` present: True
- `<section class="footnotes">` present: True
- Raw markdown `[^` syntax: 0 occurrences
- Footnote range: fn1 to fn24

## fascicle-33.html

**Status: PASS**

- Footnote references in body: 25 (25 unique footnotes; 0 cited more than once: none)
- Footnote definitions (li#fnN): 25
- Backref links: 25 total (25 unique footnote numbers)
- `<hr class="footnotes-sep">` present: True
- `<section class="footnotes">` present: True
- Raw markdown `[^` syntax: 0 occurrences
- Footnote range: fn1 to fn25

## Summary

- **Total footnote uses across all fascicles:** 221
- **Total footnote definitions across all fascicles:** 218
- **Overall integrity:** ALL PASS

## Notes on Multi-Use Footnotes

Some footnotes are cited more than once in the body text (e.g., fn3, fn6, fn23 in fascicle-26).
This is correct behavior: the HTML generator (markdown-it) assigns `id="fnrefN"` to the first use
and `id="fnrefN:1"`, `id="fnrefN:2"` etc. to subsequent uses. The footnote definition then contains
multiple backref arrows — one per use. This is not a defect.

## Verification Method

- Body references detected via: `<sup ...><a href="#fnN">` pattern
- Definitions detected via: `<li id="fnN">` pattern
- Backrefs detected via: `href="#fnrefN"` and `href="#fnrefN:K"` patterns
- Multi-use footnotes identified where body_ref_count(N) > 1
- True duplicate defs = same `<li id="fnN">` appearing twice (actual HTML bug)
- Sequential check: no gaps in fn1..fnMax range within each fascicle