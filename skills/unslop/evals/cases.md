# Regression cases

How to run: for each case, run the skill in **check mode** with the stated profile on the INPUT block, then compare the findings to EXPECTED. A case passes when every expected finding category appears with roughly the stated severity and at most one unlisted extra is flagged. Cases 6, 12, 14, 15, 16, 20 and 21 must come back clean; flagging any of them is a regression (overflagging counts as failure). All content is invented.

German-only rules still not exercised as standalone German cases after 21–22:
- over-polite mail formulas under salutation calques („Selbstverständlich unterstütze ich Sie gerne bei …“)
- double hyphen (`--`) as German dash typography
- the protected counterpart of sham breadth: a real span or range that must stay clean
- noun chains as a standalone German special case („die Realisierung der Optimierung der Prozesse“)

## Case 1 – German LinkedIn post (profile: social)

INPUT:
> In der heutigen schnelllebigen Arbeitswelt ist Weiterbildung ein echter Gamechanger. Es geht nicht um Tools. Es geht nicht um Prozesse. Es geht um Menschen. Unser neues Programm ist praxisnah, flexibel und nachhaltig – ein nahtloses Lernerlebnis, das Potenziale entfesselt. Die Zukunft bleibt spannend!

EXPECTED:
- P1: formulaic opener („In der heutigen schnelllebigen…“)
- P1: negative parallelism, stacked multi-negation
- P1: adjective triad
- P1: Tier-1 word hits (Gamechanger, nahtlos, Potenziale entfesseln)
- P2: generic closer („Die Zukunft bleibt spannend“)
- P1: Tier-2 cluster (praxisnah, flexibel, nachhaltig as universal praise)
- Must NOT flag: the correctly spaced German en dash in the social profile.

## Case 2 – English blog paragraph (profile: blog)

INPUT:
> Let's delve into the rapidly evolving landscape of workplace learning. Modern platforms serve as a testament to seamless innovation—empowering teams to unlock their full potential. It's not just training, it's transformation. Studies show that companies investing in learning outperform their peers.

EXPECTED:
- P1: Tier-1 hits (delve, ever-evolving landscape, serves as a testament, seamless, empower, unlock potential)
- P1: negative parallelism ("It's not just X, it's Y")
- P2: copula avoidance ("serve as"); the inflated stock phrase separately warrants P1
- P0: unsourced vague attribution ("Studies show")
- P1: em-dash frequency in this short blog passage, corroborated by the stock-phrase cluster

## Case 3 – Slide titles (profile: slides)

INPUT (title sequence of a deck):
> 1. Ein Blick auf unsere Ausgangslage
> 2. Was die Zahlen uns verraten
> 3. So funktioniert der neue Prozess
> 4. Die Anbieter
> 5. Wohin geht die Reise?

EXPECTED:
- P1: teaser half-sentence titles (1, 2)
- P1: colloquial sentence title (3) → noun label („Funktionsweise“ pattern)
- P1: bare topic label without function (4); flag the missing role rather than inventing a comparison
- P1: question-as-scaffolding closer title (5)
- P1: title sequence does not carry a storyline on its own

## Case 4 – Slide body (profile: slides)

INPUT (single slide, status footer included):
> **Mitmachen erwünscht!**
> Wir fangen bei null an — niemand bleibt zurück.
> Kennzahlen unbedingt vorher checken!
> [Hinweis für Moderation: hier Pause einplanen]
> Status: Entwurf – Vertraulich

EXPECTED:
- P1: colloquial register on the slide face (Mitmachen, „wir fangen bei null an“)
- P1: em dash on a slide (zero budget)
- P1: command tone instead of recommendation
- P0: moderator note on the slide face
- P1: unrequested status stamp and blanket confidentiality marker

## Case 5 – German prose, nominal style (profile: blog)

INPUT:
> Im Rahmen der Durchführung der Umstellung erfolgte eine Optimierung der Abläufe durch das Projektteam. Es wurde entschieden, dass eine Verbesserung der Reaktionszeiten realisiert werden soll, wobei die Umsetzung der Maßnahmen zeitnah vorgenommen wird.

EXPECTED:
- P2: nominalization chains („Durchführung der Umstellung“, „-ung + erfolgen/vornehmen“)
- P2: empty subject („Es wurde entschieden“)
- P2: clause stacking („wobei…“)
- P1: Tier-2 cluster (Optimierung, zeitnah); flag the missing timing without inventing a date
- Rewrite direction: actor-first sentences with verbs

## Case 6 – Clean human email (profile: email) — MUST STAY CLEAN

INPUT:
> Hi Markus, kurzes Update: der Testlauf ist durch, zwei kleinere Bugs sind noch offen (Ticket 4711 und 4712). Ich schaffe das Deployment am Donnerstag nicht mehr, Freitag Vormittag klappt. Passt das für euch? Viele Grüße, Anna

EXPECTED:
- No findings. Contractions of thought, fragments, and the direct question are the human register of a quick email.

## Case 7 – Academic abstract (profile: academic)

INPUT:
> Our novel framework significantly outperforms all existing approaches and proves that transfer learning is universally superior. Extensive experiments across numerous datasets demonstrate groundbreaking results. The data suggest that latency may depend on batch size.

EXPECTED:
- P1: overclaiming verbs (proves, universally superior) without evidence pointers
- P1: empty intensifiers (extensive, a wide range of, groundbreaking, significantly without a test)
- P1: novelty padding ("novel")
- Preserve: the calibrated hedge in the last sentence ("suggest", "may") must NOT be flagged

## Case 8 – Mixed formats and artifacts (profile: docs)

INPUT:
> Certainly! Here is an overview of the rollout. The migration covers 10,000 Geräte in 3.5 Wochen und senkt die Kosten um 12%. Weitere Details finden Sie unter https://example.com/?utm_source=chatgpt.com. Stand: 08/24/2026.

EXPECTED:
- P0: chat artifact opener ("Certainly! Here is…")
- P0: leaked AI tracking parameter in the URL
- P1: mixed number conventions in a German sentence (10,000 / 3.5 / 12% without spacing)
- P2: US date format in German prose


## Case 9 – LinkedIn story post (profile: social, narrative)

INPUT:
> Zur Einordnung: Unser Team betreut seit 2023 rund 40 Mittelständler, meist mit knappen IT-Ressourcen. Letzten Monat rief ein Geschäftsführer an. Herr Krause, seit 20 Jahren Inhaber eines Familienbetriebs und ein erfahrener Kaufmann, war zunächst skeptisch. Wir zeigten ihm das System, er testete es, und am Ende unterschrieb er. Heute läuft alles stabil, das Team ist zufrieden, und alle offenen Fragen sind geklärt. Und da wurde mir klar: Am Ende zählt nicht die Technik, sondern das Vertrauen.

EXPECTED:
- P1: realization coda („Und da wurde mir klar…“)
- P1: fully front-loaded backstory („Zur Einordnung: …“)
- P2: person introduced via description block instead of action or speech
- P2: everything resolved, no open thread; flat escalation (setup → demo → signature in even beats)
- P1: negative parallelism in the realization coda
- Rewrite direction: reorder the supplied backstory and end on a sourced event. No quote or open question is supplied; flag those gaps instead of inventing either.

## Case 10 – Product blog section (profile: blog)

INPUT:
> Der Export läuft jetzt auch nachts. Das ist wichtiger, als es klingt. Was die meisten übersehen: Die Nachtfenster entscheiden über den ganzen Tagesbetrieb. Das Beste daran: Es läuft ohne Zutun. Wir haben die Laufzeit halbiert, und das Team merkt es sofort. Am Ende zählt eben nicht die Technik, sondern die Zeit, die sie zurückgibt.

EXPECTED:
- P2: interpretive metadiscourse („Das ist wichtiger, als es klingt“)
- P1: faux-insight setup („Was die meisten übersehen:“)
- P1: colon reveal („Das Beste daran: …“)
- P1: aphoristic kicker in the last sentence („Am Ende zählt eben nicht …, sondern …“), which is also a negative parallelism
- P1: false agency („Die Nachtfenster entscheiden …“)
- Flag the gap in „das Team merkt es sofort“: what does the team notice?
- Preserve: „Wir haben die Laufzeit halbiert“ is a checkable relative change. Missing absolute figures do not justify deleting or weakening it.
- Rewrite direction: delete the asides, state the night window as a plain sentence, end on the concrete result instead of the maxim

## Case 11 – Email reply (profile: email)

INPUT:
> Hallo Petra, danke für deine Rückfrage zum Angebot. Wie du ja weißt, hatten wir im Juli über drei Varianten gesprochen, und damals war noch offen, ob die Wartung mit drin sein soll. Versteh mich nicht falsch, ich finde alle drei Varianten sinnvoll. Für diese Antwort habe ich die Unterlagen nochmal durchgesehen und mit dem Vertrieb abgestimmt. Lies das nochmal: Die Wartung ist ab sofort JEDES Jahr inklusive. Unterm Strich empfehle ich Variante B. Viele Grüße, Lars

EXPECTED:
- P2: reply rebuilds context the reader already has; the decision (Variante B) arrives last
- P1: phantom objection („Versteh mich nicht falsch …“)
- P2: text about itself („Für diese Antwort habe ich … durchgesehen …“)
- P1: staged emphasis („Lies das nochmal:“, „JEDES“)
- P1: word-list hit („Unterm Strich“)
- Must NOT flag: the salutation and the sign-off
- Rewrite direction: open with the recommendation, keep maintenance now included every year and any reasoning that changes Petra's decision; drop only the redundant recap and work narration.

## Case 12 – Weak signals only (profile: blog) — MUST STAY CLEAN

INPUT:
> Seit März messen wir die Ladezeiten jeden Morgen um 8 Uhr – die Werte schwanken zwischen 1,2 und 1,9 Sekunden. Vielleicht liegt das am CDN, sicher wissen wir es noch nicht. Die Messung wurde von Jana aufgesetzt; die Kollegin pflegt das Skript seitdem allein.

EXPECTED:
- No findings. One dash, one honest hedge, one passive sentence and one synonym change („Jana“ / „die Kollegin“) are weak signals that occur in human writing; their co-occurrence has no shared filler or repetitive function. The passive names its actor, and the uncertainty is explicit. Flagging any of them is a regression.

## Case 13 – Landing page section (profile: blog)

INPUT:
> ## Weniger suchen. Mehr finden.
> Die Zahlen sprechen für sich. Unser Tool entscheidet selbst, welche Dokumente relevant sind. Obwohl die Suche vielversprechend ist, bleibt die Datenqualität eine Herausforderung. Der Druck ist real.
> ## Drei zentrale Vorteile
> ## Ein Login. Alle Quellen.
> ## Einmal einrichten. Fertig.

EXPECTED:
- P1: false agency („Die Zahlen sprechen für sich“, „Unser Tool entscheidet selbst“)
- P1: template balance (empty concession)
- P2: the „ist real“ calque
- P2: counted list for its own sake („Drei zentrale Vorteile“)
- P1: slogan cadence (three headings built from clipped sentences in one document)
- Rewrite direction: name the figures and the matching mechanism if the source has them, otherwise flag the gaps; headings as noun labels

## Case 14 – Load-bearing language (profile: docs) — MUST STAY CLEAN

INPUT:
> Zugangsdaten dürfen niemals im Frontend-Code gespeichert werden. Das Präparat kann bei einigen Patienten Schwindel verursachen. Die Ausfallquote sank im dritten Quartal um 40 %, nicht um 4 %. Der Parser liest die Datei zeilenweise ein und schlägt fehl, wenn eine Zeile mehr als 4.096 Zeichen hat.

EXPECTED:
- No findings. The absolute („niemals“), the hedge and scope („kann“, „bei einigen Patienten“), the corrected figure („40 %, nicht 4 %“) and the technical verbs („liest“, „schlägt fehl“) are load-bearing or exempt. Flagging, softening, or strengthening any of them is a regression.

## Case 15 – Protected vocabulary and tail (profile: docs) — MUST STAY CLEAN

INPUT:
> The structure must remain robust under the specified load. The parser rejects rows exceeding 4,096 characters.

EXPECTED:
- No findings. "Robust" has a real technical meaning; the participle phrase states the rejection condition rather than performing analysis. Neither term may be mechanically cut by the self-check.

## Case 16 – Supported three-part meaning (profile: docs) — MUST STAY CLEAN

INPUT:
> Der Export enthält Name, Datum und Preis. Die drei Felder sind Pflichtfelder.

EXPECTED:
- No findings. All three list items and the informative count stay; changing the count or dropping an item to avoid a triad would lose content.

## Case 17 – Missing evidence (profile: blog)

INPUT:
> Die Einführung unterstreicht unser Engagement. Studien zeigen, dass die Lösung die Bearbeitungszeit halbiert.

EXPECTED:
- P1: significance inflation („unterstreicht unser Engagement“)
- P0: unsourced vague attribution („Studien zeigen“)
- Rewrite constraint: flag the source gap. Do not invent a study, absolute timings, an actor, or a date; preserve the halving claim's strength if retained pending evidence.

## Case 18 – Same punctuation, different surface (profile: slides, notes: prose)

INPUT:
> Slide: Der Parser liest die Datei — und prüft jede Zeile.
> Speaker notes: Der Parser liest die Datei – und prüft jede Zeile.

EXPECTED:
- P1: em dash on the slide face, even though it is a single dash
- Must NOT flag: the correctly spaced German en dash in the notes or the ordinary technical verbs. The slide prohibition concerns em dashes, not every dash character or a range marker.

## Case 19 – English load-bearing metaphors in prose (profile: blog)

INPUT:
> This architecture underpins our platform and serves as the backbone of the entire data pipeline. It pays off by streamlining operations across all regional clusters.

EXPECTED:
- P1: load-bearing metaphors used as claims ("underpins", "backbone of", "pays off")
- P2: copula avoidance ("serves as")
- P1: Tier-1 stock-phrase hit ("streamlining operations")
- Rewrite direction: replace metaphors with plain verbs and name the criterion or evidence if supplied in source; flag the missing measurement gaps rather than inventing metrics.

## Case 20 – English clean technical announcement (profile: docs) — MUST STAY CLEAN

INPUT:
> The database migration completed on Sunday at 02:00 UTC. The new index reduces query latency for accounts with over 100,000 records from 420 ms to 85 ms. No downtime was reported during the window.

EXPECTED:
- No findings. Specific timestamp, concrete thresholds, exact before/after measurements, and neutral passive ("was reported") in a technical changelog/docs context are clean human professional writing.

## Case 21 – Clean German microformats (profile: docs) — MUST STAY CLEAN

INPUT:
> „Version 2“ ging am 24. August 2026 live – nach 3,2 Sekunden war der Export fertig, 10.000 Datensätze waren geladen, und das Team sparte 50 % der Prüfzeit sowie 40 € pro Vorgang.

EXPECTED:
- No findings. Correct German quotation marks, a correctly spaced en dash, decimal comma, thousands separator, percent spacing, date format, and currency after the amount must stay clean.

## Case 22 – German special cases cluster (profile: email)

INPUT:
> Ich hoffe, diese E-Mail erreicht Sie wohlbehalten. Von der Buchhaltung bis zur Cloud deckt das Paket alles ab. Doch wie funktioniert das? Werfen wir einen Blick darauf. Fazit: Bei Fragen melde dich gern.

EXPECTED:
- P0: salutation calque / chat artifact („Ich hoffe, diese E-Mail erreicht Sie wohlbehalten“)
- P2: sham breadth („Von der Buchhaltung bis zur Cloud“)
- P1: stock transitions / question scaffolding („Doch wie funktioniert das? Werfen wir einen Blick darauf.“)
- P2: „Fazit“ ritual used as a generic closer
- P1: Du/Sie register switch within the same email („Sie“ / „dich“)
