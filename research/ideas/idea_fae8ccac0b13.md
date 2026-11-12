---
type: idea
title: >-
  Fixed positive private smoothing bounds the two signed response terms
  separately
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_whole_payoff_cameron_martin_balance
tags:
  - gaussian-bh
  - cameron-martin
  - fixed-private-smoothing
---

Round 5 proof-step observation, with general theorem and all exchange obligations still unresolved. Fix s>0 and a deterministic direction v, and put K=τ||v||. Since c(w)≥s and |b_v|≤K, k_x≤1/(s√(2π)), |dot Q(r)|≤K, and the all-active right-envelope formula, once justified, gives |dot M(r)|≤K/σ. The conditional composition formula gives |dot f(r)|≤2K/(r s√(2π)). Also f(r)∈[0,1], |f'(r)|≤1/r, hence |(χ_a f)'(r)|≤χ_a'(r)+χ_a(r)/r. Consequently the absolute bulk term is bounded by 2K/(a s√(2π)), and the absolute rank term by K[1+log(1/a)]/(σ√(2π)). These deterministic fixed-s bounds are a possible domination step after pointwise formulas have been established; they are not a proof of arbitrary directing-law differentiation or exchange. They give no separate-term bound uniform as s↓0, and no uniform-q payment. Conditional on the orthogonal field, bounded line-Lipschitz payoff times a bounded coherent C1 weight with bounded directional derivative is absolutely continuous, has integrable Gaussian-weighted derivative, and has vanishing Gaussian boundary terms. Discontinuity of that weight in orthogonal coordinates alone does not defeat this one-dimensional IBP argument. This does not by itself establish coherent versions or the identification of the derivative with the complete signed response.
