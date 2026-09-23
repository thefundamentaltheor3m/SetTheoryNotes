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
     rather than more hierarchy. All three have now been delivered: the theorem schemes
     for proofs by induction and definitions by recursion along a well-founded set-like
     class relation (2.1), and the general Mostowski Collapse Theorem Scheme promised in
     1.2.2 (2.2), whose examples the lecture of 9 Sep had only begun. So the notes read
     as groundwork and then tools, an order nobody planned but a sensible one.

     Chapter 3 was opened on 2026-09-15, out of the section the lecture of 14 Sep had
     been placed in. The previous version of this note predicted it: "the next lecture
     that is not an example of collapsing will probably be the start of chapter 3", and
     relativization is that lecture. Its objects are neither sets nor class relations but
     *formulae* -- what it takes for one to be true in a class, and how far up the
     universe a formula has to look before we can tell -- and that is a body of theory
     with its own vocabulary rather than a fourth item on chapter 2's list. So the notes
     now read as groundwork, then tools, then the language those tools get applied
     through.

     An earlier version of this note predicted chapter 2 would be Gödel's L. It was wrong
     about the order, not the destination: L is still promised by chapter 1's opening
     prose and still wants a chapter of its own when it arrives, and chapter 3 is much of
     what a construction like L needs -- L is built by relativizing the definability
     operation, and absoluteness, which 3.3 is the setup for, is how one proves anything
     about it. Chapter 1 stays the recap it says it is. -->

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
    1.2.2 Mostowski Collapse for Well-Orderings              [retitled 2026-09-10]
          The special case, stated without proof; the general
          theorem is 2.2. Retitled so the two do not share a
          name in the contents.

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

The opening was finished on 2026-09-05: the template's placeholder chapter gave up the
number 2 (it has since been pushed on to 4; see `## Template scaffolding`), and the
inbox moved to `Chapters/2_Induction/todays_lecture.tex`. It has since moved on to
chapter 3 -- **the path to type into is now
`Chapters/3_Relativization/todays_lecture.tex`.**

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

2.2 Mostowski Collapse                                       [2026-09-09]
    The structure theorem for well-founded set-like          2_2_Mostowski.tex
    extensional class relations: each is isomorphic to a
    unique transitive class under membership, by a unique
    map. Uses neither Choice nor Foundation.
    2.2.1 Extensional Relations
          The definition; a two-element non-example; transitive
          classes under membership and class linear orderings
          as examples.
    2.2.2 The Collapse Theorem
          The Mostowski Collapse Theorem Scheme, the remark
          that the uniqueness is not definitional, and the
          proof (transitivity of the range, injectivity by
          R-induction using extensionality, monotonicity,
          uniqueness via the recursion theorem).
    2.2.3 Examples                                           [2026-09-11]
          Two applications of the collapse. The finite subsets
          of OR under the lexicographic ordering of their
          decreasing enumerations collapse onto (OR, <), giving
          a parameter-free class bijection. And, for any alpha,
          a countable X elementary in V_alpha (by DLS, inside
          the ZFC formalization) collapses onto a countable
          transitive M with G^{-1} : M -> V_alpha elementary --
          the countable-microcosm subroutine, with a figure.
```

2.2.3 replaces the abandoned example the lecture of 9 Sep broke off in. The
author's own `% [CLAUDE]` directive in this lecture's notes said to remove it,
which is what the entry under `## Unplaced` had predicted would happen.

The lecture date is the one written in the file (`% 9 September`); the commit that
brought it is dated 2026-09-10, the next day's sync. The written date is used.

## 3. Relativization  ->  `Chapters/3_Relativization/`

Opened on 2026-09-15, out of the section the lecture of 14 Sep had been placed in.
The author wrote `\section{Relativisation}` live, with `% [CLAUDE] as usual, figure
out where to put this` beside it, so the placement was delegated rather than decided;
`/integrate` placed it as 2.3 because it may not open a chapter the author did not,
and recorded the mismatch as structural pressure. This pass acted on it. The chapter
takes the section's title, and the section's three subsections are its three sections
-- one heading level shed because one was gained above, with no title invented and
none lost. The chapter file carries two paragraphs of intro prose and nothing
chapter-wide.

`Chapters/3_Another_Chapter/` gave up the number 3 and is now
`Chapters/4_Another_Chapter/`, still commented out in `main.tex`. The inbox moved
with the course: **type into `Chapters/3_Relativization/todays_lecture.tex` from now
on.**

```
3.1 Relativization to a Class                                [2026-09-14]
    The recursion defining psi^A: atomic, propositional      3_1_Rel_To_Class.tex
    and quantifier steps, the variable renaming it needs
    in both directions, and how the atomic step changes
    when the relation is some R other than membership.
    No subsections.

3.2 The Relative Consistency of ZF                           [2026-09-14]
    What relativization is first used for. The theorem       3_2_Consistency.tex
    scheme that ZF - F proves sigma^WF for every ZF axiom
    including Foundation; the scheme that relativization
    carries proofs, for sentences and given a non-empty
    class; and the corollary, by contraposition, that
    Con(ZF - F) implies Con(ZF). No subsections.

3.3 Complexity of Formulae                                   [2026-09-14]
    How far up the universe a formula has to look.          3_3_Complexity.tex
    Bounded quantifiers, Delta_0 formulae, the Sigma_1
    and Pi_1 shapes, why there are no Delta_1 formulae,
    and complexity relative to a theory: Delta_0^T,
    Sigma_1^T, Pi_1^T and Delta_1^T, with the promise of
    Sigma_n and Pi_n to come. No subsections.
    Bounded quantifiers now need distinct variables:        [corrected 2026-09-23]
    exists v in v slipped through before (see 3.3's
    % [CORRECTED] marker).

3.4 Absoluteness                                             [2026-09-16]
    When a formula says the same thing in a transitive       3_4_Absoluteness.tex
    class as in a bigger one, and what that says about
    the axioms relativized to a transitive class. The
    section opens with the one definition of
    downwards-absolute, upwards-absolute and absolute.
    3.4.1 Absoluteness Theorems
          Delta_0-absoluteness for transitive M in N, with
          proof; the one-directional Sigma_1 and Pi_1
          versions; and the Sigma_1^T, Pi_1^T and Delta_1^T
          versions for non-empty transitive models of T.
    3.4.2 Absoluteness of ZFC Axioms
          For a transitive class M: Extensionality^M always;
          Comprehension^M exactly when M contains each set
          {x in A : phi^M} it should; and, given that,
          Pairing^M exactly when M is closed under pairs.
          Then the notation A^M for a class relativized to
          M, which the author flagged as a digression and
          asked where it was going. It was going to the
          next two axioms: A^M = A cap M for Delta_0-defined
          A, so Unions^M holds exactly when M is closed
          under unions, and Power Sets^M exactly when
          P(A) cap M is in M, which can be smaller than
          P(A). The lecture's notes stop at the notation;
          the rest is supplied and marked % [FILLED]. The
          list stops at Power Sets.

3.5 Levels of the V-Hierarchy as Models                      [2026-09-21]
    Which levels of the hierarchy satisfy which axioms,      3_5_V_Models.tex
    and the cardinals needed to go further.
    3.5.1 The Axioms at Limit Levels
          Extensionality, Comprehension, Pairing, Unions and
          Power Sets hold in every V_alpha with alpha a
          limit; V_omega also satisfies Replacement; and
          V_{omega + omega} does not, via n |-> omega + n.
    3.5.2 Inaccessible Cardinals
          Limit and strong limit cardinals, cofinality,
          regular and singular cardinals, weak and strong
          inaccessibility, and beth_mu = mu for strongly
          inaccessible mu.
```

3.4 and 3.5 came in one commit (`1f1265d`, "feat: latest lectures", dated 2026-09-23). The
author's `% 21 Sep 2026` marker divides them. Everything above it is undated in the file;
the author has confirmed it is the lecture of 16 Sep.

The author wrote `\section{Absoluteness}` and its two subsections live. All three are
kept as written. The 21 Sep material came with no headings; its section and both
subsections are new. It is a separate section, not a continuation of 3.4, because it asks
a different question: 3.4 asks which formulae and axioms survive the passage to a
transitive class, and 3.5 asks which levels of V satisfy which axioms. A 3.4 whose last
subsection was about inaccessible cardinals would also no longer be about absoluteness.
The relativized-class notation stays in 3.4.2, where the lecture said it. The author's
`% [CLAUDE] here is a digression, now you need to figure out where it's going` asked
where it was leading, not where to put it, and it leads to the next two axioms on 3.4.2's
list.

3.4 carries three `% [CORRECTED]` markers and 3.5 two, all from the correctness pass of
this lecture, and 3.3 one, added at the author's instruction. 3.4.2 carries three
`% [FILLED]` markers and 3.5.1 one.

Three `% [CORRECTED]` markers sit in 3.2, all from the correctness pass of 2026-09-14
and all on the same argument: the transfer scheme's non-emptiness hypothesis, its
restriction to sentences, and the hypothesis carried on the left of the corollary's
display. Each quotes what it replaced.

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

Chapter 2 had one section until 2026-09-10. Set-like relations, induction and
                                            recursion are one line of enquiry with one
                                            destination (the recursion theorem), so
                                            they are one section; "Collapse" arrived on
                                            2026-09-09 and is the second, as predicted.
                                            No longer a deviation. [2026-09-05, ended
                                            2026-09-10]

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

Chapter 3 is one lecture long, and none     Deliberate, and the cheaper of the two
of its three sections has a subsection.     mistakes available. ORGANIZATION.md says a
                                            chapter with too few sections self-heals --
                                            the next lecture adds 3.4 and nothing
                                            already written moves -- while fusing two
                                            lines of enquiry into one heading does not.
                                            Keeping relativization inside chapter 2
                                            would have been the second kind. Subsections
                                            arrive when a section acquires a second idea;
                                            3.3 will be first, since the Levy hierarchy
                                            above Sigma_1 is already promised.
                                            [2026-09-15]
                                            Partly ended on 2026-09-21: chapter 3
                                            now spans three lectures, and 3.4 and
                                            3.5 arrived with subsections; 3.1 to
                                            3.3 still have none.

3.1 is short (30 lines) and is one          Its content is one idea -- the recursion
definition rather than a line of            defining psi^A -- which is the subsection
enquiry with a destination.                 test, not the section test. It is a section
                                            only because promoting the subsections
                                            wholesale was the move that invented no
                                            headings. Ends when more of the definitional
                                            groundwork arrives (parameters done properly,
                                            class structures (A, R) in general), at which
                                            point 3.1 has subsections and reads as a
                                            section; or, if it does not, 3.1 and 3.2
                                            merge into one section with two subsections.
                                            [2026-09-15]
```

## Signposted

Topics a lecture pointed at without reaching. Not sections, and not to be promoted to
sections until a lecture supplies content.

```
Gödel's constructible universe L, and a model of ZFC in which CH holds.
    Promised in the chapter 1 intro prose, "something we will explore in great
    detail in this course". [date not recorded]

Formalizations of set theory inside models of set theory, and the internal
versus external perspective. "At some point, we will study these things in
detail", in 1.4. [date not recorded]

Consistency of ZF + "there is a countable union of pairs with no cardinality".
    Asserted, not proved, in 1.5.2. [2026-08-31]

Formalizing all of mathematics in ZFC, Model Theory included, and the downwards
Löwenheim-Skolem Theorem inside that formalization. 2.2.3 leans on both and
says "we will do this eventually in this course". Sharpens the 1.4 signpost
above, which was about the internal/external perspective in general. [2026-09-11]

The elementary-substructure-then-collapse subroutine: take a big initial piece
of V, take a countable elementary substructure by DLS, collapse it, work with
the result. 2.2.3 calls it "one of the most important subroutines in set
theory" and promises "a lot of this later on". [2026-09-11]

The Levy hierarchy above the first level. 2.3.3 closes with "keep going to
get Sigma_n and Pi_n formulae, and also Sigma_n^T, Pi_n^T and Delta_n^T
formulae", which is a promise rather than a development. What the hierarchy
is *for* -- absoluteness -- is not said either, though 2.3.3's opening
sentence gestures at it. [2026-09-14]
Absoluteness itself arrived in 3.4 [2026-09-16]. The hierarchy above
Sigma_1 is still owed.

The rest of the axioms relativized to a transitive class. 3.4.2 opens with
"Let's list out the axioms of ZF - F, relativized to M" and reaches
Extensionality, Comprehension and Pairing, and the author's directive on the
notation that follows took it on to Unions and Power Sets. Replacement,
Infinity and Foundation are not reached. [2026-09-16]

Proofs of four results stated without one and left without a \sorry: the
Sigma_1/Pi_1 and Sigma_1^T lemmas in 3.4.1, and both propositions in 3.5.1.
For the propositions, the criteria in 3.4.2 do most of the work. These are
unmarked gaps, not marked ones. [2026-09-16, 2026-09-21]

Inaccessible cardinals, defined in 3.5.2 with one property (beth_mu = mu) and
no use yet. By inference, not from anything the lecture said, they are
heading for V_mu as a model of ZFC: 3.5.1 has just shown Replacement failing
at V_{omega + omega}. [2026-09-21]

The proof of the theorem scheme that ZF - F proves sigma^WF for every ZF
axiom. Stated in 2.3.2 and used immediately; the lecture gave no proof and
left no \sorry, so this is an unmarked gap rather than a marked one. Same for
the scheme in the lemma that relativization carries proofs, which the author
introduced with "we can show that". [2026-09-14]
```

Reached, and so no longer signposts: Foundation iff V = WF (promised in 1.4.2, proved
in 1.4.3 on 2026-09-02); induction and recursion along well-founded set-like class
relations (promised by chapter 2's title on 2026-09-02, delivered in 2.1.2-2.1.3 on
2026-09-05); the general Mostowski Collapse Theorem (promised in 1.2.2 and by chapter
2's title, proved in 2.2.2 on 2026-09-09).

## Unplaced

Nothing.

One gap rather than an unplaced item, a lecture that broke off mid-sentence and sits
where it stopped as a `\sorry` with a comment rather than being guessed at:

- 2026-08-31, at the end of 1.5.4, at "It's clear", just after the alephs and the beths
  are defined. More than one continuation is plausible. Awaiting the author.

Closed on 2026-09-11: the 2026-09-09 gap at the end of 2.2.2, inside the first of two
announced examples of collapsing a class well-ordering. It did not get continued —
the lecture of 11 Sep gave two different examples instead, and the author's
`% [CLAUDE]` directive said to remove the abandoned one outright. Its `\sorry` and its
`% [IGNORE]` went with it, and 2.2.3 stands where it stood. The announced proper-class
well-ordering case was never reached and is not recorded as owed: nothing in the notes
now promises it.

## Structural pressure

What a run noticed but was not allowed to fix. Each entry is a standing recommendation.

Discharged on 2026-09-10: both outstanding `% [CLAUDE]` directives. The Replacement
diagram in 1.1.6 is drawn, and the empty marker in the recursion theorem is deleted on
the author's instruction, having named no task. Three runs had stepped over the diagram
because `/post-lecture` scoped its directive phase to the latest lecture; that rule is
now reversed, so a directive is never out of scope for being old.

Discharged on 2026-09-05, with the run that did it: the two directories numbered 2 and
the inbox stranded in chapter 1 (phase 5 of the post-lecture pass, per the "Opening a
new chapter" procedure); the stale inference note (rewritten above); the two `% [SUSPECT]`
flags in 1.4 and the chapter 1 intro and the two source defects in 1.4 (all adjudicated
and corrected by the whole-document check-correctness sweep, each with a `% [CORRECTED]`
marker quoting the original); the missing `\crefname` for the `zfcaxiom` environment
(declared in `TeX_Setup/environments.tex`, so `\Cref` to an axiom now prints "ZFC Axiom"
and multiple references no longer print `??`).

Discharged on 2026-09-15: 2.3 was not about what chapter 2 says it is about. It is now
chapter 3, its three subsections are its three sections, the placeholder gave up the
number, the inbox moved with the course, and the two labels that changed chapter were
rewritten together with their cross-references. Recorded by the run that placed the
material, acted on by the next one.

```
The course itself is not written up.        Chapter 1 is undergraduate revision and
                                            chapter 2 its first tools; the material
                                            21-602 is heading for -- L, and whatever
                                            follows -- has no home yet. Whether that is
                                            a gap or simply where the notes have got to
                                            is the author's to say, and not something
                                            /organize can fix by rearranging what
                                            exists.

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

"Elementary substructure" is defined         2.2.3 introduces X <= Y in bold inside
inside a boxexample rather than in a         the ZFC example, where the whole
boxdefinition.                               discussion is deliberately informal (the
                                             "air quotes" footnote). STYLE.md wants a
                                             term used across several results
                                             introduced in a boxdefinition, and this
                                             one is promised heavy future use. Whether
                                             to promote it is a judgment about how
                                             formal the course means to be here, and
                                             /integrate is not the pass to make it.
                                             [2026-09-11]

Cofinality, regularity and inaccessibility   They were introduced as the tool for
live in 3.5.2, while cardinal arithmetic     3.5's question and are placed with it.
otherwise lives in 1.5.                      If the course develops them as cardinal
                                             theory in their own right (cofinality of
                                             the alephs, cardinal exponentiation), they
                                             want a section of their own or a place
                                             beside 1.5. Run /organize then.
                                             [2026-09-21]
```

## Template scaffolding

Placeholder content from [Lecture-Notes-Template-2026][tpl], still standing.

```
Chapters/4_Another_Chapter/      placeholder chapter, two placeholder sections, still
                                 carrying the template's titles. Nothing has displaced
                                 its content, so nothing has been deleted -- but its
                                 \input in main.tex is commented out, because until
                                 2026-08-31 it rendered in the published PDF as a
                                 chapter called "Another Chapter" with a section called
                                 "Another Section". Renumbered from 2 to 3 on
                                 2026-09-05, when the real chapter 2 needed the number;
                                 the space in the old directory name went with it. Then
                                 from 3 to 4 on 2026-09-15, when the real chapter 3
                                 needed that one. It takes the next free number again
                                 each time a real chapter arrives.
                                 [2026-08-31, renumbered 2026-09-05 and 2026-09-15]
Chapters/Appendices/             placeholder, \input commented out in main.tex
```

Clearing either is `/organize`'s, and only once the author confirms nothing is planned
for them. Three of the four sibling repositories keep an `Appendices/` directory, two of
those with the `\input` still commented out, so leaving that one standing is in keeping
rather than an oversight.

[tpl]: https://github.com/thefundamentaltheor3m/Lecture-Notes-Template-2026
