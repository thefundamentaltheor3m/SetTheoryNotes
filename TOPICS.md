# Topics

Where each topic lives. Owned by `/organize`; `/integrate` appends to it.
What earns a chapter, a section and a subsection: `.claude/ORGANIZATION.md`.

<!-- INFERENCE, not a plan, and open for the next run to disagree with. 21-602 ran in
     Fall 2026. What is written reads as one long chapter of groundwork, and the shape it
     has settled into is a ladder up the V-hierarchy: first the axioms that license the
     construction, then the objects the construction needs (transitive sets, ordinals),
     then the hierarchy itself, then the two classes that let us talk about it as a whole
     (OR and WF), then how big its levels are.

     Where that is heading is legible from the chapter's own opening prose, which promises
     Gödel's constructible universe L and a model of ZFC in which CH holds. Nothing about
     L has been written up yet. When it is, it will be a chapter of its own rather than a
     section of this one: it introduces its own objects and its own vocabulary, and the
     prose already treats it as the destination of the course. Chapter 1 stays the recap
     it says it is.

     This is the first run of /organize over these notes. The previous version of this
     file recorded the structure as observed and unreviewed; it has now been reviewed. -->

## 1. A Recap of Undergraduate Set Theory  ->  `Chapters/1_Intro/`

The chapter file carries the intro prose, the chapter-wide `boxnotation` for
`ZFC`/`ZF`/`-F`, and the chapter-wide `boxconvention` that `sup` means "union over".

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
    then the two the course actually uses.                    2026-09-02]
                                                             1_4_Classes.tex
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
    beth hierarchies, of which exactly one is choice-free.
    1.5.1 The Size of $V_{\omega}$
    1.5.2 Cardinality Without Choice
    1.5.3 Cardinal Successors
    1.5.4 The Alephs and the Beths                           [+ 2026-09-02]
          |V_{omega + eta}| = beth_eta (with AC); the
          aleph/omega notation warning; omega + eta = eta
          for eta >= omega^2 (without AC).
```

## 2. Induction, Recursion and Collapse  ->  `Chapters/2_Induction/`

Opened on 2026-09-02 at the author's own `\chapter` heading, written live with the
note "not sure if this should be a new chapter, but perhaps it should? it's another
instalment of the course". It is: the objects are class relations in general, the
vocabulary (set-like, and the well-foundedness carried over from 1.4.3) is new, and the
title promises a development -- induction, recursion, collapse -- that is not chapter 1's
recap. The chapter file carries two sentences of intro prose and nothing chapter-wide.

```
2.1 Set-Like Relations                                       [2026-09-02]
    What it means for a class relation to be set-like;       2_1_Set_Like.tex
    membership is (and this is Comprehension in disguise);
    OR with 0 moved to the top is not.
```

`Chapters/1_Intro/` is the author's directory name for chapter 1 across three of the
four sibling repositories, whatever that chapter is titled. It is a convention, not
template residue. Leave it.

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

Chapter 1 is the only chapter.              ORGANIZATION.md is explicit that chapter 1
                                            is allowed to look thin early and that the
                                            fix is not to invent chapters 2 and 3.
                                            Ends when L is written up, which the
                                            chapter's own prose says is coming.
                                            [Ended 2026-09-02: chapter 2 opened, at
                                            the author's heading, on induction,
                                            recursion and collapse rather than L.]

2.1 has no subsections, and chapter 2       The author's live heading under the chapter
has one section.                            was an unnamed `\subsection{something}`
                                            with no section above it. Its contents are
                                            one idea (set-like relations), so it became
                                            the section heading rather than a section
                                            and a subsection with the same name; 8 of
                                            the corpus's 66 sections have no subsection.
                                            Ends when the next lecture adds a second
                                            idea to 2.1, at which point the subsection
                                            headings appear. [2026-09-02]

1.2 is short (40 lines) against a           It is two nameable ideas and the author
corpus median of 148.                       named them. Splitting or padding it would
                                            be size-driven, which ORGANIZATION.md
                                            forbids. No condition: this is simply
                                            where the material stopped.
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
    Chapter 2's title, "Induction, Recursion and Collapse", says it is coming;
    nothing about it has been written yet. [2026-09-02]

Induction and recursion along well-founded set-like class relations.
    Promised by chapter 2's title and by the definition of set-like, which is
    introduced without yet being used for anything. [2026-09-02]

Foundation is equivalent to $V = \WF$ over ZF without foundation.
    "We will eventually see that", in 1.4.2. [date not recorded]
    Reached: proved in 1.4.3, together with the equivalence to "every (A, in) is
    well-founded". [2026-09-02]

Formalizations of set theory inside models of set theory, and the internal
versus external perspective. "At some point, we will study these things in
detail", in 1.4. [date not recorded]

Consistency of ZF + "there is a countable union of pairs with no cardinality".
    Asserted, not proved, in 1.5.2. [2026-08-31]
```

## Unplaced

Nothing.

One gap rather than an unplaced item: the lecture of 2026-08-31 breaks off mid-sentence
at "It's clear", just after the alephs and the beths are defined. It sits at the end of
1.5.4 as a `\sorry` with a comment, rather than guessed at, because more than one
continuation is plausible. Awaiting the author.

## Structural pressure

What a run noticed but was not allowed to fix. Each entry is a standing recommendation.

```
Two directories are numbered 2.                Chapters/2_Induction/ is the real chapter 2;
                                            Chapters/2_Another Chapter/ is the template
                                            placeholder, still commented out in
                                            main.tex. Clearing the placeholder is
                                            /organize's, once the author confirms
                                            nothing is planned for it. [2026-09-02]

The inbox is \input from chapter 1.           Chapters/1_Intro/todays_lecture.tex is
                                            still \input at the end of 1_Intro.tex,
                                            so the next lecture's raw notes will
                                            preview as the tail of chapter 1 although
                                            the course is now in chapter 2. Moving the
                                            file or its \input line is one line and
                                            changes the path the author types into;
                                            left for the author to decide. [2026-09-02]

The inference note at the top of this file  It predicted that chapter 2 would be L.
predates chapter 2.                         Chapter 2 is induction, recursion and
                                            collapse instead, and L is still promised.
                                            /organize owns the note; revise it on the
                                            next run. [2026-09-02]

The course itself is not written up.        Chapter 1 is undergraduate revision; the
                                            material 21-602 is actually about -- L,
                                            forcing, whatever followed -- has no home
                                            yet. Whether that is a gap or simply where
                                            the notes stopped is the author's to say,
                                            and it is not something /organize can fix
                                            by rearranging what exists.

Two mathematical faults are flagged and     1_4_Classes.tex, near the top of 1.4 and
unfixed, as % [SUSPECT].                    restated later in the same section: "$V \in V$,
                                            so $V$ has no $\in$-minimal member" does not
                                            follow from Foundation as the notes state it.
                                            1_Intro.tex: Defin(A) is defined as a class of
                                            definable structures rather than the definable
                                            subsets of A. Both found by the review on the
                                            post-lecture pass of 2026-08-31, both outside
                                            its scope, neither adjudicated. Run
                                            /check-correctness with these as its scope.

Two source defects in 1.4, reported and     The OR display near the top of the section
unfixed.                                    juxtaposes two class terms with no relation
                                            or line break between them; and "$w \in W
                                            \lr w \notin W$" uses a lowercase w where W
                                            is meant. Neither is this lecture's and
                                            neither is unambiguous enough to repair as
                                            typesetting. [noted 2026-08-31]

\Cref to a ZFC axiom renders as a bare      No \crefname is declared for the zfcaxiom
number.                                     environment that baxiom wraps, so every
                                            \Cref{ZFC:...} prints without "ZFC Axiom".
                                            A preamble fix in TeX_Setup/environments.tex,
                                            not a structural one. [noted 2026-08-31]

One % [CLAUDE] directive outstanding.       1_1_ZFC.tex, in 1.1.6: "draw a diagram for
                                            this", on the Axiom of Replacement. A figure
                                            to be drawn. Run /address-comments.
```

## Template scaffolding

Placeholder content from [Lecture-Notes-Template-2026][tpl], still standing.

```
Chapters/2_Another Chapter/      placeholder chapter, two placeholder sections, still
                                 carrying the template's titles. Nothing has displaced
                                 it, so nothing has been deleted -- but its \input in
                                 main.tex is now commented out, because until this pass
                                 it rendered in the published PDF as a chapter called
                                 "Another Chapter" with a section called "Another
                                 Section". Reversing that is one line. [2026-08-31]
Chapters/Appendices/             placeholder, \input commented out in main.tex
```

Clearing either is `/organize`'s, and only once the author confirms nothing is planned
for them. Three of the four sibling repositories keep an `Appendices/` directory, two of
those with the `\input` still commented out, so leaving that one standing is in keeping
rather than an oversight.

[tpl]: https://github.com/thefundamentaltheor3m/Lecture-Notes-Template-2026
