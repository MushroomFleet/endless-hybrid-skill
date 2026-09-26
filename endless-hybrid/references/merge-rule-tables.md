# Merge-Rule Tables

The artifact that turns a merge from a vibe into a design: a table naming who owns every
layer, a block listing what was discarded, and the production-notes template that carries
both into the record.

## 1. Why a table and not a paragraph

Prose lets you avoid deciding. "Geinoh brings the atmosphere and phonk brings the energy"
sounds like a design and specifies nothing — when you sit down to write track four, you
still do not know whose bass it is.

A table forces a decision per layer and makes gaps visible: **a layer with no owner is an
unfinished merge.** It is also the document a later reader uses to understand why the batch
sounds the way it does.

## 2. Enumerating the layers

Break the medium into layers fine enough that each has exactly one natural owner. For music
prompts, the proven set:

| Layer | Typical question it answers |
|---|---|
| **Rhythm section** | kick pattern, hats, snares, fills |
| **Low end** | bass character, sub weight, sidechain behaviour |
| **Lead / hook** | which instrument carries the melody |
| **Harmony / pads** | what sits behind the lead |
| **Tonality** | scale system, tuning, microtonality |
| **Vocal treatment** | sample, singer, wordless, absent |
| **Production damage** | saturation, distortion, hiss, bitcrush, reverb character |
| **Spatial character** | room size, width, placement |
| **Atmosphere / imagery** | mood register and the concrete image |
| **Fiction / naming** | titles, conceit, catalogue grammar |
| **Structure / arc** | how the set or the track is ordered |

For a non-music merge, derive the equivalent list from the two skills' own section
headings — both skills will already have decomposed their medium, and the union of their
decompositions is your layer list.

**A layer may be shared**, but only where sharing is a real technique rather than an
unmade decision. "Both, sharing the low end — the partner's bamboo sub doubling the spine's
808" is a decision. "Both" alone is not.

## 3. The table format

```markdown
| Layer | Owner | Note |
|---|---|---|
| Rhythm section | **spine** | four-on-the-floor / half-time per lane |
| Low end | **spine**, shared | 808 weight; partner's sub doubles rather than replaces |
| Lead / hook | **partner** | archetype's own lead instrument |
| Tonality | **partner** | non-equal-tempered, applied to the spine's riffs |
| Vocal treatment | **negotiated** | see collision map — routed through the seam |
| Production damage | **spine** | intensity scales with the batch variable |
| Fiction / naming | **partner** | the layer carrying a convergent merge |
```

Then, immediately after, the discard block — **always present, even if empty**:

```markdown
**Discarded rather than merged**
1. <rule> — from <skill>. <Why. What it would have cost to honour it.>
2. ...
```

Three worked examples, one per collision type, are in `case-studies.md`.

## 4. Production-notes template

One notes file per batch, alongside the catalogues. Fill every section with specifics.

```markdown
# <Batch name> — Merge & Production Notes
*<Skill A> × <Skill B>. <N> albums, variable: <what changes>.*

## 0. What this experiment is
The two skills, the variable, and what is held constant. State the batch table:
album → pairing → lane/band → stretch (if any). One sentence on why this variable
and not another.

## 1. The collision
Type, the contested layers, and how each resolved. If a seam was used, name it and
show that both skills already endorsed that route. If an exclusion list was discarded,
say which and what honouring it would have cost.

## 2. The merge-rule table
The layer-ownership table, then the discard block.

## 3. Pairing value assessment (predicted before generation)
| Pairing | Rating | Why |
|---|---|---|
Include the weakest explicitly. After the batch is heard, add a line recording
whether each prediction held — that is what makes the next merge better.

## 4. The graded parameters
Any rule withdrawn by degrees across the batch, as a table with the gradient and the
reason for each step. Also any parameter that scales with the variable.

## 5. Knowing violations
Every rule from either skill that was suspended, with reasoning. This section exists
so a later reader can tell a decision from a mistake.

## 6. Doctrine carried unchanged
What was NOT negotiated — the constants inherited from the downstream pipeline
(output format, flags, forbidden labels) and from either skill.

## 7. QC checklist
- [ ] All catalogues dry-run clean, correct counts, no parser-hazard tags
- [ ] Every filename readable (no stripped-character stubs)
- [ ] <batch-specific checks, one per designed contrast>
- [ ] Spot-listen one item per album before accepting

## 8. Provenance and expansion
Source skills and their reference files; sibling batches; what went untested on
either side and what it would take to cover it.
```

## 5. The three rules that keep the table honest

1. **Every layer gets an owner.** No blanks. A blank is an undecided merge that will be
   decided ad-hoc, differently, on every track.
2. **"Shared" needs a mechanism.** Name how the two occupy the layer together.
3. **The discard block is never empty in a mutual-prohibition merge.** If you think it is,
   you have not read the exclusion lists properly.
