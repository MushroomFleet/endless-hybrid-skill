# Case Studies

Three real merges, 150 generated tracks, all accepted on listen. One per collision type.
Read these when you want to see the method land rather than be described — and note that
each one records a prediction that was tested, including the two that were wrong.

Common spine across all three: `endless-phonk67`, three lanes — `wave` 70–90,
`house` 112–125, `drift` 132–148. Downstream: `lyra-producer`, parser-native markdown.

---

## Case 1 — × `geinoh-instrumental` · mutual prohibition

**Partner:** a "future-ancient ecological symphony" skill — gamelan tonality, paired-detuned
metallophones, low-horn drone floor, wordless choir, biophony as compositional material.

**The collision.** Geinoh's exclusion list forbade `four-on-the-floor`, `modern trap`,
`drum-kit backbeat`, `rap` and `lo-fi hip-hop` — a near-complete inventory of the spine's
rhythm section. It also demanded `instrumental, no sung lyrics, no spoken word` inside every
prompt, against the spine's flag-based doctrine.

**Resolution.** Geinoh's exclusion list **discarded wholesale**. The spine kept
drums/808/damage; geinoh took tonality, timbre, choir, biophony and construction. Three
things discarded rather than merged: the exclusion list, geinoh's mandated instrumental
sentence, and the spine's own Russian spoken-word option (geinoh bans spoken word, and the
agreed vocal rule was chops *and* choir, not a third layer).

**Variable: blend ratio** — 70/30 phonk-led → 50/50 → 30/70 partner-led. Viable precisely
*because* the two are audibly distinct. **One shared world** (a flooded motorway interchange
reclaimed by forest) held constant so the ratio was isolated.

**Graded parameter.** Damage intensity scaled with the ratio: heavy → moderate → light,
none clean. Necessary because geinoh wants high-fidelity air and the spine demands
degradation; both cannot be maximised.

**Outcome.** 30/30. Operator confirmed the ratio was audible as designed.

**Transferable:** when the partner's exclusions target the spine's structural core, discard
them completely and give the partner full ownership of everything above that layer.

---

## Case 2 — × `endless-phonk` · convergent

**Partner:** a phantom-mixtape skill in the *same genre* — six producer archetypes, a tape
archive fiction, 70–200 BPM.

**The collision: none.** Both demanded mandatory damage, a mandatory cowbell in the drift
lane, "the vocal is a sample, never a singer", and the same prompting philosophy. Diffing
the imperatives produced almost nothing.

**Resolution.** With nothing to reconcile, the merge had to come from the partner's
**distinct layer** — its fiction. Three phantom producers, three tape series, volume
counters from VOL. 3 to VOL. 1,207, 199X datestamps, citations carried into the filenames.

**Variable: archetype pairing** — each lane crossed with the archetype sitting on its band.
A blend ratio was explicitly rejected here: **a ratio between two skills in the same domain
is inaudible.**

**Pairing ratings, predicted before spending:**

| Pairing | Rating | Reasoning |
|---|---|---|
| wave × Screwed Cruiser | **HIGH** | promotes the screwed vocal smear from texture to *melody* — something the spine's wave lane never does |
| house × Memphis Basement | **MEDIUM** | real collision: halftime archetype vs four-on-the-floor lane, overlapping only 112–120 |
| drift × Drift Engine | **LOW** | near-identical vocabulary; only the fiction differs |

**Outcome.** 30/30, all accepted. The LOW prediction held — and shipping it was still
correct.

**Transferable:** the convergent type is the dangerous one because it feels easy. Rate the
pairings honestly *before* spending, and let a weak pairing be a stated finding.

---

## Case 3 — × `endless-russianwave` · single-point

**Partner:** an Eastern European post-punk / Soviet-wave skill — six band archetypes,
Cyrillic naming, magnitizdat tape archive, 110–160 BPM.

**The collision.** Everything agreed except one absolute: the partner pins a *deep deadpan
baritone male singer* in every prompt, with optional Russian lyric blocks. The spine project
was instrumental-only.

**Resolution: the seam.** Before overriding either law, look for where the two already
touch. The spine's own promptgen spec asked for a **"cinematic Russian spoken-word sample"**
in its drift lane — so the baritone became a *pitched-down spoken-word sample buried in
cavernous reverb*, satisfying the partner's demand for the voice and the spine's prohibition
on singing, by a route both skills already endorsed. Lyric blocks forbidden batch-wide, as
both a doctrine violation and a parser hazard.

**Range analysis — the finding that shaped the batch.**

```
wave   70-90    ↔  NOTHING          partner floor is 110 — a 20 BPM dead zone
house  112-125  ↔  Chapel / Red Synth-pop / Factory Fringe   clean
drift  132-148  ↔  Courtyard Anthem / Rooftop Guitar         clean
   —            ↔  Doomer Discotheque 148-160                above every lane
```

**Variable: band archetype**, six of them, so the three lanes were *reused* — 1 wave,
2 house, 3 drift. Deliberately arranged to test **stretch in both directions**: the
pad-led Chapel pulled 30+ BPM below its floor, the Doomer Discotheque pushed 12 above the
spine's ceiling.

**Graded violation.** The spine's drift-lane cowbell law withdrawn **3 / 4 / 0** across the
three drift albums as each archetype brought its own lead and left less room for it.

**Pre-flight test that saved the batch.** The Cyrillic slug test — see
`preflight-tests.md` §1. Without it, every track would have landed as `01-1204-198x.mp3`.

**Outcome.** 60/60. Two same-lane albums with opposite temperatures (Red Synth-pop vs
Factory Fringe) were the cleanest demonstration that the archetype axis does real work.

**Transferable:** always look for a seam before overriding; always tabulate ranges and
report gaps *and* out-of-range modes rather than silently dropping them.

---

## The two predictions that were wrong

Recorded because they are the most instructive part of the record.

**1. "Longer prompts will fail more."** Predicted before case 1's generation. The opposite
held across all three batches — the longest prompts were the most reliable.

| Batch | Prompt length | Retries | Hard failures |
|---|---|---|---|
| spine only | 300–390 | 4 / 30 | 1 |
| case 1 | 384–488 | 2 / 30 | 0 |
| case 2 | 384–474 | 1 / 30 | 0 |
| case 3 | 423–590 | 5 / 60 | 1 |

**2. "The two hard failures were content refusals."** Both looked deterministic — three
attempts, no recovery, neighbours fine — and each carried one loaded word its neighbours
lacked. The story collapsed on testing:

- One failure's suspect word appeared **only in the title**, which is never posted.
- The other was retried **with the suspect word removed** and still failed an attempt.
- Retried **unchanged**, it succeeded on the third attempt — exactly where the original run
  had run out.

Both were transient, on prompts needing 2–3× normal inference time. **Re-run before
rewriting.** The generalisable lesson: an opaque error code invites over-explanation, and a
plausible content-based story is easy to build and hard to resist. Test it before recording
it as a finding.
