# Word lists: AI vocabulary, German and English

Three tiers, ordered by how reliable the signal is:

- **Tier 1 – inspect every hit; replace stock uses.** These show up at a far higher rate in machine-generated text than in human prose.
- **Tier 2 – flag when two or more cluster.** Fine on their own; a paragraph containing at least two of them is a strong signal.
- **Tier 3 – flag only when they pile up.** Normal words that AI stacks as filler.

Inflected forms count (nahtlos → nahtlose, delve → delving). Don't flag words used with real technical meaning in context (robust in structural engineering, ecosystem around platform APIs, „Testament“ as a legal term). Apply the modes and guardrails in `../SKILL.md`: check mode flags without editing; literal, quoted, attributed, domain-correct, and required brand uses stay. Never replace inside quotations, code, tables, or attributed third-party text. A listed phrase is not a finding when it carries real content (for example, an ordinary email sign-off or a real question to its recipient). These lists age; when new stock phrases keep turning up, extend the list.

## German

### Tier 1 – replace stock uses

| Instead of | Use |
|---|---|
| eintauchen in / tauchen wir ein | ansehen, durchgehen, direkt zum Punkt |
| beleuchten (Thema) | erklären, zeigen, untersuchen |
| entfesseln / freisetzen (Potenzial) | konkret sagen, was möglich wird |
| das volle Potenzial ausschöpfen | (konkreten Nutzen benennen) |
| auf ein neues Level heben | verbessern (und sagen, was sich misst) |
| Gamechanger / bahnbrechend / revolutionär | beschreiben, was sich konkret ändert |
| nahtlos | reibungslos, ohne Zwischenschritt (oder Ablauf benennen) |
| ganzheitlich | vollständig (oder aufzählen, was enthalten ist) |
| maßgeschneidert | passend für X (X benennen) |
| zukunftsweisend / wegweisend / richtungsweisend | (streichen oder konkrete Neuerung nennen) |
| dynamisch (Umfeld, Welt) | (streichen oder Veränderung benennen) |
| spannend (als Universal-Lob) | sagen, was genau interessant ist |
| Meilenstein (für Routine-Ereignisse) | (Ereignis nüchtern benennen) |
| eine neue Ära einläuten | (was ändert sich ab wann?) |
| die Weichen stellen / den Grundstein legen | entscheiden, starten, vorbereiten |
| Brücken schlagen / Brückenschlag | verbinden (was mit was, wozu?) |
| Synergien heben/nutzen | (den konkreten kombinierten Effekt beschreiben) |
| Potenziale entfalten | (was wird konkret möglich?) |
| zeugt von / unterstreicht / spiegelt wider | zeigt, belegt (oder Satz direkt formulieren) |
| steht sinnbildlich für | (weglassen, Fakt nennen) |
| vielfältig / facettenreich (als Füller) | (Facetten aufzählen oder streichen) |
| unverzichtbar / essenziell (inflationär) | wichtig für X, nötig weil Y |
| im Herzen von / eingebettet in (Orte) | liegt in, ist in |
| pulsierend / lebendig (Stadt, Szene) | (belegen: was ist dort los?) |
| Mehrwert bieten/schaffen | (den konkreten Nutzen nennen) |
| Herausforderungen meistern | (welche? wie?) |

### Tier 2 – flag when two or more cluster

optimieren, effizient (ohne Messgröße), innovativ, nachhaltig (als Universaladjektiv), zentral, entscheidend, maßgeblich, umfassend, fundiert, gezielt, individuell, flexibel, transparent (als Buzzword), agil, smart, digital (als Weihwasser: „digitale Lösungen“), zeitnah, proaktiv, niederschwellig, praxisnah, passgenau, zielführend, ergebnisoffen, wertschätzend, auf Augenhöhe, End-to-End, 360-Grad, Rundum-sorglos

### Tier 3 – flag only when they pile up

wichtig, relevant, modern, professionell, hochwertig, erfolgreich, einzigartig, beeindruckend, deutlich, erheblich, signifikant, optimal, ideal, perfekt

### German stock phrases: cut or replace

Apply the matching rule's severity in `../SKILL.md`; stock-phrase headings do not promote a P2 generic closer to P1.

**Openers:** „In der heutigen digitalen Welt / schnelllebigen Zeit…“, „Im Zeitalter von…“, „Ob Startup oder Konzern –…“, „Ganz gleich, ob…“, „Kennen Sie das?“, „Stellen Sie sich vor,…“ (als Ersatz fürs Argument), „Immer mehr Unternehmen…“, „Wir alle wissen:…“

**Transitions:** „Es ist wichtig zu beachten, dass“, „Dabei gilt es zu berücksichtigen“, „Hierbei spielt … eine entscheidende Rolle“, „Doch was bedeutet das konkret?“, „Werfen wir einen Blick auf“, „Die Antwort lautet:“, „Kurz gesagt:“ (als Ritual), „Nicht nur X, sondern auch Y“ (inflationär), „Von X bis Y“ (Schein-Spannweite, allein schwach)

**Closers:** „Fazit:“ als Standard-Überschrift, „Zusammenfassend lässt sich sagen“, „Unterm Strich“, „Am Ende des Tages“, „Es bleibt abzuwarten“, „Die Zukunft bleibt spannend“, „Eines steht fest:“, „Denn eines ist klar:“, „Sind Sie bereit für…?“, „Lust auf mehr?“

**Chat artifacts (P0):** „Gerne erstelle ich Ihnen…“, „Ich hoffe, das hilft!“, „Lassen Sie es mich wissen, falls…“, „Selbstverständlich!“, „Das ist eine gute Frage“, „Ich hoffe, diese E-Mail erreicht Sie wohlbehalten“ (Anglizismus-Kalk), „Soll ich weitermachen?“, „Möchtest du, dass ich …?“ (am Ende eines eigenständigen Textes), Denk- und Prompt-Echos: „Gehen wir das Schritt für Schritt durch“, „Gehen wir das systematisch an“, „Du fragst also, ob …“, „Um deine Frage zu beantworten“

**Faux-Insight-Aufhänger:** „Was die meisten übersehen“, „Was dir niemand sagt“, „Der Teil, den alle überspringen“, „Was kaum jemand ausspricht“, „Die unbequeme Wahrheit ist“, „Hand aufs Herz:“ (als Auftakt statt als Haltung)

**Leser-Steuerung (Metadiskurs):** „Das ist wichtiger, als es klingt“, „Entscheidend dabei:“, „Wichtig zu verstehen:“, „Wie man sieht“, „Anders gesagt“ (wenn der Satz davor schon klar war), „Merke:“, „Und genau das ist der Punkt“

**Phantom-Einwände:** „Damit will ich nicht sagen, dass…“, „Versteh mich nicht falsch“, „Um es klar zu sagen“, „Naheliegend wäre, …, doch…“, „Man könnte meinen, …“, „Das heißt nicht, dass…“ (wenn niemand das behauptet hat)

**Inszenierte Betonung:** „Lies das nochmal.“, „Lass das mal sacken.“, „JEDEN. EINZELNEN. TAG.“, ein einzelnes Wort in Versalien als Gewicht

**Ritual-Gliederung und Füller:** „Erstens … Zweitens … Drittens“ in kurzen Texten, „Hier kommt X ins Spiel“, „Last but not least“, „Nicht zuletzt“, „Interessanterweise“, „Kurz und knapp:“

**Schein-Autorität und vage Bezüge:** „Bekannt aus: …“ als Medienleiste, Follower-Zahlen als Beleg, „im Zusammenhang mit“ / „in Verbindung mit“, wenn offen bleibt, welche Rolle jemand hatte

**Schein-Agenten:** „Die Zahlen sprechen für sich“, „Die Daten erzählen eine Geschichte“, „zeichnet ein klares Bild“, „Das Tool entscheidet selbst“, „Die KI weiß, was du brauchst“

**Slogan- und Bilanzschablonen:** „Weniger X. Mehr Y.“, „Ein Tool, drei Abteilungen.“, „Obwohl X vielversprechend ist, bleibt Y eine Herausforderung“, „Einerseits … andererseits …“ ohne Fazit, „Der Druck ist real.“, „Drei zentrale Erkenntnisse“, „5 Dinge, die du wissen musst“, „In diesem Beitrag schauen wir uns … an“

**Engagement bait (social):** „Und das Beste daran?“, „Der Clou:“, „Spoiler:“, „Plot Twist:“, „Aber der Reihe nach.“, „Doch dann kam alles anders.“, 🧵, Emoji-Bullets (🚀✅💡) vor jeder Zeile, Hashtag-Blöcke ab 3 Tags

## English

### Tier 1 – replace stock uses

| Instead of | Use |
|---|---|
| delve (into) | examine, get into, take a close look at |
| landscape / realm / tapestry (metaphorisch) | field, space, area (oder konkret) |
| leverage (Verb) | use |
| robust / seamless / comprehensive | strong, smooth, complete (oder konkret) |
| pivotal / crucial (inflationär) | important, key (oder Grund nennen) |
| testament to | shows, proves |
| underscore / highlight (Verb, inflationär) | show |
| game-changer / cutting-edge / groundbreaking | (konkret sagen, was neu ist) |
| embark / journey (metaphorisch) | start, begin |
| unlock / unleash / harness / empower | enable, let (oder konkret) |
| elevate / supercharge / streamline your X | (sagen, was messbar besser wird) |
| meticulous / intricate / nuanced (als Füller) | careful, complex, specific |
| foster / cultivate / facilitate | build, support, help, run |
| due to the fact that / in order to (Füll-Formalismus) | because / to |
| utilize | use |
| vibrant / thriving / bustling / nestled | (belegen oder streichen) |
| holistic / multifaceted / myriad / plethora | complete, varied, many |
| actionable / impactful / learnings | practical, effective, lessons |
| best practices / thought leader / synergy | what works, expert, (konkreter Effekt) |
| deep dive / unpack | look at, explain |
| ever-evolving / rapidly changing | changing (oder wie genau?) |
| serves as / boasts / features (Kopula-Ersatz) | is, has |

### Tier 2 – flag when two or more cluster

navigate (figurativ), bolster, spearhead, resonate, revolutionize, catalyze, augment, illuminate, elucidate, cornerstone, paramount, poised to, burgeoning, nascent, quintessential, overarching, transformative, ecosystem (metaphorisch), interplay, encompass, notably, moreover, furthermore, additionally

### Tier 3 – flag only when they pile up

significant(ly), innovative, effective(ly), dynamic, scalable, compelling, unprecedented, remarkable, sophisticated, world-class, state-of-the-art

### English stock phrases: cut or replace

**Openers:** "Imagine a world where", "In an era of", "In today's fast-paced world", "In the ever-evolving landscape of", "Whether you're a [Gründer:in] or a [CFO]", "Let's dive in"

**Transitions:** "It's worth noting that", "At its core", "It's important to note that", "When it comes to", "That being said", "Here's the thing", "This begs the question", "Not just X, but Y"

**Closers:** "In conclusion", "The future looks bright", "To sum up", "The bottom line is", "At the end of the day", "Only time will tell"

**Chat artifacts (P0):** "Certainly!", "I hope this helps!", "Feel free to reach out", "You're absolutely right", "Great question!", "Please don't hesitate to…", "I hope this email finds you well", "Absolutely!", "Sure!", "I'd be happy to…", "That's a great point!", "As an AI…", "Would you like me to…?", "Should I continue?", reasoning and prompt echoes: "Let me think step by step", "Here's my thought process", "Breaking this down", "You're asking about", "To answer your question"

**Faux-insight setups:** "the part everyone misses", "what nobody tells you", "here's what they don't say", "what most people get wrong", "let me be clear", "the uncomfortable truth is"

**Reader steering (metadiscourse):** "that matters more than it sounds", "this distinction matters", "the key point is", "as you can see", "in other words" (when the previous sentence was already clear), "make no mistake"

**Rhetorical setups:** "What if I told you", "Think about it:", "Plot twist:", "Here's the thing:", a question answered by the next sentence as a device

**Phantom objections:** "To be clear", "I'm not saying", "Don't get me wrong", "This isn't to say", "A tempting approach would be", "You might think… but"

**Staged emphasis:** "Read that again.", "Let that sink in.", "every. single. day.", one word in capitals for weight

**Stock phrases:** "bridge the gap", "move the needle", "take it to the next level", "buckle up", "in a nutshell", "this is where X comes in", "without further ado", "as per my last email", "firstly… secondly… thirdly…" in short pieces; sentence-opening "Interestingly,", "Importantly,", "Indeed,", "Overall,", "Additionally,"

**Words:** "quietly" (as drama), "garner", "enduring", "align with", "key" as filler adjective, "gate/gated/gating" used figuratively (technical uses stay)

**Vague association:** "associated with", "in connection with", "linked to", "tied to", when the relationship stays unnamed

**False agency and template balance:** "paints a clear picture", "the data tells a story", "the numbers speak for themselves", "While X shows promise, Y remains a challenge", "on one hand … on the other hand" without a verdict, "The struggle is real.", "three key takeaways", "In this article, we will explore"

**Business collocations:** "circle back", "low-hanging fruit", "navigate challenges", "leverage synergies"

**Academic excess:** "delineate", "unveil", "invaluable", "noteworthy", "shed new light on", "holds great promise", "opens new avenues"

**Inflation phrases (corpus-measured, at up to 468× the human base rate):** "provide a valuable insight", "left an indelible mark", "play a significant role in shaping", "an unwavering commitment", "open a new avenue", "a stark reminder", "serves as a testament", "deeply rooted", "watershed moment", "marking a pivotal moment"

## Leak artifacts (P0, both languages)

Flag on sight; in rewrite/edit mode remove leaked artifacts and use a reference only when the source supplies it. Preserve unresolved gaps in the audit. Deliberate examples in audit material, code, or quotations are protected; never infer authorship from a token alone:

`oaicite`, `contentReference`, `turn0search0`, `citeturn`, `grok_card`, `attributableIndex`, `[attached_file:1]`, URL parameters `utm_source=chatgpt.com|openai|claude.ai|perplexity.ai`, unfilled placeholders (`[Name]`, `[INSERT X]`, `2025-XX-XX`, `<!-- TODO -->`), Markdown asterisks in plain-text contexts (email, DM, LinkedIn raw text)

## Microformats (weak but cheap tells)

Wrong locale conventions warrant P2 where they qualify as defects; mixed conventions inside one document are P1. Apply the weak-alone calibration in `../SKILL.md`: a single straight quote or compound hyphen is corroborating evidence only, not an automatic finding. Deliberate typography and existing human quirks stay.

**German documents:**

- Percent with a space: „50 %“, not „50%“
- Decimal comma and dot as thousands separator: „3,2 Sekunden“, „10.000 Nutzer“ – never „3.2“ or „10,000“
- Currency after the amount: „40 €“, „1,2 Mio. €“
- Dates: „24.08.2026“ or „24. August 2026“ – never „08/24/2026“ or „2026-08-24“ in running prose (ISO stays fine in tables and file names)
- Quotation marks: „deutsche“ – straight "US quotes" in an otherwise typeset German text are a paste signal (see `pattern-catalog.md`, section 16)

**English documents:** the inverse conventions apply (50%, 3.2, 10,000, $40 / €40 before or after per style, Aug 24, 2026). The flag in both languages is the same: two conventions mixed in one document. Compound modifiers keep the hyphen before the noun and drop it after it ("a high-quality report", "the report is high quality"); dictionary compounds such as "third-party" keep it everywhere. Weak alone.
