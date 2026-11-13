---
type: idea
title: >-
  Schur-square oscillation test: no accumulation of downward variation across
  hierarchical levels in nonnegative, multiscale-clone or signed-tree models
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_simes_schur_square_sparse_variation_budget
  - gaussian_simes_schur_variation_few_block_compression
  - gaussian_simes_clone_block_schur_variation_bound
  - gaussian_simes_one_sided_uniform_linear_bound
tags:
  - schur_square_path
  - numerical_experiment
  - oscillation
  - simes
  - global_null
---

Numerical observation from a side chat (13 November 2026), requested by the researcher. It tests the oscillation obstruction named in [the Schur-square tensor-lift idea](idea_6b48b2fe25e1.md): does the downward variation $\mathcal V_-(f_{q,\Sigma})$ of $f_{q,\Sigma}(t)=F_q((1-t)\Sigma+t\,\Sigma\circ\Sigma)$ accumulate when the number of hierarchical levels grows? Nothing here is a proof. No new lemma is proposed, and no research-loop stage was advanced.

## Method

- **Estimator.** Write the scores as $Y=a_tW+X_t$ with a common factor $W$ that loads $+a_t>0$ on every coordinate. The Simes event is an up-set, so conditional on $X_t$ it is a half-line in $W$, and $\mathbb P(\text{reject}\mid X_t)=\overline\Phi\bigl(\min_k(u_k-X_{t,(k)})/a_t\bigr)$, with $u_k=\overline\Phi^{-1}(qk/N)$ and clone multiplicities entering through cumulative ranks.
  - For ultrametric (tree) models $W$ is the root factor.
  - For general $\Sigma$, including signed ones, take $a_t^2=0.9/(\mathbf 1^{\mathsf T}R_t^{-1}\mathbf 1)$, so that $R_t-a_t^2J\succeq0$.
  - Common random numbers make each sample path continuous in $t$.
- **Checks of the estimator.**
  - Against exact two-clone quadrature (bivariate integral) at $q=0.1$: agreement within $1.4$ standard errors at $2\cdot10^6$ samples.
  - Against a plain-indicator Monte Carlo with an independent eigen-square-root sampler. One 2-to-5 SE gap in signed models at $t=0$ was traced to the small common loading $a_0=0.13$; with $2\cdot10^6$ samples the two estimators agree.
- **Path resolution.** Adaptive bisection on $t$ wherever the midpoint deviates from linear interpolation by more than $2\cdot10^{-5}$.
- **Honest lower bound.** Choose the decreasing runs on one sample set and evaluate their signed decrease on an independent set; this is unbiased for a quantity $\le\mathcal V_-(f)$. The plain grid $\mathcal V_-$ of a Monte Carlo mean is biased upward by Jensen, and that bias produced every apparent oscillation below.
- **Scripts and raw output** are in the untracked folder `research-local/schur_oscillation_numerics_20261113/`.

## Results (full Simes event, $q=0.1$ unless stated)

Every value below is $\mathcal V_-$ divided by $q$.

| model class (levels or size) | max $\mathcal V_-/q$ found | profile shape |
|---|---|---|
| one factor, $N=10\ldots10^5$ | $0.085$ | monotone descent |
| ultrametric clone trees, optimized, depth $1,2,3$ ($K=2,4,8$ groups) | $0.034,\ 0.053,\ 0.065$ | monotone |
| caterpillar multiscale clone groups, optimized, $L=2,4,8,16$ | $0.045,\ 0.057,\ 0.067,\ 0.073$ | monotone, $\mathcal V_+=0$ |
| geometric hierarchies, depth $1$–$5$, up to $N=7776$ | $\le0.004$ | monotone increasing |
| two-level transition test, $N=10^4$, within-group correlation crossing $\log b_1/\log N$ | $0.000$ | no dip at the crossing |
| random ultrametric scan (400 models, depth $2$–$4$) | $0.047$ | largest returning oscillation $0.005$ (noise level) |
| signed antipodal trees, optimized, depth $1,2,3$ | $0.178,\ 0.177,\ 0.170$ | one descent after the negative block crosses zero |
| signed staggered trees, depth $2$–$6$, zero crossings at distinct $t_d=1/(1-\rho_d)$ | $\le0.027$ | no stacking |

- **Saturation, not accumulation.** In every depth sweep the optimizer collapses all levels onto a single near-clone equicorrelated block (or onto one antipodal pair of clusters). The growth in $K$ in the second and third rows is the one-factor curve filling in towards about $0.09q$.
- **One-factor descent rate.** $\max\bigl(-\tfrac{dF}{d\log(1-\rho)}\bigr)/q$ equals $0.122,\ 0.127,\ 0.129,\ 0.129$ for $N=10^2,10^3,10^4,10^5$. Since $1-\rho$ grows by at most a factor $1+\rho\le2$ along the path, this caps the nonnegative one-factor variation at about $0.129\log2\approx0.09q$.
- **Spurious oscillations.** Two optimizer "oscillations" (depth 2: $0.017q$; depth 3: $0.013q$, both on the optimizer's own samples) are monotone on fresh samples, so they were overfitted noise.
- **Exact check of the largest signed case** (antipodal clone groups, $\rho=-0.961$, sizes $5265$ and $5541$, by bivariate quadrature):
  - $f(0)=q$ exactly, and $\mathcal V_+\le0.0063q$.
  - $\mathcal V_-/q$ equals $0.178,\ 0.172,\ 0.157,\ 0.141,\ 0.112$ at $q=10^{-1},10^{-2},10^{-3},10^{-4},10^{-6}$.
  - A Monte Carlo rise towards $0.27$ at $q=10^{-3}$ was noise.
- **Sparse event $S_q$** (the sparse-budget lemma):
  - Near-clone one-factor profiles become increasing ($\mathcal V_-=0$), because breaking clones moves mass into the sparse ranks.
  - The antipodal $\mathcal V_-$ is $0.07q$ at $q=0.1$ and $0.03q$ at $q=0.01$.

## Uniform $Cq$ versus the fixed-level condition

- **No counterexample to either form** was found in these classes, so no counterexample needed independent verification. The largest values, $\mathcal V_-\le0.18q$, are confirmed by an honest lower bound and, in the signed case, by exact quadrature.
- **The data are consistent with the stronger uniform form** $\mathcal V_-\le Cq$ with $C\approx0.2$: $\mathcal V_-/q$ is flat or decreasing in $q$ and in $N$, and does not grow with depth.
- **What a failure would require.** Nonnegative models satisfy $0\le f\le q$ and $\mathcal V_-=f(0)-f(1)+\mathcal V_+$.
  - Breaking the uniform $Cq$ needs unboundedly many returning oscillations of size of order $q$.
  - Breaking the fixed-level condition at one $q_*$ needs about $1/q_*$ of them.
  - The observed $\mathcal V_+$ never exceeds the Monte Carlo noise floor.

## Heuristic mechanism (unproved)

- **Nonnegative models.**
  - Decreases of $f$ come only from near-clone pairs breaking. Along the path $1-\rho$ grows by at most a factor $2$, at a nearly uniform rate in $t$, so these decreases are spread over $[0,1]$ at a bounded rate.
  - Increases come from small correlations collapsing ($\rho\to\rho^2$). These can be localized near $t\approx1-\kappa/\rho$, but they do not re-arm further descent.
  - If the descent rate $\max_t(-f')$ were bounded by $Cq$ uniformly, $\mathcal V_-\le Cq$ would follow at once. The numerics support such a bound ($\le0.13q$), but no proof is offered.
- **Signed models.** The extra descent comes only from a negative block increasing through zero to $\rho^2$. A set of mutually strongly negative directions has at most two clusters, so this mechanism does not stack either: the staggered trees in the table show it.

## Limits

- Depth $\le6$ and $K\le16$ groups in the optimizers; $N\le10^5$ coordinates.
- GREM-type phase transitions, which need $\log N\to\infty$, are tested only at $N=10^4$.
- Mixed-sign models beyond tree sign patterns, simplex frames, and the 8-group nonnegative factor search (stopped before finishing) remain untested.
