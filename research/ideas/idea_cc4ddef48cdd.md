---
type: idea
title: >-
  Exact three-coordinate Gaussian example of local nonmonotonicity in a negative
  null mean
status: draft
idea_kind: risk
origin: agent
related_assets:
  - gaussian_bh_one_sided_sharp_upper
tags:
  - pending-independent-check
  - composite-null-means
  - exact-rank-one
---

Draft exact auxiliary counterexample to COORDINATEWISE FDR monotonicity among negative null means; independent check required. It does NOT assert that all-zero null means fail to be globally least favorable, and is different from the remote screen comparing a mean0 baseline to a negative shift.

Fix q in (0,1/2). Write u=barPhi^-1(q), v=barPhi^-1(2q/3), w=barPhi^-1(q/3), so 0<u<v<w. Let epsilon=1/4, B=w+epsilon, delta=(v-u)/2, C=B+2delta, mu=B+v, M=B+delta-u. Then M>delta>0. For t in (M-delta,M+delta), use ONE Z~N(0,1), T1=Z, T2=Z-t, T3=mu-Z. Means are (0,-t,mu), true-null set {1,2}; covariance is ss^T with s=(1,1,-1), unit diagonal PSD rank1. Keep q, mu and covariance fixed while varying t. Put A=t+u, then B<A<C and t+v>C.

Claim exact ordinary BH FDP by Z region: 0 for Z<v; 1/2 for v<=Z<=B (null1+alternative reject); 1 for B<Z<A; 2/3 for A<=Z<=C (all3 reject); 1 for Z>C (one or both nulls reject, alternative cannot). Points at endpoints have probability0. Reasons: R3 iff Z>=t+u and Z<=mu-u; R2 null1+alt iff v<=Z<=mu-v=B; R2 bothnulls requires Z>=t+v>C; all remaining false rejections use null1 with Z>=w and B>w.

Thus FDR(t)=q/3+0.5 barPhi(B)-(1/3)barPhi(t+u)+(1/3)barPhi(C), and FDR'(t)=phi(t+u)/3>0. Making the true-null mean -t MORE NEGATIVE locally increases total FDR. For t_-=M-delta/2 and t_+=M+delta/2, the exact increase is [barPhi(B+delta/2)-barPhi(B+3delta/2)]/3>0.

This disproves a blanket local mean-monotonicity lemma even in exact jointly Gaussian rank1 models with valid composite nulls. The observed finite-q remote screen had a different comparison (0 versus negative), so its no-increase result is not contradicted. The all-zero-null global reduction remains unproved/unrefuted by this example. Any false rejection here requires Z>=u, so total FDR<=q; fixed N=3 makes it negligible at q sqrt(log1/q). Verify all BH cases, mean/domain constraints and formula before any theorem claim.
