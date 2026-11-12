---
type: idea
title: Check the exact signed-doubling transfer from two-sided BH to one-sided BH
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_two_sided_sharp_upper
  - gaussian_bh_one_sided_sharp_upper
tags:
  - structural_reduction
  - needs_independent_check
---

Candidate exact reduction to check independently, not a completed proof of either general conjecture. For q<1/2, replace m Gaussian statistics T_i by the 2m signed statistics (T_i,-T_i), each with one-sided p-values Q(T_i),Q(-T_i). Their sum is 1, so at BH thresholds <=q at most one sign of each original hypothesis qualifies. At rank k, Q(|T_i|)<=qk/(2m) is equivalent to the original two-sided p-value 2Q(|T_i|)<=qk/m. Check that the complete step-up largest rank and rejection set therefore coincide, including ties and singular covariance. The Gaussian law remains admissible with antipodal signs. For original centered true nulls, both signs are true one-sided nulls; if the one-sided convention treats negative alternative means as additional nulls, its doubled FDP dominates the original two-sided FDP, which still transfers an upper bound. Thus a general one-sided sharp upper bound should imply the two-sided upper bound, but the one-sided target is currently draft, so it cannot be silently cited as proved or used circularly. A plan using this reduction still needs an independent genuinely new proof tool for the one-sided bottleneck. Check whether this reduction is already present in the pack/sources before treating it as new. Approved structured one-sided bounds might yield limited two-sided consequences if their precise null-label/entropy budgets are tracked.


Constant limitation (independent planning check): the signed doubling preserves q, so transferring a one-sided leading constant 1/sqrt(pi) only yields that same constant. The current two-sided target requires 1/(2 sqrt(pi)); this reduction alone therefore does not prove its sharp constant. A further pair-specific factor-of-two improvement would be necessary. The preceding phrase about a transferred upper bound means only a potentially looser upper bound, not the stated two-sided sharp target.
