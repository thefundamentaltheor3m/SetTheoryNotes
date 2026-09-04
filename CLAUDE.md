# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A LaTeX lecture-notes project (`book` class) for **21-602, Introduction to Set
Theory I**, taught by Ernest Schimmerling at Carnegie Mellon in **Fall 2025**,
scribed by Sidharth Hariharan. Derived from
[Lecture-Notes-Template-2026](https://github.com/thefundamentaltheor3m/Lecture-Notes-Template-2026).
There is no code, no tests, and no linter — the deliverable is `main.pdf`.

**The course is over.** These notes are settled rather than accumulating, which
changes which skills are worth reaching for: `/check-correctness`, `/fill-sorries`,
`/address-comments`, `/organize` and `/americanise` all apply to finished notes, while
`/post-lecture` and its `/integrate` phase need a lecture to process and so have
nothing to do here unless the author goes back and writes up material that never made
it in.

## Building

`latexmk`, `pdflatex`, `biber`, and `make4ht` are all available locally.

```bash
# Full build with bibliography, output into TeX_Outputs/ (matches .vscode config)
latexmk -pdf -outdir=TeX_Outputs main.tex
```

Compile **at least twice**: `cleveref` and the ToC depend on the `.aux` files, and
citations need a `biber` pass in between. `latexmk` works that out for itself, which
is why CI uses it.

`TeX_Outputs/main.pdf` is **committed** (a general `*.pdf` ignore is deliberately
commented out in `.gitignore`); CI republishes it as `public/LastLocallyCompiled.pdf`.
Keep it refreshed when making substantive content changes.

## Structure

`main.tex` is the only root document. It defines course metadata as macros
(`\COURSENUMBER`, `\COURSENAME`, `\LECTURER`, `\SCRIBE`, `\UNIVERSITY`, `\TERM`) that
are consumed by the title block, then `\input`s the four preamble files in a fixed
order, and they are not interchangeable:

- `TeX_Setup/packages.tex` — all `\usepackage` calls, `hyperref` colors, `biblatex` + bib resource, TikZ libraries
- `TeX_Setup/format.tex` — sans-serif default font, `fancyhdr` headers, 1.5 line spacing, `parskip` (no paragraph indents), color definitions
- `TeX_Setup/environments.tex` — `amsthm` theorem declarations and the boxed variants
- `TeX_Setup/shortcuts.tex` — all custom macros

What is actually written:

```
Chapters/1_Intro/            A Recap of Undergraduate Set Theory     real
  1_1_ZFC.tex                  The Zermelo-Fraenkel Axioms and the Axiom of Choice
  1_2_Classes.tex              Classes
Chapters/2_Another Chapter/  placeholder, still carrying its template title and
                             two placeholder sections
Chapters/Appendices/         placeholder, \input commented out in main.tex
```

Note `Chapters/2_Another Chapter/` contains a space in its path — quote paths when
scripting over it. Clearing the placeholders is `/organize`'s job; never delete a
file that has acquired real content.

Adding a chapter means: create the directory, write the chapter file with its section
`\input`s, and add one `\input` line to `main.tex`.

## Authoring conventions

Every theorem-like environment has a plain form and a boxed `box*` form; **prefer the
boxed form in the notes** — that is what the existing content uses.

- Orange box: `boxtheorem`, `boxproposition`, `boxlemma`, `boxcorollary`
- Cyan box: `boxdefinition`
- Magenta box: `boxconvention`, `boxnotation`, `boxlnotation` (local notation), `boxabbrev`
- Green/red box: `boxexample`, `boxnexample` (non-example), `boxcexample` (counterexample)
- Gray/red box: `boxexercise`, `boxproblem`, `boxwarning`

Numbering: `theorem` and everything sharing its counter number per *section*;
`remark`, `solution`, `convention`, `notation`, `warning`, `abbreviation` are unnumbered.
Cross-reference with `cleveref` — **always `\Cref`, never `\cref`** — and label as
`Ch<N>:<Kind>:<Name>`, with chapters as `Ch<N>:CH`.

Two reference files under `.claude/` carry the conventions, and the skills point at
them rather than restating them:

- **`.claude/STYLE.md`** — how a passage *reads*: the prose voice, the LaTeX
  mechanics, the label scheme, the macro naming conventions, and pointers into the
  author's four sibling lecture-note repositories, which share this template and
  this style and are the corpus to imitate. Read it before writing any prose or
  math into the notes.
- **`.claude/ORGANIZATION.md`** — where a passage *lives*: the generality ladder that
  decides what earns a chapter, a section and a subsection, read off those same
  repositories, plus the naming conventions and the format and ownership of
  `TOPICS.md`. Read it before deciding where anything goes.

`TeX_Setup/shortcuts.tex` is large and worth grepping before writing raw math — it
already defines auto-sized delimiters (`\parenth`, `\brac`, `\set`, `\setst`, `\abs`,
`\norm`, `\floor`, `\ceil`), number sets (`\R`, `\Z`, `\N`, `\Q`, `\C`, `\F`), operator
wrappers, and `\sorry` (red `sorry` marker for gaps to fill in later). Set-theoretic
additions go under the `% SET THEORY` banner at the end of the file; add new macros
there rather than defining them inline.

## The skills

`.claude/skills/`, shared with the template and the sibling notes repositories:

| Skill | Acts on | Latitude |
| --- | --- | --- |
| `/post-lecture` | one lecture, end to end | composition; owns scope and order only |
| `/address-comments` | `% [CLAUDE]` directives | do exactly what the directive says |
| `/fill-sorries` | `\sorry` markers | work out the mathematics; decide and report |
| `/check-correctness` | what is already written | fix what is false; every change adjudicated |
| `/integrate` | one lecture's raw notes | place new material; restructure only to build the chapter the author opened |
| `/organize` | the notes as they stand | rearrange only; add and delete nothing |
| `/americanise` | British spellings | spelling only; never the mathematics |

**Two of the seven have nothing to do here**, because the course is over.
`/post-lecture` is the after-lecture pipeline — fill, address, check, respell, open the
chapter if the lecture started one, integrate, on one branch — and `/integrate` is its
last phase; both need a lecture to process. The reusable inbox they read from is
`Chapters/1_Intro/todays_lecture.tex`, kept and emptied rather than deleted; it lives
in whichever chapter is current, so opening a chapter moves it.

**Two of them do mathematics, under opposite constraints.** `/fill-sorries` supplies
an argument that does not exist, so it has the freest hand here. `/check-correctness`
overwrites one that does, so it changes as little as it can, puts *every* candidate
correction to an independent agent before applying it, and — if it changed anything —
has the result reviewed by two further independent agents on the pull request. On
settled notes like these it is the more useful of the two by a wide margin: it is the
only skill whose subject is whether what is written is *true*.

The three markers a skill may write, none of which the author writes:

| Marker | Written by | Means |
| --- | --- | --- |
| `% [FILLED]` | `/fill-sorries` | an argument supplied that the lecture did not give |
| `% [CORRECTED]` | `/check-correctness` | a statement changed, original quoted for revert-by-eye |
| `% [SUSPECT]` | `/check-correctness` | believed wrong, left unchanged, awaiting the author |

Never write a `% [CLAUDE]` marker: that is the author's channel for delegating work,
and one written by a skill is work the next run will silently do.

`\sorry` is the red marker for an unfilled gap — a proof not given, a case not
covered, a development that broke off. **There are currently none** in this
repository's content — the only `\sorry` in the tree is the macro's own definition in
`TeX_Setup/shortcuts.tex`. `/fill-sorries` closes them, and it is the one skill
authorized to work the mathematics out for itself rather than following an
instruction; it marks what it supplied with a `% [FILLED]` comment so the notes stay
honest about which arguments came from the lecturer.

`% [CLAUDE]` is the other inline marker — a small, specific writing job delegated
during a lecture. There are none in this repository at present. Do not treat one as
ordinary commented-out content, and do not delete one without addressing it.

`TOPICS.md` at the repo root is the running map of topic to chapter/section.
`/organize` owns it; `/integrate` appends to it.

## Publishing

`.github/workflows/publish-latex.yml` runs on every push/PR to `main`. It is a
**caller**: the build itself is a reusable workflow published by
[Lecture-Notes-Template-2026][tpl] and shared with the sibling notes repositories, so
a fix to the build reaches all of them rather than having to be applied seven times.
To change how the notes are built, change the template.

[tpl]: https://github.com/thefundamentaltheor3m/Lecture-Notes-Template-2026/blob/main/.github/workflows/latex-build-deploy.yml

The build compiles `main.pdf` with `latexmk` (so `biber` runs and the bibliography
resolves) and uploads it as an artifact; where that PDF then goes depends on the
trigger:

- **push to `main`** — published to the `gh-pages` root, so
  `https://thefundamentaltheor3m.github.io/SetTheoryNotes/main.pdf` updates, and
  attached to the `Current` release. The committed `TeX_Outputs/main.pdf` is
  republished alongside it as `LastLocallyCompiled.pdf`.
- **pull request** — published to `preview-<PR number>/` on the same site and linked
  from a comment on the pull request, so an unmerged draft never overwrites the
  published notes. `preview-cleanup.yml` deletes the directory when the PR closes.
  Pull requests from forks only get the artifact: their token cannot push.

The build fails loudly (`-halt-on-error`), so a broken document breaks CI rather than
publishing a broken PDF — compile locally before pushing.

CI does not install `texlive-full`; it installs exactly the packages listed in the
template's `.github/texlive-packages.txt` into a cached tree, which is why a run takes
about a minute rather than ten. **Adding a `\usepackage` to `TeX_Setup/packages.tex`
therefore means accounting for it in that manifest** — in the template, so that every
repository sharing it gets the package. A repository-local
`.github/texlive-packages.txt` would override the shared one and then have to be
maintained separately; prefer adding upstream.
