---
type: search_round
title: >-
  Round 5: finite-direction posterior entropy excludes bounded-direction
  counterexample sequences
target_asset: gaussian_bh_mixed_coherence_trace_budget
mode: refute
round: 5
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - cand_gaussian_bh_mixed_coherence_trace_budget_r5_s1_antipodal_null_tails
  - cand_gaussian_bh_mixed_coherence_trace_budget_r5_s1_three_null_directions
  - >-
    cand_gaussian_bh_mixed_coherence_trace_budget_r5_s1_vanishing_antipodal_block
  - cand_gaussian_bh_mixed_coherence_trace_budget_r5_s2_equilateral_three_nulls
  - cand_gaussian_bh_mixed_coherence_trace_budget_r5_s3_antipodal_rank_jump
statement_digest: 3c4f7eca379603e53ffd48c73869d12508d38f68f5f792a85af33304907ad513
performed_by: unknown
created_at: '2026-11-08T10:32:59.773Z'
extension_version: 0.0.4
---

## Obstructions

- **Every bounded number of distinct oriented true-null directions has a uniform square-root obstruction, even with arbitrarily many tests or alternative directions.** The calculation in [the finite-direction candidate](../candidates/cand_gaussian_bh_mixed_coherence_trace_budget_r5_s1_three_null_directions.md) is not limited algebraically to three directions. For any finite number $k\ge1$ of distinct oriented true-null vectors, on FDP support write $\alpha_g$ for their actual selected-null proportions and $\eta=H/h(u_R)$. An auxiliary terminal label with probabilities $p_g=\eta\alpha_g$, $p_0=1-\eta$ and marks $c_g=w_g/H$, $c_0=0$ has conditional mean exactly $B/f$. It adds no Brownian information and changes neither the FDP tilt nor the actual largest BH crossing. The candidate first derives innovation Brownian motion, the bounded-mark martingale energy, absolute trace and drift integrability, and the endpoint identity. Finite posterior-label entropy then gives score energy $2I(J;G)\le2\log(k+1)$, while covariance factorization of $K_t$ gives integrated mark variance at most $(1-x)/H^2$. Consequently

  $$
  |M|\le\frac FH\sqrt{2\log(k+1)(1-x)},\qquad F\le kq.
  $$

  The union bound uses the necessary event $w_g\cdot G\ge U$ for a rejection of any nonpositive-mean true null in direction $w_g$. Thus for every fixed $k$, uniformly over arbitrary finite $N,d$, singular covariance, conservative null means, alternative means and geometry, multiplicities and actual-rank cascades,

  $$
  M_+\le\frac{k}{3}\sqrt{2\log(k+1)}\,q\sqrt{1-x}
  \quad\text{for }0<q\le\overline\Phi(3).
  $$

  In particular $k\le3$ gives $M_+\le2q\sqrt{1-x}$. The same estimate forces $M=0$ when $1-x=0$. An unbounded ratio to the proposed mixed-budget right-hand side therefore requires unbounded true-null direction count; increasing only $N$, covariance rank, dimension, alternative complexity or rank-cascade complexity while keeping $k$ bounded cannot suffice. This is the round's reconstructed search obstruction, not a native-approved theorem or the unrestricted budget. Its proof-step form is saved as [Randomized terminal radial marks turn finite-direction posterior entropy into a square-root trace bound](../ideas/idea_ad465777a60a.md); the search consequence already appears in [the finite-direction observation](../ideas/idea_0e8aa4e76eba.md).

- **Unequal antipodal all-null blocks retain their deficit even as one block's proportion vanishes arbitrarily fast.** For every pair of positive multiplicities, the exact BH support consists of two opposite tails with masses $qw$ and $q(1-w)$, so $F=q$. In [the vanishing-block calculation](../candidates/cand_gaussian_bh_mixed_coherence_trace_budget_r5_s1_vanishing_antipodal_block.md), the weighted logarithmic cutoff gaps yield $\operatorname{Var}_Q(B/f)\le(18/7)(1-x)$; the established innovation identity therefore gives $M_+\le\sqrt{18/7}\,q\sqrt{1-x}$. The disappearing minority weight occurs on both sides, so a vanishing fixed-gap argument is repaired by the weighted gap. This is a scoped independent calibration of the finite-direction obstruction above, not additional coverage beyond its $k=2$ family.

- **Fixed equilateral cancellation and an internal antipodal actual-rank jump have enough rank-cutoff deficit in their checked families.** The exact zero-mean equilateral triple has no rank-three region, and its rank-two vector marks cancel enough that $1-x\ge[(18/11)\log3]/h(\overline\Phi^{-1}(q/3))^2$; [its calculation](../candidates/cand_gaussian_bh_mixed_coherence_trace_budget_r5_s2_equilateral_three_nulls.md) gives $M_+\le3q\sqrt{1-x}$. For every conservative shift $c>A-L$ in the rank-one triple $(G,G-c,-G)$, including collapsing rank-one bands, [the antipodal jump calculation](../candidates/cand_gaussian_bh_mixed_coherence_trace_budget_r5_s3_antipodal_rank_jump.md) establishes the actual rank-one/rank-two split and a uniform cutoff gap from the reference rank three, giving $M_+\le C_*q\sqrt{1-x}$ with the displayed finite family constant. Each candidate establishes absolute integrability and endpoint agreement before using trace representations. These are scoped calibrations already subsumed by the finite-direction certificate ($k=3$ and $k=2$ respectively), not independent coverage of unbounded-direction models.

- **The exact antipodal two-null tail model is a preserved repeat and contributes no new coverage.** The file [the round-five exact antipodal pair](../candidates/cand_gaussian_bh_mixed_coherence_trace_budget_r5_s1_antipodal_null_tails.md) repeats the previously tested round-one exact pair. Its positive trace is absorbed by the rank-one cutoff deficit, but neither a new model family nor a new unbounded-ratio mechanism was obtained. The file is retained unchanged and is not counted as a fifth new family.

## Limitations

- No admissible counterexample was found. The target remains draft; this round does not prove the unrestricted mixed budget or a main FDR upper bound, and none of these search calculations is represented as native-approved.
- The finite-direction estimate has a complexity-dependent coefficient $k\sqrt{2\log(k+1)}/H$. It excludes every bounded-$k$ unbounded-ratio sequence, but gives no universal constant when the true-null direction count grows with $q^{-1}$. Unbounded direction count is necessary for an unbounded-ratio sequence, not sufficient for a violation. It need not require growing covariance rank: arbitrarily many distinct oriented vectors can occur in a fixed dimension of at least two.
- Unbounded numbers of nearly aligned but unequal directions, many cancelling direction groups, unrestricted multi-direction mixed-label positive-trace interactions, and rank cascades coupled to growing directional complexity remain unresolved. No compression by angle, covariance rank, effective dimension or approximate direction grouping was justified. Each fixed finite instance falls under the finite-label inequality with its own $k$; the unresolved requirement is uniformity over the full sequence.
- The round neither establishes necessity of the entropy-linear term nor determines whether it absorbs the growing finite-label entropy. The selected-index entropy observation [idea_96ead5c9a062](../ideas/idea_96ead5c9a062.md) is a separate draft calculation, not an independently checked candidate obstruction in this round; its uncontrolled rank term and any Gaussian-channel or Gaussian-mixture extension are not treated as resolved.
- Well-posedness, absolute trace integrability and endpoint agreement were reconstructed within the candidate arguments before estimates were used. They are recorded here as supporting calculations with the indicated finite-model scope; this summary does not create an approved general result or replace the target's required proof and independent verification.
