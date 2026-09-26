# Pre-Flight Tests

Cheap empirical checks to run **before** writing a batch of prompts. Two of the three
case-study merges were saved by this step. All of them cost nothing — a throwaway file in
the scratchpad and a dry-run.

> **The governing principle: assume nothing about how a formatting convention survives the
> pipeline.** When the partner skill introduces anything the spine's format has not already
> proven — a different alphabet, a new label, an unusual heading shape — test it on three
> throwaway tracks before writing sixty real ones.

## 1. The non-Latin / special-character test

**Run whenever the partner names things in a non-Latin script, or with heavy punctuation.**

Slugifiers ASCII-fold. Folding handles accented Latin (`ö → o`) but has no mapping for
Cyrillic, Greek, CJK or similar — those characters are **stripped entirely**, and a heading
made only of them produces a filename with no words in it.

Write three variants and dry-run:

```markdown
### <Pure non-Latin title> — <LABEL> 1,204 (198X)
### <NON-LATIN> (Latin gloss) — <LABEL> 88 (198X)
### LATIN TRANSLITERATION «<non-Latin>» — <LABEL> 1,204 (198X)
```

> *Case-study result:* the pure-Cyrillic heading produced `01-1204-198x.mp3` — only the
> digits survived. The transliteration-first form produced
> `03-betonnoye-nebo-horizon-1204-198x.mp3`, complete and readable. **Rule adopted: the
> heading leads with the Latin transliteration**, with the original script riding along in
> guillemets (harmlessly stripped) and a gloss in parentheses.

## 2. The label-safety test

**Run whenever the partner skill offers an annotation convention the spine does not use.**

Downstream parsers recognise a fixed set of labels and hijack whatever follows them. A
partner convention that looks decorative may be one of them.

Put the candidate label on two throwaway tracks, dry-run, and check whether those tracks
come back tagged as carrying extra content.

> *Case-study result:* `**Sample:**` lore was **safe** — not in the recognised label set,
> and plain text rather than a fenced block, so it is ignored. `**Lyrics:**` from the same
> skill was **not** safe and was forbidden batch-wide.

## 3. The format-shape check

Confirm the spine's catalogue shape still parses once the partner's material is in it.
Count what the dry-run reports against what you intended:

- Item count matches the number of real entries — no template blocks leaking in
- Filenames are complete and readable
- No `[+lyrics]` / `[+structure]`-style tags on items that should carry neither

## 4. Downstream constants (music pipeline)

Verified across 150 tracks. Confirm they still hold if the pipeline changes.

| Constant | Value |
|---|---|
| Item boundary | `###` heading followed by a fenced code block |
| Blocks under `##` | Ignored — safe for command blocks, notes, templates |
| A `###` in a closing section | **Leaks an extra item into the run** |
| Whole-document code fence | Breaks parsing outright |
| Second fenced block under one `###` | Read as lyrics or structure |
| Slug rule | strip markdown/quotes, lowercase, ASCII-fold, drop thousands-commas, non-`[a-z0-9]` → single hyphen, cap 80 chars |
| Output folder | First **4** hyphen/underscore/space-separated words of the `.md` filename |
| Numbering | 1-based catalogue position, zero-padded; stable under `-Index`/`-Limit` |
| What is posted | **Only the fenced prompt.** Titles, notes and headers never reach the model |
| Forbidden labels | `Lyrics:` · `**Lyrics**` · `#### Lyrics` · `**Timed structure**` · `**Structure:**` |
| Forbidden by content | `[Verse]`/`[Chorus]`/`[Intro]` tags → lyrics; `[0:00]` timestamps → structure |
| Instrumental | No instrumental sentence in the prompt body; pass the producer's instrumental flag at run time |
| Full-song length | Lyria 3.5 renders about 3:00 regardless of the length requested (measured on 270 tracks) — write form, not duration, into longer pieces |

**Filename design follows from the folder rule.** Since the first four hyphen-words become
the audio folder, name catalogues `<batch>-<lane>-<album-slug>-...` and keep the album slug
at **two or more words**, or a filler word from the suffix leaks into the folder name.

## 5. Failure-mode constants

Also verified across 150 tracks, and they change how you read a run:

1. **Read the exit code, then the summary.** Since LyraProducer 2.0.1 the CLI exits `0`
   when no item failed (skips count as success), `2` when at least one item `FAILED` after
   its retries, and `1` when the run could not proceed (no key, bad path, unknown flag).
   Builds before 2.0.1 — including the one used for the case studies — exited `0` even when
   an item failed outright, so on an older build trust only the `Failed: N` line. On `2`,
   re-run the same command: skip-existing requests only the missing items.
2. **Transient failures are common and self-recovering.** ~12 occurrences in 150 tracks;
   most cleared inside the built-in retries.
3. **A "hard" failure — all retries exhausted — is usually still transient.** Both such
   failures in the case studies succeeded on re-run, one entirely unchanged. Some prompts
   simply need more attempts and take 2–3× the normal inference time. **Re-run with
   `-Index N` before rewriting anything.**
4. **Do not diagnose a failure from a word that appears only in a heading.** Only the
   fenced prompt is posted. One case-study misdiagnosis came from exactly this.
5. **Prompt length does not hurt reliability.** The longest prompts across three batches
   were the most reliable. Trim for focus, never out of fear of length.

## 6. Pre-flight checklist

```
[ ] Both skills read in full, including every reference file
[ ] Imperatives extracted from both and diffed
[ ] Collision type identified
[ ] Numeric ranges tabulated: overlaps, gaps, out-of-range
[ ] Non-Latin / special-character test run, if applicable
[ ] Label-safety test run, if the partner adds an annotation convention
[ ] Every pairing rated HIGH / MEDIUM / LOW, weakest named
[ ] Operator asked: variable, collisions, batch size, folder
[ ] Merge-rule table complete — no layer without an owner
[ ] Discard block written
```
