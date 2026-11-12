---
type: idea
title: 完整 FDP 的 OU 噪声尺度积分：从有符号秩回跳到维度无关上界
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_whole_payoff_cameron_martin_balance
  - gaussian_bh_actual_radial_loading_signed_variation
tags:
  - gaussian-semigroup
  - geometric-analysis
  - signed-cancellation
  - quantitative-bridge
---

Suggested by the teaching chat and its independent functional-analysis brainstorm; origin agent. This is a NEW proposed quantitative bridge to test, not a theorem and not an implication of the old refuted entropy/coherence trace budget. It complements the finite signed-path proposal idea_408804d0bbf6. Its generic analytic half has an identified primary source; the BH-specific half remains open and should be screened before creating a long proof chain.

## Why a different norm is needed

The current whole-payoff Cameron-Martin checkpoint is useful at fixed common noise, but its supremum Lipschitz constant cannot in general be uniform as that noise vanishes. For just one zero-mean null, let U=S^{-1}(q) and
$$
g_\sigma(x)=S((U-\sqrt{1-\sigma^2}x)/\sigma).
$$
Exactly,
$$
\sup_x|g_\sigma'(x)|=
\frac{\sqrt{1-\sigma^2}}{\sigma\sqrt{2\pi}},
\qquad
\mathbb E|g_\sigma'(G)|=
\sqrt{1-\sigma^2}\phi(U).
$$
The first diverges, while the second is of order qU. This is NOT a counterexample to the current fixed-sigma statement; it identifies a bad final norm.

Even spatial L1 variation at zero noise can count too many independent microscopic rejection faces. The proposed replacement integrates the signed response over noise scales before making a final bound.

## Generic dimension-free analytic quantity

Represent any finite Gaussian model, including singular covariance, in its finite standard Gaussian latent space. Let f(x) be its COMPLETE actual ordinary BH FDP, F=E_gamma f, pi0=N0/N. Use 0<=f<=1, without a rank cutoff. Define the Ornstein-Uhlenbeck semigroup and integrated response
$$
T_t f(x)=\mathbb E f(e^{-t}x+\sqrt{1-e^{-2t}}G),
\qquad
J(f)=\int_0^\infty\mathbb E_\gamma\|\nabla T_t f\|\,dt.
$$
For bounded measurable f, Mehler differentiation and Gaussian rearrangement give
$$
\|\nabla T_t f\|\le
\frac{I(T_t f)}{\sqrt{e^{2t}-1}},
\qquad I(p)=\phi(\Phi^{-1}(p)).
$$
Concavity of I and Gaussian invariance then imply
$$
J(f)\le \frac{\pi}{2}I(F)
\le C F\sqrt{\log(e/F)}.
$$
The time integral of (exp(2t)-1)^(-1/2) is pi/2. This is dimension independent and does not require differentiability of the original FDP or actual rank selectors.

Primary source checked live on 9 November 2026: Bakry, Gentil and Ledoux, On Harnack inequalities and optimal transportation, Proposition 2.1, displayed (16) and its consequence on page 9:
https://www.math.univ-toulouse.fr/~ledoux/Harnack.pdf .
Specialize their CD(K,infinity) inequality to the Gaussian OU generator L=Delta-x dot grad, K=1, then integrate as above. This source supplies the semigroup estimate ONLY, not any BH inequality. Extract and verify its source node through the native sources workflow if the route proceeds.

## The decisive BH-specific conjectural bridge

For all legal finite one-sided Gaussian models and small q, test whether there is a universal A such that
$$
(F-q\pi_0)_+\le A\,\frac qF J(f),\qquad F>0.
$$
If true, it immediately yields
$$
F\le q+Cq\sqrt{\log(e/F)}.
$$
When F>=q this is at most q+Cq sqrt(log(e/q)); F<q is already sufficient. Thus this bridge, unlike another regularity lemma, directly closes the desired order bound.

It does NOT follow from 0<=f<=1, entropy, or the generic Gaussian theorem. Nearly constant or rapidly oscillating generic functions can have small J at positive mean. The central question is whether ordinary Gaussian BH structure prohibits such a violation when F exceeds its q pi0 baseline.

In the zero-null-mean setting, the proposed exact finite-path identity in idea_408804d0bbf6 makes this equivalent to bounding the AVERAGED NET signed backtracking charge by A J(f)/F. For negative null means, retain the weighted density baseline and jump terms; this needs a correctly written inequality, not an assumed equality to the zero-mean formula.

## A constructive dual formulation

For smooth vector fields h_t with norm<=1, initially with compact time support, let
$$
\delta_\gamma h=x\cdot h-\operatorname{div}h,\qquad
\Psi_h=\int_0^\infty e^{-t}\delta_\gamma(T_t h_t)\,dt.
$$
OU commutation and Gaussian adjointness give
$$
\mathbb E[f\Psi_h]
=\int_0^\infty\mathbb E\langle\nabla T_t f,h_t\rangle\,dt.
$$
Taking the supremum over admissible fields, with appropriate approximation, gives J(f). A concrete proof task is therefore to assemble the NET finite rank-path charges into a uniformly bounded vector-field certificate. It is not enough to postulate a trace inequality or sum absolute contributions of individual faces.

A possible bounded building block to test, not a claimed certificate, is the smoothed posterior null-loading barycenter: b(x)=R(x)^{-1}sum_{i true,rejected}v_i, b=0 at R=0, so ||b||<=f and ||T_t b/(T_t f)||<=1 wherever the denominator is positive. Whether this field, a time-weighted version, or a field obtained from signed path cancellation yields the needed inequality must be established explicitly. Do not infer it just from boundedness.

## A finite, executable first screen

Compute
$$
\mathcal R(q,\text{model})=
\frac{F(F-q\pi_0)_+}{qJ(f)}
$$
and try to make it diverge with q, rank hierarchy, or dimension. Start with one-factor +/- clone models with mixed labels, the approved lower-bound family, and negative-null-mean examples; then two-dimensional models with geometric rank scales. Include independent null dust as a cancellation benchmark.

For a one-dimensional FDP with jumps Delta_j at b_j, an exact reduction to elementary Gaussian mixtures is
$$
J(f)=\int_0^1
\left\|\sum_j \Delta_j\phi(b_j)
\varphi_{\sqrt{1-\rho^2}}(\,\cdot-\rho b_j)
\right\|_{L^1(\mathbb R)}\,d\rho.
$$
Here varphi_s is the centered normal density of standard deviation s; the endpoint rho=1 is understood by a limit. The signed mixture is formed BEFORE taking its L1 norm. Enumerate all ordinary-BH score-threshold crossings to get the actual Delta_j. This gives a direct quadrature target with no numerical differentiation of a discontinuous rank. A numerical screen must report truncation/discretization limitations and cannot be called a proof.

First failure target: lawful Gaussian BH examples with F>q pi0 but progressively finer oscillations or an almost constant FDP, causing J/F to collapse. If this defeats the bridge, record the specific obstruction and stop proving that bridge; the unrestricted main goal and the independent signed-path identity remain intact.

No BH bridge has been proved or numerically validated in this teaching turn. The established external analytic estimate, the exact scalar diagnostic, the proposed dual formulation, and the new unproved bridge are deliberately separated.
