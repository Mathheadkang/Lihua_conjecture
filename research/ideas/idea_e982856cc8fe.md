---
type: idea
title: >-
  Two-coordinate Gaussian cells require exponentially large pointwise Stein
  budgets
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_sharp_upper
tags:
  - stein-transmission
  - pointwise-obstruction
  - finite-counterexample
---

Exact obstruction to the restricted CS64 coefficient ansatz of plan_gaussian_bh_one_sided_stein_transmission_capacity_20261104, NOT to the FDR conjecture. Independently derived/reviewed by root and checking worker. Take N=2, θ=(0,1), Σ12=−r, r=.9, q=Q(4), u=4,v=Q^{-1}(q/2),U=u−1,V=v−1. Only cells AB=(−∞,u)×(U,V), BA=(u,v)×(−∞,U), BB=(u,v)×(U,V) are needed, with κ=1,1,2 and Bκ=.5. Their cell budgets and the increasing-coordinate x=u and y=U faces force D>1597/10 via exact Mills/Taylor bounds, while D=64log6<128. Complete analytic note: research-local/stein_capacity_n2_obstruction_20261104_v1.md; numerical diagnostic is discovery only. Stronger independently reconstructed asymptotic: for any fixed r∈(.5,1), θalt=1, let Pu=(.5−cq)/φu, Pv=(Q(v−u)−cq/2)/φv, dv=1/(2φv), λ=(u+rU)/(1−r²), η=(ru+U)/(1−r²), A=1+λr/V+ηr/v. Eventually CBB,CAB<0<CBA and necessary budget L_r(u)=.5+[ηr/(2A)](dv−Pv−c/v) satisfies e^{−u²/2}L_r(u)→[r/(1+r)]log2>0. This uses u(v−u)→log2 and φv/φu→.5, giving uφu(dv−Pv−c/v)→2φ(0)log2. Full addendum research-local/stein_capacity_n2_asymptotic_obstruction_20261104_v1.md. Thus increasing64 to any fixed constant, or allowing O(u), cannot repair this SAME restricted pointwise ansatz. A genuinely new route must weaken pointwise transmission or enlarge the field class with a separately proved integrated bound.
