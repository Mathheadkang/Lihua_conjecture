---
type: idea
title: 实际选中真零索引的联合熵与互信息恒等式
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_mixed_coherence_trace_budget
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - selected-index
  - mutual-information
  - actual-rank
---

New exact entropy calculation to audit, not a main proof. Let original Gaussian G have law gamma, f=V/(R∨1), F=E_gamma f>0, and Q_G=(f/F)gamma. Let N0=|I0|>0. Under Q_G sample I uniformly from the actual V selected true nulls. Thus the joint density of (G,I=i) relative to gamma times uniform(I0) is N0 1{i true and selected}/(R F). Let pi be the resulting marginal law of I and D=KL(Q_G||gamma). Direct logarithmic calculation, retaining actual R and V, gives

KL(Q_{G,I}||gamma×Unif(I0)) = log(1/F)+E_Q log(N0/R),
I_Q(I;G)+KL(pi||Unif(I0)) = E_Q log(N0/V).

The second identity follows by subtracting D=E_Q log(f/F) from the first and using the relative-entropy chain rule. R,V>=1 Q-a.s.; at each fixed finite model all index/rank entropies are finite. With Zi=v_i·G and true means theta_i<=0, selected i obeys Zi>=u_R−theta_i>=U. Conditional Gaussian entropy variational inequality yields

KL(Q_{G,I}||gamma×Unif(I0)) >= (1/2) sum_i pi_i |E_Q[G|I=i]|² + KL(pi||Unif(I0)) >=U²/2.

This recovers only log(1/F)+E_Q log(N0/R)>=U²/2, with an uncontrolled rank term; it does not remove dimension dependence. The mutual-information cancellation may be useful for a future Gaussian-channel or barycentric transport approach to the heat-field coherence budget, but Q_G|I is a BH-truncated Gaussian law, not a Gaussian shift or Gaussian-mixture component. I-MMSE or Gaussian-mixture identities cannot be imported without a real representation. Rare tiny ranks can carry very large log(N/R) despite small coherence deficit; the older unbalanced antipodal obstruction therefore still matters. No new dependency or verified theorem is claimed.
