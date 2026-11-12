---
type: candidate
title: Antipodal saturated-loading two-well screen
status: failed
target_asset: gaussian_bh_actual_radial_loading_signed_variation
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 2
slot: 2
direction: extremal
statement_digest: 7fdc4735d0d5e381ad9fbb0ee8f7ab5df233763c161d5f77194d54300e4e7cac
performed_by: unknown
created_at: '2026-11-09T18:24:02.039Z'
extension_version: 0.0.4
---

## Object

Take the Hilbert space to be the real line, sigma=0.4, s=0.12, q=0.1 and a=0.1, so tau squared is 0.8256. Choose the permitted cutoff equal to zero below a, equal to one above 2a, and equal to 3t squared minus 2t cubed in between, where t=(r-a)/a. Let
$$
\pi=\tfrac12\delta_{(0,1,1)}+\tfrac12\delta_{(0,-1,1)}.
$$
The inward transport replaces the two loadings by plus and minus (1-epsilon). Write x=X(1), and put
$$
m_\epsilon=\tau_s(1-\epsilon)x,\qquad
c_\epsilon^2=s^2+\tau_s^2(2\epsilon-\epsilon^2),
$$
$$
H_{\epsilon,x}(z)=V_{\epsilon,x}(z)
=\tfrac12 S((z-m_\epsilon)/c_\epsilon)
+\tfrac12 S((z+m_\epsilon)/c_\epsilon).
$$
This tests separated conditional components and suffix switching, rather than the board's single-atom law. As a diagnostic only, a rank-grid screen at x=1 gives two local barrier wells near ranks 0.431 and 0.830, with barrier values about 2.345 and 5.858. These are local wells; the second is not asserted to be globally active. These numerical values play no role in the failed conclusion-negation check below.

## Checks

### H1

The regularizers are positive, sigma squared plus s squared is 0.1744<1, 0<a<1/4, and q=0.1<S(1). The stated cutoff is nondecreasing and continuously differentiable, with the required constant pieces.

### H2

Both atoms have loading norm one and true tag one with mean zero. The deterministic law is lawful, Borel, and has second mean moment zero.

### H3

The law, cutoff and perturbations are fixed before the independent standard normal variables x and Z. In one dimension the isonormal representative is simply X(v)=vx; there is no exceptional series-convergence issue.

### H4

The transport changes only loadings. Its private variance is exactly the displayed c_epsilon squared, at least s squared. Each score retains unit marginal variance because
$$
\sigma^2+\tau_s^2(1-\epsilon)^2+c_\epsilon^2=1.
$$

### NOT

The selected attempted violation is failure of the complete signed actual-rank derivative at competing conditional wells. It fails: this object's full cutoff derivative agrees with the asserted formula, including its minimum over all active suffix minimizers.

Indeed V_epsilon=H_epsilon gives f_epsilon(r)=1 for positive rank and hence dot f=0. For its actual largest rank, the exact conditional survival identity gives
$$
F_x(\epsilon):=\mathbb E_Z[\chi_a(R_\epsilon)\mid x]
=\int_a^{2a}\chi_a'(r)S(M_{\epsilon,x}(r))\,dr.
$$
This identity uses the suffix minimum, not either selected local well. For fixed finite x, the two means stay bounded and c_epsilon stays in a compact positive interval for 0<=epsilon<=1/4. Therefore Q_epsilon(t) tends to minus infinity uniformly in epsilon as t tends to one. Minimizers cannot escape to one. The positive smooth two-component density gives quantile differentiation locally uniformly below one. Ordinary compact-set minimum differentiation then yields
$$
\partial_{\epsilon+}M_{\epsilon,x}(r)
=\frac1\sigma\min_{t\in\mathcal A_{\epsilon,x}(r)}
[-\partial_\epsilon Q_{\epsilon,x}(t)].
$$
Here is an explicit integrable bound permitting differentiation of the displayed exact payoff, including the x average. Put U=S^{-1}(qa) and phi_0=phi(0). At a minimizer t>=a, write M=M_epsilon,x(r). The quantile equation differentiated in epsilon expresses its derivative as a convex combination of the component mean derivatives plus c'_epsilon times the corresponding standardized thresholds. Since c'_epsilon<=tau_s squared/s and Q=u_q(t)-sigma M,
$$
|\partial_\epsilon Q|
\le\tau_s|x|+
\frac{\tau_s^2}{s^2}(U+\sigma|M|+\tau_s|x|).
$$
Consequently every active minimizer satisfies
$$
\phi(M)|\partial_{\epsilon+}M|
\le A_0+A_1|x|,
$$
$$
A_0=\frac{\tau_s^2U\phi_0}{\sigma s^2}
+\frac{\tau_s^2\phi(1)}{s^2},\qquad
A_1=\frac{\tau_s\phi_0}{\sigma}
+\frac{\tau_s^3\phi_0}{\sigma s^2}.
$$
This holds throughout the stated epsilon interval. For fixed x, compact localization also makes the minimum locally Lipschitz in epsilon. The bound on its survival derivative therefore bounds survival difference quotients, and is integrable in x. Since the integral of chi_a' is one, dominated convergence proves
$$
\left.\frac{d}{d\epsilon+}\mathbb E_x F_x(\epsilon)\right|_0
=-\mathbb E_x\int_a^{2a}\chi_a'(r)\phi(M_x(r))
\frac1\sigma\min_{t\in\mathcal A_x(r)}[-\dot Q_x(t)]\,dr.
$$
For this law w=chi_a' and the bulk term is zero. This is exactly the target's signed response. This screen does not certify the entire general statement or its finite endpoint approximation, and it makes no genuine-extremum claim about this law.

## Failure

NOT fails: the exact full cutoff derivative of this two-atom law equals the asserted all-active-minima signed formula; the visible conditional wells do not supply a counterexample.
