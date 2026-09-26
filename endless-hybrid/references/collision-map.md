# The Collision Map

How to find where two skills contradict each other, classify what you find, and resolve it
deliberately. Build this before any other merge work — the collision type determines the
variable, the merge-rule table, and often the whole batch design.

## 1. Where collisions hide

They are almost never in the descriptions. Both skills will describe themselves in warm,
compatible-sounding language. The contradictions live in four places:

| Look in | What you are looking for |
|---|---|
| **Exclusion / negative-prompt lists** | The single richest source. One skill's "Avoid:" list is often a verbatim inventory of the other's core. |
| **"Hard rules" / "non-negotiable" sections** | Laws stated as absolute. When two absolutes disagree, one must break. |
| **"Never" and "always" sentences anywhere** | Including inside archetype descriptions and craft files, where they are easy to miss. |
| **Per-mode vocabulary banks** | Subtler: two skills can agree in principle and still demand incompatible instrumentation in a given lane. |

**Method:** extract every imperative from both skills into two lists, then diff them. Read
the partner's exclusion list *as if it were a description of the spine* — if it reads like
one, you have a mutual prohibition.

## 2. The three types

### Type 1 — Mutual prohibition

**Signature.** Each skill forbids what the other is built on. The exclusion list of one
names the core mechanics of the other.

> *Case study:* geinoh's exclusion list forbade `four-on-the-floor`, `modern trap`,
> `drum-kit backbeat`, `rap` and `lo-fi hip-hop` — which is phonk67's entire rhythm section.

**Resolution: one exclusion list is discarded wholesale.** Not softened, not partially
honoured — discarded, with the decision stated. Attempting to honour both produces output
that is neither skill, because every layer ends up compromised.

Choose which to discard by asking **which skill owns the layer the exclusions target**. If
the partner's exclusions target the spine's structural core, the exclusions go. Then give
the partner everything *above* that layer, so it is contributing at full strength
everywhere it is not in conflict.

**This type produces the most legible batches**, because the two halves are audibly
distinct — which is also the only condition under which a **blend ratio** works as the
variable.

### Type 2 — Convergent

**Signature.** The two skills occupy the same domain and describe it in near-identical
words. Diffing their imperatives produces almost nothing.

> *Case study:* endless-phonk and endless-phonk67 both demanded mandatory damage, a
> mandatory cowbell in the drift lane, and "the vocal is a sample, never a singer". One
> pairing — drift × Drift Engine — matched almost phrase for phrase.

**This is the dangerous type**, because it *feels* like the easiest merge and can produce a
batch where the partner contributed nothing. The failure mode is a null merge dressed up as
a collaboration.

**Resolution: identify the partner's genuinely distinct layer and let it carry the merge.**
Usually that is the **fiction layer** — a naming conceit, an archive framing, a
catalogue grammar the spine lacks. Sometimes it is a wider numeric range, or sub-modes the
spine has no lane for.

**A blend ratio is the wrong variable here** and will be inaudible. Use mode pairing, and
rate the pairings honestly — in the case study, one was rated LOW before spending and the
prediction held.

### Type 3 — Single-point

**Signature.** The two skills agree on nearly everything, then collide absolutely on one
law.

> *Case study:* endless-russianwave pins a deadpan baritone *singer* in every prompt, with
> optional lyric blocks. The spine project was instrumental-only. Everything else — the
> degradation laws, the cold atmospheres, the four-on-the-floor discipline — agreed.

**Resolution: find the seam.** Before overriding either side, look for a place the two
skills *already touch* on the contested layer. A single-point conflict often has one,
because skills in adjacent domains borrow from each other.

> In the case study the spine's own promptgen spec already asked for a "cinematic Russian
> spoken-word sample" in one lane. So the baritone became a **pitched-down spoken-word
> sample** rather than a singer — satisfying the partner's demand for the voice and the
> spine's prohibition on singing, through a route both skills already endorsed.

Only if no seam exists should you override, and then state which law lost.

## 3. The resolution doctrine

Four rules, in order:

1. **Name the type before choosing a variable.** The type constrains which variables work.
2. **Look for the seam before overriding.** An override is a last resort; a seam is free.
3. **When you must override, discard cleanly.** Partial compliance with an exclusion list
   produces mush. Discard it, say so, and give that skill full ownership elsewhere.
4. **Write every violation down.** In the notes, with its reasoning, so it reads as a
   decision. An unrecorded violation is indistinguishable from an error six months later.

## 4. Graded violations

A rule need not break uniformly across a batch. Withdrawing it by degrees can itself be the
design — and it must be tabulated when it is.

> *Case study:* the spine's drift lane required a cowbell in the majority of prompts. Across
> three albums it was withdrawn **3 / 4 / 0** as each partner archetype brought its own lead
> instrument and left the cowbell progressively less room. By the third, a square-wave
> earworm at 148–160 left nowhere for it to sit.

Record graded violations as a table showing the gradient and the reason for each step.

## 5. Collision map output

The artifact this file produces, which goes into the production notes:

```markdown
## Collision map

**Type:** <mutual prohibition | convergent | single-point>

**Contested layers**
| Layer | Skill A says | Skill B says | Resolution |
|---|---|---|---|
| ... | ... | ... | ... |

**Discarded wholesale**
- <rule> — from <skill>, because <reason>

**Seam used** (single-point only)
- <where the two skills already touched, and how the conflict routed through it>

**Graded violations**
| Album | Rule | Degree | Reason |
|---|---|---|---|
```
