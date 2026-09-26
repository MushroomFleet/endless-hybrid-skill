---
name: endless-hybrid
description: Merge two prompt-generation skills into one batch of albums (or other catalogued output), where the two skills' rulebooks are reconciled deliberately rather than blended by feel. Use this skill whenever the user wants to combine, cross, hybridise or fuse two generator skills — "use endless-phonk67 with endless-russianwave", "merge skill A and skill B", "what happens if we cross X with Y", "run the hybrid experiment with Z", "create the same structure using <other skill> in place of <skill>" — or asks to design a controlled experiment across several albums where one variable changes and everything else is held constant. It analyses both skills for rule collisions, maps their numeric ranges for overlap and gaps, runs empirical parser pre-flight tests, rates each pairing for how much it actually adds before anything is spent, then writes the catalogues and a production-notes artifact recording every decision. Outputs prompt catalogues and notes only; it never generates audio.
---

# Endless Hybrid

Merge two prompt-generation skills into one coherent batch. The point is not to blend them
by feel — it is to **make the merge a designed experiment**: one variable changes across
the batch, everything else is held constant, and every rule that had to break is named.

The method came out of three real merges producing 150 accepted tracks. Their compressed
case notes are in `references/case-studies.md`; read them when you want to see the method
land rather than be described.

## The core discipline

> **One variable. Everything else constant. Every broken rule named.**

A merge that changes several things at once produces output nobody can learn from. A merge
that silently violates one skill's hard rule produces output that reads as a mistake. Both
failures are avoided by the same practice: decide what varies, write down who owns what,
and record the violations as decisions.

## Hard boundaries

- **Never generate.** This skill writes prompt catalogues and one production-notes file,
  then hands off. Generation is metered and belongs to the downstream producer skill, with
  the operator confirming scope.
- **Never blend without a rule.** If you cannot state which skill owns a given layer, you
  have not finished the merge design.
- **Never hide a violation.** Every suspended rule goes in the notes with its reasoning.

## Workflow

### 1. Identify the spine and the partner

Two roles, and getting them the right way round matters:

- **The spine** — the skill whose modes/lanes organise the batch into albums. It supplies
  the structural frame and usually the output format.
- **The partner** — the skill contributing the second axis: its archetypes, its aesthetic
  vocabulary, its fiction layer, or its structural arc.

**Rule for choosing:** the skill with the tighter, more enumerable mode set becomes the
spine. If both are enumerable, the one whose output format is already proven downstream
becomes the spine, because its catalogue shape is known to parse.

### 2. Read both skills completely

SKILL.md **and every reference file**, both sides, before designing anything. The collisions
that matter are almost never in the descriptions — they are in the exclusion lists, the
"hard rules" sections, and the per-archetype vocabulary banks.

### 3. Build the collision map

Follow `references/collision-map.md`. Diff the two skills' hard rules, exclusion lists and
"never" statements, and classify what you find into one of three types:

| Type | Signature | Resolution |
|---|---|---|
| **Mutual prohibition** | Each forbids the other's core | One exclusion list is discarded **wholesale**; say which and why |
| **Convergent** | Same domain, near-identical vocabulary | Nothing to reconcile — the partner's *distinct* layer (usually fiction) must carry the merge |
| **Single-point** | Agree on everything but one law | Find the **seam** — the place the two skills already touch — and route the conflict through it |

### 4. Map the numeric ranges

Both skills usually carry a quantitative axis — tempo, scale, length, intensity. Tabulate
the partner's ranges against the spine's lanes and find three things:

- **Overlaps** — where a pairing is native to both. These are the clean pairings.
- **Gaps** — spine lanes no partner mode reaches. These need a **stretch** or a substitution.
- **Out-of-range** — partner modes outside every spine lane. These are **expansion
  candidates**; report them, never silently drop them.

### 5. Run the pre-flight tests

Follow `references/preflight-tests.md`. **This step is not optional and it is not
theoretical** — write a throwaway catalogue in the scratchpad exercising anything unusual
the partner introduces (non-Latin titles, new labels, unusual heading shapes), and dry-run
it through the downstream CLI. Two of the three case-study batches were saved by this step.

Assume nothing about how a formatting convention survives. Test it.

### 6. Rate every pairing before spending

**Mandatory.** For each proposed pairing, rate how much the two halves actually differ:

```
HIGH    the partner contributes something the spine has no equivalent for
MEDIUM  a real collision that needs a decision — the decision IS the value
LOW     near-identical vocabulary; only the partner's fiction layer differs
```

Report the ratings **before** the operator commits to generating, name the weakest pairing
explicitly, and carry the ratings into the production notes. A LOW pairing is not a reason
to refuse — one shipped and was accepted — but it must be a stated prediction, not a
post-hoc excuse.

### 7. Put the forks to the operator

Analyse, recommend, then ask. Use a multiple-choice question covering, as applicable:

- **The variable** (§8 below) — with a recommendation and its reasoning
- **Each unresolved collision** — with the resolution you propose and what it costs
- **Batch size** — default one album per spine lane; if the partner has more modes than
  the spine has lanes, report how many would go untested and offer the expansion
- **Folder and naming** — where the batch lands and what prefix the catalogues take

Do not start writing until these are answered. Every one of the three case studies had at
least one operator answer that materially changed the output.

### 8. Choose the variable

What changes across the batch. The menu, with the selection rules that matter:

| Variable | Use when | Selection rule |
|---|---|---|
| **Blend ratio** | The two skills are audibly distinct | **Only** when distinct — a ratio between two skills in the same domain is imperceptible and wastes the batch |
| **Partner mode pairing** | The partner has an enumerable archetype/mode set | Pair each spine lane with the partner mode that sits on its range |
| **Range stretch** | The partner has modes outside the spine's ranges | Tests whether the spine's discipline survives outside its own bands, in either direction |
| **Per-track gradient** | You want the migration audible inside one album | Track 1 near-pure A, track N near-pure B |
| **Structural arc** | The partner has a strong structural spine of its own | Map the partner's arc onto the album's running order |
| **Fiction gradient** | The two differ mainly in their conceit | How much of the partner's fiction returns, album by album |

**Hold the world constant when the variable is a ratio.** If the blend is what varies, one
shared concept across the whole batch isolates it. When the variable is mode pairing, each
album may have its own world — that is what makes the pairings legible.

### 9. Write the merge-rule table

Follow `references/merge-rule-tables.md`. Enumerate the layers of the medium and assign
each to the spine, the partner, or both. **Every layer gets an owner.** Then list, in a
separate block, everything discarded rather than merged, with its reason.

### 10. Write the catalogues and the notes

Per album: the spine's catalogue format, unchanged — it is the format proven to parse.
Then one production-notes file for the batch, following the template in
`references/merge-rule-tables.md` §4, covering the collision map, the merge-rule table,
the pairing ratings, the discarded rules, the knowing violations, and a QC checklist.

### 11. Dry-run everything, then hand off

Dry-run every catalogue through the downstream CLI. Confirm track counts, filenames and
the absence of any parser-hazard tags. Report the pairing ratings alongside the scope and
cost, and let the operator decide whether to spend.

## Doctrine carried from the case studies

These are conclusions from 150 generated tracks, not guesses. `references/preflight-tests.md`
holds the technical detail.

1. **Only the posted prompt matters.** Titles, program notes and headers are for humans and
   for filenames; they never reach the model. Never diagnose a generation failure by a word
   that appears only in a heading.
2. **Prompt length does not hurt reliability.** Across three batches the longest prompts
   were the most reliable. Trim for focus, never out of fear of length.
3. **A hard failure is usually still transient.** Re-run a failed item before rewriting it.
   Both hard failures in the case studies succeeded on re-run, one entirely unchanged.
4. **A near-null merge is a finding, not a failure.** Predict it, state it, ship it, and
   record whether the prediction held.
5. **Record the violations.** Every suspended rule in the case studies is written down with
   its reasoning. That is why those batches can be reasoned about now.

## Reference files

- **`references/collision-map.md`** — the three collision types, how to detect them, and the
  resolution doctrine. Read before designing any merge.
- **`references/merge-rule-tables.md`** — layer-ownership table format, the discard block,
  and the production-notes template.
- **`references/preflight-tests.md`** — the empirical tests to run before writing prompts,
  plus the downstream parser and filename constants.
- **`references/case-studies.md`** — the three proven merges in compressed form: what
  varied, what collided, how it resolved, what was predicted and what actually happened.
