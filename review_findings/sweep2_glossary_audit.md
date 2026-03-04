# Bidirectional Glossary Audit — Sweep 2
## Methodology
- Direction 1: Random sample of ~50 glossary entries verified against all 8 translation files (fascicles 26–33)
- Direction 2: All italicized Sanskrit/Pali terms extracted from all 8 translation files; checked against glossary
- Chinese character consistency in footnotes also checked

---

## DIRECTION 1: Glossary → Translation
*Checking that glossary-prescribed renderings are actually used in the translation.*

### CLEAN — No Issues Found (40 terms checked)

| Glossary Term | Expected Rendering | Verdict |
|---|---|---|
| klesha / 煩惱 | afflictions (NOT defilements) | CLEAN — no "defilements" in any file |
| asrava / 漏 | outflows (NOT canker) | CLEAN — no "canker" anywhere |
| bodhi / 菩提 | awakening (NOT enlightenment) | CLEAN — no "enlightenment" in body text |
| bhagavat / 世尊 | Blessed One (NOT World-Honored One) | CLEAN |
| vipashyana / 毘鉢舍那 | vipashyana (NOT vipassana) | CLEAN — no Pali form |
| shamatha / 奢摩他 | shamatha (NOT samatha) | CLEAN |
| dhyana / 靜慮 | dhyanas (NOT jhana) | CLEAN |
| nirvana / 涅槃 | nirvana (NOT nibbana) | CLEAN |
| anushaya / 隨眠 | latent tendency | CLEAN — used correctly throughout |
| paryavasthana / 纏 | entanglement | CLEAN — used consistently |
| ashraya-paravrtti / 轉依 | transformation of the basis | CLEAN |
| prashrabdhi / 輕安 | pliancy | CLEAN |
| dausthulya / 麁重 | heaviness | CLEAN |
| satkaya-drishti / 薩迦耶見 | view of the transitory collection | CLEAN |
| anushaya / 隨眠 | latent tendency | CLEAN |
| catur-viparyasa / 四顛倒 | four inversions | CLEAN |
| pratipada / 行迹 | course of progress | CLEAN |
| maula-dhyana / 根本靜慮 | root dhyana | CLEAN |
| gotra / 種姓 | lineage | CLEAN |
| dharmanusarin / 隨法行者 | dharma-follower | CLEAN |
| shraddhanusarin / 隨信行者 | faith-follower | CLEAN |
| samyaktva-niyama / 正性離生 | certainty of correctness | CLEAN |
| adhimoksha / 勝解 | resolute confidence | CLEAN (used in fascicle 26 person-type descriptions) |
| samprajanya / 正知 | alertness | CLEAN |
| priti / 喜 | joy (not rapture — body text uses "joy" per glossary note) | CLEAN |
| pramodya / 歡悅 | gladness | CLEAN — correctly distinguished from priti |
| vedana / 受 | feeling (NOT sensation in body text) | CLEAN — "sensation" only in footnotes and in specific non-vedana contexts |
| brahmacarya / 梵行 | pure conduct | CLEAN |
| smrityupasthana / 念住 | foundation of mindfulness | CLEAN |
| ayatana / 處 | sense base | CLEAN |
| arya-ashtangika-marga | noble eightfold path | CLEAN |
| adhimana / 增上慢 | overestimation | CLEAN |
| samvara-pradhana / 律儀斷 | discipline-abandonment | CLEAN |
| adhyashaya / 增上意樂 | superior aspiration | CLEAN |
| samyak-pradhana / 四正斷 | four right efforts | CLEAN |
| adhimoksha-manaskara / 勝解作意 | "imaginative attention" in fascicle 32 context; "attention of conviction" in fascicle 33 seven-attentions context | CLEAN — dual-context rendering correctly applied |
| samahita / 等引 | meditative equipoise | CLEAN |
| brahmavihara / 梵住 | brahmaviharas (preferred in text per glossary) | CLEAN — footnotes use "brahmavihara"; body text uses individual names or "brahmaviharas" |
| asravakshaya-jnana (as concept) | knowledge of exhaustion of outflows | CLEAN — appears only in footnote, glossed correctly |
| shushka-vipashyanaka / dry-insight | rendered as "dry-insight practitioner" | CLEAN — footnote use only |

---

### ISSUES FOUND — Direction 1

**D1-1. [MINOR] riddhipada / 神足 — Inconsistent singular/plural rendering**
- Glossary entry: "basis of supernatural power" (singular)
- Translation uses: "four bases of supernatural power" (plural) — fascicles 28 and 29
- Assessment: The plural "bases" is more natural English when referring to all four collectively; the glossary singular is appropriate when the term designates the category (each individual basis). Both forms appear. This is functionally correct but the glossary should be updated to note "basis / bases" as acceptable variants.
- Files: fascicle_28_en.md lines 478, 486, 650; fascicle_29_en.md lines 161, 165

**D1-2. [MINOR] samadhana vs samapatti — Both use 等持 Chinese character in glossary**
- Glossary has duplicate 等持 entries: row 102 maps 等持 → samapatti (meditative attainment); row 533 maps 等持 → samadhana (equipoise, stage 9).
- The translation correctly handles the distinction contextually: the ninth stage is "equipoise," general meditative attainments are "meditative attainment."
- Assessment: Glossary has an ambiguous Chinese column — the Chinese 等持 is used for two distinct Sanskrit terms. This is a glossary internal inconsistency. The translation handles it correctly, but a reader using the glossary Chinese column as a lookup could be confused.
- File: glossary/MASTER_GLOSSARY.md rows 102 and 533

**D1-3. [MINOR] abhijna / 神通 — "Supernatural power" terminology persists in riddhipada context**
- Glossary prescribes: "superknowledge" NOT "supernatural power" for abhijna
- Translation: "superknowledge" is correctly used for abhijna (fascicle 33, section on five superknowledges)
- BUT: the riddhipada (神足) is rendered "basis of supernatural power" throughout — this is a separate term from abhijna (神通) and the rendering is defensible
- Assessment: No error. The confusion arises because both riddhipada (神足, supernatural power basis) and abhijna (神通, superknowledge) involve "supernatural" in English. The glossary correctly distinguishes them; the translation applies them correctly.
- Verdict: CLEAN once distinction is understood

**D1-4. [MINOR] sapta-parishat / 七眾 — rendered "seven communities" (not in glossary)**
- Glossary does not contain sapta-parishat or a prescribed English rendering for the "seven Buddhist communities."
- Translation uses "seven Buddhist communities (*sapta-parishat*)" in a footnote.
- Assessment: Term appears only in footnote context, which is appropriate for a sub-taxonomic grouping. Should be added to glossary for completeness.

**D1-5. [MINOR] shitavana-bhavana — rendered differently from glossary entry**
- Glossary entry: 憺怕路 / shitavana-marga = "charnel ground path"
- Translation italicizes *shitavana-bhavana* ("cemetery contemplations") separately in fascicle 26 footnote
- Assessment: These are related but distinct terms. *shitavana* alone (cold forest/charnel ground) appears correctly in footnote; *shitavana-bhavana* (cemetery-based meditation practice) is used in a different register. Neither is wrong but the distinction is not articulated in the glossary.

---

## DIRECTION 2: Translation → Glossary
*Checking italicized Sanskrit/Pali terms in body text and footnotes against glossary.*

### Pali Terms (HIGH PRIORITY — violate NTC Sanskrit convention)

**D2-1. [MAJOR] *sukkha-vipassaka* — Pali form used in footnote**
- Location: fascicle_28_en.md line 666, footnote [^dhyana_requirement]
- Issue: "sukkha-vipassaka" is Pali. The glossary prescribes Sanskrit forms per NTC convention. Should be *shushka-vipashyanaka* (Sanskrit).
- Note: The glossary DOES have an entry for *shushka-vipashyanaka* (dry-insight practitioner). The footnote author used the Pali instead.
- Fix: Replace "*sukkha-vipassaka*" with "*shushka-vipashyanaka*" in the footnote.

**D2-2. [MAJOR] *vitakka* — Pali form used in footnote**
- Location: fascicle_33_en.md line 200, footnote [^second_dhyana_coarse]
- Issue: "vitakka" is Pali. Sanskrit form is "vitarka." Glossary prescribes Sanskrit.
- Context: The footnote is citing the Visuddhimagga, so there is a scholarly rationale for using the Pali, but it should be noted as Pali with Sanskrit equivalent: "*vitakka* (Pali; Skt. *vitarka*)".

**D2-3. [MAJOR] *ajjhatta-sampasadana* — Pali form used in footnote**
- Location: fascicle_33_en.md line 260, footnote [^inner_clarity]
- Issue: "ajjhatta-sampasadana" is Pali. The Sanskrit form is "adhyatma-samprasada." The glossary has an entry for *adhyatma-samprasada* (inner clarity).
- Context: Citing the Visuddhimagga parallel — Pali term is used for scholarly cross-reference. Still, if cited this way it should be labeled: "*ajjhatta-sampasadana* (Pali; Skt. *adhyatma-samprasada*)".

### Terms in Translations NOT in Glossary (Potential Missing Entries)

**D2-4. [MODERATE] *alaya-vijnana* — not in glossary**
- Location: fascicle_31_en.md footnote [^no_agent]; also implied in other contexts
- Usage: "seed-consciousness (*alaya-vijnana*)" — appears in a footnote explicating Yogacara doctrine
- Assessment: This is a major Yogacara technical term that appears in the translation. It should have a glossary entry, especially since it's central to the Sravakabhumi's philosophical framework. Suggested rendering: "storehouse consciousness / seed-consciousness (*alaya-vijnana*, 阿賴耶識)"

**D2-5. [MODERATE] *anuttara-samyak-sambodhi* — not in glossary**
- Location: fascicle_30_en.md line 116
- Usage: "supreme perfect awakening (*anuttara-samyak-sambodhi*)" — appears in body text
- Assessment: Common and important term. Should be in glossary. Rendering used in translation ("supreme perfect awakening") is standard.

**D2-6. [MODERATE] *agotra* / *agotra-pudgala* — not in glossary**
- Location: fascicle_28_en.md lines 254, 632, 668
- Usage: "person without lineage (*agotra-pudgala*)" — appears multiple times in body text and footnotes
- Assessment: Doctrinally significant Yogacara term. Appears in both body text and extended footnote. Should be in glossary.

**D2-7. [MODERATE] *tathagatagarbha* — not in glossary**
- Location: fascicle_28_en.md footnotes [^agotra] and [^agotra_context]
- Usage: In contrast to Yogacara agotra doctrine. Appears in footnotes only.
- Assessment: Should be in glossary as a contrasting term, with note that it is not a Sravakabhumi term but is cited in footnotes.

**D2-8. [MODERATE] *ashrava* — variant or error for *asrava***
- Location: fascicle_27_en.md line 244
- Usage: "The outflows (*ashrava*) are forever exhausted."
- Issue: The glossary entry uses *asrava* (correct Sanskrit). The translation uses *ashrava* at this one location — this is an alternate romanization but inconsistent with the glossary standard. All other occurrences use *asrava*.
- Fix: Change *ashrava* → *asrava* at fascicle_27_en.md line 244.

**D2-9. [MINOR] *abhyasa-ganana* — not in glossary**
- Location: fascicle_27_en.md footnote [^advanced_counting]
- Usage: "advanced counting (*abhyasa-ganana*)"
- Note: The glossary has *ganana-bhavana* (counting cultivation). *abhyasa-ganana* is a sub-component. Should be added as a sub-entry under the anapanasati section.

**D2-10. [MINOR] *satkrtya-prayoga* — not in glossary**
- Location: fascicle_26_en.md footnote [^two_applications]
- Usage: "earnest application (*satkrtya-prayoga*)"
- Note: Paired with *anantarya-prayoga* (which IS in the glossary). The paired term is missing.

**D2-11. [MINOR] *jnapti* / *jnapti-caturthi-karma* — not in glossary**
- Location: fascicle_29_en.md footnote [^formal_ordination]
- Usage: "formal monastic procedure (*jnapti-caturthi-karma*, 白四羯磨)"
- Assessment: Vinaya technical term appearing in footnote. Should be added to glossary.

**D2-12. [MINOR] *vyapada* — not in glossary**
- Location: fascicle_29_en.md footnote [^five_lower_fetters]
- Usage: "ill-will (*vyapada*)"
- Note: The term appears in the glossary's note on pancha-avarabhagiya-samyojana (in the Notes column) but has no standalone entry. As the fifth lower fetter, it should have its own entry.

**D2-13. [MINOR] Embryonic stage terms (*kalala*, *arbuda*, *peshi*) — not in glossary**
- Location: fascicle_27_en.md line 100, footnote [^embryonic_stages]
- Usage: Three embryonic stages cited in body text and footnote
- Assessment: These appear in a doctrinal context (breath ceasing at early embryonic stages). Footnote explains them well. Should be added to glossary as a set.

**D2-14. [MINOR] *ushmanas* — inconsistently in glossary**
- Location: fascicle_28_en.md line 440, footnote [^nirvedha_bhagiya]
- Glossary status: The glossary has "煗/煖 | usmagata | warmth" (using usmagata not ushmanas). The translation uses *ushmanas* in body text and footnote.
- Assessment: *ushmanas* and *usmagata* are different transliterations of the same concept. The glossary uses *usmagata* but the translation uses *ushmanas* throughout. This is an inconsistency — the glossary should either update to *ushmanas* or note the variant.
- Fix: Standardize. The *ushmanas* form (cf. Tibetan tradition: drod = warmth) is perhaps more common in this context. Update glossary to prefer *ushmanas* or add as variant.

**D2-15. [MINOR] *svakhyata* / *durakhyata* — not in glossary**
- Location: fascicle_30_en.md footnote [^exclusive_refuge]
- Usage: "the well-taught (*svakhyata*) from the wrongly-taught (*durakhyata*) dharma-vinaya"
- Assessment: Both terms appear as a pair in footnotes. Neither is in the glossary. Should be added.

**D2-16. [MINOR] *triyana* — not in glossary**
- Location: fascicle_30_en.md footnote [^three_vehicles]
- Usage: "three-vehicle (*triyana*) framework"
- Assessment: Appears only in a footnote. Standard term but not in glossary.

**D2-17. [MINOR] *sapta-manaskara* — not in glossary**
- Location: Appears in italics in translation files (seven attentions)
- Assessment: The individual seven attentions have glossary entries, but the collective term "seven attentions (*sapta-manaskara*)" does not.

**D2-18. [MINOR] *pancha-anagamin* / *panca-anagamin* — not in glossary**
- Location: fascicle_26_en.md footnote [^birth_types]
- Usage: "five subtypes of non-returners (*panca-anagamin*)"
- Assessment: Collective term for the five non-returner subtypes. Individual entries exist in glossary but collective Sanskrit term is missing.

**D2-19. [MINOR] *upanishad* — used in non-standard sense**
- Location: fascicle_32_en.md line 309
- Usage: "any *upanishad* fraction" — used in the sense of a mathematical fraction (upanishad as "one-sixteenth" or similar fraction idiom from Sanskrit)
- Assessment: This is an unusual use of "upanishad" as a numerical term (not the philosophical texts). No glossary entry. The footnote should clarify this is a Sanskrit idiomatic expression for an infinitesimally small fraction.

**D2-20. [MINOR] *anasrava* / *sasrava* — not in glossary as standalone entries**
- Location: fascicle_28_en.md footnote [^three_wisdoms]
- Usage: "necessarily mundane (*sasrava*); the third can be either mundane or supramundane (*anasrava*)"
- Assessment: These antonyms appear in footnotes. Related to asrava (漏) which is in the glossary, but the prefixed forms are not listed as entries.

**D2-21. [MINOR] *anitya-samjna*, *ashubha-samjna* — not in glossary**
- Location: Various fascicles
- Usage: Perception of impermanence, perception of impurity — appear as technical compound terms
- Assessment: The glossary has ashubha and samjna separately. The compound perception terms appear in the "twelve perceptions" context (fascicle 33) but lack glossary entries.

**D2-22. [MINOR] *shitavana-bhavana* — glossary has shitavana-marga only**
- Location: fascicle_26_en.md footnote [^corpse_stages]
- Usage: "cemetery contemplations (*shitavana-bhavana*)"
- Assessment: The glossary entry is for *shitavana-marga* (charnel ground path). *shitavana-bhavana* is the practice itself. Both forms appear in the translation but only the path form is in the glossary.

---

## DIRECTION 2: Chinese Character Consistency in Footnotes

### CLEAN Footnotes (verified against glossary)
- paryavasthana = 纏 ✓ (fascicle_26_en.md footnote [^five_affliction_types])
- anushaya = 隨眠 ✓ (same footnote)
- samyojana = 結 ✓ (same footnote)
- bandhana = 縛 ✓ (same footnote)
- upaklesha = 隨煩惱 ✓ (same footnote)
- klesha-avarana = 煩惱障 ✓ (fascicle_26_en.md footnote [^ubhaya])
- samadhi-avarana = 定障 ✓ (same footnote)
- saptatrimshad-bodhipakshya-dharma = 三十七菩提分法 ✓ (fascicle_28_en.md)
- nirvedha-bhagiya-kushala-mula = 順決擇分善根 ✓ (fascicle_28_en.md)
- jnapti-caturthi-karma = 白四羯磨 ✓ (fascicle_29_en.md)
- priti = 喜 / pramodya = 歡悅 ✓ (fascicle_32_en.md footnote [^non_regret_sequence])
- pancha-avarabhagiya-samyojana = 五下分結 ✓ (fascicle_29_en.md)

### ISSUE — Chinese Consistency

**CCC-1. [MINOR] *vimukti-avarana* appears with two Chinese glosses**
- fascicle_26_en.md footnote [^ubhaya]: glossed as 解脫障分 ("liberation-obstruction portion")
- This is the obstruction against the eight liberations. The glossary has *samadhi-avarana* = 定障 and notes "also 解脫障 (liberation obstruction)." The footnote uses 解脫障分 (with 分 = "portion/category"). This is consistent with the Chinese source. No error.

---

## SUMMARY TABLE

| # | Direction | Term | Severity | Issue |
|---|---|---|---|---|
| D1-1 | D1 | riddhipada | Minor | Glossary says singular "basis"; translation uses plural "bases" contextually — correct but glossary needs note |
| D1-2 | D1 | 等持 | Minor | Glossary maps same Chinese to both samapatti and samadhana — ambiguous Chinese column |
| D1-4 | D1 | sapta-parishat | Minor | Used in footnote; no glossary entry |
| D2-1 | D2 | sukkha-vipassaka | **Major** | Pali form in footnote; should be shushka-vipashyanaka (Sanskrit) |
| D2-2 | D2 | vitakka | **Major** | Pali form in Visuddhimagga citation footnote; should label as Pali with Sanskrit equivalent |
| D2-3 | D2 | ajjhatta-sampasadana | **Major** | Pali form in Visuddhimagga citation footnote; should label as Pali with Sanskrit equivalent |
| D2-4 | D2 | alaya-vijnana | Moderate | Important Yogacara term in footnote; no glossary entry |
| D2-5 | D2 | anuttara-samyak-sambodhi | Moderate | Major term in body text; no glossary entry |
| D2-6 | D2 | agotra / agotra-pudgala | Moderate | Doctrinally significant; in body text and footnotes; no glossary entry |
| D2-7 | D2 | tathagatagarbha | Moderate | In footnotes as contrasting doctrine; no glossary entry |
| D2-8 | D2 | ashrava | Moderate | Single-occurrence spelling variant of asrava (glossary uses asrava); inconsistency at fascicle_27_en.md line 244 |
| D2-9 | D2 | abhyasa-ganana | Minor | Anapanasati sub-term; no glossary entry |
| D2-10 | D2 | satkrtya-prayoga | Minor | Paired with glossary term anantarya-prayoga; missing from glossary |
| D2-11 | D2 | jnapti-caturthi-karma | Minor | Vinaya ordination term in footnote; no glossary entry |
| D2-12 | D2 | vyapada | Minor | Fifth lower fetter; no standalone glossary entry |
| D2-13 | D2 | kalala/arbuda/peshi | Minor | Embryonic stage terms in body text; no glossary entries |
| D2-14 | D2 | ushmanas vs usmagata | Minor | Translation uses ushmanas; glossary entry uses usmagata — inconsistency |
| D2-15 | D2 | svakhyata/durakhyata | Minor | Paired terms in footnotes; neither in glossary |
| D2-16 | D2 | triyana | Minor | In footnote; no glossary entry |
| D2-17 | D2 | sapta-manaskara | Minor | Collective term for seven attentions; no glossary entry |
| D2-18 | D2 | panca-anagamin | Minor | Collective term for five non-returner subtypes; no glossary entry |
| D2-19 | D2 | upanishad (numerical sense) | Minor | Used as "fraction" idiom; no glossary entry; needs footnote clarification |
| D2-20 | D2 | anasrava / sasrava | Minor | Antonyms of asrava; used in footnotes; no standalone glossary entries |
| D2-21 | D2 | anitya-samjna / ashubha-samjna | Minor | Compound perception terms; no glossary entries |
| D2-22 | D2 | shitavana-bhavana | Minor | Practice term; glossary has only path term shitavana-marga |

---

## ACTION PRIORITY

### Fix immediately (Pali form violations — NTC convention):
1. fascicle_28_en.md line 666: Replace `*sukkha-vipassaka*` with `*shushka-vipashyanaka*`
2. fascicle_33_en.md line 200: Add Pali label to `*vitakka*`: `*vitakka* (Pali; Skt. *vitarka*)`
3. fascicle_33_en.md line 260: Add Pali label to `*ajjhatta-sampasadana*`: `*ajjhatta-sampasadana* (Pali; Skt. *adhyatma-samprasada*)`
4. fascicle_27_en.md line 244: Change `*ashrava*` to `*asrava*`

### Fix in glossary (missing entries for body-text terms):
5. Add *anuttara-samyak-sambodhi* entry (appears in body text)
6. Add *agotra* / *agotra-pudgala* entry (appears in body text)
7. Add *alaya-vijnana* entry (major Yogacara term in footnotes)
8. Resolve *ushmanas* vs *usmagata* inconsistency in glossary

### Low priority (footnote-only terms, could add as reference):
- tathagatagarbha, triyana, sapta-manaskara, panca-anagamin, svakhyata/durakhyata, satkrtya-prayoga, vyapada, shitavana-bhavana, kalala/arbuda/peshi, abhyasa-ganana, jnapti-caturthi-karma, anasrava/sasrava, anitya-samjna/ashubha-samjna, upanishad (numerical), sapta-parishat

### Fix in glossary (structural):
- Note plural "bases" as acceptable variant for riddhipada
- Disambiguate 等持 Chinese column (add note that it serves both samapatti and samadhana in different contexts)
