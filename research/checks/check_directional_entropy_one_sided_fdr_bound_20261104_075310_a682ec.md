---
type: falsification_check
title: 'Falsification check: directional_entropy_one_sided_fdr_bound'
target_asset: directional_entropy_one_sided_fdr_bound
outcome: no_counterexample_found
statement_digest: d2f5f592be074963400a03298424a3e5e1df4050144f3e4fb2d8d8b6c4249a95
performed_by: unknown
created_at: '2026-11-04T07:53:10.076Z'
extension_version: 0.0.4
---

## Cases checked

- Round 1, boundary_degenerate: no plausible candidate.
- Round 1, small_cases: no plausible candidate.
- Round 1, drop_hypothesis: no plausible candidate.
- Round 1, known_counterexamples: no plausible candidate.
- Round 2, extremal: no plausible candidate.
- Round 2, boundary_degenerate: no plausible candidate.
- Round 2, small_cases: no plausible candidate.
- Round 2, drop_hypothesis: no plausible candidate.
- Round 3, boundary_degenerate: no plausible candidate.
- Round 3, small_cases: no plausible candidate.
- Round 3, drop_hypothesis: no plausible candidate.
- Round 3, known_counterexamples: no plausible candidate.
- Round 4, boundary_degenerate: no plausible candidate.
- Round 4, small_cases: no plausible candidate.
- Round 4, drop_hypothesis: no plausible candidate.
- Round 4, known_counterexamples: no plausible candidate.
- Obstruction: Degenerate loadings give no counterexample: empty null sets have zero FDR; zero null loadings give the bound $q\pi_0$; full null loading norms give the smaller bound $q(\pi_0+\mathcal E_0)$.
- Obstruction: Splitting a group of identical oriented null directions increases $\mathcal E_0$, hence only loosens the proposed bound; merge such groups for a stronger test. Antipodal directions remain separate under the stated grouping definition.
- Obstruction: The finite identical-null family obeys $q\pi_0\{1+\log(1/\pi_0)\}$, below the proposed right side. The known Lei families examined supplied no verified violation.
- Obstruction: For singleton null groups, $\mathcal E_0=\pi_0\log m$; the arbitrary-dependence harmonic bound $q\pi_0 H_m\leq q\pi_0(1+\log m)$ is already smaller than the proposed bound. Increasing the number of singleton directions therefore supplies no counterexample.
- Obstruction: The small-test families examined were excluded by the harmonic bound or, where its hypotheses hold, the nonnegative-correlation BH bound; these exclusions do not cover arbitrary correlated-alternative models.
- Obstruction: Merging opposite rays violates the oriented-group hypothesis. For finite $m$, every nonempty group has $\pi_h\geq1/m$ and there are at most $m_0$ such groups, so zero-mass or infinitely many positive-mass groups at fixed $m$ are inadmissible.
- Obstruction: Classical negatively correlated examples with singleton null directions remain covered by the previously recorded arbitrary-dependence harmonic bound; they supply no violation of this entropy bound. No new general family exclusion was established this round.
- Obstruction: Singular dependence can create ties between p-values, but their continuous Gaussian marginals give zero probability of equality to any fixed BH threshold $kq/m$. Such boundary atoms therefore cannot supply the proposed failure mechanism.

## Limitations

- All four directions produced no candidate files. Nonminimal factor representations supplied no verified violation, and no new known-counterexample or small-model family yielded one; these observations establish no new general family exclusion.
- The general proof remains required: justify the group-specific cutoffs and logarithmic tail costs for shared interior-loading null groups with correlated alternatives, then the uniform entropy-controlled asymptotic passage. This round supplies no such proof.

Object search: 0 candidate(s) in 4 round(s).
