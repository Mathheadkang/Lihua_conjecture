---
type: idea
title: Two-regime repair of the Mills trace budget and a dangerous-FDR restriction
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_entropy_coherence_trace_budget
tags:
  - fdp-tilt
  - trace-budget-repair
  - rare-branches
  - unproved
---

This is a NEW UNPROVED repair direction, not an edit of either failed certificate or the main statement. The original O(q)sqrt(1-x) certificate failed in the finite small-loading lower family. The later purely linear coherence-deficit certificate is now challenged by the unbalanced signed-clone candidates; those candidates are awaiting native independent verification and have F=q, not a counterexample to the main FDR target. Preserve both earlier claims and all evidence unchanged.

One possible combined budget is M_+ <= C q [sqrt(delta)+sqrt(1+D) delta], where delta=1-x and all other symbols are those of the FDP-tilted Mills heat fields. This permits both identified scales: low coherence can use the entropy-amplified term, while an extremely rare opposite branch need not obey a bound linear in its probability. No estimate of this form has been proved. A plan must provide a real Gaussian/BH mechanism, not merely posit it.

The conditional implication to the exact main order is checkable. Set z=F/(qH), c=C/z. The score, entropy and drift identities would give U <= sqrt(2D) sqrt(1-delta)+c sqrt(delta)+c sqrt(1+D) delta. For z>=4C and D>=1, write a=sqrt(2D). Since c sqrt(1+D)<=a/4 and sqrt(1-delta)<=1-delta/2, the right side is <=a-a delta/4+c sqrt(delta)<=a+c^2/a. Squaring gives U^2<=2D+3c^2. Using D<=log(1/F) and F=z phi(U), obtain log[z/sqrt(2pi)]<=3c^2/2<=3/32, so z is universally bounded. If D<1, the same right side is <=sqrt(2)+1/4+sqrt(2)/4<3, impossible for U>=3. Thus an independently proved combined budget would imply z<=max{4C,e sqrt(2pi)} without a complexity loss.

A distinct possible repair is to require the previous linear budget only in the dangerous region F>=qH (or F/(qH)>=a fixed positive universal threshold): the known unbalanced-clone family with F=q has z=1/H<1 and would be excluded. The main contradiction argument only needs a budget when z is large. This restriction also remains completely unproved and does not itself supply the missing cross-face/conditional-bridge cancellation. Future work should distinguish these two logically different repairs rather than silently weaken the already scaffolded false candidate.
