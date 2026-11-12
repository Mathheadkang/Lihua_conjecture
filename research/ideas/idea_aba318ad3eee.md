---
type: idea
title: >-
  Necessary sub-conjecture: one-sided Simes probability under arbitrary Gaussian
  correlation is O(q)
status: resolved
idea_kind: conjecture
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_two_to_one_signed_duplication
tags:
  - strategic-brainstorm-20261108
  - simes
  - global-null
  - necessary-condition
  - gram-dilution
  - local-numerics
  - rank-6-of-8
resolved_by: gaussian_simes_one_sided_uniform_linear_bound
---

Strategic direction from the 8 November 2026 brainstorm (ranked 6 of 8): a clean necessary condition for the order target, a cheap refutation test, and a standalone theorem candidate. Statement believed true; not a current goal.

1. Statement. Under the global null all $\theta_i\le0$; by the monotone coupling $T_i\le T_i-\theta_i$ the rejection count is largest at $\theta=0$, so take $T\sim N(0,\Sigma)$, $\Sigma\in\mathcal C_N$ arbitrary (singular allowed). Then $\mathrm{FDR}=\mathbb P(R^{(1)}_q\ge1)=\mathbb P(\exists k\le N:\ T_{(k)}\ge u_k)$, the one-sided Simes rejection probability. Conjecture (SIMES-G): $\sup_N\sup_{\Sigma\in\mathcal C_N}\mathbb P_\Sigma(R^{(1)}_q\ge1)\le Cq$ for $0<q\le q_0$, with universal $C$. The order target implies the weaker $\le C_1q\sqrt{\log(1/q)}$, so a Gaussian global-null family with $\mathbb P/\!\big(q\sqrt{\log(1/q)}\big)\to\infty$ would refute the current target outright. Known: nonnegative correlations give PRDS and $\le q$ (Benjamini-Yekutieli 2001; Sarkar 1998 for MTP2; classical, links not verified); negative correlations are anticonservative but mildly so for $N=2$ (Hochberg-Rom 1995, Samuel-Cahn 1996; Block, Savits, Wang; Finner, Roters, Strassburger, On the Simes test under dependence, Stat. Papers 2017, https://ideas.repec.org/a/spr/stpapr/v58y2017i3d10.1007_s00362-015-0725-8.html , all read at snippet level); for arbitrary non-Gaussian dependence the sharp bound is $qH_N$ (Guo, Rao 2008, https://www.sciencedirect.com/science/article/abs/pii/S0378375808000165), attained by a staircase coupling. A November 2026 preprint on exact Simes inequalities for two-sided Gaussian tests, https://arxiv.org/html/2611.02513 , states (snippet) that the two-sided arbitrary-covariance case is open; the one-sided arbitrary-covariance magnitude appears open as well (not verified exhaustively). Exact checks: the antipodal pair $T_2=-T_1$ gives exactly $q$; disjoint clone blocks of sizes $k$ give $\sum_k qk/N=q$; the rank-one model gives $\le q$.

2. Why Gaussian should be $O(q)$ ("Gram dilution"). The Simes event is $\{\exists w\ge U: N(w)\ge k(w)\}$, a large deviation of the exceedance count by the factor $1/q$ at some level. A Guo-Rao staircase needs blocks $K_k$ of size $k$ with all members above $u_k$ on nearly disjoint events of probability about $qk/N$; disjoint clone blocks give exactly $q$ in total, and overlapping blocks share Gaussian modes, so a coordinate in two modes has loading $\le1/\sqrt2$ on each and the joint exceedance probability drops to order $(qk/N)^2$. The BH line's log-concavity (rank $xN$ needs level $U+\log(1/x)/U$, of probability exactly $qx$) is what makes self-sustained null ranks cost $q$ in total.

3. First testable propositions. (GD) For unit vectors $v_1,\dots,v_N$ and each $k$: $\{N(u_k)\ge k\}\subseteq\{\exists K,|K|=k:\ \mathrm{mean}_K T\ge u_k\}$, where $X_K=\mathrm{mean}_KT$ has $\mathrm{Var}X_K=\mathbf 1^\top\Sigma_K\mathbf 1/k^2\le1$; bound $\mathbb P(\sup_K X_K\ge u_k)$ dimension-free by chaining/Sudakov for the family of $k$-subsets with the Gram metric, then combine the levels $k$ through the largest-rank structure (first crossing) rather than a union bound, to avoid the harmonic series. (Numerics, local, short, at most 7 workers) $N\le8$: maximize $\mathbb P_\Sigma(\text{Simes})$ over $\Sigma\in\mathcal C_N$ by random restarts plus local ascent at $q\in\{0.1,0.05,0.01\}$ (Genz-type integration or Monte Carlo with common random numbers); the question is whether $\max\mathbb P/q$ grows with $N$ beyond its $N=2$ value. Test families: antipodal-pair blocks, equi-negative correlation $-1/(N-1)$, signed duplications as in the approved [two-to-one signed duplication](gaussian_bh_two_to_one_signed_duplication).

4. Relation to the recorded obstacles. No masks, no flux identities, no cells, no coherence: a pure Gaussian-geometry statement about exceedance counts versus the line $k(w)$, to which anti-concentration and comparison tools apply directly; also the natural first testbed for the shell-program ideas.

5. Failure criterion. If the small-$N$ numerics show $\sup_\Sigma\mathbb P/q$ growing like $\log N$ at fixed small $q$, the order target itself is in doubt and the family must be scaled up (remote) as a counterexample candidate; if $\max\mathbb P/q$ stays bounded, record as supporting evidence and attempt (GD).

6. Payoff: necessary check; a standalone theorem of independent interest (one-sided Simes under arbitrary Gaussian dependence); tools reusable for the shell.
