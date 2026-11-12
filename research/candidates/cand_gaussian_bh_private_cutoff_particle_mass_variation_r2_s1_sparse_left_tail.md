---
type: candidate
title: >-
  Sparse finite-moment left-tail contamination cannot make an active minimum
  escape
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
slot: 1
direction: known_counterexamples
statement_digest: 8345cf59553f81f078aa75b8209e82e7b444527650ffec26a456254734403e01
performed_by: unknown
created_at: '2026-11-09T09:06:46.830Z'
extension_version: 0.0.4
---

## Object

Test the classical quantile-contamination pathology in which a small contaminating mass has an unbounded tail. Take the Hilbert space to be the real line, sigma=s=1/2, a=1/8, q=S(2), rho=1, lambda=0. Set pi to the point mass at (theta,v,ell)=(0,0,1), and set
$$
\nu=\sum_{n=1}^{\infty}7\,8^{-n}\delta_{(-2^n,0,1)}.
$$
Use chi_a(r)=0 for r<=a, chi_a(r)=1 for r>=2a, and chi_a(r)=3t^2-2t^3 for a<r<2a, where t=(r-a)/a. All parameters are deterministic. The attempted violation is loss of compactness of the suffix minimizers, or failure of the signed cutoff derivative, because contamination adds arbitrarily remote negative means.

## Checks

### H1

Pass. Both smoothing parameters are positive, sigma^2+s^2=1/2<1, 0<a<1/4, and 0<q=S(2)<S(1). The specified cutoff is nondecreasing and continuously differentiable, with derivative zero at its joins.

### H2

Pass. All directing atoms have norm-zero loading and a true tag with nonpositive mean. The weights sum to 7 sum_{n>=1}8^{-n}=1. The second moments are M_2(pi)=0 and
$$
M_2(\nu)=7\sum_{n=1}^{\infty}8^{-n}4^n=7.
$$
Thus both laws satisfy the closed lawful convention and the required finite second moment.

### H3

Pass. For 0<epsilon<1/16=a/2, pi_epsilon=(1-epsilon)pi+epsilon nu is an admissible mass perturbation. Its level remains q, and epsilon|lambda|=0.

### H4

Pass. The laws and the perturbation are fixed before every Gaussian innovation. Since every loading is zero, all conditional kernels are independent of the background X. The usual independent private noises give the required unit-variance scores.

### NOT

Fail for the proposed endpoint-escape and derivative violation. Write c=sqrt(1-sigma^2)=sqrt(3)/2. Explicitly,
$$
H_0(z)=S(z/c),\qquad
H_\nu(z)=\sum_{n=1}^{\infty}7\,8^{-n}S((z+2^n)/c)\le H_0(z).
$$
Consequently H_epsilon<=H_0 and Q_epsilon(t)<=Q_0(t)=cS^{-1}(t), so B_epsilon(t)>=B_0(t). In particular B_0(t) tends to positive infinity as t tends to one. Fix epsilon_0<1/16. The lower bound H_epsilon>=(1-epsilon)H_0 also gives
$$
Q_\epsilon(1/2)\ge cS^{-1}\!\left(\frac{1}{2(1-\epsilon_0)}\right)
\quad(0\le\epsilon\le\epsilon_0).
$$
Thus B_epsilon(1/2) has a finite uniform upper bound C. For every r in [a,2a], the point 1/2 belongs to the suffix [r,1]. Choose b in (1/2,1) such that B_0(t)>C+1 whenever b<t<1. Every active minimum relevant to the cutoff integral then lies in the common compact interval [a,b]. For any other fixed 0<r<1 the same argument uses the comparison point (1+r)/2 and proves compactness on a neighborhood of epsilon=0. The unbounded contaminating support cannot drive an active minimum into rank one.

On each such compact rank interval the Gaussian series and its score derivatives converge uniformly, the baseline density h_0 is positive, and implicit differentiation gives
$$
\dot Q(t)=\frac{H_\nu(Q_0(t))-t}{h_0(Q_0(t))}.
$$
Applying the compact all-active-minima envelope formula (indexed source lib_bernhard_rapaport1995_compact_danskin) therefore gives exactly
$$
\dot M(r)=\frac1\sigma\min_{t\in\mathcal A(r)}\{-\dot Q(t)\}.
$$
This reasoning does not select a unique minimizer. All tags in both laws are true, so f_epsilon(t)=1, dot f(t)=0, and g_epsilon=chi_a. Using the actual-rank survival identity,
$$
\mathcal F^a_\epsilon
=\int_a^{2a}\chi_a'(r)S(M_\epsilon(r))\,dr.
$$
Uniform implicit differentiation on [a,b] bounds the envelope difference quotients on the support [a,2a] of chi_a'. Dominated differentiation in this finite interval yields
$$
\dot{\mathcal F}^a
=-\int_a^{2a}\chi_a'(r)\phi(M_0(r))\dot M(r)\,dr,
$$
which is the claimed complete signed derivative for this object. There is no background-expectation interchange because the kernels do not depend on X.

## Failure

NOT fails: stochastic left-tail contamination raises every B, while one fixed interior comparison point bounds all relevant active minima away from rank one; the resulting full cutoff derivative agrees with the target.
