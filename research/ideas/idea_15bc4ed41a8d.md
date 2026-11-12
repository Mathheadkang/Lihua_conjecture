---
type: idea
title: 至多四种真零加载方向的最大值距离给出完整 FDP 的 OU 预算下界
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_ou_integrated_signed_budget_bridge
tags:
  - gaussian-bh
  - ou-budget
  - restricted-family
  - null-directions
---

Restricted-family proof step from search round 5; draft and unapproved. Suppose the true-null loading vectors have K<=4 distinct directions w_1,...,w_K, with arbitrary multiplicities, arbitrary nonpositive true-null means, and arbitrary alternative loadings and latent rank. Put M(x)=max_a w_a dot x, u_q=S^{-1}(q)>=1 and g(x)=-(u_q-M(x))_+. Then g is 1-Lipschitz, and the full actual-BH FDP satisfies fg=0 because f>0 implies some rejected true null has score at least u_q, hence M>=u_q. Thus Cov(f,g)=F E[(u_q-M(G))_+]. The OU covariance identity bounds its absolute value by J(f): integrate E[grad T_t f dot grad g] in t, with Lipschitz g handled by approximation; fixed finite dimension and bounded f give the required Mehler integrability. The union bound gives E[(u_q-M(G))_+] >= c_4 := integral from S^{-1}(1/4) to 1 of (1-4S(t)) dt >0. Also F<=P(f>0)<=Kq<=4q. Therefore J(f)>=c_4 F and the bridge ratio is at most 4/c_4. This extends the prior restriction on the number of true nulls to the number of distinct true-null loading directions, even with unbounded multiplicities and arbitrary alternative rank. It does not control a growing number of interacting true-null directions and does not prove the unrestricted bridge. The covariance argument and all analytic interchanges remain part of this draft approach, not an approved library dependency.
