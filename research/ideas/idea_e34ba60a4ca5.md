---
type: idea
title: >-
  Actual-rank compound calibration from conditional sub-Poisson counts without
  coordinate independence
status: resolved
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_conditional_compound_calibration
tags:
  - one-sided
  - same-rank
  - sub-poisson
  - conditional-calibration
  - spectral-slicing
  - unproved-main
resolved_by: gaussian_bh_conditional_subpoisson_calibration
---

This is a completed inline auxiliary derivation, saved as a draft observation rather than a new completion root or an approved dependency. It strengthens the available calibration mechanism but does not supply the global geometric allocation required by [the universal one-sided target](../assets/gaussian_bh_one_sided_universal_order_upper.md). It is distinct from [the approved product-law calibration](../assets/gaussian_bh_conditional_compound_calibration.md): coordinate independence and association are replaced by a count moment-generating-function hypothesis, which must be proved after conditioning on the entire alternative vector.

## Exact count hypothesis and unchanged BH rule

Fix N, the original null set I0 and q in (0,1). Fix every original alternative p-value, preserving all alternative threshold gates. Suppose the remaining null law satisfies, for one finite K>=1, every 0<s<=q and every lambda>=0,
$$
E\exp\{\lambda C(s)\}\le
\exp\{NKs(e^\lambda-1)\},\qquad
C(s)=\sum_{j\in I_0}1\{P_j\le s\}.
\tag{CP}
$$
The same statement may hold for almost every value of an external conditioning variable and the complete alternative vector. It is that final conditional law which must satisfy (CP); conditioning on a factor first does not preserve it automatically after alternatives are revealed. As s decreases to zero, the bounded random variables exp(lambda C(s)) converge to exp(lambda C(0)). Thus (CP) forces C(0)=0 almost surely.

Let A(k) count the fixed alternatives at p<=qk/N and define
$$
k_i=\max\{k\in\{0,\ldots,N\}:i+A(k)\ge k\},
\quad 0\le i\le |I_0|.
$$
These are deterministic under the stated conditioning, nondecreasing, and k_i>=i. Let R,V be the actual original largest-rank BH rejection and null counts. Maximality, with ties and non-strict inequalities, gives R=V+A(R). Consequently R is feasible for k_V. If k_V>R, then C(qk_V/N)>=V, so k_V qualifies for the original BH rule, a contradiction. Therefore
$$
R=k_V,\qquad C(qk_V/N)=V.
\tag{AR}
$$
When R=0, C(0)=0 and no alternative can equal zero (otherwise rank 1 qualifies), so the same conclusion holds. No representative, changed threshold or replacement rank is used.

## A finite universal calibration

Put alpha=qK. For i>=1 define t_i=alpha k_i>0. On {V=i}, the actual FDP is i/k_i and C(qk_i/N)=i. For any a>e, divide the possibilities into i/k_i<=a alpha and i/k_i>a alpha. The first contribution to expected FDP is at most a alpha. In the second class t_i/i<1/a. Applying (CP) at the deterministic original threshold qk_i/N and lambda=log(i/t_i)>0 gives
$$
P(V=i)\le P\{C(qk_i/N)\ge i\}
\le e^{i-t_i}(t_i/i)^i
\le(e t_i/i)^i.
$$
Hence, keeping the same actual V and R throughout,
$$
\begin{aligned}
E[\mathrm{FDP}]
&\le a\alpha+
\sum_{\{i:t_i/i<1/a\}}\frac{i}{k_i}(e t_i/i)^i\\
&\le\alpha\left[a+
\sum_{i=1}^{\infty}e^i a^{-(i-1)}\right]
=\alpha\left[a+\frac e{1-e/a}\right].
\end{aligned}
$$
Taking a=2e and using FDP<=1 proves
$$
E[\mathrm{FDP}]\le\min\{1,4e qK\}.
\tag{CC}
$$
No null-coordinate product law, covariance association, Poisson-tail domination or selected-threshold substitution was used. The only exponential estimate is at a deterministic threshold after fixing all alternatives. An empty null set is trivial.

## Gaussian negative residual covariance supplies (CP)

Let the final conditional null score vector be Gaussian with deterministic mean mu and PSD covariance H whose off-diagonal entries are all nonpositive. Zero-variance coordinates are deterministic; PSD forces their entire covariance rows to vanish, so remove them during the argument and restore their deterministic exponential factors afterwards.

For a fixed score threshold and lambda>=0, approximate exp(lambda 1{x>=b_i}) by bounded, positive, smooth increasing factors f_i(x). Interpolate H_t=diag(H)+t[H-diag(H)], 0<=t<=1. Add eta I first if needed to obtain positive definite densities. Differentiating their Gaussian densities and integrating by parts twice gives
$$
\frac d{dt}E\prod_i f_i(X_{t,i})
=\sum_{i<j}H_{ij}\,
E\!\left[f_i'(X_{t,i})f_j'(X_{t,j})
 \prod_{\ell\ne i,j}f_\ell(X_{t,\ell})\right]\le0.
$$
The density derivative identity follows by differentiating its Gaussian characteristic function, or directly its density; bounded smooth factors and Gaussian tails justify both integrations. Smooth factors can be chosen with bounded derivatives. At eta>0 there is no singular endpoint. Let eta decrease to zero for fixed factors using a common Gaussian square-root coupling and bounded convergence. Then approximate each half-line indicator, with deterministic factors already removed, and use that a positive-variance Gaussian has no atom at its threshold. Thus
$$
E e^{\lambda C(s)}
\le\prod_{i\in I_0}\{1+F_i(s)(e^\lambda-1)\}
\le\exp\!\left\{\sum_i F_i(s)(e^\lambda-1)\right\}.
\tag{NG}
$$
The deterministic factors satisfy the last inequality as well. Non-strict comparisons are preserved.

If the conditional compound envelope
$$
K=\max\left\{1,\sup_{0<s\le q}
\frac{\sum_{i\in I_0}F_i(s)}{Ns}\right\}
$$
is finite, (NG) yields (CP), and (CC) applies conditionally. Infinite K gives the trivial cap 1. Integrating gives E min{1,4e qK}. A rational supremum plus q is measurable by CDF right continuity, exactly as for the approved compound envelope.

## Precise remaining gate

An arbitrary Schur residual need not have nonpositive off-diagonal entries. Even if it does before conditioning on alternatives, the further Schur complement after fixing all alternatives can change their signs. The global spectral program must construct the conditioning and packets from the original model, prove (NG) or another exact count bound under the final conditioning, and then sum their actual-rank contributions without separate free threshold maxima. The estimate (CC) alone proves no unrestricted Gaussian order bound.

## Resolution

Promoted to the lemma gaussian_bh_conditional_subpoisson_calibration, a dependency of gaussian_bh_one_sided_universal_order_upper.
