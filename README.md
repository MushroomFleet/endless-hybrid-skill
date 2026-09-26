# Endless Hybrid

**A Claude skill for merging two prompt-generation skills into one designed batch, so their rules are reconciled on purpose rather than blended by feel.**

[github.com/MushroomFleet/endless-hybrid-skill](https://github.com/MushroomFleet/endless-hybrid-skill)

---

## What it is

Endless Hybrid is a skill for Claude (Claude Code or any client that loads skills). It takes **two existing prompt-generation skills**, such as a phonk album generator and a psychedelic blues-trio generator, and merges them into a single batch of catalogued output: albums of ready-to-generate music prompts, or any other catalogued prompt set.

Blending two skills by feel usually goes wrong in one of two ways. Changing several things at once produces output nobody can learn from. Quietly breaking one skill's hard rules produces output that reads as a mistake. Endless Hybrid prevents both with one discipline:

> **One variable. Everything else constant. Every broken rule named.**

The skill writes prompt catalogues and a production-notes file, then hands off. It **never generates audio itself**. Generation belongs to a downstream producer skill (built and proven with [`lyra-producer`](https://github.com/MushroomFleet/Lyra-Producer-skill), a Gemini Lyria 3.5 batch CLI), with the operator confirming scope before any spend.

## What it is for

- **Designing cross-genre albums as experiments.** Each merge becomes a grid of pairings you can listen to and learn from, not a one-off mash-up.
- **Reconciling contradictory rulebooks.** When one skill's exclusion list is an inventory of the other's core, the skill decides which list goes and records why.
- **Keeping merges honest.** Every pairing is rated for how much the two halves actually differ *before* anything is spent, and the weakest pairing is named up front.
- **Leaving a record.** Each batch ships with production notes explaining why it sounds the way it does, so a later reader can tell a decision from a mistake.

## How it works

1. **Spine and partner.** One skill organises the batch into albums (the *spine*); the other contributes the second axis (the *partner*): archetypes, vocabulary, fiction or structure.
2. **Read both skills completely.** Every reference file on both sides. The collisions are in the exclusion lists and "never" sentences, not the descriptions.
3. **Build a collision map.** Classify the conflict:

   | Type | Signature | Resolution |
   |---|---|---|
   | **Mutual prohibition** | Each skill forbids the other's core | Discard one exclusion list wholesale, and say so |
   | **Convergent** | Same domain, near-identical vocabulary | Let the partner's distinct layer (usually its fiction) carry the merge |
   | **Single-point** | Agree on everything but one law | Find the *seam* where the two already touch |

4. **Map the numeric ranges.** Tempo, scale or intensity: find the overlaps, the gaps and the out-of-range modes.
5. **Run pre-flight tests.** Dry-run a throwaway catalogue through the downstream CLI before writing the real one: non-Latin titles, new labels, unusual headings.
6. **Rate every pairing** HIGH / MEDIUM / LOW before spending.
7. **Put the forks to the operator.** The variable, each unresolved collision, batch size, folder and naming.
8. **Write the merge-rule table.** Every layer of the medium gets exactly one owner, plus a block listing everything discarded.
9. **Write the catalogues and the notes, dry-run everything, hand off.**

The variable menu covers blend ratio, partner-mode pairing, range stretch, per-track gradient, structural arc and fiction gradient, each with rules for when it works and when it is inaudible.

## Proven in practice

The method comes from real merges, not theory:

- **Three founding case studies:** 150 generated tracks across one merge of each collision type, all accepted on listening. Their compressed notes ship with the skill.
- **A proof batch:** three hybrid collections, each a 3×3 grid of spine lane × partner style, from one shared concept. That's 27 albums and 270 full-length tracks, all generated. The hardest merge, a mutual prohibition between an era-locked 1960s guitar-trio skill and a phonk skill, exceeded expectations on listening.

The doctrine carried in the skill comes from those runs:

- Only the posted prompt reaches the model.
- Prompt length does not hurt reliability.
- A hard failure is usually transient, so re-run before rewording.
- A near-null merge is a finding, not a failure.
- Record every violation.

## Installation

Copy the skill folder into your Claude skills directory:

```
~/.claude/skills/endless-hybrid/
├── SKILL.md
└── references/
    ├── collision-map.md       # the three collision types and the resolution doctrine
    ├── merge-rule-tables.md   # layer-ownership tables and the production-notes template
    ├── preflight-tests.md     # empirical tests and downstream pipeline constants
    └── case-studies.md        # three proven merges, predictions and outcomes
```

The skill loads automatically when a request matches. To call it explicitly, say "use the endless-hybrid skill".

## Usage

You need two prompt-generation skills installed, plus a concept (an IDEA) for the albums:

> Use the endless-hybrid skill to combine endless-phonk67 with endless-jimmy. The IDEA is "a river with no banks".

The skill reads both skills, reports the collision type, the numeric ranges and the pairing ratings, and asks you about the variable, the collisions, the batch size and the naming. Only after that does it write anything. You get one catalogue per album and a single production-notes file, all dry-run clean and ready for your producer skill.

**Downstream notes for Lyria users:**

- Pass the producer's instrumental flag at run time rather than writing negative phrasing into prompts.
- Expect full songs to render at about three minutes, whatever length the prompt requests.

## Requirements

- Claude with skill support (Claude Code recommended).
- Two source skills to merge. The skill was built against the author's `endless-*` family of phantom-album prompt generators, but any two catalogue-producing skills work.
- A downstream generator for the output (optional for writing, required for audio). `lyra-producer` is the proven pairing.

---

## 📚 Citation

### Academic Citation

If you use this codebase in your research or project, please cite:

```bibtex
@software{endless_hybrid_skill,
  title = {Endless Hybrid: a Claude skill for merging two prompt-generation skills into one designed batch},
  author = {Drift Johnson},
  year = {2026},
  url = {https://github.com/MushroomFleet/endless-hybrid-skill},
  version = {1.0.0}
}
```

### Donate:

[![Ko-Fi](https://cdn.ko-fi.com/cdn/kofi3.png?v=3)](https://ko-fi.com/driftjohnson)
