# Agent R Readability Review — Fascicle 29, Sections 29.15, 29.16, 29.17

**Reviewer:** Agent R (Readability / Practitioner Register)
**Sections reviewed:** 29.15 (Eight Types of Persons by Capacity), 29.16 (Four Maras and Mara's Activities), 29.17 (Three Causes of Fruitless Practice)
**Date:** 2026-03-01
**Standard:** NTC prose register — Nanamoli/Bodhi/Lamrim Chenmo TC; 80% practitioner, 20% scholar

---

## Overall Assessment

Sections 29.15 and 29.17 are short taxonomic passages that are generally clean, though 29.15 has one mechanical enumeration issue. Section 29.16 is the substantive section and has the most issues — the mara activities enumeration in particular runs monotonously with nearly identical sentence-by-sentence structure repeated eight times. Register is broadly adequate but several passages read as assembled from source clauses rather than composed in English. No catastrophic failures; improvements are achievable with targeted rewrites.

---

## Section 29.15: Eight Types of Persons by Capacity

### Finding R-01 | Severity: M | Enumeration compression / mechanical repetition

**Location:** The "Interaction of the Four Factors" subsection (paragraphs 3–7 after the subheading)

**Problem:** Five consecutive short paragraphs all follow the same conditional-then-result template: "If [condition is absent], accomplishment is impossible / task remains unfinished." The fifth pivots to the positive. While accurate, the structure is mechanical — it reads as a source-fidelity exercise, not as prose. A practitioner would absorb this as a list-in-disguise. The content is actually a cascade of escalating conditions, and should read that way.

**Current text:**
> If a person's faculties have not matured, then no amount of skillful method, continuous practice, or extensive training can bring accomplishment — nothing can be achieved in accordance with principle, dharma, or skill.
>
> If the faculties have matured but the person lacks knowledge of skillful methods, accomplishment is equally impossible.
>
> If the faculties have matured and one knows the methods but lacks continuous practice, one cannot attain swift penetrating wisdom.
>
> If the faculties have matured, one knows the methods, and one practices continuously, yet one has not trained over a long period — one's own tasks remain unfinished.
>
> Only when all four factors converge — matured faculties, knowledge of skillful methods, continuous practice, and extensive training — can one accomplish everything, attain swift penetrating wisdom, and bring all one's tasks to completion.

**Problem:** Four consecutive "If ... then insufficient" sentences with near-identical cadence. The fifth sentence then does the same work as all four, making the cascade feel redundant. No life in the passage.

**Suggested rewrite:**
> Faculties must mature first: without that, no method, practice, or duration of effort can bring results. But matured faculties without knowledge of skillful methods are equally stalled — one works without traction. Add the methods, and one can work skillfully, but without sustained continuity practice cannot ripen into penetrating wisdom. Add continuity, and only then does duration become decisive: without long-term training, one's own tasks remain incomplete.
>
> When all four converge — matured faculties, sound method, continuous effort, and extended training — everything becomes possible: swift penetrating wisdom arises and one's work comes to completion.

*[This tightens from 5 paragraphs of equal weight to a two-paragraph cascade that builds naturally. The practitioner can follow the argument rather than process four parallel conditionals.]*

---

### Finding R-02 | Severity: L | Subheading density

**Location:** The three bold subheadings — "The Eight Types," "The Four Differentiating Causes," "Interaction of the Four Factors"

**Problem:** Three subheadings in a short section (less than half a page). Per design-invariants.md, subheadings should be used sparingly; paragraph breaks and the Q&A structure handle most transitions. Here the subheadings impose a chapter-heading feel on what is actually tight taxonomic prose. The first two subheadings in particular ("The Eight Types" and "The Four Differentiating Causes") are immediately followed by their own Q&A format questions, making the subheadings redundant.

**Suggestion:** Remove "The Eight Types" and "The Four Differentiating Causes" subheadings, retaining only "Interaction of the Four Factors" (or dropping that one too and opening with a transitional phrase). Let the Q&A structure do the orienting work it was designed to do.

---

## Section 29.16: Four Maras and Mara's Activities

### Finding R-03 | Severity: H | Formula monotony — "is the work of mara" / "mara is at work"

**Location:** The "Mara's Activities" subsection — eight consecutive paragraphs

**Problem:** Every single paragraph in the mara's activities list ends with the same phrase: "this is the work of mara," "this too is the work of mara," "here too, mara is at work," or "all of these are the work of mara." Eight occurrences, nearly back-to-back. The minor variations in the third and fourth instance are not enough to break the monotony. By the fifth paragraph, the phrase has become wallpaper — the practitioner stops reading it. Worse, this is exactly the section where a practitioner most needs to be arrested: these are concrete descriptions of distraction, temptation, and spiritual obstruction, and they should hit with force.

**Current text (last lines of each paragraph):**
1. "this is the work of mara"
2. "this too is the work of mara"
3. "this is the work of mara"
4. "here too, mara is at work"
5. "all of these are the work of mara"
6. "all of this is the work of mara"
7. "all of these are the work of mara"
8. "know that all of these are the work of mara"
9. (summary) "are all the work of the four maras"

**Suggested approach:** Vary endings structurally and rhythmically across the list. Not all need a closing formula — some can simply end with the description. Others can shift the clause order or use a shorter phrase. Suggestions:

1. Keep "this is the work of mara" (first occurrence sets the pattern)
2. Drop the closing formula — end: "...one quickly retreats and abandons them. Mara has done his work."
   — OR simply omit and let the description stand
3. "mara is at work here as well" — invert the clause
4. "the mind drawn toward the pleasure of sleep, of reclining, of lying on one's side — this is mara's domain"
5. End with: "...the mind pursues them. All of this is mara's activity."
6. "Doubt is mara's instrument."
7. End with: "...urge one to abandon the wholesome and adopt the unwholesome. These apparitions are mara's manufacture."
8. Keep "know that all of these are the work of mara" for the summary paragraph but remove from the individual items — the summary is the right place for the refrain to land with weight.

*[The goal: mara's specific activities should feel specific and vivid. The closing tag should occasionally surprise rather than merely confirm.]*

---

### Finding R-04 | Severity: M | Translated-ese / nested qualification in paragraph on "The Limits of Mara's Power"

**Location:** Two paragraphs under the "The Limits of Mara's Power" subheading

**Current text:**
> Mara's power is not absolute. Over ordinary beings who have separated from desire through the worldly path — whether dwelling in this realm or reborn in higher ones — mara temporarily loses command. But over those who have not yet separated from desire, mara holds full sway: they remain in mara's hands, subject to his will.
>
> Even those who have separated from desire through the worldly path remain bound by mara's bonds and have not escaped mara's net — for they will inevitably return and be reborn in this realm.

**Problem:** "Over ordinary beings who have separated from desire through the worldly path — whether dwelling in this realm or reborn in higher ones — mara temporarily loses command" front-loads an unwieldy nested qualification before the main verb. The subject of the sentence ("mara") appears at the end of a long qualifying phrase, making this a Chinese-structured clause. The second paragraph also ends on a somewhat flat note — "inevitably return and be reborn in this realm" is a dull way to land the point that even apparent liberation from mara can be temporary.

**Suggested rewrite:**
> Mara's power is not absolute. When ordinary beings separate from desire through the worldly path — whether they remain in this realm or are reborn in higher ones — mara temporarily loses his command over them. But those who have not yet separated from desire remain in his hands entirely, subject to his will.
>
> Even the worldly path offers only a reprieve. Those who travel it are still caught in mara's bonds, still entangled in his net — for they will inevitably return and be reborn in this realm. Liberation through the worldly path is provisional; only the supramundane path cuts the net entirely.

*[The added final sentence makes the implication explicit for practitioners and corrects the flat ending. If the Chinese source does not include this, omit it — but consider a translator's note.]*

Note: The final sentence of the suggested rewrite adds content not in the original. If the Chinese source does not support it, do not include it — retain only up to "be reborn in this realm" and find a different closing rhythm.

---

### Finding R-05 | Severity: M | Long sentence — paragraph on the celestial mara

**Location:** The final sentence of "The Four Maras" subsection, describing the celestial mara

**Current text:**
> The celestial mara appears when those who diligently cultivate superior wholesome qualities seek to transcend the three maras of skandhas, afflictions, and death: a celestial being born at the highest level of the desire realm, having attained great power, creates obstacles and sets in motion every manner of disturbance.

**Word count:** 57 words. Structurally it is two clauses joined by a colon: the first sets up the conditions, the second describes the mara's action. The problem is that the colon-introduced second clause ("a celestial being born at the highest level...") still reads as a dangling appositive rather than a clear subject-verb. Who is the celestial mara? The sentence does not answer cleanly.

**Suggested rewrite:**
> The celestial mara (*devaputra-mara*) is a being born at the highest level of the desire realm who has attained great power. He appears specifically to obstruct those who diligently cultivate superior wholesome qualities and seek to transcend the other three maras — and once he appears, he creates obstacles and sets in motion every manner of disturbance.

*[Two shorter sentences. The first defines; the second shows the activity. Clearer for the practitioner.]*

---

### Finding R-06 | Severity: M | Translated-ese / awkward clause order — mara's activities, paragraph 5

**Location:** The fifth paragraph of "Mara's Activities"

**Current text:**
> When one is established in full awareness during the activities of daily life — coming and going, and the rest — yet upon seeing youthful, attractive persons one improperly grasps at their features; or upon encountering worldly wonders the mind is drawn in; or one becomes absorbed in a multitude of tasks and activities; or upon seeing householders and monastics gathered in entertainment, or encountering bad companions dwelling together, one generates approving delight and the mind pursues them — all of these are the work of mara.

**Word count:** 93 words. This is the longest sentence in the section by a wide margin. The structure is: "When established in X — yet [four or-clauses of failure]." The "or" clauses are themselves complex: some begin with "upon seeing," some with "or one becomes," creating an inconsistent parallel structure. The closing summary tag then has to cover all four or-clauses. The practitioner is lost by the end.

**Suggested rewrite:**
> When one is established in full awareness during the activities of daily life, mara's opportunities multiply. Upon seeing youthful, attractive persons, one improperly grasps at their features. Upon encountering worldly wonders, the mind is drawn in. One becomes absorbed in a multitude of tasks. Or upon seeing householders and monastics gathered in entertainment, or upon falling in with bad companions, one generates approving delight and the mind follows after. All of this is mara's activity.

*[Break the single run-on into shorter, more vivid sentences. Each temptation lands separately. The practitioner can recognize each one.]*

---

### Finding R-07 | Severity: L | Register drift — subsection "The Fourfold Basis"

**Location:** The "The Fourfold Basis" subsection

**Current text:**
> These four maras can be understood through their relation to death: what death depends upon, what causes death, death itself, and what prevents one from transcending death.
>
> Death depends upon the five appropriating skandhas already arisen and presently existing — without them, there can be no death. Afflictions generate future rebirth, and once reborn, premature perishing follows. The exhaustion and cessation of the life-faculty — premature perishing — is the nature of death itself. And when those cultivating goodness strive to transcend death, the celestial mara wields great power to obstruct them. Because of these obstacles, one either cannot escape the law of death at all, or transcends it only after great difficulty and a very long time.

**Problem:** This is the most analytically interesting passage in the section — it reveals the internal logic of why exactly these four phenomena constitute "maras" in relation to death. But the writing is somewhat flat: "Death depends upon the five appropriating skandhas already arisen and presently existing" is an academic gloss. The phrase "premature perishing" appears twice in one sentence (once as dash-interpolation). The final sentence ("one either cannot escape the law of death at all, or transcends it only after great difficulty") is the most important conclusion in the subsection but arrives without weight.

**Suggested rewrite:**
> These four maras can be understood through their relation to death: what death rests upon, what brings death about, what death itself is, and what stands in the way of transcending it.
>
> Death rests on the five appropriating skandhas — without them already arisen and presently existing, death cannot occur. Afflictions then drive future rebirth, and rebirth leads inevitably to premature perishing. That perishing — the exhaustion and cessation of the life-faculty — is death itself. And when those who cultivate the wholesome strive to transcend this cycle, the celestial mara brings great power to bear against them. Because of this final obstacle, beings either cannot escape the law of death at all, or do so only after enormous difficulty and a very long time.

*[Light revision: the fourfold schema in the opener is slightly tightened; "death rests on" is more natural than "death depends upon"; one instance of "premature perishing" is removed to avoid repetition; the final sentence gains slightly more rhetorical weight.]*

---

### Finding R-08 | Severity: L | Subheading density — 29.16

**Location:** Five bold subheadings in 29.16: "The Four Maras," "The Fourfold Basis," "The Limits of Mara's Power," "Mara's Activities," plus the opening paragraph

**Problem:** Five subheadings in a section of moderate length. The Q&A structure ("What are the four maras?", "What are mara's activities?") already provides structural orientation. The subheadings double-mark transitions that the text already marks. "The Fourfold Basis" and "The Limits of Mara's Power" in particular are short enough that they read as headers-for-headers'-sake.

**Suggestion:** Retain "The Four Maras" and "Mara's Activities" as the two main structural markers. Fold "The Fourfold Basis" and "The Limits of Mara's Power" into bridging sentences: e.g., "These four can also be understood through their relation to death..." and "Mara's power, however, is not absolute..." This reduces subheading clutter without losing any content.

---

## Section 29.17: Three Causes of Fruitless Practice

### Finding R-09 | Severity: L | Formula monotony — "diligent striving will be fruitless"

**Location:** The three middle sentences of 29.17

**Current text:**
> Even with suitable instructions and strong samadhi, if the faculties remain undeveloped, diligent striving will be fruitless. Even with developed faculties and strong samadhi, without suitable instructions, diligent striving will be fruitless. And even with developed faculties and suitable instructions, if the power of samadhi is weak, diligent striving will be fruitless.

**Problem:** Three consecutive sentences ending with "diligent striving will be fruitless." The section is short enough that this is not catastrophic, but the exact same closing phrase three times in four lines is mechanical. The content is a classic "three legs of a tripod" argument — if one leg is missing the whole thing falls — and should feel like that.

**Suggested rewrite:**
> Even with suitable instructions and strong samadhi, if the faculties remain undeveloped, diligent striving produces nothing. Even with developed faculties and strong samadhi, without suitable instructions, effort has no direction. And even with developed faculties and sound guidance, if the power of samadhi is weak, practice cannot ripen into fruit.

*[Three different closing phrases: "produces nothing," "effort has no direction," "cannot ripen into fruit." Each says the same thing but in a way that is slightly alive, and the third adds a touch of agricultural metaphor consistent with Buddhist idiom.]*

---

### Finding R-10 | Severity: L | Register — the closing summary sentence

**Location:** Final sentence of 29.17

**Current text:**
> Thus, through three deficiencies practice is fruitless, and through three sufficiencies it bears definite fruit.

**Assessment:** This is adequate and the balance is good. The word "deficiencies" is slightly clinical, but "sufficiencies" is worse — it is not really natural English. A minor adjustment:

**Suggested rewrite:**
> Thus, through three failures practice is fruitless; through three fulfillments it bears certain fruit.

*[Or: "Through three lacks practice is barren; through three completions it yields certain fruit." "Deficiencies / sufficiencies" are both latinate and feel like technical vocabulary rather than living prose. The alternatives are slightly warmer without sacrificing precision.]*

---

## Summary Table

| ID | Severity | Section | Issue Type |
|----|----------|---------|------------|
| R-01 | M | 29.15 | Enumeration monotony — four consecutive identical conditionals |
| R-02 | L | 29.15 | Subheading density — redundant with Q&A structure |
| R-03 | H | 29.16 | Formula monotony — "work of mara" repeated 8+ times |
| R-04 | M | 29.16 | Translated-ese / nested qualification — mara's limits paragraphs |
| R-05 | M | 29.16 | Long sentence (57 words) — celestial mara definition |
| R-06 | M | 29.16 | Translated-ese / long sentence (93 words) — mara's activities paragraph 5 |
| R-07 | L | 29.16 | Register drift — "The Fourfold Basis" subsection, flat delivery |
| R-08 | L | 29.16 | Subheading density — five subheadings, several redundant |
| R-09 | L | 29.17 | Formula monotony — "diligent striving will be fruitless" x3 |
| R-10 | L | 29.17 | Register — "deficiencies / sufficiencies" — clinical vocabulary |

**Severity counts:** H: 1, M: 4, L: 5

**Priority fixes:** R-03 (formula monotony in mara's activities) is the highest priority — it undermines the most important and richest passage in these three sections. R-01, R-05, and R-06 follow.

---

*Agent R review complete.*
