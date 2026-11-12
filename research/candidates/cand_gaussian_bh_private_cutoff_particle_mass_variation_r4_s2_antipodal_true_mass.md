---
type: candidate
title: Antipodal true-particle mass transfer with different conditional kernels
status: failed
target_asset: gaussian_bh_private_cutoff_particle_mass_variation
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 4
slot: 2
direction: small_cases
statement_digest: 8345cf59553f81f078aa75b8209e82e7b444527650ffec26a456254734403e01
performed_by: unknown
created_at: '2026-11-09T09:17:51.845Z'
extension_version: 0.0.4
---

## Object

Take the one-dimensional Hilbert space, sigma = s = 1/2, tau_s = 1/sqrt(2), a = 1/10, and q = S(1). Let
$$
\pi=\delta_{(0,1,1)},\qquad \nu=\delta_{(0,-1,1)},\qquad
\rho=1,\quad\lambda=0,\quad\pi_\epsilon=(1-\epsilon)\pi+\epsilon\nu.
$$
Use independent standard normal X and Z. Set chi_a(r)=0 for r<=a, chi_a(r)=1 for r>=2a, and chi_a(r)=3x^2-2x^3 for x=(r-a)/a in (0,1). Thus chi_a is nondecreasing C1 and its derivative has supremum 15. The two particles have different conditional kernels whenever X is nonzero; this is not a kernel-preserving tag swap. The proposed obstruction was that transferring mass between opposite background loadings might produce an additional first-order rank term after averaging the background.

## Checks

### H1

The scalar regularizers obey sigma,s>0, sigma^2+s^2=1/2<1, 0<a<1/4, and 0<q=q_max. The displayed cutoff has the required range, endpoint plateaus and C1 joins.

### H2

Both laws are deterministic Borel probability measures, each loading has norm one, and each true-tagged mean is zero. They are lawful, canonical, and have second mean moment zero. The laws and perturbation do not depend on the Gaussian innovations.

### H3

For 0<epsilon<1/20, epsilon*rho<a/2, epsilon*abs(lambda)=0, and q_epsilon=q<=q_max. The joint perturbation is exactly the one in the statement.

### H4

Use the prerequisite population's actual globally largest non-strict rank and its full fractional FDP. Conditional on X,
$$
H_{\epsilon,X}(z)=V_{\epsilon,X}(z)
=(1-\epsilon)S((z-\tau_sX)/s)+\epsilon S((z+\tau_sX)/s).
$$
Every conditional density is smooth and strictly positive. These finite-dimensional kernels are jointly measurable, and the representative issue is absent. The actual-rank survival identity from the stated prerequisite applies to this lawful privately smoothed population.

### NOT

Fails: the full derivative retains exactly the actual-rank term claimed in the target, with no missing response from this transfer. Indeed V_epsilon=H_epsilon gives v_epsilon(r)=r and f_epsilon(r)=1 for every positive rank, including the endpoint. Thus the fixed-rank true-mass difference and dot f both vanish identically.

Write u_t=S^{-1}(t), and put
$$
b(t)=\frac{u_q(t)-su_t}{\sigma},\qquad
m_r=\min_{t\in[r,1]}b(t),\qquad A_r=\operatorname*{argmin}_{t\in[r,1]}b(t).
$$
At the unperturbed law,
$$
Q_X(t)=\tau_sX+su_t,\qquad
M_X(r)=m_r-\tau_sX/\sigma,
$$
and A_r is independent of X. Direct implicit differentiation of the displayed two-component tail gives
$$
D_X(t):=\dot Q_X(t)
=s\frac{S(u_t+2\sqrt2X)-t}{\phi(u_t)}.
$$
This differentiation is uniform on compact rank intervals for each fixed X. The active minimizers stay away from rank one as epsilon decreases to zero: if epsilon_n tends to zero and t_n tends to one, the bound sup_z|H_epsilon(z)-H_0(z)|<=epsilon implies H_0(Q_epsilon(t_n))>=t_n-epsilon_n, whence Q_epsilon(t_n) tends to minus infinity and B_epsilon(t_n) tends to plus infinity. A fixed interior comparison rank has bounded barrier. Consequently the compact minimum envelope gives
$$
\dot M_X(r)=-\sigma^{-1}\max_{t\in A_r}D_X(t).
$$
No selection of a unique active rank is used here.

The layer-cake identity is exact:
$$
F^a_\epsilon=\mathbb E_X\int_a^{2a}\chi_a'(r)S(M_{\epsilon,X}(r))\,dr.
$$
For completeness this identity can be differentiated after both integrations in this example. Let L=L_{q,a}, d=epsilon and delta=dL/sigma. A qualifier at rank t transfers between the two tails with a rank loss at most d. On ranks at least a/2, changing rank by d changes u_q by at most dL. Therefore, writing p_X(r)=S(M_X(r)), with survival extended by one and zero beyond its rank interval,
$$
S(M_X(r+d)+\delta)
\le p_{\epsilon,X}(r)
\le S(M_X(r-d)-\delta).
$$
Here a Z-shift of size delta changes the Gaussian survival probability by at most delta/sqrt(2*pi). Since p_X is nonincreasing with total variation at most one, integrating the horizontal differences against chi_a' costs at most 2d times its supremum. Thus, uniformly in X,
$$
\frac{|\mathbb E_Z\chi_a(R_\epsilon)-\mathbb E_Z\chi_a(R_0)|}{\epsilon}
\le30+\frac{L}{\sigma\sqrt{2\pi}}.
$$
For fixed X, the smooth unperturbed barrier has locally Lipschitz suffix minimum; its Gaussian survival is absolutely continuous, with no rank-one jump. Horizontal difference quotients are dominated in the integral by averages of translations of its integrable derivative. The preceding brackets therefore give the L1 rank-variable convergence needed to combine the pointwise envelope limit with the layer-cake identity. The uniform bound then permits the X expectation. The result is exactly
$$
\dot F^a=-\mathbb E_X\int_a^{2a}\chi_a'(r)\phi(M_X(r))\dot M_X(r)\,dr,
$$
which is the target's formula because its signed bulk term is zero and (chi_a f)'=chi_a'. Different conditional kernels and a nonempty true sector do not supply the proposed omitted term in this concrete family.

## Failure

NOT: the antipodal true-particle transfer has zero fixed-rank payoff response and exactly the asserted all-active-minima actual-rank response.
