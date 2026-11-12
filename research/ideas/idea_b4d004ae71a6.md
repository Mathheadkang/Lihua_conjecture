---
type: idea
title: >-
  Independent check confirms simplex envelope obstruction for both testing
  tracks
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_sharp_upper
  - gaussian_bh_two_sided_sharp_upper
tags:
  - independent-check
  - certificate-limitation
  - pending-native-asset-integration
---

Independent read-only review of idea_45ea077b792d by fresh agent /root/simplex_envelope_review (2026-11-04) found no blocking mathematical defect, including a two-sided extension. This records review evidence, not native asset approval, a human review, or a refutation of either unrestricted BH conjecture. The proposed statement remains an idea, pending formal graph integration.

Common model: m=ceil(exp(2/q)/q), T_i=(X_i-Xbar)/sqrt(1-1/m), iid standard normal X, all null means zero. Sigma has kernel 1, forcing D=0 in every Sigma=A A^T+D independent-diagonal-residual Gaussian factor representation. Complete-factor conditioning therefore yields S_i=1{P_i<=q}/P_i in every representation, for either P_i=barPhi(T_i) or P_i=2barPhi(|T_i|).

Let Y_i=min(S_i,m), mu=1+log(qm)>=1+2/q; E Y_i²=2m-1/q. One-sided monotone negative Gaussian covariance gives Var(avg Y)<=2. For the two-sided extension, rho=-1/(m-1), normalized Hermite expansion of the SAME bounded centered function g gives Cov(g(T_i),g(T_j))=sum_{k>=1} a_k² rho^k <=rho² Var(g) (odd terms nonpositive; even terms <=rho²). Thus Var(avg Y)<=Var(Y)/(m-1)<=2m/(m-1). Consequently E min(1,q avg S)>=1-[2m/(m-1)]q²/(1+q)² ->1 for both tracks. One-sided has the slightly stronger constant 2 in place of 2m/(m-1). Taking the infimum over all such representations cannot improve this certificate.

Actual BH global-null FDR=q(1+o(1)) for BOTH tracks. Write delta=q², M=2sqrt(log m). With probability at least 1-e_m, e_m<=16/(m q^4)+2m barPhi(M)=o(q²), |Xbar|<=delta/4, max|X_i|<=M and eventually max|T_i-X_i|<=delta. For sufficiently small q, z_q-delta>=1, and z_{q/(cm)}<=M (two-sided z_{q/(2cm)}<=M), where c=exp(delta(M+1))=1+O(q^(3/2)); m(q) grows fast enough for these quantile checks. Mills hazard h(x)<=x+1/x bounds tail ratios on [1,M]. On this event, global BH_X(q/c) rejects => BH_T(q) rejects => BH_X(cq) rejects, using the same rank grid. Independent Simes is applied UNCONDITIONALLY, then add/subtract e_m: q/c-e_m <= FDR_T(q) <=cq+e_m. Hence ratio to q tends to 1, whereas the optimized full-factor envelope tends to 1 in absolute scale.

Scope: an exact PSD rank-(m-1) simplex family and this particular full-factor conditional-supremum certificate with independent diagonal residuals. Arbitrary alternative conditioning arguments, signed rank identities, and actual Gaussian BH sharp constants are untouched. Independent reviewer specifically required writing the quantile/Mills conditions and unconditional Simes transfer explicitly. The standard independent Simes result can be sourced to https://academic.oup.com/biomet/article-abstract/83/4/928/253627 before any manuscript citation is added; not yet added to the paper bibliography.
