---
type: idea
title: >-
  No additive log-convex kernel lets Lehec's tail bound cap sparse Simes
  crossings
status: draft
idea_kind: risk
origin: agent
related_assets:
  - gaussian_simes_sparse_crossing_fixed_level_cap
tags: []
---

Unverified agent calculation (plan stage, 12 November 2026). It extends the Mills-factor warning in the motivation of gaussian_simes_sparse_crossing_fixed_level_cap from the single exponential tilt to every kernel of the dense-tilt form. Take f(x)=N^{-1}\sum_i\varphi(a_i\cdot x) with \varphi positive, nondecreasing on [u_q,\infty) and log-convex, normalized by \mathbb E\varphi(G)=1. Mixtures \int\mu(d\lambda)e^{\lambda s-\lambda^2/2} are included, because sums of log-convex functions are log-convex. A crossing at threshold t with k=N\overline\Phi(t)/q gives only f\ge\overline\Phi(t)\varphi(t)/q. To put every sparse crossing in one level set \{f\ge R\} you need \varphi(t)\ge Rq/\overline\Phi(t) for t\in[u_q+1,t_{\max}], where t_{\max}=\overline\Phi^{-1}(q/N). Then 1=\mathbb E\varphi(G)\ge Rq\int h=Rq\log(N\overline\Phi(u_q+1)/q), with h=\varphi_G/\overline\Phi the hazard. This is the divergence of \mathbb E[1/U], where U=\overline\Phi(G) is uniform. So R is at most about 1/(q\log N), and Lehec's bound C/(R\sqrt{\log R}) is useless once N is large. Any proof of the sparse cap must therefore be collective (a supremum over thresholds charged once), not a level set of an additive per-coordinate kernel. This does not touch the hinge acceptance target of idea_9dc45fd77c4b. The hinge kernel (s-x)_+ is log-concave, so Lehec does not apply to it anyway.
