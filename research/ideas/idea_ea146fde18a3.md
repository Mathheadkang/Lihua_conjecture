---
type: idea
title: >-
  Log-FDR regularization gives feasible Gaussian-score MGF constraints at
  extremizers
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - parameter-extremality
  - log-fdr
  - gaussian-score
  - projected-moments
  - unproved
---

Variant of idea_5d513ff67111 to verify, not an established main bound. For fixed finite N,q and nonempty frozen true-label set, consider maximizing log F-epsilon p(theta)+(eta/N)logdet Sigma, p(theta)=log(1+||theta||^2), over the same closed mean orthants and positive-definite unit-diagonal covariances, and jointly over label sets. Log F<=0 makes the proposed penalties coercive; positive reference F and the label-boundary relabel argument still need complete verification. Original singular models and divergent means require approximation, not an assumed limiting optimizer.

At a verified optimizer, Gaussian mean-score identities give grad_theta logF=E_Q[S] and Hess_theta logF=Cov_Q(S)-Sigma^{-1}, with S=Sigma^{-1}(T-theta). On directions z supported on the interior-mean index set J, mean second-order optimality would give z^T(Cov_Q(S)-Sigma^{-1})z<=2epsilon||z||^2. For w=Sigma^{-1/2}z and G=Sigma^{-1/2}(T-theta), this yields a projected latent covariance bound Var_Q(w dot G)<=(1+2epsilon N)||w||^2, since ||Sigma||op<=N. This is only a bound on the free-mean score subspace, not global Cov_Q<=I and not a Poincare inequality. Compared with F rather than logF regularization, no division by F is needed in this error term.

A global feasible-shift condition may be stronger than just local moments. For a fixed Sigma and any delta for which theta+delta stays in the same closed label orthants, Gaussian likelihood ratios imply F(theta+delta)/F(theta)=E_Q exp(w dot G-||w||^2/2), w=Sigma^{-1/2}delta. Optimality of the proposed log objective would therefore give log E_Q exp(w dot G)<=||w||^2/2+epsilon[p(theta+delta)-p(theta)]. The penalty difference is bounded above by ||delta|| because ||grad p||<=1. This is a concrete Gaussian-score MGF constraint on feasible directions; it must not be extended outside the allowed mean shifts or mistaken for a conditional-on-every-boundary-null bound.

Covariance differentiation has a crucial outer-product term: C_log=grad_Sigma logF=(1/(2F))Hess_theta F=(Hess_theta logF+(grad_theta logF)(grad_theta logF)^T)/2. Thus covariance KKT would be C_log+(eta/N)Sigma^{-1}=Lambda diagonal. Replacing C_log by half the mean Hessian of logF alone would be wrong. Reprove all identities by Gaussian-density differentiation (the checked Price source supplies background), preserving fixed labels and barrier terms. If using a q-envelope, keep regularization parameters fixed throughout the integration interval.

No connection from these additional stationary constraints to the required universal FDR order has yet been proved. The next substantive gate remains an explicit signed actual-BH face estimate or a genuinely justified optimized-envelope inequality, with no dimension-dependent completion or unproved global entropy-stability hypothesis hidden.
