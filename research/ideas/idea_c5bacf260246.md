---
type: idea
title: >-
  Replace the directional-entropy union bound by a multi-scale chaining bound on
  null directions
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - directional_entropy_one_sided_fdr_bound
  - gaussian_bh_one_sided_free_central_window_core
  - spherical_isotropic_population_bh_bound
tags:
  - strategic-brainstorm-20261108
  - chaining
  - directional-entropy
  - multiscale
  - structured-class
  - rank-3-of-8
---

Strategic direction from the 8 November 2026 brainstorm (ranked 3 of 8). UNPROVED.

1. Core idea and origin. The approved [One-sided Gaussian BH bound from oriented null directional entropy](directional_entropy_one_sided_fdr_bound) charges $q\sum_h\pi_h\log(1/\pi_h)$: a one-scale union bound over direction groups. The heuristic "a scalar BH level can be tuned to one direction at a time" says this is loose by a factor $U$ in the many-direction regime: for $G$ orthogonal equal null groups with standardized projections $Y_g$, tracking the leader gives total tilt $\frac1G\mathbb E[\max_g e^{Y_g^2/2}\wedge q^{-1}]=\frac1{\sqrt{2\pi}}\int_0^{y_q}\Phi(t)^{G-1}dt\le y_q/\sqrt{2\pi}$ with $y_q=\sqrt{2\log(1/q)}$, i.e. no gain over one direction, while entropy charges $\log G$. Generic chaining (Talagrand) is precisely the technology that turns Dudley-type union bounds into sharp supremum bounds for Gaussian processes indexed by a metric space; here the index set is the set of null directions on the unit sphere with the chordal metric, and the "process" is the tilt $\rho_{r}(L,Y_i)$ at the common level. Program: a tree of groupings at scales $\epsilon_k$, conditional entropies along the tree (entropy chain rule), and the key Lipschitz input: two directions at angle $\delta$ have projections differing by $O(\delta|Z|)$, so their tilts at any common level cannot be separated, and within a coarse group of angular diameter $\delta_H$ the entropy charge should be replaceable by $O(U\delta_H)$.

2. Literature (verified links; read at snippet level): Talagrand, Majorizing measures: the generic chaining, Ann. Probab. 1996, https://projecteuclid.org/journals/annals-of-probability/volume-24/issue-3/Majorizing-measures-the-generic-chaining/10.1214/aop/1065725175.full ; Talagrand, Upper and Lower Bounds for Stochastic Processes (draft), https://people.stat.ucla.edu/ywu/research/documents/BOOKS/TalagrandChaining.pdf ; J. R. Lee, notes on majorizing measures, https://homes.cs.washington.edu/~jrl/cse599wi23/notes/mm2.pdf . Project baselines: the entropy asset; the pooled-shell plan's RS bound (weights $\min\{(b_h-U)/(s_i\sqrt{2\pi}),\log(1/\pi_h)\}$); the approved [spherical isotropic population bound](spherical_isotropic_population_bh_bound) as the continuum sanity check ($O(q\log U)$, far below $qU$).

3. First testable proposition (CH-2, two levels). Coarse groups $H$ with masses $\pi_H$ and angular diameters $\delta_H$; fine groups $h\subset H$ with conditional masses $\pi_{h|H}$. Claim: $\mathrm{FDR}\le q\pi_0(\tfrac12+\tfrac U{\sqrt{2\pi}})+Cq\big[\sum_H\pi_H\log\tfrac1{\pi_H}+\sum_H\pi_H\min\{\sum_h\pi_{h|H}\log\tfrac1{\pi_{h|H}},\ C'U\delta_H\}\big]$, uniformly in all other parameters. The first term is the approved entropy bound at the coarse scale; the new content is the cap $C'U\delta_H$ on the within-group charge. Falsification: a two-level family (one coarse group of diameter $\delta$ split into many fine groups) whose FDR exceeds the display; the cheapest probe is the clone-limit population computation of the approved common-loading framework on a remote server.

4. Why it bypasses the obstacles. Obstacle 1: chaining produces inequalities for suprema, not identities; the external input is the Lipschitz dependence of tilts on the direction, which no flux route uses. Obstacle 2a: no crossing counting. Obstacle 2b: coherence is replaced by angular diameter at the level of tilts; the low-coherence antipodal counterfamily cx_gaussian_bh_entropy_coherence_trace_budget_r3_s1_unbalanced_antipodal_clones has two directions at distance $2$ and is charged by the coarse entropy $\log 2$, consistent with its $O(qU)$ FDR. Obstacle 2c: no cells. Obstacle 2d: the metric is intrinsic; the ambient dimension never appears.

5. Failure criterion. Stop if the within-group charge cannot be bounded by $U\delta_H$ because the tilt's Lipschitz constant in the direction blows up on the shell, or if (CH-2) is never better than the one-scale entropy bound in any example. Note the intrinsic limit: chaining alone cannot be universal (any $m$ directions have $\gamma_2\lesssim\sqrt{\log m}$, unbounded in $m$); universality additionally needs the self-sustaining cap "a direction cluster of mass $\le e^{-CU}$ cannot be tracked beyond level $U+C$". If that cap resists proof, the outcome is a structured class only.

6. Payoff: partial / new structured class (null direction sets of bounded multi-scale complexity, strictly wider than entropy $o(\sqrt{\log(1/q)})$); full order bound only together with the cap.
