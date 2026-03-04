# Footnote System Coherence Audit
## Sweep 2 — Internal Coherence Review

Scope: All 280 footnotes across fascicles 26–33 (45 + 41 + 37 + 36 + 24 + 23 + 41 + 33) plus front matter (00_introduction.md, 00_methodology.md — no footnotes in those files). Cross-fascicle labels identified and compared. All body-text references verified against actual section numbers.

---

## 1. INTERNAL CONTRADICTIONS

### [Contradiction — Moderate] [^four_inversions] — Fascicles 28 and 32 — Different ordering of the four inversions

The `[^four_inversions]` footnote is defined identically-labeled in two fascicles but lists the inversions in different order:

- **Fascicle 28** (`[^four_inversions]`): "perceiving purity in the impure, pleasure in suffering, permanence in the impermanent, and self in the non-self"
- **Fascicle 32** (`[^four_inversions]`): "seeing permanence in the impermanent, purity in the impure, happiness in suffering, and self in the non-self"

Ordering: F28 leads with purity-inversion; F32 leads with permanence-inversion. Additionally, F28 uses the full Sanskrit compound *catur-viparyasa* while F32 uses only *viparyasa*. The content of the two notes is otherwise compatible. **Fix:** Standardize ordering and Sanskrit citation to match F28's fuller treatment.

---

### [Contradiction — Moderate] [^three_sufferings] — Fascicles 27 and 31 — Different English rendering for third suffering

The third type of suffering has different English names in the two fascicles:

- **Fascicle 27** (`[^three_sufferings]`): "suffering of conditioned existence (*samskara-duhkhata*, 行苦)"
- **Fascicle 31** (`[^three_sufferings]`): "suffering of formations (*samskara-duhkhata*)"

Both use the same Sanskrit and Chinese but differ in English: "conditioned existence" vs. "formations." The F27 version is more expansive (includes a definition of the subtle nature of samskara-duhkhata) and cites two reference works; the F31 version is compressed. This inconsistency in English rendering contradicts the one-term-one-rendering principle. **Fix:** Standardize to one English rendering; the glossary should be consulted to determine which is authoritative. "Suffering of conditioned existence" more clearly conveys the scope; "suffering of formations" is more common in the Tibetan tradition.

---

### [Contradiction — Moderate] [^four_objects] vs. [^four_objects_complete] — Fascicle 26 vs. Fascicle 27 — Wrong section numbers

The `[^four_objects]` footnote in fascicle 26 cites incorrect section numbers:

- **F26 [^four_objects]** states: "(3) skillful objects — developing analytical understanding (section 27.1); (4) affliction-purifying objects — directly removing afflictions through insight (sections 27.2–27.5)."
- **Actual fascicle 27 structure**: 27.1 = Dependent Origination (purifying-conduct), 27.2 = Element Differentiation (purifying-conduct), 27.3 = Mindfulness of Breathing (purifying-conduct), **27.4 = Skillful Objects**, **27.5 = Affliction-Purifying Objects**.
- **F27 [^four_objects_complete]** correctly states: "skillful objects (*kaushala-alambana*, 27.4)… affliction-purifying objects (*klesha-vishodhana-alambana*, 27.5)."

The F26 footnote is wrong by three sections on skillful objects and wrong by two sections on affliction-purifying objects. A reader following F26's cross-reference will land on the wrong content. **Fix:** Correct F26 [^four_objects] to read "section 27.4" for skillful objects and "section 27.5" for affliction-purifying objects.

---

### [Contradiction — Minor] [^worldly_path] vs. [^two_paths] — Fascicles 27 and 33 — Different Sanskrit terms for the same concept

The worldly/mundane path is referred to with two different Sanskrit terms in two footnotes that appear to discuss the same entity:

- **Fascicle 27** (`[^worldly_path]`): "*samvriti-marga*" (世俗道, "conventional path")
- **Fascicle 33** (`[^two_paths]`): "*laukika-marga*" (世間道, "worldly path")

These are different Chinese compounds and different Sanskrit terms, though they are used for what appears to be the same concept (the path of temporary affliction suppression through coarse/peaceful contrast, distinct from the supramundane path). Neither footnote cross-references the other. A reader could reasonably conclude these are two different things. **Fix:** One footnote should note that *samvriti-marga* and *laukika-marga* are equivalent designations, or the terminology should be unified.

---

### [Contradiction — Minor] [^transformation] — Fascicles 26 and 31 — Different frames for the same technical term

`[^transformation]` is defined in both fascicle 26 and fascicle 31 for the term *ashraya-paravrtti*. The two definitions are not contradictory per se, but they describe different aspects of the same concept without cross-referencing:

- **Fascicle 26**: Transformation = cognitive shift from desire-realm mind to meditative equipoise through **elimination of heaviness** (*dausthulya*); practitioner transcends the mental image and attains direct perception.
- **Fascicle 31**: Transformation = the point where shamatha and vipashyana **cease being separate trainings** and become a self-sustaining process generating direct, non-conceptual knowledge.

These are two different contextual appearances of *ashraya-paravrtti* — the F26 use is in the context of the pervasive objects framework; the F31 use is in the context of shamatha-vipashyana integration. The notes are individually accurate but a reader following F31's note back to F26 (or vice versa) would not find a reconciliation. The notes should at minimum acknowledge each other's context. **Fix:** Add cross-references or clarify that these are two applications of the same concept.

---

## 2. ORPHANED MARKERS

None. Orphan check complete for all eight fascicles:

- Fascicles 28–33: Every footnote label appears exactly twice (once as body reference, once as definition). Total occurrences ÷ 2 = definition count in all cases.
- Fascicle 26: Two labels appear three times each — `[^ubhaya]` (2 body references, 1 definition) and `[^satkaya]` (2 body references, 1 definition). Both multi-references are intentional and appropriate: the concept recurs legitimately in the same fascicle. Not an error.
- Fascicle 27: Exactly twice each.

**No orphans detected.**

---

## 3. DUPLICATE INFORMATION

### [Duplication — Significant] [^agotra] and [^agotra_context] — Fascicle 28 — Two footnotes on the same sentence making the same point

Both footnotes are attached to the *same sentence* in the body text (line 254: "Permanent destruction of yoga refers to a person without lineage (*gotra*).[^agotra][^agotra_context]"). Both make substantively the same claims:

- **[^agotra]**: Introduces the *agotra* concept; notes that other traditions reject it; cites *tathagatagarbha* and Madhyamaka/East Asian opposition; says the text presents the Yogacara position without qualification.
- **[^agotra_context]**: Opens identically ("The doctrine of *agotra*..."); notes it is "most contested"; cites *Lankavatara Sutra* and *Lotus Sutra*; mentions Paramartha's harmonization effort; also says "Asanga's presentation here represents the early, unmodified Yogacara stance."

The second note adds the Paramartha detail and the specific sutra citations (*Lankavatara*, *Lotus*) but is 85% duplicative of the first. Having two footnotes attached to a single term in the same sentence is editorially unusual and reader-disorienting. **Fix:** Merge into a single footnote incorporating the Paramartha detail and sutra citations from [^agotra_context] into [^agotra].

---

### [Duplication — Minor] Body-part count footnotes create a confused picture across three fascicles

Three distinct footnotes report different counts for body-part lists, without noting they are different lists:

- **F26 [^body_parts]**: "approximately thirty-four items" — refers to the internal impurity substances list in section 26.6 (hair, nails, flesh, etc.)
- **F28 [^thirtyfive_body]**: "35-fold classification" — refers to the abstract body-type taxonomy in section 28.11 (body with/without consciousness, male/female body, etc.)
- **F32 [^thirtysix]**: "thirty-six bodily substances" — refers again to the hair-to-urine substance list (same type as F26)

These are genuinely three different lists, so the different counts are correct. However, F32's `[^thirtysix]` makes an erroneous cross-reference that conflates them (see Section 4 below). The counts themselves are not contradictions but the overall picture is confusing. A clarifying note in each that distinguishes "bodily substance list" from "abstract body classification" would help.

---

## 4. CROSS-REFERENCE ERRORS (DISTINCT FROM CONTRADICTIONS)

### [Cross-ref Error — Significant] [^thirtysix] — Fascicle 32 — Points to wrong fascicle section

The footnote `[^thirtysix]` states: "The full list was presented in fascicle 28.11."

However, fascicle 28, section 28.11 contains the **35-fold abstract classification** of body types (body with/without consciousness, female body, male body, etc.) — not the bodily substance list (head-hair through urine). The substance list (hair, nails, teeth, skin, flesh, bones, organs, fluids, excretions) appears in **fascicle 26, section 26.6**. Fascicle 28.11 explicitly labels its list "thirty-five aspects of body" (confirmed in body text and in [^thirtyfive_body]), not thirty-six substances.

**Fix:** Correct the cross-reference in `[^thirtysix]` from "fascicle 28.11" to "fascicle 26, section 26.6."

---

### [Cross-ref Error — Minor] [^four_reasonings_ref] (F27) — Points to section 30.14 with different content claim

The fascicle 27 footnote `[^four_reasonings_ref]` says the four types of reasoning are "defined in detail in the vipashyana framework (section 30.14)." This reference resolves correctly — section 30.14 is "The Three Doors and Six Aspects of Vipashyana" and the footnote `[^four_reasonings]` appears there. However, the F26 footnote `[^four_reasonings]` also gives a full definition with Sanskrit names, while the F27 note merely defers to F30. A reader reading sequentially through F27 who wants the definition must jump to F30. This is a minor usability issue, not an error, but the F27 note could include a brief inline definition.

---

## 5. FOOTNOTE-TO-FOOTNOTE REFERENCES

No footnote explicitly references another footnote by label notation. Several footnotes cross-reference body text sections, and those references were individually verified above. No footnote-to-footnote chains exist that need resolution.

---

## 6. FOOTNOTE DENSITY BALANCE

Counts and word-per-footnote ratios (body text words / number of footnote definitions):

| Fascicle | Words | Footnotes | Words/Note |
|----------|-------|-----------|------------|
| F26 | 11,034 | 45 | ~245 |
| F27 | 11,367 | 41 | ~277 |
| F28 | 12,246 | 37 | ~330 |
| F29 | 11,356 | 36 | ~315 |
| F30 | 7,573 | 24 | ~315 |
| F31 | 6,867 | 23 | ~298 |
| F32 | 9,213 | 41 | ~224 |
| F33 | 9,327 | 33 | ~282 |

**Observations:**

- Fascicles 26 and 32 are the most densely annotated (~245 and ~224 words/note). F26's density is appropriate: it introduces the entire conceptual vocabulary of the translation. F32's density is also appropriate: it is the most practice-facing fascicle, where new concepts accumulate rapidly.
- Fascicle 28 is the least densely annotated (~330 words/note). F28 covers the three trainings, the thirty-seven factors, and the four foundations — topics that are the most thoroughly treated in secondary literature and least in need of translator comment. The lighter annotation is appropriate.
- The overall range of 224–330 words/note is reasonable and proportional to content density. No fascicle appears systematically over- or under-annotated relative to its content.

---

## 7. REMOVED FOOTNOTE TRACES

The footnote audit removed approximately 50 notes. A scan of body-text passages for artifacts of removal (passages that seem to address an explanation no longer present, unexplained jargon, or textual apologies) found no clear orphaned explanatory context. The body text does use "as explained above" and "as broadly explained above" formulas, but these refer to the text's own internal explanations, not to removed footnotes. No removed-footnote artifacts detected.

---

## 8. TONAL CONSISTENCY

Overall, the 280 footnotes are tonally consistent: scholarly, precise, impersonal, comparative. They consistently cite canonical sources in the format (e.g., MN 10, SN 38.14, Abhidharmakosha VI), provide Sanskrit with Chinese in parentheses, and maintain the register of a specialist translator addressing a reader who is 80% practitioner and 20% scholar.

Three localized tonal deviations:

### [Tonal — Minor] [^mutual_support], [^signless_beginner], [^completion_criteria] — Fascicle 31 — Double-dash instead of em-dash

Three footnotes in fascicle 31 use double-dash (`--`) instead of the em-dash (`—`) used everywhere else in the translation. All other 277 footnotes use em-dashes consistently. The affected footnotes are:

- `[^mutual_support]`: "neither calm abiding alone nor insight alone suffices -- only their union..."
- `[^signless_beginner]`: "This instruction -- that a beginner should initially..." and "This "clearing-first" approach may reflect..."
- `[^completion_criteria]`: "These completion criteria -- specifying exactly when..."

**Fix:** Replace `--` with `—` in all three instances.

### [Tonal — Minor] [^pliancy_process] — Fascicle 32 — Shift from scholarly to direct practitioner address mid-note

The `[^pliancy_process]` footnote begins in scholarly register ("This passage describing the arising of pliancy... is one of the most important in the entire Sravakabhumi") but transitions to direct practitioner address ("A practitioner experiencing these should continue practice without either pursuing or suppressing them"). No other footnote addresses the reader as a practitioner or offers personal meditation guidance. This is a register shift within a single note. The note then returns to scholarly mode for the Tsongkhapa warning. **Fix:** Rephrase the practitioner-address sentence in third person ("Practitioners experiencing these sensations should continue without...") or as descriptive instruction ("The text implicitly counsels continuation without...").

### [Tonal — Minor] [^signless_beginner] — Fascicle 31 — Hedging language inconsistent with assertive tone elsewhere

This note ends: "This 'clearing-first' approach may reflect a distinctively Yogacara pedagogy." The phrase "may reflect" is notably hedged compared to other notes, which assert confidently (e.g., "is a distinctively Yogacara concern," "is central to Yogacara soteriology"). The hedging is not inappropriate — the claim is genuinely speculative — but it departs from the dominant assertive register. This is the same footnote with the double-dash issue noted above.

---

## SUMMARY TABLE

| # | Type | Location | Severity | Issue |
|---|------|----------|----------|-------|
| 1 | Contradiction | [^four_inversions], F28 vs F32 | Moderate | Different ordering of the four inversions |
| 2 | Contradiction | [^three_sufferings], F27 vs F31 | Moderate | Third suffering: "conditioned existence" vs. "formations" |
| 3 | Section Ref Error | [^four_objects], F26 | Significant | Claims skillful objects=27.1 and affliction-purifying=27.2-27.5; should be 27.4 and 27.5 |
| 4 | Cross-ref Error | [^thirtysix], F32 | Significant | Claims substance list is in F28.11; it is in F26 section 26.6 |
| 5 | Duplication | [^agotra] + [^agotra_context], F28 | Significant | Two footnotes on the same sentence; ~85% duplicate content |
| 6 | Formatting | [^mutual_support], [^signless_beginner], [^completion_criteria], F31 | Minor | Double-dash instead of em-dash (3 instances) |
| 7 | Contradiction | [^transformation], F26 vs F31 | Minor | Same term, different framing, no cross-reference |
| 8 | Contradiction | [^worldly_path] vs [^two_paths], F27 vs F33 | Minor | Different Sanskrit/Chinese for same concept |
| 9 | Tonal shift | [^pliancy_process], F32 | Minor | Shifts to direct practitioner address mid-note |
| 10 | Tonal hedge | [^signless_beginner], F31 | Minor | "May reflect" vs. assertive register of other notes |
| 11 | Typo | [^liberation_mastery], F33 | Minor | "abhibhv-ayatana" should be "abhibhu-ayatana" |
| 12 | Density | None | Note | F32 is most dense (~224 words/note); appropriate to content |

**No orphans detected. No footnote-to-footnote reference chains found. Total: 4 significant issues, 7 minor issues, 0 orphans.**
