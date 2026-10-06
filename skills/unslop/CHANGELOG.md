# Changelog

## v1.8.2 – 2026-10-06

- Reviewed English coverage, stock phrases, and word list hygiene
- Removed duplicate 'additionally' from English Tier 2 word list
- Calibrated wordy formalisms ('due to the fact that / in order to') in Tier 1 word list
- Audited all 30 pattern families in `pattern-catalog.md` for fact fidelity; confirmed every AFTER line preserves facts of its BEFORE line without additions
- Added regression cases 19 and 20 to `evals/cases.md` for English load-bearing metaphors and clean technical announcements (marked MUST STAY CLEAN)
- Verified `README.md` accuracy against `SKILL.md`
- Bumped version to 1.8.2 in `plugin.json` and `marketplace.json`

## v1.8.1 – 2026-10-05

- Aligned the short version, severity list, and self-check with register profiles, vocabulary tiers, permitted triads and contrasts, meaningful participle tails, action titles, and required summaries; stock phrases use their rule's severity; check mode continues to flag without editing
- Clarified weak-alone calibration: co-occurring legitimate choices do not automatically form a defect; sentence length needs repetitive construction, and a single passive with a known or irrelevant actor stays
- Removed the self-check's hypothetical-detail loophole; factual gaps stay separate from the deliverable, including embedded quality passes, and relative measurements such as „halbiert“ retain their strength
- Removed authorship verdicts from check/workflow wording and leak guidance; ordinary salutations, sign-offs, recipient questions, and numbered instructions stay protected
- Merged template-scaffolding guidance into the heading rule; removed the duplicate English „crucial“ tier entry while keeping its inflated Tier-1 use
- Repaired the dangling bold-formatting reference (catalog section 11) and quotation-mark reference (section 16); aligned the catalog's dash budget with SKILL.md and limited the slide prohibition to em dashes
- Repaired source-unsupported facts, figures, names, dates, mechanisms, and feelings in catalog sections 1–13 and 17–24; removed the stand-in-fact exception and used explicit audit gaps where no faithful rewrite is possible
- Corrected additional content loss or invented specificity in sections 25–29: backup consequences, provider sources and price sorting, endpoint load, release-test attribution, parser failure, slogan comparisons and counts, migration assessment, and preview–recap headings
- Kept slide warnings at their original strength, preserved „immer“ as „vor jedem Versand“, and required source support for academic claim-strength changes and named actors
- Corrected German quotation marks and nested quotes in rules and examples; kept deliberately defective typography and clean human input unchanged, and clarified that colon capitalization alone is not a tell
- Updated eval severities and expectations for closers, copulas, valid en dashes, vocabulary clusters, missing title roles, narrative gaps, false agency, relative measurements, and reply reasoning
- Added cases 15–18 for protected technical vocabulary and participle conditions, meaningful three-part lists, unsupported evidence gaps, and slide-face versus speaker-note punctuation
- Rebuilt the two README rewrite examples so every fact in the After line comes from the Before line; retained the 30-family count, corrected the claim that each family has both language pairs, and removed the unsupported total-rule count
- Catalog follow-ups: the template-balance AFTER no longer repeats the concession it is meant to remove, the tidy-ending example now shows an open thread kept from the source, and the endpoint example states the replacement as a fact again
- Cases 15 and 16 join 6, 12 and 14 as mandatory clean cases; reordered a few stock-phrase lists and reworded two eval inputs and two explanatory sentences
- Bumped the plugin version and both marketplace versions to 1.8.1; retained the frontmatter name, description triggers, file layout, and Markdown-only skill

## v1.8 – 2026-10-05

- Meaning at the same strength: the no-silent-loss guardrail now covers causes, comparisons, conditions, negations, scope, approximations, ranges, list items, and attributed quotes
- New guardrail: load-bearing hedges, negations, and absolutes in legal, medical, scientific, safety, and security text are never removed, softened, or strengthened; unsupported absolutes in persuasive prose are flagged
- Rewrite decision rule: change a sentence only when the defect is plainer than the risk of changing it; a word-list hit is a reason to look, not a licence to edit
- New patterns: contrastive definitions with three protected look-alikes, slogan cadence (threshold three per document), false agency and tool anthropomorphism, parenthetical hedging, the „ist real" calque, counted lists for their own sake, template balance, preview and recap symmetry
- Measurable structure signals for check mode (connective paragraph openers, repeated openers, one-line staccato, commenting tails, sentence-length extremes)
- Heading rule: no agency for tools or calendar slots, no uplift transformations; renaming the abstraction is not a repair
- Maintenance rule: every pattern enters with one example to catch and one look-alike to leave alone
- Word lists (DE + EN), catalog sections 28–30, regression cases 13 and 14, self-check items 19–20

## v1.7 – 2026-10-02

- Weak-alone calibration: single dashes, one hedge, one passive, one synonym change, "von X bis Y" spans and similar signals count only when they cluster; synonym variation downgraded accordingly
- New guardrail "No silent loss": a rewrite that drops a supported fact, ranking, or simultaneity has failed
- New level-3 patterns: phantom objections, text about itself (method and layout narration, heading echo), replies that rebuild context the reader already has
- New level-2 patterns: repeated sentence openings, staged emphasis (capitals, dotted words, "Read that again")
- Extended: negative parallelism (reversed form, clipped negative tail), paragraph-scale triads, prestige lists and vague association, stock "challenges and outlook" sections, mid-text aphorisms, speculation dressed as background (P0)
- Embedded use: when another skill calls unslop as its quality pass, return only the corrected text; a user's own writing sample overrides the generic budgets
- Check mode judges patterns, never authorship
- Word lists extended (DE + EN), English hyphenation microformat, catalog sections 25–27, regression cases 11 and 12, self-check items 17–18

## v1.6 – 2026-10-01

- Colon reveals as a level-2 pattern: the staged noun phrase + colon + payoff, with the distinction from the colon that carries a list, a label, or a plain consequence
- Interpretive metadiscourse and faux-insight setups as a level-3 pattern: asides that tell the reader how to read the text, or cast the writer as the only one who noticed
- Aphoristic kickers: the closing maxim gets deleted, not improved; the text ends on its most concrete sentence
- The portability test named and made operational, replacing the old self-check wording
- Formatting follows content: headings over two-sentence sections, bullets where prose reads better
- Rewrite mode: the size of the edit matches the amount of slop; one question about register when it would change the verdict
- Word lists extended (faux-insight setups, reader steering, rhetorical setups, DE + EN), catalog sections 22–24, regression case 10, self-check items 15–16

## v1.5 – 2026-09-03

- Narrative-content rules derived from StoryScope v6 (arXiv:2604.03136): realization codas and epilogues, ambivalence allowed to stand, one temporal move instead of front-loaded backstory, people introduced through action or speech, real quotes over narration, one untied tangent, varied intensity, sparse direct address
- Anti-convergence rule made explicit: one or two structural moves per piece, rotated – never the whole menu
- Severity wiring (codas/backstory P1; escalation, atmosphere filler, description-block intros P2), self-check item 14, catalog section 21, regression case 9

## v1.4 – 2026-09-03

- Load-bearing metaphors as a level-2 pattern („das trägt", „tragfähig", „zahlt sich aus", „Rückgrat", "backbone", "pays off"): sound decisive, assert nothing checkable; replace with the plain verb plus the criterion, literal uses stay
- Constructive half: the verb has to name the real operation once the actor is named
- Repeating item lists (catalogues, card decks): entry-length uniformity flagged, with a target mix
- Slide register: no load-bearing metaphors as verdicts; profile-table row and P1 wiring added

## v1.3 – 2026-08-24

- "The short version": ten-rule core checklist plus an order of precedence
- Write mode now runs the self-check against its own draft before returning anything
- New section on working with other content skills (brand vocabulary beats word lists; structure rules and guardrails always apply)
- Severity mapping extended to the newer rules (slide titles, slide register, stamps, storyline, microformats)
- German trigger terms (Präsentationen, Folien, Folientitel) added to the description
- Mixed-document rule: slide face vs. speaker notes
- Deck storyline rule: the title sequence has to carry the summary on its own
- Microformats section in the word lists (percent spacing, decimal comma, dates, currency; mixed conventions flagged)
- `evals/cases.md` added for regression checks; maintenance section in SKILL.md

## v1.2.1 – 2026-08-24

- All worked examples rebuilt as invented equivalents; no verbatim source material remains

## v1.2 – 2026-08-24

- The slide register: nominal style, no sensational one-liners, recommendation tone, positive framing, zero em dashes, notes and stamps rules
- Catalog sections 18–20 (headings and slide titles, sentence construction, slide register)
- Compound-noun title rule sharpened

## v1.1 – 2026-08-24

- Constructive half of level 2: actor and verb early, verbs over nominalizations, concrete subjects, the everyday word
- Noun-label rule for headings and slide titles
- Slides/deck column in the context-profile table

## v1.0 – 2026-08-10

- Initial release: three levels, four modes, DE+EN word lists, pattern catalog, context profiles, severity tiers, guardrails
