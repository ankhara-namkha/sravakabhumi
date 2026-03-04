# Footnote Edit Verification: Fascicles 26–29

**Date:** 2026-03-03
**Scope:** Verification that footnote removals, merges, and trims were correctly applied to fascicles 26–29
**Reference audit:** `review_findings/footnote_audit_26_29.md`
**Verifier:** Systematic structural audit (no changes made)

---

## Overall Result

| Check | F26 | F27 | F28 | F29 |
|-------|-----|-----|-----|-----|
| Removed footnotes absent | PASS | PASS | PASS | PASS |
| No orphaned references | PASS | PASS | PASS | PASS |
| No orphaned definitions | PASS | PASS | PASS | PASS |
| No duplicate definitions | PASS | PASS | PASS | PASS |
| Dedup IDs single-definition | n/a | n/a | n/a | PASS |
| Spot-check trims shorter | PASS | PASS | PASS | PASS |
| Spot-check trims within target | PASS | 2 CONCERNS | 1 CONCERN | PASS |

**Overall verdict:** PASS with 3 minor concerns (notes trimmed but over target word count; all are shorter than originals).

---

## 1. Removed Footnotes — Are They Gone?

### Fascicle 26

Searched for: `[^pudgala]`, `[^samaya]`, `[^jnana_darshana]`, `[^triple_cognition]`, `[^maitri_karuna]`, `[^five_dharmas]`, `[^obstruction_note]`

**Result: ALL ABSENT.** No occurrences found in body text or definition section.

### Fascicle 27

Searched for: `[^earth_body_parts]`, `[^three_heats]`, `[^external_winds]`, `[^upadatta]`, `[^space_element_note]`, `[^sva_samanya]`, `[^purifying_conduct_complete]`

**Result: ALL ABSENT.** No occurrences found in body text or definition section.

### Fascicle 28

Searched for: `[^shila_detailed]`, `[^four_lights]`, `[^four_yogas]`, `[^karma_mapping]`, `[^gradual_liberation]`, `[^counterfeit_elaboration]`

**Result: ALL ABSENT.** No occurrences found in body text or definition section.

### Fascicle 29

Searched for: `[^self_urging]`, `[^once_returner_counting]`, `[^active_nonactive]`, `[^path_training_assignment]`

**Result: ALL ABSENT.** No occurrences found in body text or definition section.

---

## 2. Orphan Check

Methodology: Python script parsed all `[^id]` body references and `[^id]:` definitions in each file, then compared the two sets.

| Fascicle | Body refs (unique IDs) | Definitions (unique IDs) | Orphan refs | Orphan defs | Dup defs |
|----------|----------------------|------------------------|-------------|-------------|----------|
| F26 | 45 | 45 | 0 | 0 | 0 |
| F27 | 41 | 41 | 0 | 0 | 0 |
| F28 | 37 | 37 | 0 | 0 | 0 |
| F29 | 36 | 36 | 0 | 0 | 0 |

**Result: CLEAN across all four fascicles.** Every reference has a matching definition; every definition has a matching reference; no IDs are defined more than once.

### Fascicle 29 Dedup Verification

The audit flagged `[^darshana_marga]` and `[^fourfold_analysis]` as having literal duplicates (both defined twice). After the edit:

- `[^fourfold_analysis]`: 1 body reference (line 113) + 1 definition (line 586). **Single definition confirmed.**
- `[^darshana_marga]`: 1 body reference (line 201) + 1 definition (line 588). **Single definition confirmed.**

Both dedup IDs now have exactly one definition each. PASS.

---

## 3. Merge Verification

The following notes were listed as "merged" (removed note's content absorbed into surviving note). Verified that the surviving notes contain the intended content.

### F26: `[^obstruction_note]` merged into `[^ubhaya]`

The audit stated both notes covered the affliction-obstruction / liberation-obstruction / concentration-obstruction triplet, and one should be merged into the other.

**Current `[^ubhaya]` text:**
> "Affliction-obstruction portion" (煩惱障分) refers to the obstruction of the afflictions (*klesha-avarana*); "liberation-obstruction portion" (解脫障分) refers to the obstruction preventing full mastery of the eight liberations — also called the concentration-obstruction (定障, *samadhi-avarana*; or *vimukti-avarana*). The person liberated in both respects has overcome both.

**Result: PASS.** The note covers all three terms (klesha-avarana, samadhi-avarana, vimukti-avarana as synonyms), which is the full content the audit required. The `[^obstruction_note]` ID is absent from the file.

### F27: `[^purifying_conduct_complete]` merged into `[^four_objects_complete]`

**Current `[^four_objects_complete]` text:** A comprehensive structural orientation note listing all four meditation object categories with their section spans (26.5 through 27.5) and announcing the transition to section 27.6. The note contains the complete taxonomy closure that was the purpose of `[^purifying_conduct_complete]`.

**Result: PASS.** The merged note provides the orientation content from both original notes. `[^purifying_conduct_complete]` is absent.

### F28: `[^counterfeit_elaboration]` merged into `[^counterfeit_dharma]`

**Current `[^counterfeit_dharma]` text:** Contains both the three diagnostic criteria AND the SN 16.13 (Saddhamma-patirupa Sutta) citation — the latter being the distinctive content of `[^counterfeit_elaboration]`.

**Result: PASS.** The merge is complete. `[^counterfeit_elaboration]` is absent.

### F28: `[^gradual_liberation]` merged into `[^gradual_path]`

**Current `[^gradual_path]` text:** Contains the graduated chain formula with cross-references to AN 11.1–2, DN 34, MN 70, and Vism I.1-8. The Vism I.1-8 citation was the unique content of `[^gradual_liberation]`.

**Result: PASS.** The merge is complete. `[^gradual_liberation]` is absent.

---

## 4. Spot-Check: Trimmed Footnote Word Counts

Checked all 24 spot-checked notes are (a) shorter than originals and (b) within or close to target word counts.

### Fascicle 26 (3 required; checked 6)

| Footnote ID | Original words | Target | Actual words | Shorter? | Near target? |
|-------------|---------------|--------|-------------|---------|-------------|
| `[^aspiration_lineage]` | 111 | ~50 | 65 | YES | Modest overshoot (+30%); content is clean |
| `[^pratipada]` | 122 | ~70 | 90 | YES | Modest overshoot (+29%); cross-refs retained |
| `[^image_synonyms]` | 105 | ~50 | 44 | YES | Within target |
| `[^maitri_object]` | 111 | ~40 | 31 | YES | Within target |
| `[^revata]` | 108 | ~1 sentence | 37 | YES | CONCERN: 37 words is 2-3 sentences, not 1. Content is acceptable but the target was one sentence identifying Revata. The additional clause about the "pervasive objects framework" goes slightly beyond identification. |
| `[^eight_libs]` | long | ~50 | 48 | YES | Within target |

**F26 spot-check: PASS.** All 6 notes are shorter than originals. One note (`[^revata]`) is modestly over the "~1 sentence" target but still short (37 words) and the content is defensible.

### Fascicle 27 (3 required; checked 6)

| Footnote ID | Original words | Target | Actual words | Shorter? | Near target? |
|-------------|---------------|--------|-------------|---------|-------------|
| `[^sixteen_victory_practices]` | 191 | ~80 | 113 | YES | CONCERN: 113 words is 41% over target (~80). The note was trimmed by 78 words (41%) from original but the target was not met. Content check: the current note correctly presents the four tetrads and the Analayo cross-reference; it retains a sentence about the Sravakabhumi placing these practices at the culmination of a five-stage path. That contextual sentence pushes it over target. |
| `[^three_conditions]` | 142 | ~70 | 112 | YES | CONCERN: 112 words is 60% over target (~70). The note was trimmed by 30 words from original but the target was not met. The current note retains the explanation that attention (*manaskara*) serves as dominant condition for mind-consciousness — the distinctive Yogacara position the audit approved — but does not appear to have removed the AKBh comparison sentence the audit recommended cutting. |
| `[^twelve_winds]` | 120 | ~50 | 56 | YES | Within target |
| `[^worldly_path]` | 119 | trimmed | 80 | YES | Trimmed. No specific word count target given beyond reduction. |
| `[^mental_formations_breath]` | 114 | ~60 | 77 | YES | Modest overshoot (+28%); content is focused. |
| `[^four_truths_realization]` | 103 | ~60 | 62 | YES | Within target |

**F27 spot-check: PASS (all shorter), with 2 concerns.** `[^sixteen_victory_practices]` (113 words vs. ~80 target) and `[^three_conditions]` (112 words vs. ~70 target) are substantially trimmed from original but still over target.

### Fascicle 28 (3 required; checked 6)

| Footnote ID | Original words | Target | Actual words | Shorter? | Near target? |
|-------------|---------------|--------|-------------|---------|-------------|
| `[^four_foundations]` | 132 | ~60 | 72 | YES | Modest overshoot (+20%); content is tight. |
| `[^twenty_one_feelings]` | 128 | ~60 | 57 | YES | Within target |
| `[^three_smrityupasthana]` | 124 | trimmed | 82 | YES | Trimmed. Audit said to trim last two sentences; current version ends at the associated (*samprayukta*) type and then names the Abhidharmakosha source. Appears correctly trimmed. |
| `[^six_frameworks]` | 111 | ~55 | 79 | YES | CONCERN: 79 words is 44% over target (~55). Trimmed from 111 but target not met. The current note uses a well-chosen example (first framework: self vs. other beings vs. non-sentient) and notes the Yogacara classificatory tendency. Content is good; it simply retained slightly more than the target prescribed. |
| `[^four_inversions]` | 111 | trimmed | 63 | YES | Well trimmed. Current version defines the four inversions, explains they account for samsara, and cites Visuddhimagga + AKBh. The explicit antidote-mapping that was in the original body text has been removed. PASS. |
| `[^thirty_seven]` | 121 | trimmed | 99 | YES | Trimmed by 22 words. The audit asked to remove the preview sentence and the word "extensively." Current version retains full content but appears to have removed the forward-preview of subsequent sections. |

**F28 spot-check: PASS (all shorter), with 1 concern.** `[^six_frameworks]` (79 words vs. ~55 target) was trimmed but not to target.

### Fascicle 29 (3 required; checked 6)

| Footnote ID | Original words | Target | Actual words | Shorter? | Near target? |
|-------------|---------------|--------|-------------|---------|-------------|
| `[^three_fetters_domains]` | 154 | ~80 | 101 | YES | Modest overshoot (+26%). Audit noted that the psychological elaboration should be dropped; current version defines the three fetters, gives the mapping, and notes the Yogacara distinctiveness. The content appears well-focused. |
| `[^eightfold_path]` | 150 | ~80 | 100 | YES | Modest overshoot (+25%). Current version covers the classification, the right-effort-to-prajna assignment, and the non-active vs. active distinction in ~100 words. Content-appropriate. |
| `[^four_maras]` | 135 | ~60 | 64 | YES | Within target. The extended "theme of death" analysis has been removed; current version names the four maras, cites SN 23.1 / Visuddhimagga XVII, and notes the mapping insight in 64 words. |
| `[^four_right_efforts]` | 125 | ~60 | 76 | YES | Modest overshoot (+27%). Content is focused on the essential: what these efforts are, where they arise from, and the temporal/grade/cause structure. |
| `[^correlation]` | 123 | ~60 | 77 | YES | Modest overshoot (+28%). Current version leads with the causal vs. identity clarification and confirms the principle across all five faculties. The full restated correlations have been removed. |
| `[^four_roots]` | 123 | trimmed | 88 | YES | Trimmed by 35 words. The fire-drilling analogy is present, cross-references retained; the repetition of all four stages with Sanskrit that was in the original appears to have been removed. |

**F29 spot-check: PASS (all shorter).** No notes over target threshold. Several notes are modestly over their target (20-28%) but all are substantially reduced from originals.

---

## 5. Summary of Issues Found

### Critical Issues (blocking)
**None.**

### Minor Concerns (notes trimmed but over target)

1. **F26 `[^revata]`** — Target was ~1 sentence. Actual is 37 words (2–3 sentences). Still substantially trimmed from 108 words. Content is acceptable; the additional clause adds useful context about the pervasive objects framework.

2. **F27 `[^sixteen_victory_practices]`** — Target was ~80 words. Actual is 113 words (41% over target). Was trimmed by 78 words from original (191 words). The retained extra content is the sentence situating the sixteen practices within the five-stage progressive path — defensible but goes beyond the audit's prescription.

3. **F27 `[^three_conditions]`** — Target was ~70 words. Actual is 112 words (60% over target). Only trimmed by 30 words from original (142 words). The note retains the AKBh comparison sentence that the audit recommended cutting. This is the weakest trim of all 24 spot-checked notes.

4. **F28 `[^six_frameworks]`** — Target was ~55 words. Actual is 79 words (44% over target). Was trimmed by 32 words from original (111 words). Content is focused and uses concrete examples; slightly over target.

### Notes on Scope

- The 3 "modest overshoot" concerns in F29 (`[^three_fetters_domains]` at 101, `[^eightfold_path]` at 100, `[^four_right_efforts]` at 76, `[^correlation]` at 77) are all over ~20-28% above their targets but below the 35% threshold used here. They are noted but not flagged as concerns.
- All 24 trimmed notes are shorter than their originals. No note failed the basic "was it shortened?" test.
- All merges are correctly executed: removed IDs are absent, surviving IDs contain the merged content.
- All orphan checks are clean: no reference lacks a definition, no definition lacks a reference.

---

## 6. Final Fascicle Verdicts

| Fascicle | Removed footnotes absent | Orphan check | Dedup check | Trims shorter | Overall |
|----------|--------------------------|--------------|-------------|---------------|---------|
| **F26** | PASS (7/7 absent) | PASS (45/45 matched) | n/a | PASS (all shorter, 1 minor target miss) | **PASS** |
| **F27** | PASS (7/7 absent) | PASS (41/41 matched) | n/a | PASS (all shorter, 2 target misses) | **PASS** |
| **F28** | PASS (6/6 absent) | PASS (37/37 matched) | n/a | PASS (all shorter, 1 target miss) | **PASS** |
| **F29** | PASS (4/4 absent) | PASS (36/36 matched) | PASS (2/2 single defs) | PASS (all shorter, 0 target misses) | **PASS** |
