---
type: idea
title: >-
  Two-level rectangular critical bulk has a uniform L2 maximal bound; coherent
  rare remainders remain open
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_frozen_ray_two_level_tree
  - gaussian_frozen_ray_independent_equal_weights
tags:
  - frozen-ray
  - two-level-tree
  - critical-truncation
  - partial-bound
  - unproved-full-target
---

This is an agent-derived weaker result, recorded as a draft idea for independent checking. It does not prove either full assertion of gaussian_frozen_ray_two_level_tree and creates no new asset or goal. It adapts only the elementary critical-truncation calculations in the approved iid proof, motivated by idea_59590d03f60c; endpoints remain as in idea_fe88235f5b95. The planted-SNR program idea_dc6cf14ab94d supplies no paid estimate for the remaining terms.

## Precise weaker statement
Put u_k=sqrt(2 log b_k), including u_k=0 when b_k=1. With the Gaussian variables and a in the target, set p_i(w)=b1^{-1}exp(sqrt(a)w G_i-a w^2/2) and q_ij(w)=b2^{-1}exp(sqrt(1-a)w G_ij-(1-a)w^2/2). Define

$$
B_w=\sum_i p_i(w)\mathbf1_{\{G_i\le u_1\}}\sum_j q_{ij}(w)\mathbf1_{\{G_{ij}\le u_2\}},\qquad F_{\rm rect}=\sup_{w\ge0}B_w.
$$

The concrete proposed calculation below gives ||F_rect||_2 <=64, uniformly in b1,b2,a, hence E F_rect<=64 and P(F_rect>=t)<=4096/t^2 for every t>0. This controls only the doubly clipped collective part, at the target's common w.

## Complete elementary calculation for this weaker scope
For iid standard normals H_j, b>=2 and u=sqrt(2log b), let C_b(v)=b^{-1}sum_j exp(v H_j-v^2/2)1{H_j<=u}, M_b=sup_{v>=0}C_b(v). In the approved iid proof, Q_v=(H-v)exp(vH-v^2/2)1{H<=u} has E Q_v=-phi(u-v)<=0 and

$$
\int_0^\infty\sqrt{\mathbb E Q_v^2/b}\,dv\le4+\sqrt{2\pi}=:K_0.
$$

Its two-range proof is given in that proof's Uniform mean of the collective envelope section. The same calculation upgrades directly to L2: if E Y<=0 then Y_+<=(Y-EY)_+<=|Y-EY|, so ||(C_b'(v))_+||_2<=sqrt(Var C_b'(v))<=sqrt(E Q_v^2/b). Pathwise M_b<=C_b(0)+integral(C_b')_+, with C_b(0)<=1. Minkowski on finite intervals followed by monotone convergence therefore gives ||M_b||_2<=1+K_0<8. All derivatives are finite sample derivatives, and all supremums are countable rational supremums by continuity. For b=1,u=0, M_1=1{H_1<=0} since the retained exponential decreases on v>=0; thus ||M_1||_2<=1.

For each parent i let M_i be this clipped-child envelope formed from G_ij, so the M_i are iid, independent of all G_i, and E M_i^2<=64. Pointwise, retaining the original common w before the bound,

$$
B_w\le\frac1{b_1}\sum_i M_i e^{vG_i-v^2/2}\mathbf1_{\{G_i\le u_1\}},\qquad v=\sqrt a\,w.
$$

For b1>=2 call the right side H(v). If a>0, v ranges over [0,infinity). We have ||H(0)||_2<=b1^{-1}sum_i||M_i||_2<=8. The derivative is b1^{-1}sum_i M_i Q_v(G_i), its mean is -E M_i phi(u1-v)<=0, and independence of the pairs (M_i,G_i) gives

$$
\|(H'(v))_+\|_2\le\sqrt{\operatorname{Var}H'(v)}\le\sqrt{\mathbb E M_i^2}\sqrt{\mathbb E Q_v(G)^2/b_1}.
$$

The identical positive-variation/Minkowski calculation gives ||sup_v H(v)||_2<=8(1+K0)=8(5+sqrt(2pi))<64. If a=0 only H(0) is needed. If b1=1,u1=0, the retained parent factor exp(vG1-v^2/2)1{G1<=0} is at most one, so F_rect<=M1 and the same constant applies. Thus the calculation includes a=0,a=1,b1=1,b2=1 without taking limits. Independence used here is of parent blocks and auxiliary child marks; it does not assert independence of the original leaves.

## Exact remaining obstruction to a full-target plan
The pointwise identity L_w=B_w+A_w+D_w has A_w=sum_i p_i(w)1{Gi>u1}sum_j qij(w) and D_w=sum_i p_i(w)1{Gi<=u1}sum_j qij(w)1{Gij>u2}. To prove the target one still needs a joint common-w treatment of A and D that pays the single sharp sqrt(log c/pi) budget and the maximal 1/(alpha sqrt(log alpha)) tail. No such estimate has been supplied here. Independently maximizing the parent rare factor and the full child field produces products of borderline rare envelopes; their independence is not a justification for multiplying maximal-tail estimates, and it discards peak alignment. Replacing these remainders by sums of scalar leaf envelopes also pays log(b1*b2) for a coherent rare parent before child resolution. Either overestimate can exceed the required parameter-uniform budget. A plan that simply asks to prove a common-SNR remainder bound would restate the unsolved part.

First unproved gate for any extension of this partial calculation: an explicit common-w rare-parent/rare-child decomposition with a proved scalar charging identity or occupation estimate that assigns only one sharp budget. Failure condition for that route: if its proposed comparison requires separate parent and child suprema whose truncated integral grows faster than sqrt(log c), or constants depend on b1,b2,a, reject that comparison rather than weaken the target. Five search rounds with no refuter do not pay this gate. No pending proof plan is proposed.
