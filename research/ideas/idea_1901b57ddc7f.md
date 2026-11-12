---
type: idea
title: One active BH rank face on each coordinate line
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_sharp_upper
  - gaussian_bh_two_sided_sharp_upper
tags:
  - bh-self-consistency
  - coordinate-faces
  - stein-transmission
---

Auxiliary deterministic observation for the current transmission route (known BH simplicity structure, no novelty claim). Fix all p-values except coordinate j and write t_k=qk/N, n_{-j}(k)=#{i≠j:p_i≤t_k}. Let R0=max({k:n_{-j}(k)≥k}∪{0}) and R1=max{k:n_{-j}(k)≥k−1}; R1≥R0+1 and R1≥1. Then the full BH count is exactly R1 if p_j≤t_{R1}, and R0 otherwise. Proof: R1 qualifies in the first case and no k>R1 can qualify even after adding coordinate j. In the second case all k>R0 with k≤R1 have p_j>t_k and n_{-j}(k)<k, and k>R1 cannot qualify regardless. Thus among the complete grid faces on each coordinate line only the face at p_j=t_{R1} changes R, including tied other p-values. For centered one-sided nulls, on this active face the j-th baseline Stein term h_{z_κ}(g_j)/t_κ has zero jump (when R0=0 use κ=1); other null terms can have nonzero jumps. This may simplify a global flux construction, but proves neither CS64 nor the desired upper bound; negative null means need separate treatment and do not have the centered cancellation.
