---
type: idea
title: >-
  Structured class: tree-structured (ultrametric) null directions, the
  many-equal-directions regime where entropy fails
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - directional_entropy_one_sided_fdr_bound
  - multifactor_radial_fdr_bounds
  - lei2026_conditional_fdp_bound
  - slow_factor_dimension_one_sided_sharpness
tags:
  - strategic-brainstorm-20261108
  - structured-class
  - ultrametric
  - tree-covariance
  - heavy-path
  - rank-7-of-8
---

Strategic direction from the 8 November 2026 brainstorm (ranked 7 of 8): the positive-theorem companion of the hierarchical counterexample probe. UNPROVED.

1. Core idea and origin. Hierarchical factor models $T_i=\theta_i+\sum_{\ell\le D}r_\ell Z_{\ell,\mathrm{anc}_\ell(i)}+s_i\varepsilon_i$ (GREM-type: any depth, any branching, ultrametric null Gram matrix) are covered by none of the approved structured results: not one-factor, the factor dimension (number of leaves) is unbounded so the [multifactor radial bounds](multifactor_radial_fdr_bounds) and the [slow factor dimension sharpness](slow_factor_dimension_one_sided_sharpness) do not apply, the [directional entropy bound](directional_entropy_one_sided_fdr_bound) charges $q\mathcal E_0$ with $\mathcal E_0$ up to $\log(\#\text{leaves})\gg U$, and the spherical result needs isotropy. Conjecture: the order bound holds uniformly over this class. The regime of $G\to\infty$ equal leaf groups is exactly where the entropy union bound is loose by a factor $U$ (leader-tracking computation: $\frac1G\mathbb E[\max_ge^{Y_g^2/2}\wedge q^{-1}]\le y_q/\sqrt{2\pi}$), so a proof here is the first genuinely "many heavy directions" theorem. Route: conditional independence given the leaf factors gives Lei's leave-one-out bound; the tree supplies a root-to-leaf filtration along which "which branch the level tracks" is a stopping-type variable; at each node the scalar level can follow at most one child's factor, light children are charged by mass-weighted entropy and the followed child recursively, with the Bovier-Kurkova cascade picture identifying the followed child as the carrier of the extremal process. Warning recorded: naive telescoping of the light-children entropies along the heavy path reproduces the full entropy; the needed extra input is the self-sustaining cap (a cluster of mass $\pi$ can be tracked only on a level range of length $\log(1/\pi)/U$, which costs $\pi\log(1/\pi)$, and clusters of mass $\le e^{-CU}$ cannot be tracked beyond level $U+C$ at all).

2. Literature (verified links; snippet level): Bovier, Kurkova, Derrida's generalised random energy models 1, 2 (Ann. IHP 2004), https://www.numdam.org/article/AIHPB_2004__40_4_439_0.pdf , https://www.numdam.org/article/AIHPB_2004__40_4_481_0.pdf ; Kistler, https://arxiv.org/abs/1412.0958 ; Gaussian comparison notes (Slepian, Sudakov-Fernique, Gordon), https://www.math.ucla.edu/~biskup/PIMS/PDFs/lecture5.pdf and https://math.iisc.ac.in/~manju/GP/4-comparison%20theorems.pdf . Caveat established while brainstorming: Slepian/Gordon control maxima and orthant probabilities, but the count events $\{N(w)\ge k\}$ are symmetric threshold events that are not monotone in correlations, and Gordon's row/column conditions collapse for the subset-min process, so comparison inequalities alone cannot carry this; they are at best a tool for the global-null sub-conjecture. Project: idea_cd01eda5d536 (copy budget plus self-count for exchangeable blocks).

3. First testable proposition (TREE-2). Depth two, root factor $Z_0$, $G$ equal leaf groups with factors $Z_g$, nulls $r_0Z_0+r_1Z_g+s\varepsilon$ (mean $0$ or negative), alternatives arbitrary unit-norm combinations of $(Z_0,Z_g,\text{own noise})$ with arbitrary means. Claim: $\mathrm{FDR}\le Cq(1+U)$ uniformly in $G$, $r_0,r_1,s$, means and alternatives. Sub-steps: exchangeable groups first (idea_cd01eda5d536's copy budget plus self-count plus Berry-Esseen anti-concentration of the sum of independent group counts given $Z_0$), then geometric masses $\pi_g\propto2^{-g}$, then arbitrary depth by induction.

4. Why it bypasses the obstacles. Obstacle 1: the tree filtration localizes the tracking to one branch per realization; the estimate is an inequality on which branch is followed, not an identity in a calibrated variable. Obstacle 2a: no crossing counts; anti-concentration is for sums of conditionally independent group counts, dimension-free in $G$. Obstacle 2b: no coherence certificate; the tree metric replaces coherence. Obstacle 2c: no cells. Obstacle 2d: no matrix Cauchy-Schwarz.

5. Failure criterion. If (TREE-2) for $G\to\infty$ equal groups cannot be proved by any pooled argument and the counterexample probe's numerics grow, this family IS the counterexample; if every proof attempt needs $\log G$, it is the entropy bound again (stop).

6. Payoff: a new structured class strictly beyond directional entropy (the first many-heavy-directions theorem) and the natural testbed for the chaining and nested-level-set ideas; a stepping stone, since nets of directions behave like trees at each scale.
