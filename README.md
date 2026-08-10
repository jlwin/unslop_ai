# unslop

A writing guardrail for Claude that prevents and removes AI slop, in German and English.

`unslop` is an [Agent Skill](https://agentskills.io) (a single `SKILL.md` plus two reference files) that works with Claude Code, Claude Desktop/Cowork, and any other agent that reads the SKILL.md format. It treats German prose as a first-class citizen rather than as an afterthought.

## Why word filters are not enough

Most "humanizer" prompts ban a list of words (delve, tapestry, seamless) and call it a day. That fails twice. Word lists age with every model generation; GPT-5-era output already avoids most of the classic vocabulary. And the durable fingerprint sits elsewhere: in the StoryScope study (Russell et al. 2026, 61,608 texts), discourse structure alone identified AI text with 93.2 % accuracy, while professional sentence-level rewriting moved detection by just 1.6 points.

So this skill works on three levels, weighted toward the deeper two:

| Level | What it catches | Examples |
|---|---|---|
| 1 – Words | Vocabulary, stock phrases, punctuation | „nahtlos", „Gamechanger", *delve*, *serves as a testament*, em-dash overuse |
| 2 – Rhythm | Sentence-level patterns | uniform sentence lengths, parataxis chains, triads, „nicht X, sondern Y" / *"It's not X, it's Y"*, hedge stacking, participle tails |
| 3 – Structure | The shape of the whole text | the takeaway repeated per section, uniform paragraphs, template scaffolding, vague instead of named references, performed emotion („ein Kloß im Hals") instead of a named feeling |

One rule runs through all three levels: swap the vague claim for the checkable fact. A number, a name, a date, a price, a mechanism. And when that fact is missing, the skill flags the gap; it never invents one.

## What makes this one different

**German support.** AI slop in German has its own tells that English rule sets miss: the em dash without spaces inside German text (the correct Gedankenstrich is a spaced en dash), the ritual „Fazit"-heading that summarizes what was already said, salutation calques („Ich hoffe, diese E-Mail erreicht Sie wohlbehalten"), genitive noun chains, sham-breadth constructions („Ob Handwerksbetrieb oder DAX-Konzern"). All covered, with German word lists and worked examples.

**Guardrails against the humanizer failure mode.** The classic mistake of de-slopping tools is trading one fingerprint for a new one: chopped staccato fragments, fake first-person anecdotes, performed candor („Real talk:"). This skill treats every such move as a failed rewrite. It may cut and sharpen; it may not add facts, stance, or personality the author never wrote. Human quirks and typos in source text stay where they are.

**Calibrated, not dogmatic.** Rules apply per register. Fragments are native on LinkedIn and a tell in long-form prose. Hedging is a bug in marketing copy and a requirement in academic writing, where neutral precision *is* the human voice. A context-profile table (Social, Blog, Email, Docs, Academic) sets the strictness per rule.

## Modes

| Mode | Trigger | Behavior |
|---|---|---|
| **Write** | default for new text | applies the rules silently while drafting |
| **Check** | „prüfe auf AI-Muster", *"scan this"* | flags only, grouped by severity (P0/P1/P2), changes nothing |
| **Rewrite** | „mach das menschlicher", *"de-slop this"* | audit, cleaned version, change log, second pass on its own output |
| **Edit file** | „bereinige draft.md direkt" | minimal in-place edits, leaves human passages untouched |

## Install

**Claude Code** (global):

```bash
git clone https://github.com/jlwin/unslop_ai.git ~/.claude/skills/unslop
```

Per project instead: clone into `.claude/skills/unslop` inside the repo.

**Claude app (Desktop, Cowork, claude.ai):** zip the folder (`SKILL.md` at the archive root, `references/` beside it) and add it as a skill in your Claude settings.

**Other agents:** anything that reads the agentskills `SKILL.md` format can use it as-is.

## Usage

```
Schreib einen LinkedIn-Post über unser neues Feature.   → Write mode kicks in automatically
Prüfe diesen Text auf AI-Muster, ändere nichts.          → Check
De-slop this blog draft.                                 → Rewrite
Klingt das nach ChatGPT?                                 → Check
Bereinige README.md direkt in der Datei.                 → Edit file
```

A taste of what the rewrite mode does:

> **Before:** „Unsere Plattform ist schnell, sicher und intuitiv."
> **After:** „Die Plattform lädt Reports in unter zwei Sekunden. Und sie besteht den BSI-Grundschutz-Check."

> **Before:** *"This launch stands as a powerful testament to our team's relentless pursuit of excellence."*
> **After:** *"We shipped the export feature today. The beta group has been running it since April without a single support ticket."*

More in [`references/pattern-catalog.md`](references/pattern-catalog.md): 17 pattern families, each with German and English before/after pairs.

## Repository layout

```
SKILL.md                        the skill: levels, modes, workflow, profiles, guardrails
references/word-lists.md        banned and suspect vocabulary, DE + EN, in three evidence tiers
references/pattern-catalog.md   worked before/after examples for every pattern family
```

## Scope and ethics

This skill serves good writing. It is not a tool for evading AI detectors or disclosure duties: where AI use must be declared (university, publisher, client, employer), declare it. The patterns here are statistical signals, not proof of authorship; humans on deadline produce many of the same shapes, which is exactly why the skill calibrates by register instead of flagging on sight.

## License

MIT. See [LICENSE](LICENSE).
