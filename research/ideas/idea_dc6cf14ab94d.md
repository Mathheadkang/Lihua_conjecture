---
type: idea
title: >-
  Proof program for the frozen-ray maximal inequality: planted-SNR calculus,
  monotone resolved fraction, and zone occupation
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - directional_entropy_one_sided_fdr_bound
  - lei2026_integrated_conditional_tail_ratios
tags:
  - cross-discipline-brainstorm-20261110
  - gaussian-channel
  - i-mmse
  - optimal-transport
  - nishimori-line
  - zone-occupation
  - unproved-key-inequality
---

Proof program for the conjecture (T) of idea_9f8ffb204424 (frozen-ray maximal likelihood ratio), from the cross-disciplinary brainstorm of 10 November 2026. Tools come from information theory (Gaussian channel in SNR), optimal transport, stochastic filtering and the statistical physics of inference. Items marked (verified) were derived in the chat and checked numerically (research-local/frozen_ray_maxlr_diagnostic_20261110/); none is natively verified. The inequality (K) and the occupation bound below are OPEN.

## Notation

$\mu$ on the unit ball; $Y_w=wX+G$ with $X\sim\mu$ independent of the standard Gaussian $G$ (planted model, law $Q_w$, density $L_w$ against the Gaussian law $\gamma$); posterior $\nu_w(\cdot\mid y)\propto\exp(w\langle x,y\rangle-w^2\|x\|^2/2)\,\mu(dx)$ with mean $\hat X_w(y)$; score $s_w(y)=\partial_w\log L_w(y)=\mathbb E[\langle X,G\rangle\mid Y_w=y]$; $m(w)=\mathbb E\|\hat X_w(Y_w)\|^2$ (resolved fraction), $D(w)=\mathrm{KL}(Q_w\|\gamma)$, $J(w)=\mathbb E\,s_w(Y_w)^2$ (Fisher information of the SNR parameter).

## Identities (verified)

(I1) Record identity. Since $\partial_wL_w=L_ws_w$ and $\mathbb E_\gamma[L_w\,\cdot\,]=\mathbb E_{Q_w}[\,\cdot\,]$,
$$
\mathbb E_\gamma\min\{c,\Lambda\}=1+\int_0^\infty\mathbb E\Big[(s_w(Y_w))_+\,\mathbf 1\{L_v(Y_w)\le L_w(Y_w)<c\ \ \forall v\le w\}\Big]\,dw .
$$
The indicator says that $w$ is a record time of the SNR profile of the observed point and that the cap is not reached; in particular $L_w(Y_w)\ge1$. In one direction the integrand is $\mathbb E[\zeta_+\mathbf 1\{w^2/2+w\zeta<\log c\}]$ and the formula returns $\tfrac12+\sqrt{\log c/\pi}+c\,\overline\Phi(\sqrt{2\log c})$ exactly. Formal Kac-Rice form: $\mathbb P_\gamma\{\Lambda\ge\alpha\}\le\alpha^{-1}\int_0^\infty\mathbb E[(s_w)_+\,\delta(\log L_w(Y_w)-\log\alpha)]\,dw$, an equality in one direction.

(I2) Planted factorization: $L^{\mu}_w(wx+g)=\exp(w\langle x,g\rangle+w^2\|x\|^2/2)\,L^{\mu_x}_w(g)$ with $\mu_x$ the law of $X'-x$. The planted likelihood ratio is the one-direction planted ratio times the null ratio of the recentred prior.

(I3) Tangent intercept: $\log L_w(y)-ws_w(y)=\int_0^wv\,\kappa_v(y)\,dv$ with $\kappa_v=-\partial_v^2\log L_v\le1$ and $\mathbb E\,\kappa_w(Y_w)=J(w)$. Hence $\log L_w\le w^2/2+ws_w$ pointwise; at a first passage of level $\log\alpha$ the accumulated curvature is at most $\log\alpha$. The score is 1-sub-Gaussian under $Q_w$ (Jensen).

(I4) I-MMSE: $D'(w)=w\,m(w)$ with $m$ nondecreasing; $D''=m+2w^2\,\mathbb E\|\mathrm{Cov}(X\mid Y_w)\|_{HS}^2$.

(I5) Fisher identity: $J=m+w^2\,\mathbb E\|\mathrm{Cov}(X\mid Y_w)\|_{HS}^2-w^2\,\mathbb E[\hat X_w^{\top}\mathrm{Cov}(X\mid Y_w)\hat X_w]\le D''$. It follows from $w\partial_wL_w=-\mathcal LL_w$ for the OU generator $\mathcal L$ and the $\Gamma_2$ computation; checked by quadrature to six digits for unit-norm atoms in dimension two.

(I6) Continuity equation: the Lebesgue density $p_w$ of $Q_w$ satisfies $\partial_wp_w+\nabla\cdot(p_w\hat X_w)=0$, and $\tfrac12\int|\partial_wp_w|=\mathbb E(s_w)_+$ is the mass swept per unit SNR.

## Mechanism

In one direction $\log L_w(Y_w)=w^2/2+w\zeta$ and $s_w=\zeta$: the planted ratio crosses the zone $[1,c)$ in SNR-time at most $\sqrt{2\log c}$ at unit sweep rate. For a general prior the sweep rate is heuristically of order $\sqrt m$ (only the resolved part of the signal moves the law) and the entropy grows at rate $wm$. Because $m$ is nondecreasing, Chebyshev's sum inequality and Cauchy-Schwarz give (verified)
$$
\int_{w_0}^{w_1}\sqrt{m(w)}\,dw\le\sqrt{2\{D(w_1)-D(w_0)\}} .
$$
Since $\sqrt{m(w)}$ is the $L^2(Q_w)$ norm of the velocity field in (I6), the Wasserstein length of the SNR path over any window in which the entropy grows by $\log c$ is at most $\sqrt{2\log c}$, for every prior and every dimension: the SNR path is a quasi-geodesic for Talagrand's transport inequality. (T) is the same statement with swept mass in place of Wasserstein length and with the zone defined pathwise.

Target inequality (K): $J(w)\,D(w)\le C\,D'(w)^2$ whenever $D(w)\ge1$, i.e. the Fisher-Rao speed is at most a constant times the growth rate of $\sqrt D$. One direction: equality with $C=\tfrac12$. Planted Monte Carlo along the path gives ratios between $0.25$ and $0.61$ wherever $D\ge0.1$ for independent directions, clusters with coherent weight $0.3$, $0.05$, $0.02$, trees and a sparse prior. Unavailable shortcuts: $J\le Cm$ is false (sparse priors before detection have $J/m\approx1+w^2$), and $J\le D''$ does not give (K) across sharp secondary transitions.

## Reduction to zone occupation (verified up to constants)

Because $\partial_w^2\log L_w\ge-1$, $\Lambda\le\sqrt e\int_0^\infty L_w\mathbf 1\{|w-w^*|\le1\}\,dw$ with $w^*$ the maximizing SNR, and the integral is at most $2\Lambda$. Hence the shell form of the tail bound, $\mathbb P_\gamma\{\Lambda\in[\alpha,e\alpha)\}\le C/(\alpha\sqrt{\log\alpha})$, is equivalent to
$$
\mathbb E\,\mathrm{Leb}\Big\{w\ge0:\ \log\Lambda(wX+G)\in[a,a+1),\ |w^*(wX+G)-w|\le1\Big\}\le\frac{C}{\sqrt a},\qquad a=\log\alpha,
$$
for the planted pair $(X,G)$. The function $F(w)=\log\Lambda(wX+G)$ is convex (log-convexity of $\Lambda$), so it spends at most $1/|F'|$ in a unit window on each branch, with $F'(w)=w^*\langle\hat X_{w^*}(Y_w),X\rangle$. The content is that the event "the SNR maximum-likelihood estimate is within one of the truth" has probability comparable to $F'/\sqrt a$: in a cluster phase with coherent weight $\rho$ the slope is $\sqrt{2a\rho}$ and that probability is of order $\sqrt\rho$.

## Routes

(R1) Perturbation in the SNR, the Eldan-Lee mechanism with a dimension-free perturbation: $\mathrm{KL}(Q_{w+\eta}\|Q_w)\le\eta^2/2$ by convexity of relative entropy, while along the planted ray $F(w+\eta)-F(w)\ge\eta F'(w)$ by convexity; so $F$ cannot concentrate under $Q_w$ on a window shorter than $F'$.

(R2) Brownian coupling. Every term in (I1) is an integral of one-SNR marginals, so any coupling of $(Y_w)_w$ may be used. With $Y_t=tX+B_t$, $w=\sqrt t$: $\log L=\int\langle\hat X,d\bar B\rangle+\tfrac12\int\|\hat X\|^2dt$ for the innovation Brownian motion $\bar B$, and for unit-norm priors $N_t=\sqrt t\,s_{\sqrt t}=\langle\hat X_t,Y_t\rangle-t$ is a martingale with $dN_t=\langle\mathrm{Cov}(X\mid\mathcal F_t)Y_t+\hat X_t,d\bar B_t\rangle$ (verified by Ito calculus). Needed: $\mathbb E\int_0^\infty\frac{(N_t)_+}{2t}\mathbf 1\{1\le L_t<c\}\,dt\le C\sqrt{\log c}$.

(R3) Inference physics. Under $Q_w$ the posterior is a Gibbs measure on the Nishimori line; $m$ is the overlap, (I4) and (I5) are Nishimori-type identities, and overlap concentration for Bayes-optimal inference is the heuristic reason why a general prior behaves like a scalar channel at effective SNR $\int_0^w\sqrt m$. It also says why multi-scale probes (idea_aca5b09e9a0c, idea_38a72ab5ee7e) should fail inside this class: each level's resolution adds to $m$ monotonically, and the zone is exhausted in entropy, not in levels.

(R4) Extremality of one direction by comparison. No monotone interpolation was found: at fixed $w$ more correlation lowers $\mathbb E\Psi(L_w)$ for concave $\Psi$, while the supremum prefers coherence; a comparison proof would have to act on the supremum itself.

## Gates and failure criterion

(G1) Native verification of (I1) to (I6) and of the lemmas listed in idea_9f8ffb204424. (G2) Prove (T) for independent equal directions and for two-level trees by explicit zone computations: already a theorem beyond direction entropy in the weak-loading population class. (G3) The occupation bound, through (K) in the zone or through (R1) or (R2). Stop if a family is found with in-zone ratio $JD/(D')^2$ unbounded and $\mathbb E\min\{c,\Lambda\}/\sqrt{\log c}$ unbounded; if only the ratio is unbounded, replace $\sqrt J$ by the $L^1$ norm of the score and continue.

## Sources (recalled from memory, not opened in this session; verify before any use)

Guo, Shamai, Verdu, Mutual information and minimum mean-square error in Gaussian channels, IEEE Trans. Inform. Theory 51 (2005); derivative of the MMSE as the squared conditional covariance: Payaro and Palomar (2009) and Guo, Wu, Shamai, Verdu (2011), both IEEE Trans. Inform. Theory; Nishimori line and overlap concentration: Zdeborova and Krzakala, Statistical physics of inference, Adv. Phys. 65 (2016); method of mixtures and pseudo-maximization: Robbins and Siegmund (1970), de la Pena, Klass, Lai, Ann. Probab. 32 (2004).
