---
type: search_round
title: First-round trace-budget search and scoped entropy-bridge obstructions
target_asset: gaussian_bh_entropy_coherence_trace_budget
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - cand_gaussian_bh_entropy_coherence_trace_budget_r1_s1_antipodal_two_tail
  - cand_gaussian_bh_entropy_coherence_trace_budget_r1_s1_constant_direction
  - cand_gaussian_bh_entropy_coherence_trace_budget_r1_s2_independent_two_test
  - cand_gaussian_bh_entropy_coherence_trace_budget_r1_s2_singleton
  - >-
    cand_gaussian_bh_entropy_coherence_trace_budget_r1_s3_parallel_composite_nulls
statement_digest: 282de99c92b14dd593f40c0583da4cc65ddd227e11dcc3d261ec31f0e3456ce2
performed_by: unknown
created_at: '2026-11-08T07:14:17.795Z'
extension_version: 0.0.4
---

## Obstructions

- In the entire all-null parallel-loading family, with arbitrary finite nonpositive means and the original largest-rank BH rule, the FDP tilt reduces to the halfspace law $Y\ge A$, $A\ge U$. A terminal Mills deficit $\eta=1-H/h(u_R)$ satisfies $1-x\ge\mathbb E_Q\eta$. The product-Itô trace identity and the conditional Brownian-bridge bound on the integrated halfspace drift give $M_+\le(3q/H)(1-x)$. Thus negative means, singular rank-one covariance and arbitrarily small positive FDR within this family do not refute the proposed bound. Constant-field cases, including a single composite null and identical zero-mean copies, have $x=1$ and $M=0$ exactly. The full calculations are retained in [the parallel composite-null candidate](../candidates/cand_gaussian_bh_entropy_coherence_trace_budget_r1_s3_parallel_composite_nulls.md), [the singleton candidate](../candidates/cand_gaussian_bh_entropy_coherence_trace_budget_r1_s2_singleton.md) and [the constant-direction candidate](../candidates/cand_gaussian_bh_entropy_coherence_trace_budget_r1_s1_constant_direction.md).
- In the full independent two-test family with one original composite null and one positive-mean alternative, the exact two-state heat posterior has a pointwise nonpositive spatial Jacobian trace. Hence $M_+=0$, including a diverging positive alternative mean. Independence here is a property of the candidate family, not an assumption of the target lemma; see [the independent two-test candidate](../candidates/cand_gaussian_bh_entropy_coherence_trace_budget_r1_s2_independent_two_test.md).
- For the all-null antipodal model $(G,-G)$, the actual rejection event is $|G|\ge u(q/2)$ and the FDP tilt has two separated tails. Binary posterior information together with the actual tail separation yields the stronger estimate $M\le4q(1-x)$ over the required small-$q$ interval. Disconnected support, singular covariance and the two competing directions in this particular family therefore do not refute the target; see [the antipodal two-tail candidate](../candidates/cand_gaussian_bh_entropy_coherence_trace_budget_r1_s1_antipodal_two_tail.md).

## Limitations

- Five candidates failed their NOT check in this round; no survivor was found. These scoped candidate derivations have not undergone native independent proof verification. This record summarizes their mathematical obstructions and does not approve them as dependencies or prove the target lemma.
- The assertion permits arbitrary universal finite $C$ and a sufficiently small universal $q_0$. One large finite ratio, a positive local interface contribution, or the simultaneous limits $M\to0$ and $x\to1$ do not refute it. A counterfamily must make the normalized positive trace unbounded in every sufficiently small admissible interval, or violate another conclusion of the stated lemma.
- Positive correlation with a diverging alternative mean remains unresolved. [The saved correlated strong-alternative test case](../ideas/idea_19c44519bec3.md) gives exact linear upper and lower comparisons between $1-x$ and a rare one-rejection posterior probability, but has not determined the complete signed trace's matching rate. The independent two-test sign calculation cannot be transferred to this family, and the terminal alternative face alone is not the integrated heat trace.
- No worker supplied a uniform bound for false-null-triggered multi-rank cascades, a general cross-direction conditional drift-bias estimate, or a global cancellation of the linear tangential terms arising at such transitions. The all-null halfspace bridge argument cannot be extended by assuming that an arbitrary FDP tilt is a halfspace law.
- This round does not cover arbitrary growing dimension, large mixed-sign Gram configurations, or all $q$-dependent combinations of negative null means and alternative means. It does not justify Gaussian covariance or Poincaré assumptions for the tilted law, a free-rank substitution, or replacing the actual BH rule by an empirical envelope.
- The proof-like conditional-bridge mechanism is preserved as [a scoped approach idea](../ideas/idea_6d9b9136c320.md). Its proposed use beyond parallel all-null loadings remains an open research step, separate from both the draft trace-budget lemma and the unrestricted main FDR upper bounds.
