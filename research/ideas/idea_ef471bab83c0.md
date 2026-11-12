---
type: idea
title: 凸序面的配对须保留秩标记，不能由投影配对直接支付Mills迹
status: draft
idea_kind: risk
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_mixed_coherence_trace_budget
tags:
  - convex-order
  - rank-marks
  - signed-boundary
---

Supplement to the correlated-clone variation idea idea_dee8f2040d8f. Even if the nonlinear first variation establishes convex order for the signed active-face measure after projection onto the orthogonal latent coordinate Y, a martingale coupling of that projected measure does not yet control the Mills trace. Different actual ranks r can contribute at the same Y, with different thresholds u_r, FDP denominators, null marks and 1/h(u_r) factors. Projection may cancel those charges while their marked trace contributions remain nonzero. A successful argument must construct a lift/cancellation on the full face state (Y,r,labels), preserve every mark and inverse-rank term, and estimate the resulting Gaussian cost; zero cost in projected Y alone is insufficient. In addition, zero-null mean boundaries can leave unmatched signed mass. No global convex order or trace estimate has been proved. This is a precise limitation to check in any future plan based on Strassen couplings, not a counterexample to the main target.
