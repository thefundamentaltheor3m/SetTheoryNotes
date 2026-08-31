# Topics

Where each topic lives. Owned by `/organize`; `/integrate` appends to it.
What earns a chapter, a section and a subsection: `.claude/ORGANIZATION.md`.

<!-- INFERENCE, not a plan, and written after the fact. 21-602 ran in Fall 2025 and
     these notes were taken before this file existed, so the outline below is read
     off the sources rather than accumulated lecture by lecture, and the usual
     per-line lecture dates are not recoverable. Treat the structure as observed,
     not as endorsed: nobody has yet run /organize over it.

     What is here reads as one chapter of undergraduate revision, laid down as
     groundwork, with the course proper not yet written up. Chapter 2 is still the
     template's placeholder. The next run should feel free to disagree. -->

## 1. A Recap of Undergraduate Set Theory  ->  `Chapters/1_Intro/`

```
1.1 The Zermelo-Fraenkel Axioms and the Axiom of Choice      [date not recorded]
    The axioms, stated and discussed.                        1_1_ZFC.tex, 210 lines
1.2 Classes                                                  [date not recorded]
    What a proper class is and why the axioms need them.     1_2_Classes.tex, 36 lines

    -- appended 2026-08-31. The numbering above is stale: the file 1_1_ZFC.tex
    -- actually carries three sections, so Classes is 1.4 and not 1.2. Entries for
    -- this lecture are filed under their real numbers. See Structural pressure.

1.4 Classes                                                  [2026-08-31]
    1.4.2 Well-Foundedness gains the properties of rank:     1_2_Classes.tex
    the criterion for membership in WF, the strict drop of
    rank on members, the Rank Formula, rank(b) = b for
    ordinals, and V_b cap OR = b.
1.5 Cardinals and the Axiom of Choice                        [2026-08-31, new]
    How big the levels of the hierarchy are, and which of    1_3_Cardinals.tex
    the answers need choice. Walks to the aleph and beth
    hierarchies, one of which is choice-free and one not.
    1.5.1 The Size of V_omega
    1.5.2 Cardinality Without Choice
    1.5.3 Cardinal Successors
    1.5.4 The Alephs and the Beths
```

No subsections anywhere in the chapter. 1.1 is long enough that `ORGANIZATION.md`
would expect a few; whether it wants them is a question about whether it holds one
idea or several, and answering it is `/organize`'s job, not something to assume from
the line count.

`Chapters/1_Intro/` is the author's directory name for chapter 1 across three of the
four sibling repositories, whatever that chapter is titled. It is a convention, not
template residue. Leave it.

## Deliberate deviations

Nothing recorded. Nothing here has been through `/organize`, so an apparent deviation
is at present more likely to be an unreviewed accident than a tolerated one.

## Signposted

Topics a lecture pointed at without reaching. Not sections, and not to be promoted to
sections until a lecture supplies content.

Consistency of ZF + ``there is a countable union of pairs with no cardinality''
— asserted 2026-08-31 in 1.5.2, not proved.

Whether $V_{\omega + 1}$ has a cardinality at all in the absence of choice
— raised 2026-08-31 in 1.5.2, left as a remark.

Nothing else recorded — the lecture notes the rest of this would have been built from
were taken before this file existed.

## Unplaced

Nothing. One gap rather than an unplaced item: the lecture of 2026-08-31 breaks off
mid-sentence at ``It's clear'' after defining the alephs and the beths. Placed at the
end of 1.5.4 as a `\sorry` with a comment, rather than guessed at, because more than one
continuation is plausible. Awaiting the author.

## Structural pressure

What `/integrate` noticed but is not allowed to fix. Each entry is a standing
recommendation to run `/organize`.

```
The course itself is not written up.        Chapter 1 is undergraduate revision;
                                            21-602's own material has no home yet.
                                            Whether that is a gap or simply where the
                                            notes stopped is the author's to say.

One file holds three sections.              [noted 2026-08-31] 1_1_ZFC.tex contains
                                            \section{The Zermelo-Fraenkel Axioms and the
                                            Axiom of Choice}, \section{Transitive Sets}
                                            and \section{The $V$-Hierarchy}, so every
                                            section file after it is misnumbered:
                                            1_2_Classes.tex is section 1.4 and the new
                                            1_3_Cardinals.tex is section 1.5. The author
                                            marked the seam themselves, at
                                            1_1_ZFC.tex:237. Run /organize.

A subsection titled ``Old stuff''.          [noted 2026-08-31] 1_1_ZFC.tex:258, rendering
                                            in the ToC as 1.3.1. It holds the argument
                                            that $V_{\omega}$ is a set, which is neither
                                            old nor stale. Run /organize.

Chapter-wide notation buried in it.         [noted 2026-08-31] The ZFC / ZF / -F notation
                                            box sits inside that same subsection, though
                                            it is used in 1.4 and 1.5 as well.
                                            ORGANIZATION.md puts chapter-wide notation in
                                            the chapter file. Run /organize.
```

## Template scaffolding

Placeholder content from [Lecture-Notes-Template-2026][tpl], still standing.

```
Chapters/2_Another Chapter/     placeholder chapter, two placeholder sections,
                                still carrying the template's titles. \input is
                                live in main.tex, so it renders in the PDF.
Chapters/Appendices/            placeholder, \input commented out in main.tex
```

Clearing these is `/organize`'s, and only once the author confirms nothing is
planned for them. Three of the four sibling repositories keep an `Appendices/`
directory, two of those with the `\input` still commented out, so leaving that one
standing is in keeping rather than an oversight.

[tpl]: https://github.com/thefundamentaltheor3m/Lecture-Notes-Template-2026
