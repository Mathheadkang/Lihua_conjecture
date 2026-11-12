---
type: search_round
title: >-
  Second trace-budget search round - bounded reweighting, correlated pairs and
  large independent arrays
target_asset: gaussian_bh_entropy_coherence_trace_budget
mode: refute
round: 2
directions:
  - known_counterexamples
  - extremal
  - idea_19c44519bec3
candidates:
  - >-
    cand_gaussian_bh_entropy_coherence_trace_budget_r2_s1_nonpositive_correlation_two_nulls
  - cand_gaussian_bh_entropy_coherence_trace_budget_r2_s2_iid_high_dimension
  - cand_gaussian_bh_entropy_coherence_trace_budget_r2_s3_correlated_two_test
statement_digest: 282de99c92b14dd593f40c0583da4cc65ddd227e11dcc3d261ec31f0e3456ce2
performed_by: unknown
created_at: '2026-11-08T07:23:05.349Z'
extension_version: 0.0.4
---

## Obstructions

- In the entire two-test family with one original composite null, one positive-mean alternative and arbitrary correlation, the actual FDP is bounded between $1/2$ and $1$ whenever the null statistic exceeds its rank-one threshold. Gaussian truncation and this bounded reweighting compare the complete tilted drift with a halfspace drift plus $1/(2\sqrt{1-t})$. A conditional Brownian bridge on the actual single-null-rejection cell then bounds the integrated drift bias by $4$. The exact two-state posterior trace and deficit identities yield $M_+\le(4q/H)(1-x)$, uniformly in both means and every correlation, including singular endpoints. Thus neither a diverging alternative mean nor an arbitrarily small one-rejection probability within this family produces an unbounded trace-to-deficit ratio. This closes the strong-alternative uncertainty retained in the first-round record within its full two-test scope; see [the correlated two-test candidate](../candidates/cand_gaussian_bh_entropy_coherence_trace_budget_r2_s3_correlated_two_test.md).
- For two zero-mean true nulls with nonpositive correlation, the actual BH partition has up to three posterior states, including a genuine two-rejection state when the covariance is nonsingular. Three-state posterior entropy, conditional bridge classification bounds and the actual joint-tail probability control the full signed trace and retain a positive coherence deficit. The resulting uniform constant $C=100$ excludes the entire correlation interval $[-1,0]$, rather than merely the antipodal endpoint already treated in round one; see [the nonpositive-correlation two-null candidate](../candidates/cand_gaussian_bh_entropy_coherence_trace_budget_r2_s1_nonpositive_correlation_two_nulls.md).
- In the independent all-null family with $N\ge3q/\overline\Phi(2H)$, the exact largest-rank leave-one-out identity gives $F=J=q$. The terminal field has squared norm $1/[R h(u_R)^2]$. The displayed dimension condition controls ranks at most three, while the factor $1/R$ controls ranks at least four, yielding the pointwise bound $H^2\|b\|^2\le1/4$ and hence $x\le1/4$. The exact entropy/trace relation gives $M_+\le2q$, so the proposed budget holds with the fixed constant $C=3$. Arbitrarily large finite dimensions, including dimensions chosen with $q$, therefore do not refute the target within this specified independent family; see [the high-dimensional independent candidate](../candidates/cand_gaussian_bh_entropy_coherence_trace_budget_r2_s2_iid_high_dimension.md).

## Limitations

- All three new candidates failed their NOT check; this round found no survivor. Their scoped calculations have not undergone native independent proof verification. This record neither approves them as dependencies nor proves [the draft trace-budget lemma](../assets/gaussian_bh_entropy_coherence_trace_budget.md) or either unrestricted main FDR upper bound.
- The assertion permits an arbitrary finite universal constant and a sufficiently small universal level interval. A positive local face, one large finite normalized ratio, or simultaneous limits $M\to0$ and $x\to1$ do not refute it. A legal counterfamily must invalidate that universal quantifier, for example by an unbounded normalized positive trace in every sufficiently small admissible interval. The complete heat trace, original means and actual largest BH rank must be retained.
- The independent-array exclusion has the explicit lower bound on $N$ stated above; it is not a proof for every independent array and does not cover general dependent growing-dimensional models. The two-null correlated calculation covers nonpositive correlation, not the full positive-correlation near-coherent regime. Neither calculation controls general mixed-sign Gram matrices or all $q$-dependent arrangements of directions and composite null means.
- For three or more tests, false-null-triggered multi-rank cascades, several selected true-null directions and their vector posterior terms remain uncontrolled. The two-test terminal field is only two-valued, and its $[1/2,1]$ reweighting on the rank-one null tail cannot be assumed for a general BH FDP. No uniform cross-direction drift-bias estimate or cancellation of all linear tangential interface terms was established here.
- The new bounded-reweighting bridge argument is preserved in [a scoped approach idea](../ideas/idea_a7ecc31ede74.md). Its possible use is to construct and reprove an actual-rank comparison beyond two tests; that extension is an explicit missing proof step. In particular, this round does not supply covariance or Poincare conditions for arbitrary FDP tilts, justify a free-rank substitution, or replace BH by an empirical threshold envelope.
