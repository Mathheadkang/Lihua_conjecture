---
type: idea
title: Cold-checked proof of the null-block completion certificate obstruction
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_sharp_upper
tags:
  - cold-verified-draft
  - scope-clarified
  - pending-native-integration
---

This complete proof remains a DRAFT research idea, not a native approved asset or manuscript theorem. Fresh cold reviewer /root/completion_final_cold_review confirmed all mathematical steps in source idea_ce4038795c70, SHA256 271ceeb1a8c17a237162660d07f32432abd0694b5c7d0da811eb69c0a212fb43, on 2026-11-04. The present copy preserves the proof with exactly three requested clarifications: D0 is diagonal, the O(1/z_N) shift refers to the normal argument, and the reference endpoint is lambda=0. No mathematical estimate was changed. The obstruction concerns the null-diagonal/block completion certificate class, while the scalar FDR conjecture is unrefuted.

1. Model and constants. Fix ANY q in (0,1/2). Let beta=10, eta=(q/2)e^{-beta}, r=1-eta, alpha=log(2/q-e^{-beta}), D=alpha*r-beta*eta. Then alpha>1.38, eta<1.14e-5, D>0, and the equation h(s;-beta,0)=1/q has root s=1, where
h(s;A,lambda)=(1/2)e^{A s-lambda s^2/2}+(1/2)e^{alpha s}.
Choose c=1/100, even N=2n, z_N=sqrt(2c log N), rho_N=lambda/z_N^2. True nulls i<=n are
T_i=-beta/z_N+sqrt(rho_N)W+sqrt(1-rho_N)epsilon_i;
alternatives j>n are T_j=alpha/z_N+epsilon_j.
All variables W,epsilon are independent standard Gaussians. For each fixed lambda and sufficiently large N, Sigma_N is PD, unit diagonal, with only its null block equicorrelated by rho_N; alternative block and crossblock are I and0. Null means are negative and alternative means positive. B=I is the fixed-alternative starting covariance; Gamma_N=diag(J_n,I_n) is a valid PSD correlation completion with the SAME alternative block.

2. Root neighborhood. At (A,lambda)=(-beta,0), h(0)=1<1/q, h(1)=1/q, and h_s(1)=D/q>0. Choose epsilon>0 and lambda0>0 sufficiently small (depending on this fixed q), so for |A+beta|<=epsilon and 0<=lambda<=lambda0 the unique positive root S(A,lambda) lies in (.9,1.1). This follows from continuity and strict convexity: take epsilon<beta/2 and lambda0<(beta-epsilon)^2, so the null exponential's second derivative ((A-lambda s)^2-lambda)e^{A s-lambda s²/2} is positive for all s>=0; the alternative second derivative is positive. The function grows to infinity via e^{alpha s}. Thus S is smooth in a compact parameter neighborhood. For every fixed small delta>0, h stays uniformly below1/q for 0<=s<=S-delta and is uniformly above1/q at S+delta, with a positive margin.

3. Uniform normal-tail ratios. Conditional on W, A=-beta+sqrt(lambda)W. Let x=barPhi^-1(t), s=x/z_N. Uniformly for |A+beta|<=epsilon and x in[u_q,(3/2)z_N], where u_q=barPhi^-1(q)>0,
F_{0,N}(t|W)/t=e^{A s-lambda s²/2}+o(1),
F_{1,N}(t)/t=e^{alpha s}+o(1).
Here F0,F1 are actual conditional null/alternative p-value CDFs. To verify, use h_G(x)=phi(x)/barPhi(x), 0<h_G(x)-x<=1/x, on x>=u_q/2; the normal-argument shift is O(1/z_N). Taylor expansion of log barPhi with bounded hazard derivative on that interval gives log(F0/t)=A x/z_N-lambda x²/(2z_N²)+O(1/z_N), and the analogous alternative formula. Constants may depend on fixed q/epsilon/lambda0, which is sufficient. The lower endpoint s=u_q/z_N is included, so all larger BH grid levels are covered.

4. GLOBAL BH localization in the finite Gaussian array. Given W in the root neighborhood, each of the two groups has n iid continuous p-values. Elementary uniform empirical-CDF concentration suffices: take M_N=ceil(N^{1/4}) true-CDF quantile grid points in each group. Chebyshev at each point gives error>N^{-1/4} probability O(N^{-1/2}); union over O(N^{1/4}) points and monotonicity gives sup_t|Fhat_h-F_h|<=3N^{-1/4} with probability1-O(N^{-1/4}), uniformly in W. This needs no unapproved DKW black box.
Let t_min=barPhi((3/2)z_N), so t_min is of order N^{-(9/4)c}/sqrt(log N), and N^{-1/4}/t_min->0 since (9/4)c=.0225<1/4. Also (q/N)/t_min->0. Therefore empirical mixture Fhat(t)/t converges uniformly to h(x/z_N;A,lambda) for ALL t in[t_min,q].
For any small delta, no BH grid level t>=barPhi((S-delta)z_N) qualifies, by the strict below-line margin. A grid level within q/N of barPhi((S+delta)z_N) does qualify, by the above-line margin and negligible relative grid error. Since S+delta<3/2, this level is >=t_min and has polynomially many rejections. Hence the LARGEST BH threshold has scaled normal score converging in conditional probability to S. This rules out larger-rank crossings, not merely a local root. The actual FDP converges to
g(A,lambda)=(q/2)e^{A S-lambda S²/2}=1-(q/2)e^{alpha S}
on the same neighborhood, because empirical null-CDF errors divided by the threshold vanish. Boundedness gives conditional expectation convergence and then convergence after integrating over a fixed W neighborhood. At lambda=0 the independent reference FDR tends to eta.

5. Localized Gaussian mixing and positive gain. Define E_lambda={|sqrt(lambda)W|<=epsilon}; no smooth-root assertion outside E_lambda is needed. The Gaussian tail is O(exp(-epsilon²/(2lambda)))=o(lambda). Smooth Taylor expansion on the compact neighborhood and finite Gaussian third moments give
E[1_{E_lambda} g(-beta+sqrt(lambda)W,lambda)]
=eta+(lambda/2)G0+o(lambda).
At the base point, S_A=-eta/D, S_lambda=eta/(2D), g_A=alpha*r*eta/D, and 2g_lambda=-g_A. Direct implicit differentiation gives
G0=g_AA+2g_lambda
=alpha*r*eta²/D³ [2alpha*r(beta-1)+beta*eta(alpha+2-beta)]>0.
For alpha>=8 the bracket is positive termwise; for 1.38<alpha<8, its first term exceeds24 while the only possible negative term is <80eta<.001. Thus positivity holds for every fixed q<1/2. The factor is G0/2, not G0, in the lambda gain. Select sufficiently small fixed lambda>0 so this localized expectation exceeds eta+lambda G0/4. On E_lambda^c use FDP nonnegativity. The finite-N convergence in step4 and independent reference limit therefore yield
liminf_N [B_N(Sigma_N)-B_N(I)] >=lambda G0/4>0,
where B_N denotes actual BH FDR.

6. Certificate obstruction and limits. In the fixed-alt path I->Sigma_N only null-null offdiagonal entries vary. The exact finite-model corner identity (from the prior plans) gives
tr(Gamma_N K_N)=[B_N(Sigma_N)-B_N(I)]/rho_N,
also when K_AA is set to0, since both Sigma and Gamma have zero alternative offdiagonals and zero crossblock. Consequently
liminf_N tr(Gamma_N K_N)/log N >=cG0/2>0.
For any feasible corrected block certificate M-K_N PSD, with D0=Diag(d) on the null block and M=embed_null(D0)+embed_alt(H), pairing with Gamma_N gives tr(D0)+tr(H I)>=tr(Gamma_N K_N). Thus NO such certificate can have an N-uniform trace budget depending only on this q. This refutes the GENERAL constrained-completion certificate, not only the explicit row recipe (R). Fix q first, then epsilon/lambda, then N; no uniform positive G0 in q is needed, and q can be arbitrarily small. All models belong to the already covered one-common-factor-plus-independent-residual class, so this calculation supplies no counterexample to the actual sharp-FDR conjecture. It proves a limitation of pairing the kernel from one covariance with other admissible completions.
