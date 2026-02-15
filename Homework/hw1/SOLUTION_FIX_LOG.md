# HW1 Solution Fix Log

Date: 2026-02-15
File: `Homework/hw1/main.tex`

## Scope
- Exercise 3 solution rigor fixes only.

## Changes
1. Rewrote the proof of `V(x^b-y^a) \subseteq \operatorname{im}(\varphi)`:
- Replaced the "direct check" step with a complete argument using roots of unity.
- Added the bijectivity of `\eta \mapsto \eta^b` on `\mu_a` when `\gcd(a,b)=1`.
- Constructed `s=\eta s_0` and verified `s^a=x`, `s^b=y` explicitly.

2. Corrected the birational inverse verification:
- Removed the incorrect identity
  `x^{\alpha n}y^{\beta n} = x^{\alpha n+\beta m}` (and its analogue).
- Replaced with a function-field proof via pullbacks `\varphi^*` and `\psi^*`,
  showing both compositions are identity maps.

## Verification
- Recompiled with `latexmk -pdf -interaction=nonstopmode -halt-on-error main.tex`.
- Build succeeded; no new LaTeX errors introduced by these edits.

## 2026-02-15 (Notes Alignment)
- Updated mathematical wording in `Homework/hw1/main.tex` to align with
  `Notes-dev/lecturenotes.pdf` (not formatting-level changes).
- Added explicit references to notes results/definitions where used:
  affine subvarieties via zero loci `V(S)` (Section 2.1), Zariski-closed finite
  unions (Lemma 2.1), and the function-field criterion for birationality
  (Lecture 2 discussion of rational maps/function fields).

## 2026-02-15 (More explicit notes citations)
- Expanded the aligned passages with more displayed equations and line breaks.
- Wrote concrete note anchors directly in the solution text:
  `Section 2.1 (Definition of affine subvarieties)`,
  `Lemma 2.1 (V(I) \cup V(J)=V(IJ))`,
  and `Lecture 2 (rational functions/function fields + birational criterion)`.
