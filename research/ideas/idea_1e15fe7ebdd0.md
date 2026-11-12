---
type: idea
title: Boundary search obstruction for radial Gaussian BH bounds
status: draft
idea_kind: observation
origin: agent
related_assets:
  - multifactor_radial_fdr_bounds
tags:
  - boundary_degenerate
  - counterexample-search
---

Slot 1, round 1 refutation search; no counterexample found. These are boundary obstructions only, not a proof of the target.

The hypotheses checked were: H1 positive integers m,d and an admissible Gaussian multifactor representation; H2 the specified one- or two-sided Gaussian p-values and true-null set; H3 the track-specific level range; H4 the upper-q chi_d quantile and the stated loading coefficients. A genuine counterexample would additionally need NOT: failure of the quantile inequalities or of the displayed FDR bound.

1. Empty true-null set: V=0 pointwise, hence FDR=0; NOT fails. For m=1, a true-null marginal is standard normal at the boundary and stochastically smaller for a negative one-sided mean, so FDR<=q; the displayed right side is >=q. Thus no m=1 counterexample.

2. Every true null has r_i=0, with arbitrary alternative loadings and means: conditional on Z its p-value CDF obeys F_{i,z}(t)<=t. The approved conditional FDP bound therefore gives FDR<=q*pi_0<=q. This whole family cannot violate the target, whose right side is >=q.

3. The side claims about b and Delta cannot fail at any dimension. The pointwise inequality ||Z||>=|Z_1| gives q=P(||Z||>b)>=2*barPhi(b). Consequently b>=u_2(q)>=u_1(q), Delta_2>=0, and Delta_1>=log(2). At d=1 the equalities are b=u_2(q), Delta_2=0, Delta_1=log(2).

4. Full-loading rank-one, all boundary nulls: d=1, theta_i=0, a_i in {-1,+1}. For two-sided tests all null p-values are identical and uniform, so BH rejects all or none and FDR=q. For one-sided tests let n_+,n_- be the counts of the two signs. Since q<1/2, only the positive sign group can reject when Z>0 and only the negative sign group when Z<0. BH rejection is respectively barPhi(Z)<=q*n_+/m or barPhi(-Z)<=q*n_-/m. The disjoint probabilities sum to q. Thus r=1 and singular covariance alone do not produce a violation, even though gamma_i=0.

Limitations: these calculations do not cover rank-one mixed alternatives with negative one-sided null means, or saturated factors in d>=2 with distinct loading directions. No claim that the target theorem has been proved.
