# Topics

Where each topic lives. Owned by `/organize`; `/integrate` appends to it.
What earns a chapter, a section and a subsection: `.claude/ORGANIZATION.md`.

<!-- INFERENCE, not a plan, and open for the next run to disagree with. 21-602 runs in
     Fall 2026. Chapter 1 is one long chapter of groundwork shaped as a ladder up the
     V-hierarchy: the axioms that license the construction, the objects it needs
     (transitive sets, ordinals), the hierarchy itself, the two classes that let us talk
     about it as a whole (OR and WF, ending in Foundation iff V = WF), then how big its
     levels are.

     Chapter 2 leaves the ladder and generalizes. Its objects are class relations rather
     than membership, and its title names machinery -- induction, recursion, collapse --
     rather than more hierarchy. Two of the three have now been delivered (the theorem
     schemes for proofs by induction and definitions by recursion along a well-founded
     set-like class relation); "Collapse" is still to come, and the general Mostowski
     Collapse Theorem promised in 1.2.2 is the obvious candidate. So the notes read as
     groundwork and then tools, an order nobody planned but a sensible one.

     An earlier version of this note predicted chapter 2 would be Gödel's L. It was wrong
     about the order, not the destination: L is still promised by chapter 1's opening
     prose and still wants a chapter of its own when it arrives, and the tools chapter 2
     is assembling are what a construction like L needs. Chapter 1 stays the recap it
     says it is. -->

## 1. A Recap of Undergraduate Set Theory  ->  `Chapters/1_Intro/`

The chapter file carries the intro prose, the chapter-wide `boxnotation` for
`ZFC`/`ZF`/`-F`, a one-line `boxnotation` for `dom(f)` (added 2026-09-05 at the
author's request), and the chapter-wide `boxconvention` that `sup` means "union over".

```
1.1 The Zermelo-Fraenkel Axioms and the Axiom of Choice      [date not recorded]
    The axioms, stated one at a time and discussed, with     1_1_ZFC.tex
    the empty set and omega derived along the way.
    1.1.1 Extensionality        1.1.6 Replacement
    1.1.2 Comprehension         1.1.7 Foundation
    1.1.3 Pairing               1.1.8 Choice
    1.1.4 Unions                1.1.9 Infinity
    1.1.5 Power Sets

1.2 Transitive Sets                                          [date not recorded]
    The objects the hierarchy is built out of, and the       1_2_Trans.tex
    sense in which the ordinals exhaust the well-orderings.
    1.2.1 Ordinals
    1.2.2 Mostowski Collapse

1.3 The $V$-Hierarchy                                        [date not recorded]
    The hierarchy itself, what ZFC is a description of,      1_3_V_Hierarchy.tex
    and why its first infinite level is a set at all.
    1.3.1 The Existence of $V_{\omega}$

1.4 Classes                                                  [date not recorded,
    What a proper class is and why the axioms need one,       extended 2026-08-31,
    then the two the course actually uses, and what the       2026-09-02]
    second of them says about Foundation.                    1_4_Classes.tex
    1.4.1 The Class of Ordinals
    1.4.2 Well-Foundedness                                   [+ 2026-08-31]
          WF, rank, and the properties of rank: the
          membership criterion, the strict drop on
          members, the Rank Formula, rank(b) = b for
          ordinals, and V_b cap OR = b.
    1.4.3 Well-Foundedness of Membership                     [2026-09-02]
          Well-founded class relations in general; (A, in)
          is well-founded for A in WF; the transitive
          closure and its construction in omega steps; a
          transitive set with well-founded membership is in
          WF; and, over ZF - F, Foundation iff every (A, in)
          is well-founded iff V = WF.

1.5 Cardinals and the Axiom of Choice                        [2026-08-31,
    How big the levels of the hierarchy are, and how much     extended 2026-09-02]
    of the answer needs choice. Walks to the aleph and       1_5_Cardinals.tex
    beth hierarchies, of which exactly one is choice-free,
    then sizes every level from V_omega on by the second.
    1.5.1 The Size of $V_{\omega}$
    1.5.2 Cardinality Without Choice
    1.5.3 Cardinal Successors
    1.5.4 The Alephs and the Beths                           [+ 2026-09-02]
          |V_{omega + eta}| = beth_eta (with AC); the
          aleph/omega notation warning; omega + eta = eta
          for eta >= omega^2 (without AC).
```

`Chapters/1_Intro/` is the author's directory name for chapter 1 across three of the
four sibling repositories, whatever that chapter is titled. It is a convention, not
template residue. Leave it.

## 2. Induction, Recursion and Collapse  ->  `Chapters/2_Induction/`

Opened on 2026-09-02 at the author's own `\chapter` heading, written live with the
note "not sure if this should be a new chapter, but perhaps it should? it's another
instalment of the course". It is: the objects are class relations in general, the
vocabulary (set-like, and the well-foundedness carried over from 1.4.3) is new, and the
title promises a development -- induction, recursion, collapse -- that is not chapter 1's
recap. The chapter file carries two sentences of intro prose and nothing chapter-wide.

The opening was finished on 2026-09-05: `Chapters/2_Another Chapter/` gave up the number
2 (it is now `Chapters/3_Another_Chapter/`, still commented out in `main.tex`), and the
inbox moved to `Chapters/2_Induction/todays_lecture.tex`, `\input` at the end of the
chapter file. **That is the path to type into from now on.**

```
2.1 Induction and Recursion                                  [2026-09-02,
    What a class relation has to look like for induction     2026-09-05]
    and recursion along it to work, and the two theorem      2_1_Induction_Recursion.tex
    schemes that say they do.
    2.1.1 Set-Like Relations                                 [2026-09-02]
          The definition; membership is set-like on every
          class (and this is Comprehension in disguise);
          OR with 0 moved to the top is not.
    2.1.2 Proofs by Induction                                [2026-09-05]
          A nonempty subclass of A has an R-minimal member
          (via the R-closure of a singleton), and the
          theorem scheme for induction along R.
    2.1.3 Definitions by Recursion                           [2026-09-05]
          The theorem scheme for recursion along R, the
          warning that "there is a class function" is not
          a sentence of set theory, approximations, the
          proof, and the lemma that G(x) = s is first-order.
```

## Deliberate deviations

```
1.3 has one subsection.                     Four of the corpus's 66 sections have
                                            exactly one, so this is inside the range
                                            rather than a violation, but it is thin.
                                            Ends when the course returns to the
                                            hierarchy -- the relativisation of V to
                                            L is the obvious occasion -- or if 1.3
                                            merges into 1.2. Do not force a second
                                            subsection out of the material that is
                                            there: the definition, the monotonicity
                                            and "what ZFC describes" are one idea.

Chapter 2 has one section.                  Set-like relations, induction and recursion
                                            are one line of enquiry with one
                                            destination (the recursion theorem), so
                                            they are one section; the author's own live
                                            heading put set-like relations at
                                            subsection level, which is where they now
                                            sit. A chapter with too few sections
                                            self-heals: "Collapse" is the next section
                                            when the lecture supplying it arrives.
                                            [2026-09-05]

1.2 is short (40 lines) against a           It is two nameable ideas and the author
corpus median of 148.                       named them. Splitting or padding it would
                                            be size-driven, which ORGANIZATION.md
                                            forbids. No condition: this is simply
                                            where the material stopped.

1.4 is long (about 330 lines) against a     Re-read on 2026-09-05 and left as one
corpus IQR of 99-229.                       section: its destination is the two classes
                                            the course uses, and 1.4.3 is the payoff of
                                            the second of them (WF) rather than a new
                                            question. Ends if a later lecture adds
                                            material about WF that is not about
                                            Foundation, at which point 1.4.2-1.4.3 want
                                            a section of their own.
```

## Signposted

Topics a lecture pointed at without reaching. Not sections, and not to be promoted to
sections until a lecture supplies content.

```
Gödel's constructible universe L, and a model of ZFC in which CH holds.
    Promised in the chapter 1 intro prose, "something we will explore in great
    detail in this course". [date not recorded]

The general Mostowski Collapse Theorem, dropping the well-ordering requirement
and replacing "ordinal" with "transitive set".
    Stated as the generalization in 1.2.2. [date not recorded]
    Chapter 2's title, "Induction, Recursion and Collapse", says it is coming, and
    the recursion theorem of 2.1.3 is the tool it needs; nothing about it has been
    written yet. [2026-09-02, 2026-09-05]

Formalizations of set theory inside models of set theory, and the internal
versus external perspective. "At some point, we will study these things in
detail", in 1.4. [date not recorded]

Consistency of ZF + "there is a countable union of pairs with no cardinality".
    Asserted, not proved, in 1.5.2. [2026-08-31]
```

Reached, and so no longer signposts: Foundation iff V = WF (promised in 1.4.2, proved
in 1.4.3 on 2026-09-02); induction and recursion along well-founded set-like class
relations (promised by chapter 2's title on 2026-09-02, delivered in 2.1.2-2.1.3 on
2026-09-05).

## Unplaced

Nothing.

One gap rather than an unplaced item: the lecture of 2026-08-31 breaks off mid-sentence
at "It's clear", just after the alephs and the beths are defined. It sits at the end of
1.5.4 as a `\sorry` with a comment, rather than guessed at, because more than one
continuation is plausible. Awaiting the author.

## Structural pressure

What a run noticed but was not allowed to fix. Each entry is a standing recommendation.

Discharged on 2026-09-05, with the run that did it: the two directories numbered 2 and
the inbox stranded in chapter 1 (phase 5 of the post-lecture pass, per the "Opening a
new chapter" procedure); the stale inference note (rewritten above); the two `% [SUSPECT]`
flags in 1.4 and the chapter 1 intro and the two source defects in 1.4 (all adjudicated
and corrected by the whole-document check-correctness sweep, each with a `% [CORRECTED]`
marker quoting the original); the missing `\crefname` for the `zfcaxiom` environment
(declared in `TeX_Setup/environments.tex`, so `\Cref` to an axiom now prints "ZFC Axiom"
and multiple references no longer print `??`).

```
The course itself is not written up.        Chapter 1 is undergraduate revision and
                                            chapter 2 its first tools; the material
                                            21-602 is heading for -- L, and whatever
                                            follows -- has no home yet. Whether that is
                                            a gap or simply where the notes have got to
                                            is the author's to say, and not something
                                            /organize can fix by rearranging what
                                            exists.

One % [CLAUDE] directive outstanding.       1_1_ZFC.tex, in 1.1.6: "draw a diagram for
                                            this", on the Axiom of Replacement. A figure
                                            to be drawn. Run /address-comments.

One empty % [CLAUDE] marker.                2_1_Induction_Recursion.tex, in the
                                            statement of the recursion theorem, just
                                            before its display. It names no task, so no
                                            pass can act on it; the author should say
                                            what was meant or delete it. [2026-09-05]

"R-closed" and "R-closure" are used but     2.1.2 defines the R-closure of a set by its
never defined in a box.                     construction inside a proof, and 2.1.3
                                            glosses "R-closed" inline in the definition
                                            of an approximation. STYLE.md wants a term
                                            used across several results introduced in a
                                            boxdefinition. Supplying one is mathematics
                                            the lecture did not write, so it is not
                                            /organize's; a % [CLAUDE] directive from the
                                            author would let /address-comments do it.
                                            [2026-09-05]
```

## Template scaffolding

Placeholder content from [Lecture-Notes-Template-2026][tpl], still standing.

```
Chapters/3_Another_Chapter/      placeholder chapter, two placeholder sections, still
                                 carrying the template's titles. Nothing has displaced
                                 its content, so nothing has been deleted -- but its
                                 \input in main.tex is commented out, because until
                                 2026-08-31 it rendered in the published PDF as a
                                 chapter called "Another Chapter" with a section called
                                 "Another Section". Renumbered from 2 to 3 on
                                 2026-09-05, when the real chapter 2 needed the number;
                                 the space in the old directory name went with it. It
                                 takes the next free number again if a real chapter 3
                                 arrives. [2026-08-31, renumbered 2026-09-05]
Chapters/Appendices/             placeholder, \input commented out in main.tex
```

Clearing either is `/organize`'s, and only once the author confirms nothing is planned
for them. Three of the four sibling repositories keep an `Appendices/` directory, two of
those with the `\input` still commented out, so leaving that one standing is in keeping
rather than an oversight.

[tpl]: https://github.com/thefundamentaltheor3m/Lecture-Notes-Template-2026
