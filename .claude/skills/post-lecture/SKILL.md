---
name: post-lecture
description: Everything that needs doing after a lecture, in one pass and one pull request — fill the `\sorry` gaps, address the `% [CLAUDE]` directives, check the mathematics for correctness, convert spellings to American, open the chapter the lecture started if it started one, and integrate the result into the chapter structure. Works out which material is the latest lecture's from the git diff. Use when the user says "/post-lecture", "do the post-lecture pass", "process today's lecture", "I've just finished a lecture", or otherwise asks for the whole after-lecture routine rather than one part of it.
---

# The post-lecture pass

Five things need doing after every lecture, and a sixth after the lectures that start
a new chapter. Doing them separately means a branch, a pull request and a review for
each, for one lecture's worth of work. This skill runs them all on one branch and
opens one pull request.

**It is a composition, not a skill with a scope of its own.** It adds no rules about
how to write, what mathematics to work out, where material goes, or which spellings
are house style — each component skill owns that, and duplicating any of it here would
just create two copies to drift apart. Read each component skill when you reach its
phase and follow it as written. The only things this file decides are what counts as
this lecture's material, which phases run and in what order, the branching, and how
the phases report.

## The phases, and why in this order

| | Phase | Skill |
| --- | --- | --- |
| 1 | Fill the marked gaps | `.claude/skills/fill-sorries/SKILL.md` |
| 2 | Address the inline directives | `.claude/skills/address-comments/SKILL.md` |
| 3 | Check the mathematics | `.claude/skills/check-correctness/SKILL.md` |
| 4 | Convert spellings | `.claude/skills/americanise/SKILL.md` |
| 5 | Open the chapter the author started, if they started one | `.claude/skills/organize/SKILL.md`, **Opening a new chapter** |
| 6 | Integrate the new material | `.claude/skills/integrate/SKILL.md` |

The order is not arbitrary and should not be rearranged. The shape of it is: **write
the material, then check it, then tidy it, then build the shelf, then put it on the
shelf** — every phase that produces text runs before every phase that inspects text,
and the two structural phases go last because they should be housing finished passages
rather than half-finished ones.

**`/fill-sorries` goes first** because it writes the most and reaches the furthest. It
is authorized to reshape the passage it is filling — split a proof into a lemma, add
an example, promote a remark — and doing that after the other phases have worked over
the same passage would waste their work and strand their edits. It also runs while the
lecture's own context is still intact and in one place, which is exactly what a
half-written argument needs to be reconstructed.

**`/address-comments` goes second**, on arguments that are now complete. A directive
like "finish proof using previous lemma" reads very differently before and after the
gap two lines above it has been closed.

> Where a `% [CLAUDE]` directive sits on the same gap as a `\sorry` — a marker with
> "prove this" written beside it — **the directive wins and phase 1 leaves it alone.**
> A scoped instruction the author wrote by hand is `/address-comments`' job, as
> `fill-sorries/SKILL.md` says itself. Phase 1 fills the bare markers; phase 2 fills
> the ones that came with instructions.

**`/check-correctness` goes third**, once every word this lecture is going to acquire
has been written. It checks the author's raw notes *and* what phases 1 and 2 wrote,
which is the point of putting it after them: the passages this run generated are new,
unreviewed mathematics and want checking more than the settled notes do. It also runs
while the material is still in lecture order and in one place, so a statement and the
argument that depends on it are still adjacent.

**`/americanise` goes fourth**, so that it catches the prose of all three phases
before it. The author writes British English by habit and the raw notes need
converting; phases 1 through 3 also write prose, and sweeping first would miss every
word of it.

**Phase 5 usually does not run at all**, and when it does, it runs *before* the
integration rather than after. The author sometimes writes a `\chapter{...}` heading
live, mid-lecture. When they have, the chapter they started should exist as a real
directory before `/integrate` starts placing sections, so that this lecture's material
is written into it rather than written into chapter 1 and moved out again a phase
later. What that involves, and the one condition under which it fires, is
[below](#when-the-lecture-opens-a-new-chapter).

**`/integrate` goes last.** Everything it moves is by then finished, checked and
correctly spelled, which is a much better thing to redistribute than raw notes. The
cost is that the linking prose `/integrate` writes itself never sees the spelling
sweep — so **phase 6 writes American spellings directly** (`STYLE.md` requires it
anyway), and the verification step below re-greps the diff for British spellings as a
cheap backstop. Do not "fix" this by running `/americanise` again as a
seventh phase: one spelling commit per lecture, and a handful of words caught in the
final grep.

## Finding the latest lecture

Every phase here is scoped to **one lecture's material**, and working out which
material that is happens once, up front, before phase 1 starts.

**The git diff is the source of truth.** `/integrate` carries the full procedure —
establish a watermark, take the diff from there to `HEAD`, and take the union with the
uncommitted working tree — and it is worth reading before you start rather than
reinventing it. The short version:

```bash
git log --oneline -- TOPICS.md                    # the last integration pass
git log --oneline -20 -- Chapters/ TeX_Setup/     # the rhythm of raw arrivals
git diff <watermark>..HEAD -- Chapters/ TeX_Setup/
git status --short && git diff -- Chapters/ TeX_Setup/   # not yet committed
```

**The author's own markers narrow it.** Raw notes usually carry something that says
where the lecture starts — a leading `% 26 Aug 2026`, a `\subsection{Ramsey Numbers}`
written live, the reusable inbox at `Chapters/1_Intro/todays_lecture.tex`. Use them,
because they are the only thing that can separate two lectures that arrived inside one
diff window, and because the date on one is the sharpest indicator of which lecture
this is. But use them **as corroboration, not as the definition**: they are
conventions the author may not have followed today, and material typed without one is
still this lecture's material. Where a written date and the commit date disagree, ask
— one of them is a typo and guessing picks the wrong one.

Write the scope down as a list of files and line ranges, and **give the same scope to
every phase.** This is the one thing this file adds to the component skills, and it
matters, because three of them will otherwise take the whole document: `/fill-sorries`
sweeps every `\sorry` in the repository, `/address-comments` every directive,
`/americanise` every British spelling. Under `/post-lecture` all three are confined to
this lecture. A marker from three lectures ago that nobody has closed is not this
run's business; note it in the report and leave it.

Two exceptions, both narrow. `/check-correctness` follows a correction into an earlier
section when the passage it is checking depends on one — a `\Cref` pointing at the
wrong result, a definition that contradicts this lecture's use of it. And `/integrate`
necessarily writes into the sections it places material in. Neither licenses a general
sweep of settled notes.

## When the lecture opens a new chapter

`/integrate` may create a section or a subsection and nothing larger. Opening a chapter
renumbers every result under it, so `ORGANIZATION.md` puts it out of scope and tells
`/integrate` to record the pressure and recommend `/organize` instead.

That is the right rule for a chapter *you* think is earned. It is the wrong rule for
one the **author** opened, and the difference matters, because a `\chapter{...}` typed
live mid-lecture is not a considered structural decision — it is an ad-hoc choice made
at speed, and it comes with a claim on this pass either way:

- **If you agree with it**, the chapter exists from that moment, and it needs a
  directory, a chapter file, a line in `main.tex` and the files that belong in it.
  Agreeing and then not building it leaves the heading stranded in the middle of the
  previous chapter's last section, which is how the published PDF renders it until
  somebody runs `/organize`.
- **If you disagree with it**, say so and fold the material into the chapter it
  belongs in, exactly as you would overrule any other live heading. `/integrate`'s
  **The author's structure is a gift** governs how — never silently, always
  individually revertable.

What you may not do is the third thing: keep the author's heading, place the material
under it, and leave the structure it implies unbuilt. **An ad-hoc live choice is a
proposal to be adjudicated, not a fact to be preserved.** That applies to a
`\subsection{something}` typed as a placeholder just as much as to a `\chapter`, and
adjudicating it is integration's job rather than a later pass's, because the run that
places the material is the run that knows what the material is.

So there is a phase 5, and it fires on exactly one condition.

**The trigger is the author's own `\chapter{...}` heading in this lecture's material,
or an explicit instruction from them. Nothing else.** A chapter *you* judge to be
earned, over material the author did not open one for, still goes under
`## Structural pressure` in `TOPICS.md` with a recommendation to run `/organize`. A new
chapter is a bet on where the course is going, it is expensive to unwind, and this pass
does not place that bet on the author's behalf.

**The mechanics belong to `/organize`**, under **Opening a new chapter** in
`.claude/skills/organize/SKILL.md`: freeing the number if a template placeholder is
sitting on it, creating `Chapters/<N>_<Abbrev>/<N>_<Abbrev>.tex`, moving whatever
section files belong to the new chapter, rewriting the `\input` lines in both chapter
files and in `main.tex`, moving `todays_lecture.tex` into the chapter the course is now
in, and rewriting the `Ch<N>:` label prefixes and every `\Cref` to them. Follow it as
written; this file will not restate it. Two things are worth saying about running it
here rather than inside a full `/organize` pass:

- **Most of what moves is not this lecture's material.** Opened from a live heading,
  the new chapter is usually empty at phase 5 — its sections are about to be written by
  phase 6, straight into the directory you just made. The moves that do happen are the
  ones around it: the placeholder directory holding the number, and the inbox. Both are
  consequences of the chapter you just opened, so both are yours to finish, and neither
  is `## Structural pressure`.
- **Take that procedure and nothing else from `/organize`.** No re-diagnosis of the
  existing arrangement, no moving of settled material the new chapter did not take with
  it, no rewriting of the `TOPICS.md` outline. `/integrate` appends to `TOPICS.md` in
  phase 6, and the new chapter is one of the things it appends.

Commit it on its own — subject `Open chapter <N>: <title>` — because it is almost
entirely `git mv`s and `\input` lines, and the author should be able to read it apart
from the mathematics. Then quote their heading in the pull request body: the chapter is
theirs, and the diff should say so.

## One branch, one commit per phase, one pull request

Each component skill has its own "branch, commit, PR" step. **Those are overridden
here.** Do not create a branch per phase and do not open a pull request per phase.

```bash
git checkout -b post-lecture/<lecture-date>
```

Commit **once per phase**, with the phase named in the subject. A commit per phase
rather than one for the lecture, because the phases are very different kinds of change
and the author needs to tell them apart in review: what was invented to close a gap,
what was written to satisfy a directive, what was corrected, what is a cosmetic
spelling sweep, what is pure plumbing, and what merely moved. `/americanise` in
particular touches a lot of lines shallowly, and folded into one commit it would swamp
the changes that need real attention.

### The pull request opens after phase 3

`/check-correctness` requires a pull request to exist, because its two independent
review rounds happen on the review thread rather than in the report. So:

1. After phase 3's commit, push the branch and open the pull request **as a draft**.
2. Run `/check-correctness`'s two review rounds there, against the phase-3 commit,
   while that diff is still the head of the branch and still reviewable on its own.
   Waiting until the end would hand the reviewers a diff in which every corrected
   line had also been respelled and moved to another file.
3. Then carry on with phases 4 through 6 on the same branch.
4. Update the pull request body at the end (`gh pr edit --body-file`) so it covers
   every phase that ran, and mark it ready (`gh pr ready`).

If phase 3 corrected nothing, there are no review rounds and no reason to push early:
open the pull request at the end as usual.

## Phases that have nothing to do

Skip them. A lecture with no `\sorry` markers makes no phase-1 commit; a lecture whose
mathematics is clean makes no phase-3 commit; already-American spellings make no
phase-4 commit; a lecture that opens no chapter makes no phase-5 commit, which is the
ordinary case. Say so in the report. **Never create an empty commit to mark a phase
as having run**, and never manufacture work for a phase to justify its existence —
phase 3 finding nothing to correct is a good outcome, not a failed sweep.

If phase 6 finds nothing new at all, then there was no lecture to process: stop, say
so, and do not open a pull request.

## When a phase cannot finish

Do not abandon the run. Complete the phases that can be completed, and be exact in the
report about what was left and why. A lecture where the gaps were filled, the
directives addressed, the mathematics corrected and the material integrated, with one
`\sorry` left open and two suspect statements flagged, is a good outcome; a lecture
where nothing happened because one directive was unclear is not.

The component skills each say when to stop and ask rather than guess — an ambiguous
`% [CLAUDE]` directive, two readings of a `\sorry`, a statement that is wrong in a way
you cannot fix, a date that disagrees with the commit. Honor that, but **batch it**:
gather the questions and ask them together, at the end, rather than interrupting five
times.

## The approval gate

`/integrate` says to produce a plan and stop for confirmation before writing anything.
That gate exists because placement is editorial judgment and the author is the editor.

When `/post-lecture` is invoked as a single autonomous pass, you cannot stop for it.
`/integrate` already provides for this: say plainly that you are proceeding without
approval, apply the plan, and put the full plan and its rationale in the commit message
and the pull request body instead. The pull request *is* the approval step — which is
why the placement rationale and every overruled heading of the author's have to be
legible there, not merely implied by the diff.

If the author is present and interactive, prefer the gate: show the plan after phase 4
and wait. Where phase 5 is going to open a chapter, that belongs in the same plan —
it is the largest structural claim the pass makes, even when it is only executing a
heading the author wrote themselves.

**Phase 3's gate is not waivable in the same way.** Its adjudication step — an
independent agent per candidate correction — and its two review rounds are not
approval checkpoints that an autonomous run may skip; they are how the phase works.
An autonomous `/post-lecture` run does all of it.

## Verify once, at the end

Each phase has its own checks; run them. But the build is what matters and it only
needs to pass once, on the final state:

```bash
latexmk -pdf -outdir=TeX_Outputs main.tex
```

Read the log for undefined references and duplicate labels, refresh the committed
`TeX_Outputs/main.pdf`, and confirm the inbox came out as `/integrate` requires. Then
two closing greps over the branch diff:

```bash
git diff main...HEAD -- '*.tex' | grep -nEi '\+.*(colour|neighbour|\wis(e|ing|ation)\b|centre|analyse|labelled|whilst)'
git diff main...HEAD -- '*.tex' | grep -n '^\+.*\\cref{'
```

the first for British spellings phase 6 introduced after the sweep, the second for the
lowercase `\cref` that appears nowhere in these notes.

If phase 5 ran, also run the chapter-plumbing checks from step 7 of `/organize` —
duplicate directory numbers, every `\input` resolving, no orphaned file under
`Chapters/`, label prefixes matching their chapters, and the inbox sitting in the
chapter the course is now in. A half-opened chapter compiles perfectly well, so the
build will not catch it.

## Report back

One report, one section per phase that ran, in phase order — each as its component
skill specifies, so nothing about what to report is decided here. Then, across the
whole run:

- **What you took to be this lecture's material, and how you identified it** — the
  watermark, the commits and unstaged hunks, and which in-file marker or date
  corroborated it. If the signals disagreed, say how you resolved it.
- **Which phases ran and which were skipped**, with why.
- **Everything batched for the author**: questions, ambiguities, anything flagged.
- **The corrections and the flags**, hoisted from the phase-3 section, together with
  the outcome of the two review rounds. This and the item below are the two places
  where your judgment overrode the author's, and they should not have to be dug out
  of the middle of a six-part report.
- **The overruled structure**, hoisted from the phase-6 section. It is the single most
  likely thing to want reverting. Every live heading of the author's that this pass
  kept, changed, dropped or promoted to a chapter goes here — including the ones you
  agreed with, since agreement is a judgment too and they wrote the heading in a
  hurry.
- **The chapter, if phase 5 opened one**: their heading quoted, its directory, what
  moved into it, what the placeholder it displaced was renamed to, and where the inbox
  now lives.
- **Markers left in the notes** — `\sorry` you could not close, `% [SUSPECT]` you
  flagged, and any out-of-scope marker from an earlier lecture you deliberately left.
- The build result.

## What this skill deliberately does not include

- **`/organize`.** That is the periodic restructuring pass over the notes as a whole,
  not a per-lecture chore. `/integrate` records structural pressure in `TOPICS.md`
  when it sees it; `/organize` gets run when that has accumulated. Restructuring
  renumbers every result under the heading it touches, and that belongs in a diff of
  its own rather than at the end of a routine pass.

Phase 5 borrows exactly one procedure from `/organize` — **Opening a new chapter** —
and only to build the chapter the author themselves opened. That is housekeeping caused
by this lecture, not a restructuring of the notes as they stand, and it does not license
any of the rest: the omission above is not an oversight, so do not helpfully add it.
