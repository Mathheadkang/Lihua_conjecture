---
type: idea
title: >-
  Horizontal rank-survival brackets can justify a complete particle-mass
  derivative
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_private_noise_cutoff_signed_transport_variation
  - gaussian_bh_averaged_signed_mean_level_complementarity
  - gaussian_bh_one_sided_universal_order_upper
tags: []
---

More explicit proof candidate for the mass-variation part of the next route; not yet executed or approved. Fix q,sigma,s,a and two lawful finite-M2 directing laws pi,nu, chosen before innovations (enlarge the separable Gaussian background if needed). For pi_epsilon=(1-epsilon)pi+epsilon nu, conditional total and true score tails differ from baseline by at most epsilon uniformly in score and X. At each fixed rank r, H_epsilon(Q_epsilon)=H(Q)=r and V is a submeasure of H, so |V_epsilon(Q_epsilon(r))-V(Q(r))|<=2epsilon. Hence |f_epsilon(r)-f(r)|<=2epsilon/a for r>=a, without any lower bound on the score density h. Local implicit differentiation gives Qdot=(H_nu(Q)-H(Q))/h(Q) and fdot=[V_nu(Q)-V(Q)-(h0(Q)/h(Q))(H_nu(Q)-H(Q))]/r.
Take epsilon<a/2 and let Delta_z=L(q,a/2)*epsilon/sigma, where L bounds |d u_q(r)/dr| on [a/2,1]. A qualifier at rank r in the perturbed model implies a baseline qualifier at r-epsilon after a common-Z shift Delta_z, by H_epsilon-H<=epsilon and u_q(r-epsilon)-u_q(r)<=sigma Delta_z. The converse gives, for r>=a, indicator brackets 1{R_0(Z-Delta_z)>=r+epsilon}<=1{R_epsilon(Z)>=r}<=1{R_0(Z+Delta_z)>=r-epsilon}. Thus the rank-survival difference quotients are bounded by horizontal difference quotients of F_X(r)=S(M_X(r)) plus the constant 2Delta_z/(epsilon sqrt(2pi)).
Show F_X is absolutely continuous on [a/2,1] after setting F_X(1)=0: the private kernel makes B C1 and B(1)=infinity, the suffix minimum M is nondecreasing and locally Lipschitz below 1, and local chain-rule integrals pass to 1 because total variation is at most one and there is no endpoint atom. Horizontal difference quotients of this absolutely continuous F_X are uniformly integrable in r (translations of its L1 derivative). The pointwise all-active-minima envelope limit therefore converges in L1(r) by Vitali, justifying its integral against bounded w=(chi f)'. Combine with the bounded payoff quotient and rank convergence at Gaussian-continuity levels. This establishes the full conditional mass-response formula rather than assuming a derivative from value continuity.
Also derive a conditional-X-uniform Lipschitz bound for the entire expected cutoff payoff. Let W=||chi'||inf+1/a and T=1+log(1/a). Integrating the rank-indicator brackets gives E_Z|g_0(R_epsilon)-g_0(R_0)|<=2epsilon W+2Delta_z*T/sqrt(2pi), while the fixed-rank payoff change is <=2epsilon/a. Thus full conditional difference quotients are bounded independently of X,pi,nu,s, allowing the final X expectation by dominated convergence. The full signed derivative is the approved formula with the above Qdot,fdot; joint level velocity only adds a bounded common-Z shift and -lambda m(u_q(t))/sigma in the envelope. Moment derivative is M2(nu)-M2(pi), and source finite endpoint recovery applies after fixing epsilon. All endpoint brackets, absolute continuity, and Vitali steps must be checked; this is a proposed self-contained calculus lemma, not a main q-scaled bound. Its fixed-parameter constants still depend on a and sigma.
