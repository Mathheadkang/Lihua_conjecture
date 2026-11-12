---
type: search_round
title: Round 2 obstructions for the unrestricted two-sided Gaussian BH upper bound
target_asset: gaussian_bh_two_sided_sharp_upper
mode: refute
round: 2
directions:
  - idea_28ab51ce8127
  - idea_9692ea16c23a
  - extremal
  - boundary_degenerate
candidates:
  - cand_gaussian_bh_two_sided_sharp_upper_r2_s1_finite_type_residual_arrays
  - cand_gaussian_bh_two_sided_sharp_upper_r2_s2_common_gate_primary_cap
  - >-
    cand_gaussian_bh_two_sided_sharp_upper_r2_s3_high_dimensional_spherical_entropy
  - cand_gaussian_bh_two_sided_sharp_upper_r2_s4_growing_negative_simplex
statement_digest: 2aaf3b157d839619c9429607bf182d896b1dacb3bc592c3dc8041bc442b8ed40
performed_by: unknown
created_at: '2026-11-04T09:08:33.546Z'
extension_version: 0.0.4
---

## Obstructions

These are scoped summaries of the four failed candidate reports in the round's context pack, not independent verification of their calculations or proofs. Each reported bound gives zero after division by $q\sqrt{\log(1/q)}$.

- The two prescribed finite-type repeated-signal residual families are reported to have global BH FDR at most $16q$, uniformly over their specified diverging dimensions, means, and vanishing tail masses; repetition and residual noise in these two families therefore fail the asymptotic NOT check.
- The tested growing common-gate regime with $B\asymp q^{-2}$ and $\epsilon=1/\sqrt2$ is reported to admit a global primary cap giving FDR at most $q\{1+o(1)\}$ apart from a gate event of probability $q^{2+o(1)}$; changing secondary-source details within this capped regime cannot produce a counterexample.
- The tested exact, growing-rank, high-entropy spherical Gaussian arrays are reported to have global all-null BH FDR at most $(1+o(1))q_j$ along their specified level sequence; growing rank and angular entropy in these arrays fail the asymptotic NOT check.
- The tested growing-rank singular negative-equicorrelation simplex family is reported to have global BH FDR at most $q\{1+o(1)\}$; its dimension growth and negative dependence fail the asymptotic NOT check.

## Limitations

- Weak common-gate coupling, including $q$-dependent $\epsilon$ outside the tested strongly coupled regime, remains open. The primary-cap report does not settle the entire common-gated family.
- Richer interior residual-noise models, beyond the two prescribed finite-type repeated-signal families, remain open; the reported $16q$ bound is not a uniform theorem for arbitrary interior Gaussian covariance models.
- Growing-block, high-rank, and singular or nonsingular covariance structures outside the particular schedules and designs tested this round remain uncovered. The four reports do not exhaust arbitrary $q$-dependent dimensions, means, or covariance matrices.
- No candidate survived the asymptotic NOT check, and this round supplies no counterexample to the unrestricted conjecture. Its failed searches also do not prove the proposed uniform upper bound; any later argument relying on a reported candidate calculation still needs the relevant independent verification.
