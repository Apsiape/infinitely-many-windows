# A perturbed cellular automaton with infinitely many ergodicity transitions

Seth Douglas and Nidhal Mghirbi. Version 1.0.0, November 2026. The version DOI is recorded in the commit that follows the release.

**This is a preprint. It has not been peer reviewed.**

## Abstract

Can the ergodicity of one cellular automaton under noise switch on and off infinitely often as the noise rate decreases? Marsan, Sablik and Törmä built a one-dimensional automaton that is ergodic at small and at large noise rates and not ergodic in between, and asked which sets of rates can occur. We give one cellular automaton on ℤ⁴, with one finite alphabet and one neighbourhood, whose perturbation by independent uniform replacement of the whole symbol at rate ε has infinitely many alternating windows: open intervals of rates, with rational endpoints computable from their index and decreasing to 0, on which the perturbed automaton alternately has two translation-invariant stationary laws and has one stationary law that attracts every initial law. The rule is given in full, including its action on malformed configurations.

The construction starts from a one-dimensional automaton whose unique stationary law makes a display bit mostly 1 at the rates b/(kB^k) with k odd and mostly 0 with k even. Seeds created by the noise start base-B counters. A changed counter letter makes its anchored prefix decay. The head freezes a previously validated message bit; once the length-parity messages have settled, this is the parity of the counter's length before the failure. Heads write their bits on the display. Independent copies of this automaton gate Toom's north-east-centre majority rule in two further dimensions, which keeps memory when the gates are mostly open and forgets when they are mostly closed. Through the correspondence between probabilistic cellular automata and space-time Gibbs measures, one finite-range interaction on ℤ⁵ with energies 0 and 1 has infinitely many computable alternating intervals of inverse temperature, tending to infinity, with at least two and with exactly one translation-invariant Gibbs measure. All windows lie at astronomically small noise rates.

## What the paper proves

A perturbed cellular automaton is ergodic if it has one stationary law and forgets its initial configuration. Marsan, Sablik and Törmä (J. Stat. Phys. 193 (2026), article 6) built a one-dimensional automaton with two ergodicity transitions and asked which sets of noise rates can be ergodicity sets. The paper shows that one automaton can have infinitely many transitions:

- **Theorem A (Section 7).** There is one cellular automaton F on ℤ⁴, with one finite alphabet and one neighbourhood, and open intervals I₁, J₁, I₂, J₂, … of noise rates with rational endpoints computable from the index, each interval lying above the next and tending to 0, such that uniform replacement at rate ε after F has at least two translation-invariant stationary laws for every ε in Iₙ, and exactly one stationary law, attracting every initial law, for every ε in Jₙ.
- **Theorem B (Section 8).** There is one translation-invariant finite-range interaction on ℤ⁵ with energies 0 and 1, and open intervals A₁ < B₁ < A₂ < B₂ < ⋯ of inverse temperatures with rational endpoints computable from the index and tending to infinity, with at least two translation-invariant Gibbs measures at every β in Aₙ and exactly one translation-invariant Gibbs measure at every β in Bₙ. Uniqueness is among translation-invariant Gibbs measures only.
- **Theorem C (Sections 3 to 6).** The source of the construction is an explicit one-dimensional automaton Q, ergodic under uniform replacement at every rate in (0, 1/2304). At the rates ε_k = b/(kB^k), with b = 2⁷⁰ and B = b², the stationary density of its display bit exceeds 1 − θ for all large odd k and is below θ for all large even k, where θ = 2⁻³²3⁻⁸.

The rule is given completely in Section 3, field by field, including its action on malformed configurations. The automaton is four-dimensional, its alphabet has more than 3^(3^9216) symbols, and the windows that the estimates guarantee lie at rates below 2^(−140·3^9216); no window has been located. The automaton is not nilpotent; whether one nilpotent automaton can have infinitely many windows remains open, as does the one-dimensional question of Marsan, Sablik and Törmä.

## Contents and reproduction

- `paper/main.pdf`: the manuscript.
- `paper/`: LaTeX source (`main.tex`), plain-text abstract and a strict build driver. Run `python -B build.py` there with pdflatex installed. The build disables shell escape, runs pdflatex three times and rejects warnings, unresolved references and box defects.
- `SHA256SUMS`: SHA-256 hashes of every shipped file except this manifest. Check with `sha256sum -c SHA256SUMS` from the repository root.

No computation is used in any proof. The paper imports Toom's stability theorem in the quantitative form of Gács (arXiv:2105.05968) and the space-time Gibbs correspondence in the form of the authors' paper *Exponential ergodicity and the space-time Gibbs states of one-dimensional probabilistic cellular automata* (version 1.1.0, DOI [10.5281/zenodo.24023364](https://doi.org/10.5281/zenodo.24023364)).

## Citation and rights

See `CITATION.cff` for citation metadata. Paper and documentation: CC BY 4.0. Build script: MIT or Apache 2.0, at your option. See `RIGHTS.md`, the license files and `NOTICE`.
