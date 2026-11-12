---
type: candidate
title: Extremely distant false-particle insertion into a true Gaussian population
status: failed
target_asset: gaussian_bh_private_cutoff_particle_mass_variation
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
statement_digest: 8345cf59553f81f078aa75b8209e82e7b444527650ffec26a456254734403e01
performed_by: unknown
created_at: '2026-11-09T09:06:46.830Z'
extension_version: 0.0.4
---

## Object

Take the Hilbert space to be the real line, with every particle having loading zero. Set sigma = s = 1/2, q = 1/10, a = 1/10, rho = 1 and lambda = 0. Use any allowed cutoff chi_a. Write c = sqrt(1-sigma^2) = sqrt(3)/2. Let pi be the unit mass at (theta,v,ell) = (0,0,1), and let nu be the unit mass at (10^6,0,0). The perturbed law is (1-epsilon)pi + epsilon nu. The insertion has a distinct score kernel and an extremely large but finite second mean moment. It tests possible amplification of a small inserted mass through the quantile's reciprocal density; it is not a coincident-kernel tag swap.

Put J(z) = S((z-10^6)/c). There is no background dependence, and
$$
H(z)=V(z)=S(z/c),\qquad H_\epsilon(z)=(1-\epsilon)H(z)+\epsilon J(z),\qquad V_\epsilon(z)=(1-\epsilon)H(z).
$$

## Checks

### H1

Pass. Both smoothing parameters are positive, their squared sum is 1/2 < 1, a lies in (0,1/4), and 0 < q = 0.1 < S(1). The cutoff has precisely the stipulated properties.

### H2

Pass. Both laws are deterministic Borel probabilities on a common separable Hilbert space. The zero-mean true particle and the strictly positive-mean false particle obey the original tag rules. Their second mean moments are respectively 0 and 10^12, both finite. Loadings have norm zero.

### H3

Pass. The laws, rho and lambda are fixed before every innovation. For every 0 < epsilon < a/2, epsilon rho < min(a/2,1), epsilon |lambda| = 0, and q_epsilon = q remains in the allowed level interval.

### H4

Pass. The private population construction has variance sigma^2+c^2 = 1, with independent private noises. The approved prerequisite identification applies to this deterministic, finite-support directing family. No actual-global-maximum assumption is made, so this object does not activate either conditional extremal inequality.

### NOT

Fail. The proposed reciprocal-density amplification does not contradict the target. In fact its true-mass response is exactly bounded without using any lower density bound. At every rank 0 < r < 1 the quantile identity gives
$$
V_\epsilon(Q_\epsilon(r))=r-\epsilon J(Q_\epsilon(r)).
$$
Consequently
$$
|V_\epsilon(Q_\epsilon(r))-V(Q(r))|\le\epsilon,
\qquad
\dot f(r)=-\frac{J(Q(r))}{r}.
$$
At rank one the true mass is 1-epsilon, so the endpoint variation also agrees. Since Q(r)=c S^{-1}(r) and h(Q(r))=phi(S^{-1}(r))/c, implicit differentiation gives
$$
\dot Q(r)=\frac{J(Q(r))-r}{h(Q(r))}.
$$
Here h_0/h = 1 and V_nu = 0; these are exactly both claimed fixed-rank formulas, including the signed cancellation. Large second moment does not multiply the true-mass response.

The same object also gives the asserted full signed derivative. At epsilon zero f = 1, so g = chi_a and w = chi_a'. Write A(r) for the unperturbed active suffix minimizers and define
$$
d(r)=\max_{t\in A(r)}\frac{J(Q(t))-t}{h(Q(t))}.
$$
Then
$$
\dot M(r)=-d(r)/\sigma,
\qquad
\dot{\mathcal F}^a
=-\mathbb E_Z\frac{\chi_a(R)J(Q(R))}{R}
+\frac1\sigma\int_a^{2a}\chi_a'(r)\phi(M(r))d(r)\,dr.
$$
For completeness, this derivative follows directly here: B(t) tends to positive infinity as t approaches one; on r in [a,2a], all minimizing t stay in a common compact subset of [a,1), uniformly for small epsilon. The kernels converge uniformly and their positive densities give uniform quantile differentiation on that compact set. The finite-minimum envelope therefore has derivative -d/sigma, with every active minimizer included. Its derivative is bounded on this compact rank range, which permits differentiation of the survival integral for E chi_a(R_epsilon). For the remaining term use the exact identity
$$
\mathcal F_\epsilon^a
=\mathbb E\chi_a(R_\epsilon)
-\epsilon\mathbb E\frac{\chi_a(R_\epsilon)J(Q_\epsilon(R_\epsilon))}{R_\epsilon}.
$$
The displayed fractional integrands are defined as zero at ranks at most a; the second integrand is therefore bounded by 1/a. Almost-sure convergence of the actual rank outside its countable Gaussian-null jump levels, followed by compact quantile continuity, gives its displayed limit by dominated convergence. Rank one has probability zero. All kernels are independent of X, so there is no further background-expectation interchange.

Thus both the bulk and rank effects are present, with exactly the claimed signs. This calculation tests the distinct-kernel distant-insertion mechanism; it is not a verification of the target for arbitrary directing laws or actual extrema.

## Failure

NOT fails: even an extremely distant false insertion has exact true-mass change at most epsilon and gives the target's complete signed actual-rank derivative.
