---
title: >-
  Ghirlanda-Guerra identities for the null-tag overlaps of a penalized Gaussian
  BH maximizer
type: lemma
status: deprecated
source:
  kind: original
  note: >-
    Route lemma (slot 5) of the researcher-selected ultrametric route
    (idea_b808cca5bf7f, content idea_ae102c56085d), parallel round of 12
    November 2026. Unproved and high-risk. Only the overlaps among null-tagged
    particles are constrained; alternative directions stay free.
depends_on:
  - gaussian_bh_exchangeable_array_variational_compactification
uses_definitions:
  - gaussian_bh_marked_exchangeable_parameter_array
  - gaussian_worst_case_bh_fdr
tags:
  - parallel-round-20261112
  - ultrametric
  - ghirlanda-guerra
---

# Ghirlanda-Guerra identities for the null-tag overlaps of a penalized Gaussian BH maximizer

## Statement

Use the lawful jointly exchangeable [marked parameter arrays](../definitions/gaussian_bh_marked_exchangeable_parameter_array.md) $\omega=((\theta_i,\ell_i)_{i\ge1},(C_{ij})_{i,j\ge1})$, their law spaces $\mathfrak P\supseteq\mathfrak P_2$, the moment $M_2$, and the completed conditional Gaussian FDR functional $\mathcal F(P;q,\sigma)=\lim_{n\to\infty}\mathcal F_n(P;q,\sigma)$, which exists for $P\in\mathfrak P$ and $0<q<1/2$ by item 1 of [the marked-array compactification](gaussian_bh_exchangeable_array_variational_compactification.md). Put $q_{\max}=\overline\Phi(1)$. Call $P\in\mathfrak P$ canonical if $P\{\theta_1=0,\ \ell_1=0\}=0$.

**Null-tag overlap array.** For $\omega$ let $J(\omega)=\{i\ge1:\ell_i=1\}$ and let $E_0$ be the event that $\lim_{n\to\infty}n^{-1}|J(\omega)\cap\{1,\ldots,n\}|$ exists and is strictly positive. On $E_0$ enumerate $J(\omega)=\{i_1<i_2<\cdots\}$ and put
$$
R^0_{kl}=C_{i_ki_l}\qquad(k,l\ge1,\ k\ne l).
$$
If $P(E_0)>0$, let $\mathbb E^0_P$ denote expectation under $P(\cdot\mid E_0)$. The null-tag overlap array of $P$ satisfies the Ghirlanda-Guerra identities if, for every integer $n\ge2$, every bounded measurable $f:[-1,1]^{n(n-1)/2}\to\mathbb R$ of $R^{0,(n)}=(R^0_{kl})_{1\le k<l\le n}$, and every bounded measurable $\psi:[-1,1]\to\mathbb R$,
$$
\mathbb E^0_P\!\left[f(R^{0,(n)})\,\psi(R^0_{1,n+1})\right]
=\frac1n\,\mathbb E^0_P\!\left[f(R^{0,(n)})\right]\mathbb E^0_P\!\left[\psi(R^0_{12})\right]
+\frac1n\sum_{l=2}^{n}\mathbb E^0_P\!\left[f(R^{0,(n)})\,\psi(R^0_{1l})\right].
$$
Only the residual correlations among null-tagged indices enter; the means, the alternative-tagged indices and all correlations involving them are unconstrained.

**Claim.** Fix $0<\sigma<1$, $0<q\le q_{\max}$ and $\eta>0$. Then there is a canonical law $P_*\in\mathfrak P_2$ such that
$$
\mathcal F(P_*;q,\sigma)-\eta M_2(P_*)=\max_{P\in\mathfrak P_2}\{\mathcal F(P;q,\sigma)-\eta M_2(P)\}=A_{\eta,\sigma}(q),
$$
$P_*(E_0)>0$, and the null-tag overlap array of $P_*$ satisfies the Ghirlanda-Guerra identities. The law $P_*$ may be an outer mixture and may depend on $\sigma,q,\eta$. No ultrametricity, finite support, positive definiteness or FDR order bound is asserted.

## Notes

Role in the route: it supplies the structural input to which Panchenko's ultrametricity theorem is applied in [the null-ultrametric selection lemma](gaussian_bh_null_ultrametric_maximizer_selection.md). The value $A_{\eta,\sigma}(q)\ge q>0$ of item 2 of the compactification forces null mass, so $P_*(E_0)>0$ is not an extra restriction.

Suggested mechanism (not part of the statement): perturb the penalized objective by small overlap-moment functionals of the null-tag array, for example $\sum_{p\ge1}2^{-p}x_p\,\mathbb E^0_P[(R^0_{12})^p]$ with random $x_p\in[0,1]$, and use that the perturbed value function, a supremum of affine functions of the mixture, is convex in the perturbation parameters; alternatively, tilt the null-tag part of the directing measure by an independent Gaussian process with covariance a function of the overlap (a lawful exchangeability-preserving competitor with no moment cost) and use stationarity at the maximum together with the approved first-variation results and [the global particle-potential certificate](gaussian_bh_global_particle_potential_certificate.md). Passing to the limit of perturbed maximizers uses compactness of moment sublevels, continuity of $\mathcal F$ and lower semicontinuity of $M_2$ (items 1 and 4 of the compactification), and the closedness of the identities under weak convergence for continuous $f,\psi$.

Cheap first test (from idea_ae102c56085d): average the approved first-variation identities over a random perturbation family and check whether an identity of the displayed shape appears. If the objective has no convexity or concentration structure playing the role of the free energy, this lemma is obstructed for that reason. A legal falsifier is a fixed $(\sigma,q,\eta)$ at which every canonical maximizer has a null-tag overlap array violating the identities, for instance one forced to contain negatively correlated null directions (the identities imply nonnegative overlaps).
