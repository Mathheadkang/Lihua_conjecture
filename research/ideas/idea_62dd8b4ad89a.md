---
type: idea
title: >-
  The fixed-common-loading model classes are nested, but nesting does not make
  their constants uniform
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_exchangeable_array_variational_compactification
tags: []
---

Elementary inclusion to verify in the array framework if useful. For 0<sigma1<sigma2<1, every covariance Sigma=(1-sigma2^2)C+sigma2^2 11^T can be rewritten as (1-sigma1^2)C'+sigma1^2 11^T, with C'=[(1-sigma2^2)C+(sigma2^2-sigma1^2)11^T]/(1-sigma1^2), a convex combination of correlation matrices. Thus the canonical fixed-sigma finite model classes are nested and W_sigma(q) is nonincreasing as sigma increases. Earlier proposals' phrase 'no monotonicity asserted' meant it was unnecessary, not a counterclaim. This inclusion plus finite covariance smoothing supports the pointwise sigma->0 value reduction, but supplies no uniform rate or control of a bound C_sigma q log(1/q) as sigma->0. At an actual all-d marked-array maximum, the allowed residual-Gram competitor C_t=(1-t)C+t 11^T can increase shared residual loading without changing means or their penalty. Any proposed extremal boundary-flux estimate should use genuine covariance competitors as needed; mean complementarity alone has not proved that estimate. No covariance derivative formula or main bound is asserted here.
