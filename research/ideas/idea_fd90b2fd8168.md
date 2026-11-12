---
type: idea
title: Cutoff-to-fixed-threshold domination for fixed-regularizer level coercivity
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_averaged_signed_mean_level_complementarity
tags:
  - gaussian-bh
  - level-coercivity
  - fixed-regularizers
---

Proposed proof step for clause 5, not a proof of the complementarity target. The round-2 summary pack supplies no candidate objects and does not reproduce the threshold/marginal identities, so those identities must first be checked against the approved private-noise variation and directing-population definition.

For the actual BH rank R in [0,1], write V_R for the true-tag discovery mass and V_q for the true-tag discovery mass at the deterministic p-value cutoff q (equivalently the raw threshold U=S^{-1}(q), if that is exactly the approved convention). Verify (i) discoveries at rank R use cutoff qR≤q, hence V_R≤V_q; (ii) D=V_R/R on R>0; (iii) 0≤χ_a≤1 and χ_a=0 on R≤a; and (iv) the unconditional lawful true-tag marginals are superuniform, so E[V_q]≤q. If these checks hold, pathwise χ_a(R)D≤V_q/a and therefore F^a≤q/a, uniformly over lawful directing laws. Thus F^a/(qU)≤1/(aU)≤1/a because U≥1. The unpenalized objective is at most 1/(aU)−δ log(1/q), which tends to −∞ as q↓0 uniformly in the law.

Choose any fixed lawful finite-moment comparison pair (π*,q*) and restrict 0<η≤η*. Its penalized objective has a common finite lower bound. The preceding uniform upper bound then confines all normalized penalized maxima to q≥q_min>0. This addresses the boundary escape issue only at fixed a,δ; the constant deteriorates as a↓0 and no unrestricted flux bound follows.

Once uniform finiteness is established, the value/penalty limit itself has an elementary comparison route. Let J denote the objective without −η M2 and L0=sup J over finite-moment pairs. For any ε>0 choose a finite-moment pair with J≥L0−ε. Then Lη≥L0−ε−η M2 of that pair and Lη≤L0, proving Lη→L0. At any maximizer, 0≤η M2(πη)=J(πη,qη)−Lη≤L0−Lη→0. None of this establishes the target's UI, support representation, cone separation, or survival-flux identity.
