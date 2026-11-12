---
type: idea
title: >-
  Gibbs variational formula: the maximal null tilt is a penalized supremum over
  null sub-populations (PAC-Bayes form)
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - directional_entropy_one_sided_fdr_bound
  - gaussian_bh_radial_strip_refinement
  - gaussian_simes_one_sided_uniform_linear_bound
tags:
  - cross-discipline-brainstorm-20261110
  - gibbs-variational-principle
  - pac-bayes
  - directional-entropy
  - leader-tracking
  - weak-loading-population
---

From the cross-disciplinary brainstorm of 10 November 2026. Exact and elementary (verified in the chat by the Donsker-Varadhan formula; not natively verified). Recorded because it explains several existing results in one line and gives the conjecture (T) of idea_9f8ffb204424 a PAC-Bayes form.

Setting: $\mu$ a probability measure on the unit ball of a Hilbert space (the empirical law of null loading vectors in the weak-loading regime), $G$ standard Gaussian, $L_w(g)=\int\exp(w\langle x,g\rangle-w^2\|x\|^2/2)\,\mu(dx)$, $\Lambda=\sup_{w\ge0}L_w$.

## Formula

For every $g$,
$$
\log\Lambda(g)=\sup_{\nu\ll\mu}\left\{\frac{\big(\int\langle x,g\rangle\,\nu(dx)\big)_+^2}{2\int\|x\|^2\,\nu(dx)}-D(\nu\|\mu)\right\},
$$
with $0/0=0$. Proof: $\log L_w=\sup_\nu\{w\int\langle x,g\rangle\,d\nu-\tfrac{w^2}{2}\int\|x\|^2d\nu-D(\nu\|\mu)\}$ (Gibbs variational principle), then maximize over $w\ge0$. The maximizer is the posterior $\nu^*\propto\exp(w^*\langle x,g\rangle-w^{*2}\|x\|^2/2)\,\mu$ with the self-consistency $w^*=\int\langle x,g\rangle\,d\nu^*/\int\|x\|^2d\nu^*$; for unit-norm $\mu$, $\log\Lambda=w^{*2}/2-D(\nu^*\|\mu)\le w^{*2}/2$.

Consequently, with $Z_\nu=\int\langle x,G\rangle\,\nu(dx)$ (centered Gaussian of variance $\|\int x\,d\nu\|^2\le\sigma_\nu^2:=\int\|x\|^2d\nu$),
$$
\{\Lambda\ge\alpha\}=\bigcup_{\nu\ll\mu}\Big\{Z_\nu\ge\sigma_\nu\sqrt{2\log\alpha+2D(\nu\|\mu)}\Big\} .
$$
This is a union of half-spaces indexed by re-weightings of the null population, and $\{\Lambda<\alpha\}$ is a convex set containing the ball of radius $\sqrt{2\log\alpha}$.

## Reading for BH

In the weak-loading population class the conditional FDP can exceed $q\pi_0\alpha$ at some level only if some sub-population $\nu$ of nulls has a standardized collective conditional mean above $\sqrt{2\log\alpha+2D(\nu\|\mu)}$: a coherent shift pays an entropy price for the size of the sub-population that shares it.

- One cluster of mass $\pi_h$ along one direction: $D=\log(1/\pi_h)$ and the threshold is $\sqrt{2\log(\alpha/\pi_h)}$; with $\alpha=1/q$ this is the cutoff $b_h$ of the approved directional-entropy theorem, and a union bound over a partition into clusters is that theorem.
- Onset. A cluster of mass $\pi_h$ exceeds the bulk level one only beyond $\sqrt{2\log(1/\pi_h)}$, so its useful window has length at most $\sqrt{2\log(\alpha/\pi_h)}-\sqrt{2\log(1/\pi_h)}\le\sqrt{2\log\alpha}$ whatever $\pi_h$ is. Summing windows weighted by mass gives the target scale with no entropy term; integrating each cluster from zero charges the entropy. This is the precise sense in which the entropy term of the approved bound is an artifact of the union bound, and it is what the chaining idea idea_c5bacf260246 and the leader-tracking remarks aim at.
- Hierarchies. Nested sub-populations are nested re-weightings with additive entropies along the tree; no separate chaining structure is needed in this formulation.

## PAC-Bayes form of (T)

The tail part of (T) reads: with probability at least $1-C/(\alpha\sqrt{\log\alpha})$, simultaneously for all $\nu\ll\mu$, $Z_\nu<\sigma_\nu\sqrt{2D(\nu\|\mu)+2\log\alpha}$. The classical PAC-Bayes argument (fixed $w$, Markov on $L_w$, then Donsker-Varadhan) gives failure probability $1/\alpha$ for each fixed $w$ and pays a grid or logarithmic factor to optimize $w$ for each $\nu$. (T) asserts that for Gaussian processes the optimization over $w$ is free and that Markov improves by $\sqrt{\log\alpha}$, the one-point case $\overline\Phi(\sqrt{2\log\alpha})$ being extremal. I do not know this statement in the PAC-Bayes or generic-chaining literature; only one standard web query was made.

## Limits (checked in the chat)

1. Indicator kernels. For statistics without private noise the relevant events are $\{\mathrm{mean}_KT\ge\overline\Phi^{-1}(q|K|/N)\}$ over subsets $K$ (route (GD) of idea_aba318ad3eee): hard entropy $\log(N/|K|)$ and Mills-calibrated thresholds. The soft version with Kullback entropy is heuristically FALSE for independent coordinates once $\sqrt{2\log N}>1/(q\sqrt{2\pi})$: the Gibbs tilt of the uniform law at inverse temperature $w$ has mean about $w$ and entropy about $w^2/2$, and $\overline\Phi(w)\le qe^{-w^2/2}$ as soon as $w\ge1/(q\sqrt{2\pi})$. So the formula does not by itself settle (GD) or the all-null Simes conjecture.
2. Chernoff inside BH. $\mathbf 1\{t\ge x\}\le e^{x(t-x)}$ gives, for every finite model, $V(x)/(N\overline\Phi(x))\le\sqrt{2\pi}\,h(x)\,\pi_0L^0_x(G)$ with $h=\phi/\overline\Phi$ and $L^0$ built on the null directions; the price of passing from the indicator kernel to the exponential kernel is exactly the hazard $h(x)\ge U$, the same Mills factor.
