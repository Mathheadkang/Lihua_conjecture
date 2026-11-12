---
type: idea
title: >-
  Unverified rank-three signed OU surface mixture with a positive actual-BH
  excess
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_ou_integrated_signed_budget_bridge
tags:
  - signed-ou-surface
  - unverified-diagnostic
---

Draft search round4 slot2 diagnostic, not independently verified and not an approved bridge or budget obstruction. No main-theorem candidate. The requested OU functional and gate were missing from the pack, so the Statement of gaussian_bh_ou_integrated_signed_budget_bridge was requested natively. This calculation preserves its fixed full actual FDP and forms the complete signed vector mixture before the norm.

MODEL AND POSITIVE EXCESS. Let U=barPhi^{-1}(q), G=(X,Y,Z) standard independent Gaussian, T1=X, T2=Y, T3=A=(-X-Y+Z)/sqrt(3)+mu with mu=1/U>0. The null labels are delta1=delta2=1, delta3=0 and pi0=2/3. Unit loading vectors are v1=e1, v2=e2, v3=(-e1-e2+e3)/sqrt(3), giving covariance rank three with Corr(X,A)=Corr(Y,A)=-1/sqrt(3). Put br=barPhi^{-1}(qr/3), r=1,2,3. All rank statements below refer to the original N=3 largest-crossing BH.

FULL SIGNED JUMP GEOMETRY. On the latent hyperplane Hi,r={y: vi dot y=ai,r}, ai,r=br-theta_i, let h>=ell be the ordered remaining two statistic values, with delta_h the label of their higher coordinate. Coincident comparisons are irrelevant to surface measure. The jump Delta_i,r is the upper-in-Ti FDP minus the lower-in-Ti FDP:
r=1: the gate is h<b2 and ell<b3, with Delta_i,1=delta_i; elsewhere zero.
r=2: the gate is h>=b2 and ell<b3, with Delta_i,2=(delta_i+delta_h)/2-delta_h*1{h>=b1}; elsewhere zero.
r=3: the gate is ell>=b3, with Delta_i,3=2/3-w, where w=(delta_j+delta_k)/2 if ell>=b2, w=delta_h if ell<b2 and h>=b1, and w=0 otherwise; elsewhere zero.
These gates exclude every larger crossing first, then compute the actual lower-side rank. They retain negative jumps: for example an alternative r=2 face with h>=b1 has jump -1/2, while the same alternative face with b2<=h<b1 has jump +1/2. A null r=3 face can also be negative. No positive-part replacement is made. Distributionally,
Df=sum_(i,r) vi * Delta_i,r(y) * H^2 restricted to Hi,r.
The score map has rank three, so intersections of distinct faces have zero H^2 measure.

EXACT HIGHER-RANK OU REDUCTION TO VERIFY. Let gamma3(y) be standard three-dimensional Gaussian density, rho=e^(-t), s=sqrt(1-rho^2), and K_s the centered three-dimensional Gaussian density of covariance s^2 I. Define the complete signed vector mixture
M_rho(x)=sum_(i,r) vi integral_(Hi,r) Delta_i,r(y) gamma3(y) K_s(x-rho y) dH^2(y).
Mehler differentiation and reversibility gamma3(x)K_s(y-rho x)=gamma3(y)K_s(x-rho y) give
gamma3(x) grad P_t f(x)=rho M_rho(x),
and, using dt=-d rho/rho,
J_OU(f)=integral_0^1 integral_R3 ||M_rho(x)||_2 dx d rho.
The vector sum, including both signs of every face, is inside the norm. This is the dimension-three surface analogue of the draft one-dimensional signed-mixture formula. The finite polyhedral partition gives a BV justification; an independent verifier must check the distributional differentiation and all limiting interchanges. A face may equivalently be evaluated as phi(ai,r) times the conditional Gaussian surface integral with y=ai,r vi+(I-vi vi^T)W. No independence of the other statistic gates is asserted.

DIRECT FINITE-MODEL NORM BOUNDS. Kernel mass one and the triangle inequality only after forming this exact signed mixture yield
||E[G f]||_2 <= J_OU(f) <= sum_(i,r) integral_(Hi,r) |Delta_i,r| gamma3 dH^2 <= sum_(i,r) phi(ai,r).
The lower bound follows by integrating M_rho over x, which equals E[Gf] for every rho by Gaussian integration by parts. Since br=U-log(r/3)/U+o(1/U), the upper sum is (4+2e+o(1))qU.

ACTUAL FDR EXPANSION AND LOWER NORM SCALE. Let f0 be the auxiliary two-null BH FDP with the alternative p-value set to one while retaining denominator N=3; this is bookkeeping only, not a replacement of the original model. Its expectation is exactly 2q/3 because the two null p-values are independent uniforms. Off the event {p1<=q,p2<=q,p3<=q}, the actual change f-f0 is the sum of the two exact pair corrections
0.5*1{pi<=2q/3,p3<=2q/3}-1{pi<=q/3,p3<=2q/3}, i=1,2.
The bounded remainder has probability at most q^2 barPhi((2+sqrt(3))U-sqrt(3)/U)=q^(9+4sqrt(3)+o(1)). Indeed the triple event forces X,Y>=U and Z>=(2+sqrt(3))U-sqrt(3)/U.

For the bivariate null-alternative law put rho0=-1/sqrt(3), lambda=1/(1+rho0)=(3+sqrt(3))/2, and Jtail=P{X>=b2,A>=b2}. Quadrant Laplace integration with x=U+s/U,a=U+t/U gives, for fixed c,d>0,
P{X>=barPhi^{-1}(cq),A>=barPhi^{-1}(dq)}~C_rho0*(cd)^lambda*U^(-2)*exp(-lambda U^2),
where C_rho0=exp(lambda)/(2*pi*sqrt(1-rho0^2)*lambda^2). Thus the mixed-threshold to equal-threshold ratio tends to 2^(-lambda), and Jtail=q^(3+sqrt(3)+o(1)). The actual full FDR consequently has the proposed expansion
F=2q/3+2*(1/2-2^(-lambda))*Jtail+o(Jtail).
The coefficient is positive, so this test has a genuinely nonzero bridge numerator; it does not escape by having F<=q*pi0.

Finally E[Gf0]=(qU/3,qU/3,0)+o(qU). The support of f-f0 requires an alternative and at least one null statistic above U, whose probability is q^(3+sqrt(3)+o(1)); Cauchy-Schwarz therefore makes E[G(f-f0)]=o(qU). It follows that J_OU(f)>=(sqrt(2)/3+o(1))qU, and hence J_OU(f)=Theta(qU). Combined with the positive-excess expansion, the tested bridge ratio F(F-q*pi0)_+/(q J_OU(f)) is of order Jtail/(qU) and tends to zero.

SCOPE. This is an exact-face and asymptotic diagnostic pending independent verification, not a proof of the generic analytic prerequisite or the universal BH gate. The fixed three-test model neither refutes the bridge nor the main theorem. The useful output is a full higher-rank signed-vector surface formula with explicit positive and negative actual-rank jumps, and a nonvacuous test whose bridge ratio stays controlled. Any rank-preserving adaptive carrier must still pay the complete mixed-label surface mixture uniformly over arbitrary rank and dimension.
