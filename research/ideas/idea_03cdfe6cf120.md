---
type: idea
title: >-
  Phase2 batch3 actual analytic test: AH-main hugging functional is infinite
  already for one Gaussian null
status: draft
idea_kind: test_case
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_two_sided_universal_order_upper
tags:
  - phase2
  - batch3
  - auxiliary-counterexample
  - actual-bh
  - analytic-test
tried_in:
  - target: gaussian_bh_one_sided_universal_order_upper
    round: 2
    slot: 3
    statement_digest: 00cfb3c66a8136044b1cb19c4e657b92bca75995aa6b9711598a30aa2009eff2
    outcome: no candidate written (show idea_03cdfe6cf120 for what was found)
---

New exact first test of idea_9e08f52bc7c4, preserving its original text/status. This refutes its displayed AH-main functional as written, not either main theorem, not every possible shell program.

Take N=1, theta=(0), Sigma=[1], T1=G standard normal, q∈(0,1/2), U=S^{-1}(q), one true-null direction group g with n_g=N=1. Its displayed k(w)=N S(w)/q=S(w)/q satisfies 0<k(w)<=1 for every finite w>=U. The count of OTHER coordinates is identically N_-g(w)=0. Hence k(w)-n_g<=N_-g(w)<k(w) at EVERY w>=U. The proposed functional is exactly A=∫_U^∞ h(w)dw=∞, since h(w)=phi(w)/S(w)=−d log S(w)/dw and S(w)->0. The right-hand C(1+U) is finite. No covariance, asymptotic, discrete-grid or numerical ambiguity is involved.

Actual ordinary largest BH rank is R=1 iff S(G)<=q, otherwise0; FDP=1{G>=U}, FDR=q. At moving nominal level u its one actual interface is G=z(u), jump0->1, speed1/phi(z(u)), Gaussian face weightphi(z(u)), so S_positive(u)=1 and signed FDR derivative1. Thus the divergent hugging proxy is unrelated to a divergent actual q-flux in this object.

Stronger diagnostic: for ANY fixed finite-score realization in ANY finite model and ANY nonempty null group n_g>0, choose W>max(U,max_j T_j,S^{-1}(q n_g/N)). For w>W, N_-g(w)=0 and 0<k(w)<n_g, so its displayed indicator is again1 and the same improper integral diverges. The missing restriction is not a rare family: the proxy counts levels above all observed scores. A revised proxy must keep actual group activation/realized rank support or an explicit genuine finite mesh; deriving a paid majorant after that repair would be a materially new obligation, not an edit to the original during proof.

The claimed AH-flat convexity and any correctly weighted/group-activated shell majorant are separate questions. No claim here that all shell programs fail. Recomputable analytically from one normal survival function; no simulation was used.

## Tried

- Search round 2 for gaussian_bh_one_sided_universal_order_upper (slot 3): no candidate written (show idea_03cdfe6cf120 for what was found)
