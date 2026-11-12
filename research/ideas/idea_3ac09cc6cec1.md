---
type: idea
title: >-
  Secondary-transition screen for (K): separate the coherent Gaussian shift from
  the REM channel
status: draft
idea_kind: risk
origin: agent
related_assets:
  - gaussian_frozen_ray_two_level_tree
  - gaussian_frozen_ray_independent_equal_weights
tags:
  - cross-discipline-brainstorm-20261110
  - unverified-screen
---

A targeted refinement of [the existing secondary-transition stress family](idea_57338934f2f7.md) and [the planted-SNR program](idea_dc6cf14ab94d.md), not a new claimed theorem or a counterexample. For a single coherent cluster x_j=sqrt(rho)e_0+sqrt(1-rho)e_j, j=1,...,K, the planted channel factors into a known common Gaussian shift and an independent equal-weight REM channel. At u=w sqrt(1-rho), elementary product-density calculus suggests exact decompositions D_cluster(w)=rho*w^2/2+D_REM(u), J_cluster(w)=rho+(1-rho)J_REM(u), and m_cluster(w)=rho+(1-rho)m_REM(u), with D'=w*m. These formulas require native verification before proof use.

This yields a sharper finite diagnostic: sample near the REM recovery onset where m_REM is of order rho, rather than using a coarse uniform w grid. In a large-K heuristic, onset is near sqrt(2 log K), recovery width is order one, and score moments before recovery can be larger than m_REM by a factor of log(1/rho). If the coherent contribution already gives D>=1 there, JD/(D')^2 might grow as rho tends to zero. This is a heuristic risk to inequality (K), NOT a proved divergence. In particular K must be large enough to separate onset and the chosen pre-recovery window, and exact finite expressions or certified asymptotics must replace these heuristic approximations.

Even an actual failure of (K) would affect only that sufficient intermediate step of the proof program: it would not refute the frozen-ray assertions, the Gibbs formula, the fixed-noise-floor target, either BH main bound, or the stress estimator. The program itself permits replacing sqrt(J) by the L1 score norm. The remote numerical manifest records this distinction; remote runs have not yet launched because the configured SSH connection times out. Link and reuse the original stress family rather than making duplicate test-case nodes.
