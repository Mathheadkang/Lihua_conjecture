---
type: idea
title: >-
  PRDS-defect accounting: an exact signed Abel identity, a rank-drop coupling
  that isolates negatively correlated partners, and a negative-correlation-mass
  lemma to test
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_finite_signed_p_path_identity
tags:
  - side-chat-20261111
  - carrier-cap
  - prds-defect
  - rank-drop-coupling
  - unproved-key-lemma
---

Side-chat proposal of 11 November 2026, companion to idea_420827cf1b7e (capped conditional-PRDS lemma) and idea_121635a0e4a9 (carriers and regime map). The identity and the coupling inequality are elementary and still need native verification. The mass lemma (NM) is a conjecture to be tested first; it may be false as stated.

## Exact identity for one null, any joint law

Fix a null $i$, $t_k=qk/N$, $F_i(t)=\mathbb P(p_i\le t)$, $a_{i,k}=F_i(t_k)/k$ with $a_{i,0}=0$, and $\beta_k(t)=\mathbb P(R\ge k\mid p_i\le t)$ with $\beta_{N+1}\equiv0$. Put
$$
\delta_{i,k}=\beta_{k+1}(t_{k+1})-\beta_{k+1}(t_k)\qquad(1\le k\le N-1).
$$
Then
$$
\mathbb E\Big[\frac{\mathbf 1\{i\in\mathcal R\}}{R\vee1}\Big]=\sum_{k=1}^{N}(a_{i,k}-a_{i,k-1})\,\beta_k(t_k)+\sum_{k=1}^{N-1}a_{i,k}\,\delta_{i,k},
$$
and, wherever the conditional probabilities are defined,
$$
\delta_{i,k}=\Big(1-\frac{F_i(t_k)}{F_i(t_{k+1})}\Big)\Big[\mathbb P(R\ge k+1\mid t_k<p_i\le t_{k+1})-\mathbb P(R\ge k+1\mid p_i\le t_k)\Big].
$$
PRDS on $i$ is the statement $\delta_{i,k}\le0$ for all $k$. In general, when $k\mapsto a_{i,k}$ is unimodal,
$$
\mathrm{FDR}\le\sum_{i\in I_0}\Big\{\max_ka_{i,k}+\sum_{k}a_{i,k}(\delta_{i,k})_+\Big\}.
$$
The same holds conditionally on a carrier. A residual that is not exactly PRDS on the nulls therefore costs only the defect sum $\mathcal D=\sum_{i\in I_0}\sum_ka_{i,k}(\delta_{i,k})_+$. This is a different bookkeeping from the [finite signed conditional p-path identity](../assets/gaussian_bh_finite_signed_p_path_identity.md): positive dependence is absorbed by monotonicity before any signed term appears, and the signed term involves negative partners only.

## Rank-drop coupling for Gaussian models

Work in the pivotal frame of the null $i$: $T_j=\theta_j+\rho_{ij}g+\xi_j$ for $j\ne i$, where $g=G_i$ is independent of $\xi$. Let $R_i(\cdot)$ be the forced rank obtained by setting $p_i=0$; it is nondecreasing in the other statistics, and on $\{p_i\le t_{k+1}\}$ the events $\{R\ge k+1\}$ and $\{R_i\ge k+1\}$ coincide. For $g\le g'$ define $T^{\mathrm{mix}}$ by evaluating the coordinates with $\rho_{ij}\ge0$ at $g'$ and those with $\rho_{ij}<0$ at $g$. Then $T^{\mathrm{mix}}\ge T(g)$ and $T^{\mathrm{mix}}\ge T(g')$ coordinatewise, and $T^{\mathrm{mix}}$ differs from $T(g')$ only in the negatively correlated coordinates, which are lower in $T(g')$ by $|\rho_{ij}|(g'-g)$. Hence for every $k$
$$
\mathbb P\{R_i(T(g))\ge k+1\}-\mathbb P\{R_i(T(g'))\ge k+1\}\le\mathbb P\{R_i(T^{\mathrm{mix}})\ge k+1>R_i(T(g'))\}.
$$
Taking $g$ in the slab $[c_{k+1},c_k)$ and $g'$ distributed as $G_i$ given $G_i\ge c_k$ bounds the bracket in $\delta_{i,k}$. For a uniform null,
$$
\sum_ka_{i,k}(\delta_{i,k})_+\le\frac qN\sum_{k}\frac1{k+1}\,\mathbb P\{R_i(T^{\mathrm{mix}}_k)\ge k+1>R_i(T^{\mathrm{low}}_k)\},
$$
the expected logarithmic rank drop caused by lowering the negatively correlated partners of $i$ by $|\rho_{ij}|$ times an overshoot of order $1/c_k$. The right side is zero when $i$ has no negative partner and of order $(q/N)\log N$ for the one-null staircase of idea_75d71c7756b4, where it is tight.

## Lemma to test (NM)

Is there a universal $C$ such that, for every model,
$$
\mathcal D\le C\,\frac qN\sum_{i\in I_0}\sum_{j\ne i}(\Sigma_{ij})_-\ ?
$$
Heuristic. A partner $j$ changes the event $\{R\ge k+1\}$ only if it lies within $|\rho_{ij}|\cdot O(1/c_k)$ above the current threshold. The levels $c_k$ are spaced by about $1/(kc_k)$, so summing with weights $1/k$ integrates the density of $T_j$ once and leaves $|\rho_{ij}|$.

If true, a residual whose negative entries on null rows have total mass $O(N)$ costs $O(q)$. Example: conditioning mutually independent nulls on one normalized sum leaves correlations $-1/n$ with total mass $n$.

Risks. (a) Avalanches. If one extra rejection can raise the rank by a large factor, which needs alternatives that hug the BH line, the left side can exceed the heuristic by a factor $\log N$. The lemma may need a correction by the probability of such configurations, or may hold only after averaging over a carrier. (b) The bound is linear in correlation mass. It is useless for diffuse collective negative dependence: in the lower-bound family the mass is of order $N^2$ times the product of the loadings. That part has to be in the carrier.

Tests before any proof attempt, by exact computation or short simulation: antipodal pairs; equicorrelated negative nulls; the one-null staircase; a staircase whose partners form a tight cluster; a perfectly correlated near-hugging ladder plus one weakly negatively correlated null (risk a).

## Use

With (NM), a carrier only has to make the residual PRDS on the nulls up to negative mass $O(N)$. This is the form needed when nulls are independent before conditioning, since they become weakly negatively correlated after conditioning on linear functionals. It is the missing link between the capped lemma and the independent-null test case recorded separately.
