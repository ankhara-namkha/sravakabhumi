# Readability Review: Fascicle 27, Sections 27.1-27.2

## Summary
18 issues found (2 critical, 9 moderate, 7 minor)

---

## Findings

### R-1: "Only dharmas give rise to dharmas" — Critical
- **Location:** Line 23
- **Issue:** The sentence "Only dharmas give rise to dharmas; there is no agent and no experiencer" uses the word "dharma" untranslated and without explanation. A general English reader has no way to know whether "dharma" here means Buddhist teachings, phenomena, mental events, or something else entirely. This is the first occurrence of "dharma" used in this technical sense in this section and it receives no gloss. The word appears four times in the same sentence. Someone without Abhidharma background will be completely lost.
- **Current text:** "Throughout the three times — past, present, and future — there are only formations, only dharmas, only events, only causes, and only results..."
- **Suggestion:** Add a bracketed gloss on first use: "only dharmas (phenomena, mental and physical events)" or add a footnote: "Here *dharma* means any conditioned phenomenon — a mental event, physical process, or moment of experience — not the Buddhist teachings." The list structure "only formations, only dharmas, only events" is also redundant-feeling since "dharmas" and "events" are very close in meaning; a brief clarifying note would help readers understand these are distinct categories.

### R-2: Four reasonings listed without explanation — Critical
- **Location:** Line 23
- **Issue:** "reasoning from dependence, reasoning from function, reasoning from proof, and reasoning from the nature of things" appears with no explanation and a footnote that merely says "were defined in section 26.5." A reader encountering section 27 without having read section 26 — or a reader who read it and did not retain the technical definitions — has no way to understand what these four reasonings mean or why they matter for this meditation object. The footnote is a cross-reference, not an explanation.
- **Current text:** "[^four_reasonings_ref]: The four types of reasoning (*yukti*) were defined in section 26.5 (the limit of things). See footnote [^four_reasonings] in fascicle 26."
- **Suggestion:** Expand the footnote to include at least a one-sentence gloss of each reasoning, e.g.: "Reasoning from dependence: things arise in dependence on conditions. Reasoning from function: things are known by what they do. Reasoning from proof: valid cognition (perception and inference) establishes what exists. Reasoning from the nature of things: fire is hot, water is wet — their natures are simply what they are." Without this, the four reasonings are jargon that does no work for the reader.

### R-3: "Personally appropriated" is unexplained on first use in the main text — Moderate
- **Location:** Line 46
- **Issue:** The phrase "personally appropriated" appears in the running translation text (line 46) before the footnote that explains it (footnote on line 110). Readers reading linearly will encounter this strange phrase — "which is personally appropriated" — and have no idea what it means. The footnote is well-written but it is only visible if the reader looks down at the bottom of the document.
- **Current text:** "...which is personally appropriated.[^upadatta]"
- **Suggestion:** Add a brief parenthetical in the text itself: "...which is personally appropriated (i.e., experienced from the inside as part of one's own living body).[^upadatta]" The footnote can remain for fuller explanation. This is a case where the inline gloss is more important than the footnote because the phrase is otherwise opaque.

### R-4: Sentence over 50 words — Moderate
- **Location:** Line 23
- **Issue:** The opening sentence of section 27.1 is 72 words and contains four coordinate phrases, a parenthetical enumeration, and a self-referential close. It is grammatically coherent but requires multiple re-reads.
- **Current text:** "Throughout the three times — past, present, and future — there are only formations, only dharmas, only events, only causes, and only results, all falling within correct reasoning: reasoning from dependence, reasoning from function, reasoning from proof, and reasoning from the nature of things."
- **Suggestion:** Break into two sentences: "Throughout the three times — past, present, and future — there are only formations, only dharmas (phenomena), only events, only causes, and only results. All of this falls within correct reasoning: reasoning from dependence, reasoning from function, reasoning from proof, and reasoning from the nature of things."

### R-5: "Delusion-conduct" is introduced without definition — Moderate
- **Location:** Line 25
- **Issue:** "a person of delusion-conduct" is used without any prior definition in sections 27.1-27.2. A reader beginning in section 27 has no idea what "delusion-conduct" means. The term "pride-conduct" appears later (line 100) in the same way. These are technical typological categories that require at least a one-line explanation on first use.
- **Current text:** "Through attending to this object, a person of delusion-conduct has all their delusion-conduct attenuated..."
- **Suggestion:** Add a footnote on first use of "delusion-conduct": "*Delusion-conduct* (*moha-carita*): one of five character types defined in the Sravakabhumi based on a person's dominant mental tendency. A person of delusion-conduct is characterized by confusion, dullness, or clouded perception as their most prominent affliction. Each type is paired with a specific meditation object that directly counteracts its dominant tendency." A similar note should appear for "pride-conduct" on line 100.

### R-6: "Notion of unity" — unclear English — Moderate
- **Location:** Line 100
- **Issue:** The phrase "they abandon the notion of unity with regard to the body" is unclear in English. "Notion of unity" does not naturally communicate the sense of perceiving the body as a single, solid self. A general reader might understand it as abandoning the idea that the body is coherent or organized, rather than the specifically Abhidharma meaning of mistaking a collection of elements for a unified personal self.
- **Current text:** "they abandon the notion of unity[^eka_samjna] with regard to the body"
- **Suggestion:** Rephrase to "they abandon the perception of the body as a single, unified whole" and let the footnote handle the Sanskrit. The footnote (line 122) actually states this interpretation clearly; it should be brought up into the text.

### R-7: Fire element instances sentence is over 50 words — Moderate
- **Location:** Line 76
- **Issue:** The description of the external fire element's instances runs to approximately 82 words in a single sentence with multiple coordinate clauses. The logical structure (fire sought, fire produced, things fire can burn, fire subsides) is clear but the sentence is fatiguing.
- **Current text:** "Among humans, fire is sought by means of fire-drills and the like... Such and similar things are called the external fire element."
- **Suggestion:** Break into two or three sentences: "Among humans, fire is sought by means of fire-drills and the like, or from dried cow dung and other materials. Once produced, fire can burn cow dung, grass, firewood, thickets, wilderness, mountains, or islets; it can also burn villages, cities, and entire countries with their surroundings. Such and similar things are called the external fire element."

### R-8: Wind element instances sentence is over 50 words and contains unexplained Sanskrit — Moderate
- **Location:** Line 88
- **Issue:** The external wind element paragraph (line 88) contains two unexplained Sanskrit terms (*vishva* and *vairamana*) in the main text list, and the sentence describing the effects of these winds runs to approximately 85 words. A reader will stumble on "the *vishva* wind, the *vairamana* wind" without context. The footnote explains these, but the list would benefit from a brief note inline.
- **Current text:** "...the *vishva* wind, the *vairamana* wind, the cosmic wind-wheel, and the seasonal great wind.[^external_winds]"
- **Suggestion:** After the Sanskrit terms, add "(traditional Indian wind names; see note)" or move the explanation inline: "the *vishva* and *vairamana* winds (traditional Indian names for powerful wind types), the cosmic wind-wheel (the foundational wind supporting the world-system in Buddhist cosmology), and the seasonal great wind." Also break the long sentence after the list.

### R-9: "Pippala wind" in the internal winds list — Moderate
- **Location:** Line 84
- **Issue:** "the *pippala* wind" appears in the list of twelve internal winds without any inline explanation. This is the only Sanskrit term that appears unexplained in the main body of the internal wind list (the others are descriptive English). A reader will encounter it as a stumble without understanding what quality or sensation it refers to.
- **Current text:** "the *pippala* wind"
- **Suggestion:** Add a brief parenthetical: "the *pippala* wind (a trembling, pervasive sensation, named after the quivering of *pippala* tree leaves)" or move the key phrase from the footnote into the text.

### R-10: Redundant closing formula repeated throughout — Minor
- **Location:** Lines 50, 52, 60, 64, 72, 76, 84, 88, 92, 96
- **Issue:** The phrase "Such and similar things are called the [X] element" appears at the end of nearly every sub-section. While this is faithful to the source structure, the repetition creates a rote, formulaic feel in English that may cause readers to skim. The formula appears approximately ten times in the section.
- **Current text:** "Such and similar things are called the internal earth element." / "Such and similar things are called the external earth element." (repeated)
- **Suggestion:** Consider using slight variation for the external elements: "These constitute the external earth element" or "These are examples of the external earth element." Alternatively, a translator's note could acknowledge that the repetition is a deliberate structural feature of the source text, which would help readers understand why it sounds formulaic.

### R-11: Space element description assumes anatomical knowledge — Minor
- **Location:** Line 92
- **Issue:** The space element is described as "the openings and cavities of the eyes, ears, nose, mouth, throat, and so forth. Through these one swallows; within these one swallows; and after swallowing, through these openings what has been consumed passes downward and is eliminated." The phrase "through these one swallows; within these one swallows" is slightly awkward and logically ambiguous — it sounds like it is saying the same thing twice. The anatomical pathway (mouth to throat to gut to elimination) is implied but not stated.
- **Current text:** "Through these one swallows; within these one swallows; and after swallowing, through these openings what has been consumed passes downward and is eliminated."
- **Suggestion:** Rephrase for clarity: "Through these openings one takes in food and drink; through this passage what has been consumed moves downward and is eventually eliminated." A brief footnote could note that the "space element" here refers to the hollow passages of the body, not outer space or emptiness.

### R-12: Footnote [^pratityasamutpada_object] is long and front-loads scholarly framing — Minor
- **Location:** Line 104
- **Issue:** This footnote (line 104) is 72 words and begins by characterizing the section as "notably concise" — an observation that is useful for a scholar but mildly disorienting for a practitioner who may not know what length to expect. The note also introduces the Sanskrit compound *pratyaya-pratityasamutpada* and the technical term "delusion-conduct" in the footnote, but neither term has yet been explained in the main text.
- **Current text:** "This section is notably concise. The nature of conditions and dependent origination (*pratyaya-pratityasamutpada*, 緣性緣起) as a meditation object addresses delusion-conduct by revealing that all phenomena arise solely through causes and conditions, without any creator or experiencer."
- **Suggestion:** Remove the opening characterization "This section is notably concise" or move it to a translator's preface note. Begin the footnote with the explanation: "The meditation on dependent origination — the arising of all phenomena through causes and conditions, without any creator or experiencer — directly counteracts delusion-conduct (the tendency toward confusion and clouded perception). The fuller treatment of this practice appears in sections 27.3 and 27.4."

### R-13: Footnote [^citta_manas_vijnana] is too technical for the general practitioner — Minor
- **Location:** Line 120
- **Issue:** This footnote (line 120) introduces "Yogacara psychology," "alaya-vijnana," and "klishta-manas" without explanation. A practitioner without Yogacara background will not know what any of these terms mean and will find the footnote raises more questions than it answers. The footnote is well-written for a scholar but misses the general practitioner reader.
- **Current text:** "In more technical Yogacara contexts (e.g., the Yogacarabhumi's Chitta section), they take on distinct meanings corresponding to the alaya-vijnana, klishta-manas, and the six active consciousnesses respectively."
- **Suggestion:** Either remove the second paragraph of the footnote (the Yogacara technical detail) or add brief parenthetical glosses: "the alaya-vijnana (storehouse consciousness), klishta-manas (the afflicted thinking mind), and the six active consciousnesses (the senses plus conceptual mind)." Alternatively, mark the second paragraph as "For scholars:" to signal it is optional reading.

### R-14: Logical flow break at end of section 27.2 — Minor
- **Location:** Lines 98-100
- **Issue:** The section "Application to Pride-Conduct" (lines 98-100) appears at the end of the element-differentiation section without a transitional sentence. A reader who has been reading descriptions of the six elements suddenly encounters "when a person of pride-conduct attends to element differentiation" without any signal that the analytical description is complete and the practical application is beginning. This is a mild but real discontinuity.
- **Current text:** (immediately after the consciousness element description, the sub-heading "Application to Pride-Conduct" appears)
- **Suggestion:** Add a transitional sentence before the sub-heading: "Having enumerated the six elements, the text now explains how this analysis is applied in meditation practice." Or rephrase the sub-heading to "27.2 Closing: Meditation Application for Pride-Conduct" to make the shift explicit.

### R-15: "Included in the category of the solid and hard, included in the category of earth" — repetitive phrasing — Minor
- **Location:** Lines 46, 48
- **Issue:** The phrase "included in the category of the solid and hard, included in the category of earth" appears twice in the earth element definitions (internal and external). The repetition is intentional (structural fidelity to the source), but the English phrase "included in the category of" is formal and slightly stilted. For the external element, it appears again in slightly compressed form. This is a minor style issue.
- **Current text:** "included in the category of the solid and hard, included in the category of earth"
- **Suggestion:** Consider "characterized by solidity and hardness, belonging to the earth element" as a more natural English rendering, while preserving the parallel structure. Alternatively, a translator's note acknowledging the deliberate repetition would help readers understand the stylistic choice.

### R-16: "Heat, uniform heat, and thorough heat" — unexplained categories — Minor
- **Location:** Line 72
- **Issue:** The three types of heat (熱, 等熱, 遍熱) are introduced in the main text but the footnote (line 114) that explains them is detailed and helpful. The main text sentence — "whatever warmth there is in the body that causes heat, uniform heat, and thorough heat throughout the body" — is slightly awkward because "heat" and "uniform heat" and "thorough heat" all sound like degrees of the same thing to an English reader, not three distinct categories.
- **Current text:** "whatever warmth there is in the body that causes heat, uniform heat, and thorough heat throughout the body"
- **Suggestion:** Add a brief inline gloss or reorder for clarity: "whatever warmth there is in the body — including localized heat, evenly distributed warmth, and the pervasive heat that sustains all bodily functions — which is personally appropriated." The footnote can then confirm and expand.

### R-17: Title "Purifying-Conduct Objects" is not self-explanatory — Minor
- **Location:** Lines 19, 29
- **Issue:** The section headings "Purifying-Conduct Objects: Dependent Origination" and "Purifying-Conduct Objects: Element Differentiation" use the term "purifying-conduct" without explanation anywhere in these first two sections. A reader does not know whether this means objects that purify one's conduct, objects appropriate to a purified practitioner, or something else. The term is a translation of a technical category in the Sravakabhumi's typology of meditation objects.
- **Current text:** "### 27.1 Purifying-Conduct Objects: Dependent Origination"
- **Suggestion:** Add a translator's note at the first occurrence of "purifying-conduct objects" explaining the category: "*Purifying-conduct objects* (*carya-vishodhana-alambana*): meditation objects specifically prescribed for practitioners whose predominant character type (conduct-type) requires purification of a specific affliction. Each of the five character types has a corresponding purifying object: impurity for lust-conduct, loving-kindness for hatred-conduct, dependent origination for delusion-conduct, element differentiation for pride-conduct, and mindfulness of breathing for discursive-conduct."

### R-18: "Formations" is ambiguous — Minor
- **Location:** Line 23
- **Issue:** "There are only formations, only dharmas, only events, only causes, and only results" — the word "formations" (*samskara*) will be read by a general English reader as a military or geological metaphor. It has a specific technical meaning in Buddhist contexts (conditioned, constructed things) but that meaning is not available to a reader without background.
- **Current text:** "there are only formations, only dharmas..."
- **Suggestion:** Add a brief parenthetical: "only formations (conditioned, constructed phenomena), only dharmas (mental and physical events)..." or a footnote on first use of "formations" that explains: "*Formations* (Sanskrit: *samskara*) refers to conditioned or constructed phenomena — anything that comes into being through causes and conditions."
