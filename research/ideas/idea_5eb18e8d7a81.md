---
type: idea
title: >-
  Unverified signed rank-three rare-gate expansion at the actual largest BH
  crossing
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - signed-rank-gate
  - unverified-diagnostic
---

Draft analytic diagnostic, not independently verified, not an approved budget obstruction, and not a counterexample to the main theorem. Search round3 slot2 small_cases. This tests a higher-rank signed gate rather than a radial support family or a positive-part replacement for the actual FDR.

MODEL. Let U=barPhi^{-1}(q), let X,Y,Z be independent standard Gaussians, and use four statistics T1=X, T2=Y, T3=A=(X+Y+Z)/sqrt(3)+1/U, T4=B=(X-Y-Z)/sqrt(3)+1/U. The true nulls are exactly 1,2. This is a unit-diagonal PSD Gaussian model of covariance rank three. Its correlations include Corr(A,B)=-1/3, Corr(Y,B)=-1/sqrt(3), and three positive null-alternative correlations Corr(X,A)=Corr(X,B)=Corr(Y,A)=rho=1/sqrt(3). Each alternative has marginal probability barPhi(U-1/U)~e q of p<=q. All p-values are one-sided, with ordinary full N=4 largest-crossing BH and original labels.

EXACT RANK DECOMPOSITION. Write Ei={pi<=q}. Outside the event D that both nulls are in E or both alternatives are in E, at most one null and one alternative are in E. If just this pair (i,a) can cross, ranks three and four fail since the remaining p-values exceed q. The largest crossing is rank two exactly when pi,pa<=q/2; it is rank one when the smallest p-value is <=q/4 and rank two fails. Therefore the exact pair correction relative to the baseline indicator 1{pi<=q/4} is
delta(i,a)=0.5*1{pi<=q/2,pa<=q/2}-1{pi<=q/4,pa<=q/2}.
This includes both the added rank-two false discovery when pi is between q/4 and q/2 and the dilution of an existing rank-one false discovery when pi<=q/4. It uses the actual largest crossing, including ties; ties have probability zero for the relevant bivariate laws. On D the discrepancy between this decomposition and actual FDP is bounded by a universal constant.

ERROR CONTROL. The two null p-values are independent, so P(E1 intersect E2)=q^2. The alternatives have correlation -1/3 and means 1/U, hence their simultaneous tail is q^(3+o(1)). Thus the expectation of the bounded remainder is O(q^2). The negative-correlation null-alternative pair (Y,B) has joint tail q^(3+sqrt(3)+o(1)), also negligible below. The other three null-alternative pairs have identical positive-rho bivariate laws.

TAIL RATIO DERIVATION. Put lambda=1/(1+rho)=(3-sqrt(3))/2 and let J(c,d)=P{X>=barPhi^{-1}(cq), A>=barPhi^{-1}(dq)} for fixed positive c,d. The threshold expansion is barPhi^{-1}(cq)=U-log(c)/U+o(1/U). In the bivariate density, set x=U+s/U and a=U+t/U. Centering the alternative by its mean 1/U yields the Gaussian exponent lambda U^2+lambda(s+t-1)+o(1). Laplace integration over s>=-log(c), t>=-log(d) gives
J(c,d)~C_rho*(c*d)^lambda*U^(-2)*exp(-lambda U^2),
where C_rho=exp(lambda)/(2*pi*sqrt(1-rho^2)*lambda^2). This calculation needs independent verification, including the standard domination justification for this quadrant Laplace limit. In particular, if Jq=J(1/2,1/2), then J(1/4,1/2)/Jq tends to 2^(-lambda), and Jq=q^(3-sqrt(3)+o(1)). Hence q^2=o(Jq).

SIGNED ACTUAL-FDR CONSEQUENCE, SUBJECT TO VERIFICATION. Taking expectations of the rank decomposition gives
FDR(q)=q/2+3*(1/2-2^(-lambda))*Jq+o(Jq).
Since lambda<1, the coefficient 1/2-2^(-lambda) is negative. For each positive-correlation pair the local added-discovery piece is asymptotic to 0.5*(1-2^(-lambda))*Jq>0, while the local dilution piece is -0.5*2^(-lambda)*Jq; their signed sum is negative. Thus an independent-product estimate of order q times the marginal rare-alternative survival probability (order q^2) cannot bound these individual local pieces: their ratio to q^2 diverges. This does not refute a signed payment, does not establish that the total alternative contribution increases FDR, and does not prove a main-theorem obstruction. Rather, it identifies the joint rank gate and its cancellation that a model-adaptive weighted-carrier argument must preserve. Fixed N=4 has FDR of order q here, so no asymptotic main-theorem candidate is written.
