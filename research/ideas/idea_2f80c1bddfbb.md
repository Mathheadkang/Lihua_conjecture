---
type: idea
title: >-
  Independent all-null BH dust has exact FDR q but vanishing full signed OU
  budget
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_ou_integrated_signed_budget_bridge
tags:
  - signed-ou
  - independent-dust
  - plan-stage-partial
---

Draft rigorous diagnostic produced by a focused PLAN-stage worker and preserved without authoring or self-verifying a target proof. It concerns the full actual-BH OU functional, not a facewise positive-part substitute. It does not refute gaussian_bh_ou_integrated_signed_budget_bridge because the actual excess numerator below is exactly zero.

MODEL AND EXACT BASELINE. Fix q in (0,1). Take N independent standard Gaussian null scores, all means zero, all original labels null. Let f_N(x)=1{ordinary largest-nonstrict-crossing BH has R_N(x)>0}. Thus the full actual FDP is an indicator. Exact independent-BH calibration gives F_N=E f_N=q: for each coordinate i, forcing its p-value to zero gives R_i>=1 independent of p_i; on rejection of i the actual R equals R_i, so E[1{i rejected}/R]=sum_r P(R_i=r)(qr/N)/r=q/N. Summing gives q.

NEW CLAIM TO CHECK INDEPENDENTLY. For this lawful finite sequence, J(f_N)=integral_0^infinity E||grad P_t f_N||dt tends to zero as N tends to infinity, at fixed q. Hence no universal lower payment J(f)>=cF, or positive baseline replacement inside the OU bridge, can hold. The existing bridge retains (F-q*pi0)_+=0 and survives this test.

FINITE RANK AND REPLICA CONTROL. Put c_q=log(1/q)-1+q>0 and tau_K=exp[-c_q(K+1)]/[1-exp(-c_q)]. If R_N>K, some r>=K+1 has Bin(N,qr/N)>=r. The exponential Chernoff bound for each r and a union bound give P(R_N>K)<=tau_K. This is for the original largest BH rank, not a replaced small-rank procedure.

Let X,Y be Gaussian replicas, independent across i, with Corr(X_i,Y_i)=rho in (0,1). For N>=2qK set b=barPhi^{-1}(qK/N)>=0. Categorize each replica's p_i into K bins with endpoints qk/N and an outside category. Each coordinate has rare mass a=qK/N. The total variation distance between the paired categorical law and independent copies is at most 2[P(X_i>=b,Y_i>=b)+a^2]. One elementary proof uses the rare-rare block, whose L1 difference is at most P(both rare)+a^2; the two rare-outside blocks and outside-outside entry are then controlled by the identical marginals. Tensorization bounds the N-coordinate total variation by N times this quantity. Also P(X_i>=b,Y_i>=b)<=exp[-b^2/(1+rho)] by applying a Gaussian Chernoff bound to X_i+Y_i.

The event of a BH crossing among ranks <=K is determined by these categorical counts. It differs from f_N only on R_N>K. Restoring both replicas and their product of expectations therefore gives the explicit safe bound
|Cov(f_N(X),f_N(Y))| <= 2N exp[-b^2/(1+rho)] + 2(qK)^2/N + 4 tau_K.
Since b^2=2log N+O_{q,K}(loglog N), the first term tends to zero for every fixed rho<1. First taking N to infinity and then K to infinity proves that this covariance tends to zero.

MEHLER PAYMENT WITH CANCELLATION RETAINED. Direct differentiation of P_s g and the directional Gaussian Cauchy-Schwarz/Bessel inequality give
E||grad P_s g|| <= sqrt[Var(g)/(exp(2s)-1)]
for bounded g. Apply this with s=t/2 and g=P_{t/2}f_N. Then
E||grad P_t f_N|| <= sqrt[Var(P_{t/2}f_N)/(exp(t)-1)].
By Gaussian reversibility the numerator is the preceding replica covariance with rho=exp(-t), so it tends to zero for every t>0. Because 0<=P_s f_N<=1, an integrable dominating function is 1/[2sqrt(exp(t)-1)], whose time integral is pi/2. Dominated convergence proves J(f_N)->0. No unsigned sum of face masses is substituted anywhere.

IMPLICATION AND REMAINING MAIN GATE. Even a fixed positive F=q can have vanishing total signed OU gradient after smoothing in high dimension. Thus carrier arguments must isolate genuine excess over independent calibration and preserve cancellation across distinct faces and ranks; a generic Gaussian perimeter or score lower bound in terms of F alone cannot pay the BH gate. No noncircular estimate for F(F-q*pi0)_+/(q J(f)) is supplied here. The fresh rank-three diagnostic idea_60909aecaf27 remains only a supporting test; the full signed budget and unrestricted one-sided order theorem remain unproved. No frozen or approved asset, old failed plan or native loop state is changed.
