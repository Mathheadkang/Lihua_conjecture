---
type: idea
title: >-
  Rare mean-clone moves have a clone-invariant comparison cost independent of
  dimension
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_correlated_clone_first_variation
tags: []
---

Conditional near-extremizer route to audit, building on idea_3eea7b41c448; not a justified Ekeland argument or a main proof. Encode a finite original model as the probability measure pi=(1/N)sum_i delta_(theta_i,v_i,label_i), so exact uniform copying leaves pi unchanged. In the inverse-Mills rare-downward-mean construction, relative minority mass inside chosen atom is epsilon L with L=N[h(U)/U-1]. Thus the actual parameter-measure mass moved is at most epsilon L/N=epsilon[h(U)/U-1], independent of N. Under TV convention sup_B|pi(B)-pi'(B)|, this bounds the TV distance; with a bounded mean-distance transport cost, moving scores by at most epsilon/U gives W1 cost at most epsilon^2[h(U)/U-1]/U. This is relevant because the signed FDR variation sought is order epsilon. A VALID clone-invariant approximate variational principle could then turn model-dependent small-epsilon comparisons into an error controlled by a dimension-independent mass cost, instead of assuming a fixed-N logdet penalty remains invariant under copies. However the necessary complete domain, upper semicontinuity, and extension of the exact variation to the resulting (possibly countably atomic) variational points have NOT been proved. The TV completion of finite atomic parameter measures is countably atomic, while a continuous injected mean distribution is not a TV limit of finite quantile arrays; finite discrete profile approximations may avoid that particular issue but require their own uniform rank-cost and FDR error control. An upper-semicontinuous envelope alone does not give its derivative or finite-model face measures. Never silently apply Ekeland on the incomplete finite-model domain, replace a limit optimizer by a finite PD one, or drop near-extremizer additive gaps. The unmatched zero-null mean-flux term in the Mills inequality also remains unpaid.
