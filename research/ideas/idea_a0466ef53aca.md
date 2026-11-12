---
type: idea
title: >-
  Independent C candidate check: negative threshold excluded by local domain;
  unrestricted reading fails
status: draft
idea_kind: risk
origin: agent
related_assets:
  - gaussian_bh_one_sided_free_central_window
tags:
  - candidate_check
  - central_window
  - threshold_domain
  - scope_ambiguity
---

## Scope and immutable inputs

Independent candidate-only evidence check of the proposed constant-threshold example in idea_1921f69406a3, read with native show. Read only the exact Statement and Source notation and scope of gaussian_bh_one_sided_free_central_window and its five declared definitions; did not read its proof, original source plan, failed plans, or other reviews. Asset SHA256: 381e3f0c9325e5fac840b309a4af5f43c53b21a36120494f11ead7e16b1edfe2. Candidate idea SHA256: daab99f635622126def98f68e94284e9f18bb630ca902a773214c3420802fd8b. No theorem, proof, approval, plan verdict, loop state, or settings changed. This is not a main BH target counterexample.

## Exact candidate and hypotheses

Take q=1/10, r=99/100, s=sqrt(1-r^2), U=barPhi^{-1}(1/10), u(y)=-10, and u_f=10. Constant maps are Borel measurable, and 0<q<1/2, 0<=r<1, s>0 hold. A genuine allowed Gaussian multifactor model realizing the kernel is N=d=1, theta_1=0, a_1=r, Z=Y standard normal, and independent epsilon standard normal, so X=rY+s epsilon is marginally standard normal. This also satisfies the one-sided true-null convention and all model restrictions.

However, the exact Statement opens with "all v>=U"; Source notation twice specifies u_k>=U and consequence (i) explicitly works on this domain. The proposed u(y)=-10 is strictly below U>0. Thus the candidate violates the locally supplied threshold range if consequence (ii), introduced as a consequence, inherits that range. The phrase "for any ... threshold map" in (ii) does not explicitly resolve the map's codomain. No declared definition specifies an unrestricted real-valued threshold-map class. A candidate satisfying every exact/local hypothesis therefore has NOT been established.

## Analytic computation on the unrestricted-real interpretation only

Let A=int_{y<=U} phi(y) rho_r(-10,y)dy and B=int_{y<=U} phi(y) rho_r(10,y)dy. Then
A=P(Y<=U,X>=-10)/barPhi(-10)>=(0.9-barPhi(10))/(1-barPhi(10))>0.899.
The last inequality follows, for example, from barPhi(10)<phi(10)/10<0.001. Also 0<U<2 (barPhi(2)<phi(2)/2<0.1), s<0.142, and rU<1.98. Hence (10-rU)/s>56, and monotonicity yields B<=0.9 barPhi(56)/barPhi(10). Mills bounds barPhi(56)<phi(56)/56 and barPhi(10)>10 phi(10)/101 give
B<0.9*(101/560)*exp(-(56^2-10^2)/2)<exp(-1500).
Since gamma_r=sqrt(0.01/1.99)<0.071 and 1/sqrt(2*pi)<0.4, the asserted bound is <0.5+0.071*2*0.4<0.557. Thus A-B>0.899-exp(-1500)>0.557: the unrestricted-real interpretation fails analytically.

Reproducible supplementary numerical calculation using only Python standard library:
```python
from math import sqrt, pi
from statistics import NormalDist
r = 0.99
U = NormalDist().inv_cdf(0.9)
s = sqrt(1-r*r)
gamma = sqrt((1-r)/(1+r))
print(U, s, (10-r*U)/s, 0.5+gamma*U/sqrt(2*pi))
```
Output approximately: 1.2815515655446006, 0.14106735979665894, 61.89428910200415, 0.5362426223009596. Numerical values are supplementary; the strict failure above uses analytic inequalities.

## Candidate-only verdict

EXCLUDED under the locally inherited threshold domain [U,infinity); AMBIGUOUS if the intended scope of consequence (ii) is unresolved. Conditional failure for unrestricted real thresholds is confirmed, but this is not a confirmed counterexample satisfying all hypotheses of the exact auxiliary lemma. No refutation of the displayed central kernel/integral inequality, consequence (i), or main BH target follows.
