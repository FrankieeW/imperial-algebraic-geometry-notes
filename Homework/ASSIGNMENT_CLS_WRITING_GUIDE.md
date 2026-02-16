# Assignment `cls` Writing Guide

This guide is for documents using `Homework/assignment.cls` (including linked usage from `Homework/hw1/assignment.cls`).

## 1. Base setup

Use:

```tex
\documentclass[12pt]{assignment}
```

For homework folders like `Homework/hw1`, keep:

- `assignment.cls` as a symlink to `../assignment.cls`
- `figures` as a symlink to `../figures`

This keeps style and assets globally consistent.

## 2. Metadata fields (title block)

Use these class macros:

```tex
\title{...}
\author{...}
\email{...}
\date{...}
\institute{...}
\course{...}
\lecturer{...}
% optional:
\studentid{...}
\github{...}
```

## 3. Problem structure standard

Use one outer `enumerate` for major questions, and inner `enumerate` for sub-questions.

```tex
\begin{enumerate}
  \item Question 1 ...
  \item Question 2 ...
    \begin{enumerate}
      \item (a) ...
      \item (b) ...
    \end{enumerate}
\end{enumerate}
```

Do not leave any `\item` outside an active list.

## 4. Sub-question separator standard

Use dashed separators (not solid lines), with vertical spacing and full local width alignment.

Add once in preamble:

```tex
\newcommand{\subqdash}{%
  \par\vspace{0.8\baselineskip}%
  \noindent\makebox[\linewidth][l]{\leaders\hbox to 0.9em{\hss-\hss}\hfill\kern0pt}%
  \par\vspace{0.8\baselineskip}%
}
```

Then place `\subqdash` between sub-parts.

## 5. Lecture citation policy (mandatory format)

For lecture references, only cite:

- `Notes-dev/lecturenotes.pdf`

Use this exact citation style:

```text
[Lemma 2.1, §2.2, p.4, Algebraic Geometry, 2026]
```

Allowed type labels:

- `Definition`
- `Lemma X.Y`
- `Theorem X.Y`
- `Corollary X.Y`
- `Proposition X.Y`
- `Fact` (if no numbered theorem-like item exists)

Examples:

- `[Definition, §2.1, p.3, Algebraic Geometry, 2026]`
- `[Corollary 7.3, §7, p.26, Algebraic Geometry, 2026]`

## 6. Recommended solution environment

If needed, define:

```tex
\newenvironment{solution}
{\par\noindent\rule{\linewidth}{0.4pt}\par\smallskip\begin{proof}[Solution]}
{\end{proof}\par\noindent\rule{\linewidth}{0.4pt}\par\smallskip}
```

## 7. Build commands

From `Homework/hw1`:

```bash
latexmk -pdf -interaction=nonstopmode -halt-on-error main.tex
```

Clean rebuild:

```bash
latexmk -C && latexmk -pdf -interaction=nonstopmode -halt-on-error main.tex
```

## 8. Pre-submit checklist

- No lonely `\item` errors.
- Sub-question separators use `\subqdash` consistently.
- Lecture citations follow the exact bracket format.
- References point only to `Notes-dev/lecturenotes.pdf`.
- PDF compiles without LaTeX errors.
