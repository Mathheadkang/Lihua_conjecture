---
type: idea
title: >-
  Null maximum distance test gives an OU bridge bound for at most three true
  nulls
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_ou_integrated_signed_budget_bridge
tags:
  - gaussian-bh
  - ou-bridge
  - null-count
---

For the full actual-BH FDP f, put m0=|I0|, u_q=S^{-1}(q)>=1 and M(x)=max_{i in I0} v_i dot x. Test the OU covariance identity with g(x)=-(u_q-M(x))_+. This is 1-Lipschitz; f g=0, since a rejected true null has theta_i+v_i dot x>=u_q and theta_i<=0. A direct Mehler/OU calculation, with its interchanges justified, gives |Cov(f,g)|<=J(f), hence J(f)>=F E[(u_q-M(G))_+]. For 1<=m0<=3, the union bound gives E[(u_q-M(G))_+]>= integral_0^1 [1-3S(t)]_+ dt>0.08002948. Since F<=m0 q, the bridge ratio is below 37.487 in this restricted-null-count class, independently of alternatives and latent rank. This is a draft proof approach requiring independent checking, not an approved analytic black box. It differs from the existing idea_9146e39dd8dd fixed-rank hole-covariance direction: it exploits the maximum over null directions and bounds null count instead of latent rank. The union-bound estimate need not stay positive uniformly as m0 grows, so it does not prove the universal bridge.
