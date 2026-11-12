---
type: idea
title: >-
  Shell-only order program: Gaussian-averaged transversality of the count
  process at the BH line
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_two_sided_universal_order_upper
  - gaussian_bh_one_sided_free_central_window_core
  - directional_entropy_one_sided_fdr_bound
tags:
  - strategic-brainstorm-20261108
  - shell-program
  - anti-hugging
  - coarea
  - anti-concentration
  - rank-1-of-8
---

Strategic direction from the 8 November 2026 cross-field brainstorm (ranked 1 of 8 by success probability times payoff). UNPROVED; no statement is changed.

Notation (as in the plans): $U=\overline\Phi^{-1}(q)\approx\sqrt{2\log(1/q)}$, $u_k=\overline\Phi^{-1}(qk/N)$, $h=\phi/\overline\Phi$, $k(w)=N\overline\Phi(w)/q$ (the BH line in level space), $N(w)=\#\{j:T_j\ge w\}$, $L=u_R$ the realized BH level, $M(w)=N^{-1}\#\{i\in I_0:T_i\ge w\}$. Exact identity (routine, from $N(u_R)=R$ by maximality of the rank): on $\{R\ge1\}$, $\mathrm{FDP}=V/R=q\,M(L)/\overline\Phi(L)$, so $\mathrm{FDR}/q=\mathbb E[M(L)/\overline\Phi(L)]$ with the convention $0$ at $R=0$.

1. Core idea and origin. The approved [free central window core](gaussian_bh_one_sided_free_central_window_core) gives $\mathrm{Ce}\le q\pi_0(\tfrac12+U/\sqrt{2\pi})$ for every multifactor representation, so the universal order target is EQUIVALENT to the pooled shell inequality $\mathrm{Sh}\le Cq(1+U)$, where $\mathrm{Sh}$ sums over nulls whose standardized factor projection $Y_i$ exceeds $U$. The failed pooled-shell plan plan_gaussian_bh_one_sided_free_center_pooled_shell_20261106 established (its Progress, bound RS) that the shell gain of a null block $g$ of size $n_g$ at level $w$ is paid only when the count of the OTHER coordinates hugs the BH line, $k(w)-n_g\le N_{-g}(w)<k(w)$, at $g$'s tilt level; its failure was a counterfactual budget across heterogeneous blocks. Proposal: bound the pooled hugging functional directly by a Gaussian-averaged transversality (coarea) argument instead of counting crossings, with a dichotomy. (a) Flat backgrounds (counts insensitive to $Z$, the LLN regime): the ratio $w\mapsto\sum_j\overline\Phi(w-\theta_j)/\overline\Phi(w)$ of an expected count to the line should be log-convex in $w$ when all $\theta_j>0$, hence crosses any constant level at most twice; so the hugging set has length $O(n_g/(k(w)\,\bar\theta))$ in $w$, contributing $o(1)$ after weighting by $h(w)$. (b) $Z$-sensitive backgrounds: the time the count spends within $n_g$ of the line is controlled by its transversal speed through the coarea formula, and the dimension-free Gaussian total variation bound for counts of half-space indicators recorded in idea_3e5a62570bb0 ($\mathbb E\|\nabla B_{\eta,t}\|\le N^{-1}\sum_{\rm alt}\phi(z_t-\theta_j)\le\pi_1\phi(0)$) is the right speed estimate. This upgrades the MLR-rigidity heuristic idea_a4ba452bf4a7 to a program. Discipline of origin: geometric measure theory (coarea) plus Gaussian anti-concentration (Chernozhukov-Chetverikov-Kato style) plus convexity.

2. Literature (read at abstract/snippet level, links verified): Chernozhukov, Chetverikov, Kato, Comparison and anti-concentration bounds for maxima of Gaussian random vectors, PTRF 2015, https://link.springer.com/article/10.1007/s00440-014-0565-9 (anti-concentration depending on dimension only through the expected maximum). Arratia, Goldstein, Gordon, Two moments suffice for Poisson approximations, Ann. Probab. 1989, https://projecteuclid.org/journals/annals-of-probability/volume-17/issue-1/Two-Moments-Suffice-for-Poisson-Approximations--The-Chen-Stein/10.1214/aop/1176991491.full (Chen-Stein with Stein factor $1/\lambda$, for conditionally independent indicator counts). Littlewood-Offord / Erdos anti-concentration for Bernoulli sums: classical, link not verified. Project sources: plan_gaussian_bh_one_sided_free_center_pooled_shell_20261106 (RS bound and the exact needed pooled inequality), idea_a4ba452bf4a7, idea_3e5a62570bb0, idea_cd01eda5d536 (exchangeable-block case believed provable).

3. First testable propositions. (AH-flat) For any finite set of means $\theta_j>0$, the function $w\mapsto\log\sum_j\overline\Phi(w-\theta_j)-\log\overline\Phi(w)$ is convex on $[U,\infty)$. Reduction: its derivative is a mixture of $h(w)-h(w-\theta_j)$; convexity follows if the normal hazard $h$ is convex (to be checked first; Sampford 1953 gives $0<h'<1$, convexity must be verified or replaced by a one-sided statement on $[U,\infty)$). Negative-mean background terms are each at most $\overline\Phi(w)\le(q/N)k(w)$ and must be shown negligible for hugging within $n_g$. (AH-main) The pooled hugging functional
$$
\mathcal A=\sum_g\frac{n_g}{N}\,\mathbb E\int_U^\infty h(w)\,\mathbf 1\{k(w)-n_g\le N_{-g}(w)<k(w)\}\,dw\le C(1+U)
$$
uniformly over finite models and block decompositions of the nulls into direction clusters. Falsification: a heterogeneous block design (remote numerics only) or an analytic family with $\mathcal A/(1+U)\to\infty$ as $q\downarrow0$; the clone one-direction model gives $\mathcal A\approx\pi_0\log(1/\pi_0)$, which is consistent.

4. Why it bypasses the recorded obstacles. Obstacle 1 (every route ends in an exact identity whose remainder is the unknown FDR): nothing is differentiated here; the shell is bounded by an inequality on the MEASURE of the hugging set, and two external inputs enter (convexity of the flat ratio; anti-concentration of $Z$-sensitive counts), neither of which is available from integration by parts in a calibrated variable. Obstacle 2a (crossing envelope $N^2/4$ versus one real rank jump): the deterministic envelope is replaced by the expected transversal crossing measure, which weights each potential crossing by its Gaussian density rather than counting it. Obstacle 2b (false coherence certificate; low-coherence trace of order $qU$): no coherence quantity is used; $\mathcal A$ is allowed to be of order $U$. Obstacle 2c (cell conditional-mean term $K$): no convex cells. Obstacle 2d (Cauchy-Schwarz loses $\sqrt d$ and a $q$ factor): dimension enters only through the total-variation bound $\pi_1\phi(0)$, which is dimension-free.

5. Failure criterion. Abandon if (i) $h$ is not convex and no replacement convexity holds on $[U,\infty)$, so flat backgrounds can cross the line unboundedly often; or (ii) a design with $\mathcal A\gg U$ but $\mathrm{FDR}\le CqU$ is found (then the hugging functional is not the right majorant of $\mathrm{Sh}$); or (iii) the coarea step cannot be made dimension-free.

6. Payoff: full order bound if (AH-main) holds; partial result (block classes with bounded heterogeneity, extending idea_cd01eda5d536) otherwise.
