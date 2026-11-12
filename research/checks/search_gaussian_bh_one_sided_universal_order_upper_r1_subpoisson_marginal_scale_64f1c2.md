---
type: search_round
title: >-
  Marginal scale obstruction in the main Gaussian upper-bound search after
  sub-Poisson calibration
target_asset: gaussian_bh_one_sided_universal_order_upper
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates: []
statement_digest: 4fe10575d36df3f3f1d7a5d3b02045f11cc1642e336a0a94fe50ce0a9f321484
performed_by: unknown
created_at: '2026-11-11T22:48:19.894Z'
extension_version: 0.0.4
---

## Obstructions

- Every admissible original one-sided true null has a superuniform marginal p-value, including negative null means and singular joint covariance. Writing $z_s=\overline\Phi^{-1}(s)$, for $\theta_i\le0$ one has $\mathbb P(P_i\le s)=\overline\Phi(z_s-\theta_i)\le s$. Consequently the original null count satisfies $\mathbb E[C(s)]\le ms$, where $m=|I_0|$; no sign or independence assumption on covariance is used.
- This marginal statement gives the finite-model harmonic bound $\operatorname{FDR}\le q(m/N)H_N$, with $H_N=\sum_{r=1}^N1/r$, for the same actual BH rank and original null labels. Indeed, the deterministic BH contribution inequality is $\operatorname{FDP}\le C(q)/N+\sum_{r=1}^{N-1}C(qr/N)(1/r-1/(r+1))$; substitution of $\mathbb E[C(s)]\le ms$ gives the bound. This is the marginal Benjamini-Yekutieli scale, not the desired dimension-uniform improvement.
- A refutation of the stated existence of an arbitrary finite universal constant requires an admissible sequence $q_n\downarrow0$ and finite Gaussian models for which $\operatorname{FDR}_n/[q_n\sqrt{\log(1/q_n)}]\to\infty$ after taking a subsequence. The harmonic bound forces $(m_n/N_n)H_{N_n}/\sqrt{\log(1/q_n)}\to\infty$ along that subsequence. In particular $\log N_n/\sqrt{\log(1/q_n)}$ must be unbounded; families with $\log N=O(\sqrt{\log(1/q)})$ cannot refute the order assertion. An isolated example with FDR exceeding $q$, or exceeding a chosen fixed multiple of the proposed scale, does not refute existence of some larger universal constant.
- Fixed dimension and a uniformly bounded number of original true nulls are excluded even if the remaining model parameters vary with $q$. For $m\ge1$, monotonicity of $H_N/N$ gives $(m/N)H_N\le H_m$, so $\operatorname{FDR}\le qH_m$. A bounded $m$ therefore makes the normalized ratio tend to zero as $q\downarrow0$. If $m=0$, FDP is identically zero.

## Limitations

- This first main-target round after approval of the sub-Poisson helper produced no candidate files and no surviving counterexample. All prior rounds, check records, and historical idea files are preserved; no generic marginal-scale idea was recorded again.
- The harmonic necessary condition does not exclude unrestricted $q$-dependent families with sufficiently large dimension and enough original true nulls. It supplies no Gaussian realizability construction attaining that scale and no dimension-uniform upper bound.
- The newly approved conditional sub-Poisson result calibrates the original actual BH rank when its conditional count hypothesis holds. It does not by itself establish that hypothesis for every Gaussian geometry after the entire alternative vector is conditioned on, or bound the resulting averaged calibration cost uniformly at order $\sqrt{\log(1/q)}$.
- Uncovered cases retain arbitrary covariance signs, covariance rank, factor dimension, null-direction count, alternative means, null proportion, and simultaneous growth with $1/q$. The remaining same-actual-rank allocation across general Gaussian geometry is not resolved by this search summary.
- This record uses the current context pack and an explicit marginal calculation. It does not inspect the omitted target proof or historical idea bodies, declare any failed proof inequality a counterexample, or supply a native proof-verification verdict for the main theorem.
