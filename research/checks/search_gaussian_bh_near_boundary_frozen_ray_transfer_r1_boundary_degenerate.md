---
type: search_round
title: >-
  Refute search round 1, slot 1 (boundary and degenerate cases) for the
  near-boundary frozen-ray transfer
target_asset: gaussian_bh_near_boundary_frozen_ray_transfer
mode: refute
round: 1
directions:
  - boundary_degenerate
candidates:
  - >-
    cand_gaussian_bh_near_boundary_frozen_ray_transfer_r1_s1_nonneg_equicorrelated_boundary_nulls
  - >-
    cand_gaussian_bh_near_boundary_frozen_ray_transfer_r1_s1_single_boundary_null_antithetic_alternatives
statement_digest: be073e791d4239baa7b5f7c3e9a5802f0f6c644848af48ae7b3362b87b76b57d
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T08:00:46.953Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Obstructions

- No single instance, and no family with bounded ratio, can refute: the constants are existential and the right side is always at least $A_{\mathrm T}q>0$ (also $\Lambda_{B_q}\geq|B_q|/N$ from $w=0$). A counterexample must be a family along which left/right is unbounded, and since the left side is at most $1$, the family needs $q\,\mathbb E\min\{1/q,\Lambda_{B_q}\}\to0$ relative to the left side and the left side $\gg q$.
- Benjamini-Yekutieli summation (valid for super-uniform nulls, any dependence): $\mathbb E[V_{B_q}/(R\vee1)]\leq q\,(|B_q|/N)\,H_N$. So every family with $N$ bounded fails (this covers $N=1$, $N=2$ antithetic pairs, and all small-dimensional degenerate $\Sigma$), and any counterexample needs $N\to\infty$ with $|B_q|H_N/N\to\infty$. A single near-boundary null, or $|B_q|=O(N/\log N)$, can never refute.
- Nonnegative covariances (all of $\Sigma_{ij}\geq0$, including $\Sigma=I$ and the rank-one $\mathbf 1\mathbf 1^{\mathsf T}$) give PRDS one-sided p-values, hence the left side is at most $q|B_q|/N\leq q$: every such family fails NOT. A counterexample needs negative correlations involving the near-boundary nulls.
- Pointwise hazard ceiling: on $\{V_{B_q}\geq1\}$ every rejected $i\in B_q$ has $Z_i\geq T_i\geq x^*=\overline\Phi^{-1}(qR/N)\geq U$, so taking $w=x^*$ and $\overline\Phi(x)\geq\phi(x)\,x/(1+x^2)$ gives $\Lambda_{B_q}\geq\mathrm{FDP}_{B_q}/(\sqrt{2\pi}(x^*+1/x^*)q)$, hence pointwise $\mathrm{FDP}_{B_q}\leq\sqrt{2\pi}(x^*+1/x^*)\,q\min\{1/q,\Lambda_{B_q}\}$. The ratio left/right is therefore at most of order $\overline\Phi^{-1}(q/N)\approx\sqrt{2\log(N/q)}$; a counterexample must live on events with small $R$ where the near-boundary nulls cross the BH cutoff with overshoot $\ll1/x^*$ while the other near-boundary terms of the field stay negligible.
- Pushing near-boundary nulls toward the band edge $\theta_i\downarrow-a_q$ only hurts a counterexample: their rejection rate at cutoff $U$ drops to about $q e^{-Ua_q}=q/U^2$ while their field contribution (which depends on $Z$ only) is unchanged. Diluting with far-negative nulls outside $B_q$ rescales the problem to level $qm/N$ with the same field term and a larger $A_{\mathrm T}q$ floor.

## Limitations

- No negatively correlated design with $N\to\infty$ and $|B_q|\gtrsim N/\log N$ was examined (for example many independent antithetic pairs or block designs with negative within-block correlation); these are the only families the obstructions above leave open, and they belong to the dependence-structure directions rather than this slot.
- The PRDS step relies on the standard Benjamini-Yekutieli / Blanchard-Roquain argument for super-uniform PRDS nulls; it was used, not re-derived here.
- The q-dependence of $B_q$ (band width $a_q$ against an effective level after dilution) was only argued qualitatively.
