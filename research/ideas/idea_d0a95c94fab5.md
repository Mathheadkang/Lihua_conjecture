---
type: idea
title: Exact BH peeling filtration and compensated Gaussian history-face kernel
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - universal-order
  - peeling-filtration
  - conditional-gaussian-history
  - signed-compensator
  - online-resource-trial
---

NEW DRAFT alternative route, not an established main upper bound. It preserves actual BH selection through its algorithmic descending peeling filtration instead of optimizing over free thresholds. A separate worker derived these candidate identities and exact finite calibration; each must be independently reconstructed in native execution before use.

Let S0=[N], m_n=|S_n|, t_n=q*m_n/N, and S_(n+1)={i in S_n:p_i<=t_n}. Sets are nested; finish at the first unchanged set or an empty set. Prove the terminal set is the ordinary largest-rank BH rejection set. Set t_(-1)=1, V_n=|I0 intersection S_n|, W_n=V_n/t_(n-1) before stopping, and freeze W after stopping (empty state W=0). At an unchanged set the denominator equals qR/N, so final W=(N/q)FDP. The finite compensated identity to derive is

$$
\operatorname{FDR}=q|I_0|/N+(q/N)\sum_n\mathbb E D_n,
$$

where before stopping

$$
D_n=\sum_{i\in I_0\cap S_n}\left\{\Pr(T_i\ge u_{m_n}\mid\mathcal H_n)/t_n-1/t_{n-1}\right\},\qquad u_k=S^{-1}(qk/N),
$$

and the process is frozen afterwards. Each finite history is a rectangle of Gaussian score bands, with actual means and original true labels. For an alive i in a fixed history h put a=S^{-1}(tprev), b=S^{-1}(t), p_x=S(x-theta_i), r=p_b/p_a. Gaussian marginal tail monotonicity for theta_i<=0 implies r<=t/tprev. Write w_h(x)=P(other-coordinate history rectangle | T_i=x). The exact history-weighted i-defect is

$$
\Pr(h)\{\Pr(T_i\ge b\mid h)/t-1/tprev\}
=t^{-1}\int_a^\infty K(x)w'_h(x)\,dx+\Pr(h)\{r/t-1/tprev\},
$$

with nonpositive last term and the NONNEGATIVE explicit kernel

$$
K(x)=\begin{cases}r(p_a-p_x),&a\le x<b,\\(1-r)p_x,&x\ge b.\end{cases}
$$

At the first history a=-infinity and tprev=1; prove all endpoint and freezing conventions rather than silently divide by zero. This is integration by parts of the signed density [1{x>=b}-r*1{x>=a}]phi(x-theta_i), whose primitive is -K. Under positive-definite covariance, conditional Gaussian regression gives w'_h as the signed sum of covariance-weighted LOWER minus UPPER conditional rectangle-face masses. The new concrete calculation is to pair opposite faces of SIBLING reveal histories before taking absolute values and before discarding the nonpositive composite-null term. Different histories have different t and K weights, so naive cancellation is not already a proof. A total budget of C N(1+U), U=S^{-1}(q), for the actual signed history-kernel charge would suffice for the order target, but is UNPROVED and might fail. Never call the unknown budget a martingale theorem. Any singular transfer requires a uniform finite-PD estimate first.

Exact finite stress test (N=2 or3, also any N>=2): let X~N(0,1), T1=X, T_j=mu-X for j>1, mu=u_N+u_1>0, Sigma=vv^T, v=(1,-1,...,-1), I0={1}. History S1={1} is exactly X>u_1 up to null boundaries; it has probability q/N. Next conditional null survival is1 rather than1/N. Its expected normalized drift is1-1/N, while first-stage and other drifts vanish; actual FDR=(q/N)(2-1/N). The conditional-history weight has derivative a point mass at u_1 and K(u_1)/t=1-1/N, confirming the kernel normalization. A positive-definite regularization must be checked before using densities. This refutes only a pointwise reverse-supermartingale shortcut, not the main bound; rare-history probabilities must be retained.

Source-scope verification: original author-hosted PDF Exact Post-selection Inference for Forward Stepwise and Least Angle Regression, Jonathan Taylor, Richard Lockhart, Ryan J. Tibshirani and Robert Tibshirani, https://www.stat.cmu.edu/~ryantibs/journalclub/taylor_2014.pdf, Lemma1 pp5-6, supplies a general-covariance Gaussian polyhedral truncation technique, not sequential FDR control; its introduction explicitly leaves sequential FDR stopping outside its scope. This hosted copy has no verified publication metadata asserted here. Philipp Heesen and Arnold Janssen, Inequalities for the false discovery rate (FDR) under dependence, https://arxiv.org/abs/1410.8290v2 (17February2015), distinguishes reverse-martingale dependence from PRDS; no arbitrary-Gaussian optional-stopping guarantee is imported. All candidate identities above should be proved inline; no unapproved library dependency is used.

## Resolution

Converted to the native stopped-peeling and sibling-history-kernel trial; all source calculations remain unverified candidates until execution and fresh checking.
