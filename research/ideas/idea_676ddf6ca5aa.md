---
type: idea
title: Directional-entropy finite-q bound with individually weighted tail cutoffs
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_sharp_upper
tags: []
---

Precise candidate extension, unverified: in a conditionally independent Gaussian multifactor model, partition true-null nonzero loading vectors into H oriented-ray groups; zero loadings may join any group; pi_h=m0,h/m>0, sum pi_h=pi0. Put r_i=||a_i||, gamma_i=sqrt((1-r_i)/(1+r_i)), u=barPhi^{-1}(q), q<1/2, b_h=barPhi^{-1}(q*pi_h). On event Y_h<=b_h use integrated envelope I_b<=I_u+log(q/barPhi(b))=I_u+log(1/pi_h); complementary group FDP<=1 costs q*pi_h. Summing gives FDR <= (3/2)q*pi0 + (q*u/sqrt(2pi))*m^{-1}sum_{I0}gamma_i + q*E, E=sum_h pi_h log(1/pi_h). Thus E=o(sqrt(log(1/q))) preserves one-sided target upper constant regardless of ambient factor dimension. Projections need not be independent. This is a different condition from bounded rank. All-null/no-null cases and r=0,1 require explicit handling. Prior optimistic entropy=o(log(1/q)) without a loading gap is not justified: r=1 outer envelope integral is logarithmic. With uniform norm r<=r*<1 a sharper entropy condition might be possible but is not this statement.
