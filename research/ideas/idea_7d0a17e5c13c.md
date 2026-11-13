---
type: idea
title: All-or-nothing law for the worst-case Gaussian Simes size
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_simes_one_sided_uniform_linear_bound
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - global-null-simes
---

Agent derivation, 12 November 2026; needs independent verification. Serves [the global-null Simes question](idea_b897932e6b15.md).

Let $B(q)$ be the supremum over finite $N$ and unit-diagonal PSD $\Sigma$ of the one-sided Simes rejection probability at level $q$ (the all-null FDR of ordinary BH).

1. Amplification ([the block amplification observation](idea_8699fa13f1f6.md)): for $M$ independent copies of an $m$-test model, a local rejection at level $q/M$ with rank $r$ has local $p_{(r)}\le qr/(Mm)$, and the global $r$-th smallest p-value is no larger, so rank $r$ qualifies globally at level $q$. Hence $B(q)\ge1-(1-B(q/M))^M$ for every integer $M\ge1$.
2. $B$ is nondecreasing in $q$, since the Simes rejection region grows with the level.
3. Dichotomy: if $B(t)/t$ is unbounded as $t\downarrow0$, choosing $M=\lfloor q/t\rfloor$ gives $B(q)\ge1-e^{-(1+o(1))qB(t)/t}\to1$, so $B(q)=1$ at every level. Otherwise $B(t)\le Ct$.
4. Fixed-level criterion: if $B(\alpha_0)<1$, then $B(\alpha_0/M)\le\log(1/(1-B(\alpha_0)))/M$, and monotonicity gives $B(t)\le2\log(1/(1-B(\alpha_0)))\,t/\alpha_0$ for $t\le\alpha_0/2$.

Consequences: the linear Gaussian Simes bound is equivalent to $B(\alpha_0)<1$ at a single level, and any uniform worst-case FDR bound tending to zero, including the project target, implies it. Under arbitrary non-Gaussian dependence $B\equiv1$ for large $N$ (Hommel's harmonic factor), so any proof must use Gaussian structure.

## Complete fixed-level calculation from the side chat

Saved at the researcher's request on 12 November 2026. This supplies details of the argument above; the observation stays draft and has no native proof-verification verdict.

Fix a level $\alpha_0$ and assume $B(\alpha_0)\le1-\delta$ with $0<\delta<1$. For every integer $M\ge1$ and every $\varepsilon>0$, choose a finite centered Gaussian model whose rejection probability $b$ at $\alpha_0/M$ is at least $B(\alpha_0/M)-\varepsilon$. Make $M$ independent copies. The block-diagonal covariance is still a correlation matrix, including when a local covariance is singular.

If one block of size $n$ has a qualifying rank $r$, its local p-value satisfies $p_{(r)}\le\alpha_0r/(Mn)$. The global $r$-th order statistic is no larger than that block's $r$-th order statistic. Hence the ordinary global Simes event contains the union of the $M$ local rejection events; it does not require that the global largest qualifying rank equal any local rank. Independence gives global probability at least $1-(1-b)^M$. Letting $\varepsilon\downarrow0$ proves
$$
B(\alpha_0)\ge1-\bigl(1-B(\alpha_0/M)\bigr)^M.
$$
It follows that
$$
B(\alpha_0/M)\le1-\delta^{1/M}
\le\frac{\log(1/\delta)}{M}.
$$
For $0<t\le\alpha_0/2$, set $M=\lfloor\alpha_0/t\rfloor$. Then $M\ge\alpha_0/(2t)$ and $t\le\alpha_0/M$. Monotonicity therefore gives
$$
B(t)\le\frac{2\log(1/\delta)}{\alpha_0}\,t.
$$
This proves the fixed-level implication without assuming that the supremum is attained. It does not establish the premise $B(\alpha_0)<1$.

Independent replication also preserves any fixed covariance operator-norm bound, since the copies form a block-diagonal matrix. The separate [bounded-spectrum calculation](idea_fc8702e63d1e.md) proves a useful subclass bound, while [the convex hinge acceptance reduction](idea_9dc45fd77c4b.md) identifies the missing uniform premise for unrestricted models.
