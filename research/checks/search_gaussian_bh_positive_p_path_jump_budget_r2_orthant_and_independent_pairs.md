---
type: search_round
title: Positive p-path budget round 2 — orthant comparison and independent pairs
target_asset: gaussian_bh_positive_p_path_jump_budget
mode: refute
round: 2
directions:
  - known_counterexamples
  - extremal
  - boundary_degenerate
candidates:
  - cand_gaussian_bh_positive_p_path_jump_budget_r2_s1_regular_simplex
  - >-
    cand_gaussian_bh_positive_p_path_jump_budget_r2_s2_independent_antipodal_pairs
  - >-
    cand_gaussian_bh_positive_p_path_jump_budget_r2_s3_independent_antipodal_pairs
statement_digest: 301a9fdf2ecda11e42541631b84ac56c2ad1d8a75b5cf72d593e5cd71674b0e2
performed_by: unknown
created_at: '2026-11-09T21:31:13.283Z'
extension_version: 0.0.4
---

## Obstructions

- The regular-simplex obstruction extends to the zero-mean all-null family with every off-diagonal correlation nonpositive. Its selected-null paths have only downward net jumps, so the positive jump budget agrees with the signed jump budget. Orthant domination followed by a union bound yields
  $$
  \frac1N\sum_{i=1}^N\mathbb E B_i\leq\frac{e^2q}{1-eq},\qquad 0<q\leq S(1).
  $$
  Since $eS(1)<1$ and $\sqrt{\log(1/q)}\geq\sqrt{\log(1/S(1))}>0$, this bounds the normalized budget uniformly in dimension, rank and admissible $q$. Neither the simplex nor its zero-mean, all-null, nonpositive-correlation extension supplies an unbounded refutation.
- Arbitrarily many independent antipodal pairs do not produce an unbounded budget merely through increasing covariance rank. Conditioning on a selected zero-mean null freezes all background ranks; the checked zero-null family has at most one downward net jump and $B_i\leq1$. The checked extension including strictly negative null means has at most two actual positive jumps and $B_i\leq2$. Simultaneous crossings are merged into net jumps and original weights are retained. Consequently their null-averaged normalized budgets are at most $1/\sqrt{\log(1/S(1))}$ and $2/\sqrt{\log(1/S(1))}$, respectively. These finite bounds are compatible with the asserted existence of an unspecified universal constant; all three round-2 candidates fail NOT.

## Limitations

General mixed-sign covariance and heterogeneous means remain uncontrolled. The orthant argument above is restricted to zero-mean all-null models with nonpositive correlations; the finite jump counts are restricted to the independent-pair families with frozen background ranks. No reduction from general Gaussian models to either family is established. These search obstructions neither prove the universal positive-budget statement nor independently verify its finite signed-identity dependency. No counterexample surviving NOT was found in this round. Orthant domination combined with equality of positive and signed charges suggests a proof route only within its stated restricted setting; extending either ingredient beyond that setting is unresolved.
