# Regression cases

How to run: for each case, run the skill in **check mode** with the stated profile on the INPUT block, then compare the findings to EXPECTED. A case passes when every expected finding category appears with roughly the stated severity and at most one unlisted extra is flagged. Case 6 must come back clean; flagging it is a regression (overflagging counts as failure). All content is invented.

## Case 1 – German LinkedIn post (profile: social)

INPUT:
> In der heutigen schnelllebigen Arbeitswelt ist Weiterbildung ein echter Gamechanger. Es geht nicht um Tools. Es geht nicht um Prozesse. Es geht um Menschen. Unser neues Programm ist praxisnah, flexibel und nachhaltig – ein nahtloses Lernerlebnis, das Potenziale entfesselt. Die Zukunft bleibt spannend!

EXPECTED:
- P1: formulaic opener („In der heutigen schnelllebigen…")
- P1: negative parallelism, stacked multi-negation
- P1: adjective triad
- P1: Tier-1 word hits (Gamechanger, nahtlos, Potenziale entfesseln)
- P1: generic closer („Die Zukunft bleibt spannend")
- Note: em dash / spaced dash usage worth flagging alongside

## Case 2 – English blog paragraph (profile: blog)

INPUT:
> Let's delve into the ever-evolving landscape of workplace learning. Modern platforms serve as a testament to seamless innovation—empowering teams to unlock their full potential. It's not just training, it's transformation. Studies show that companies investing in learning outperform their peers.

EXPECTED:
- P1: Tier-1 hits (delve, ever-evolving landscape, serves as a testament, seamless, empower, unlock potential)
- P1: negative parallelism ("It's not just X, it's Y")
- P1: copula avoidance ("serve as")
- P0: unsourced vague attribution ("Studies show")
- P1: em dash without need

## Case 3 – Slide titles (profile: slides)

INPUT (title sequence of a deck):
> 1. Ein Blick auf unsere Ausgangslage
> 2. Was die Zahlen uns verraten
> 3. So funktioniert der neue Prozess
> 4. Die Anbieter
> 5. Wohin geht die Reise?

EXPECTED:
- P1: teaser half-sentence titles (1, 2)
- P1: colloquial sentence title (3) → noun label ("Funktionsweise" pattern)
- P1: bare topic label without function (4) → compound noun pattern
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
- P1: colloquial register on the slide face (Mitmachen, „wir fangen bei null an")
- P1: em dash on a slide (zero budget)
- P1: command tone instead of recommendation
- P0: moderator note on the slide face
- P1: unrequested status stamp and blanket confidentiality marker

## Case 5 – German prose, nominal style (profile: blog)

INPUT:
> Im Rahmen der Durchführung der Umstellung erfolgte eine Optimierung der Abläufe durch das Projektteam. Es wurde entschieden, dass eine Verbesserung der Reaktionszeiten realisiert werden soll, wobei die Umsetzung der Maßnahmen zeitnah vorgenommen wird.

EXPECTED:
- P2: nominalization chains („Durchführung der Umstellung", „-ung + erfolgen/vornehmen")
- P2: empty subject („Es wurde entschieden")
- P1/P2: clause stacking („wobei…") and vague „zeitnah" without a date
- Rewrite direction: actor-first sentences with verbs

## Case 6 – Clean human email (profile: email) — MUST STAY CLEAN

INPUT:
> Hi Markus, kurzes Update: der Testlauf ist durch, zwei kleinere Bugs sind noch offen (Ticket 4711 und 4712). Ich schaffe das Deployment am Donnerstag nicht mehr, Freitag Vormittag klappt. Passt das für euch? Viele Grüße, Anna

EXPECTED:
- No findings. Contractions of thought, fragments, and the direct question are the human register of a quick email.

## Case 7 – Academic abstract (profile: academic)

INPUT:
> Our novel framework significantly outperforms all existing approaches and proves that transfer learning is universally superior. Extensive experiments on a wide range of datasets demonstrate groundbreaking results. The data suggest that latency may depend on batch size.

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
- P1: realization coda („Und da wurde mir klar…")
- P1: fully front-loaded backstory („Zur Einordnung: …")
- P2: person introduced via description block instead of action or speech
- P2: everything resolved, no open thread; flat escalation (setup → demo → signature in even beats)
- Rewrite direction: end on the event or an open question, one temporal move, let Herr Krause enter through his own words

## Case 10 – Product blog section (profile: blog)

INPUT:
> Der Export läuft jetzt auch nachts. Das ist wichtiger, als es klingt. Was die meisten übersehen: Die Nachtfenster entscheiden über den ganzen Tagesbetrieb. Das Beste daran: Es läuft ohne Zutun. Wir haben die Laufzeit halbiert, und das Team merkt es sofort. Am Ende zählt eben nicht die Technik, sondern die Zeit, die sie zurückgibt.

EXPECTED:
- P2: interpretive metadiscourse („Das ist wichtiger, als es klingt")
- P1: faux-insight setup („Was die meisten übersehen:")
- P1: colon reveal („Das Beste daran: …")
- P1: aphoristic kicker in the last sentence („Am Ende zählt eben nicht …, sondern …"), which is also a negative parallelism
- P1: vague claim without a checkable fact („halbiert" without the two figures; „merkt es sofort")
- Rewrite direction: delete the asides, state the night window as a plain sentence, end on the concrete result instead of the maxim

## Case 11 – Email reply (profile: email)

INPUT:
> Hallo Petra, danke für deine Rückfrage zum Angebot. Wie du ja weißt, hatten wir im Juli über drei Varianten gesprochen, und damals war noch offen, ob die Wartung mit drin sein soll. Versteh mich nicht falsch, ich finde alle drei Varianten sinnvoll. Für diese Antwort habe ich die Unterlagen nochmal durchgesehen und mit dem Vertrieb abgestimmt. Lies das nochmal: Die Wartung ist ab sofort JEDES Jahr inklusive. Unterm Strich empfehle ich Variante B. Viele Grüße, Lars

EXPECTED:
- P2: reply rebuilds context the reader already has; the decision (Variante B) arrives last
- P1: phantom objection („Versteh mich nicht falsch …")
- P2: text about itself („Für diese Antwort habe ich … durchgesehen …")
- P1: staged emphasis („Lies das nochmal:", „JEDES")
- P1: word-list hit („Unterm Strich")
- Must NOT flag: the salutation and the sign-off
- Rewrite direction: open with the recommendation, keep the one fact Petra lacks (maintenance now included every year), drop the recap

## Case 12 – Weak signals only (profile: blog) — MUST STAY CLEAN

INPUT:
> Seit März messen wir die Ladezeiten jeden Morgen um 8 Uhr – die Werte schwanken zwischen 1,2 und 1,9 Sekunden. Vielleicht liegt das am CDN, sicher wissen wir es noch nicht. Die Messung wurde von Jana aufgesetzt; die Kollegin pflegt das Skript seitdem allein.

EXPECTED:
- No findings. One dash, one honest hedge, one passive sentence and one synonym change („Jana" / „die Kollegin") are weak signals that occur in human writing; none of them clusters with another tell here. Flagging any of them is a regression.

## Case 13 – Landing page section (profile: blog)

INPUT:
> ## Weniger suchen. Mehr finden.
> Die Zahlen sprechen für sich. Unser Tool entscheidet selbst, welche Dokumente relevant sind. Obwohl die Suche vielversprechend ist, bleibt die Datenqualität eine Herausforderung. Der Druck ist real.
> ## Drei zentrale Vorteile
> ## Ein Login. Alle Quellen.
> ## Einmal einrichten. Fertig.

EXPECTED:
- P1: false agency („Die Zahlen sprechen für sich", „Unser Tool entscheidet selbst")
- P1: template balance (empty concession)
- P2: the „ist real" calque
- P2: counted list for its own sake („Drei zentrale Vorteile")
- P1: slogan cadence (three headings built from clipped sentences in one document)
- Rewrite direction: name the figures and the matching mechanism if the source has them, otherwise flag the gaps; headings as noun labels

## Case 14 – Load-bearing language (profile: docs) — MUST STAY CLEAN

INPUT:
> Zugangsdaten dürfen niemals im Frontend-Code gespeichert werden. Das Präparat kann bei einigen Patienten Schwindel verursachen. Die Ausfallquote sank im dritten Quartal um 40 %, nicht um 4 %. Der Parser liest die Datei zeilenweise ein und schlägt fehl, wenn eine Zeile mehr als 4.096 Zeichen hat.

EXPECTED:
- No findings. The absolute („niemals"), the hedge and scope („kann", „bei einigen Patienten"), the corrected figure („40 %, nicht 4 %") and the technical verbs („liest", „schlägt fehl") are load-bearing or exempt. Flagging, softening, or strengthening any of them is a regression.
