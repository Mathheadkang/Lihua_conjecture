---
type: idea
title: >-
  Sharp half-coefficient strip bound for a capped bivariate Gaussian likelihood
  envelope
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_two_sided_sharp_upper
tags:
  - proved-local-lemma
  - gaussian-pair
  - half-constant
---

Original auxiliary candidate proof, independently checked with no blocking defect within its stated scope. NOT an approved research asset and NOT a BH bound without a cutoff-witness theorem. Frozen proof research-local/bivariate_gaussian_capped_likelihood_strip_candidate_20261104.md SHA1bb50ab90a103daa608c7d8cab875b1b667a51de5c3b89418c288be64bbefb3f; bounded cold audit research-local/bivariate_gaussian_capped_likelihood_strip_cold_audit_20261104.md SHA6c2b2a6850547b764c7a0c6436747ffdc64d499d5e0aa4a06f15c0632d5ac993. For any standardGaussianpair(X,V), arbitrarycorr incl±1 andu>=1, E1{1<X<=u}sup0<=a<=X exp(-a²/2)cosh(aV)<=u/(2sqrt(2pi))+2; leadingcoefficientoptimalatcorr1. No independence, rank or mean-catalogclaimisincluded. Full elementary Gaussian-integral proof follows for native retrieval.

# Candidate sharp strip bound for a bivariate Gaussian likelihood envelope

Date: 2026-11-04. Original local candidate lemma, not an approved node or proof of either BH conjecture. This calculation is intended to test correlated block-packing ideas; it asserts no general BH cutoff representation.

Let (X,V) be centered jointly Gaussian, each of variance one, with any correlation rho in [-1,1]. Write phi0=1/sqrt(2pi), Q=bar-Phi, and for t>=0 define

$$
M_t(v)=\sup_{0\le a\le t} e^{-a^2/2}\cosh(av).
$$

The proposed bound is, for all u>=1,

$$
E[\mathbf1\{1<X\le u\}M_X(V)]
\le \frac{u}{2\sqrt{2\pi}}+2.\tag{1}
$$

Its leading coefficient is attained at rho=1, so it cannot be decreased uniformly in rho. The candidate proof below uses only Gaussian integrals.

## Reduction

Cosine hyperbolic is even, so changing V to -V lets us suppose 0<=rho<=1. For x>0 put

$$
S_x(v)=\sup_{0\le a\le x}e^{a|v|-a^2/2}
=\begin{cases}e^{v^2/2},&|v|\le x,\\e^{x|v|-x^2/2},&|v|>x.\end{cases}
$$

Since exp(-a|v|-a²/2)<=1 for a>=0,

$$
M_x(v)\le\tfrac12 S_x(v)+\tfrac12.\tag{2}
$$

Thus it is enough to bound the strip integral of S. First take 0<=rho<1 and sigma=sqrt(1-rho²).

## Low correlation: 0<=rho<=1/2

On x>=1 and |v|<=x the joint density times exp(v²/2) is

$$
\frac1{2\pi\sigma}
\exp[-(x-\rho v)^2/(2\sigma^2)]
\le\frac1{2\pi\sigma}e^{-x^2/8}.
$$

Here |x-rho v|>=x/2, sigma<=1 and sigma>=sqrt(3)/2. Integration in v over [-x,x] and then x>=1 gives a contribution at most

$$
\frac{2}{\pi\sqrt3}\int_0^\infty x e^{-x^2/8}dx
=\frac8{\pi\sqrt3}.
$$

On v>x, Gaussian tilting gives the exact x-integrand

$$
\phi(0)e^{-(1-\rho)^2x^2/2}
\Phi\left(\frac{\rho(1-\rho)x}{\sigma}\right).
$$

It is at most phi0 exp(-x²/8), whose integral over x>=0 is one. On v<-x the analogous formula is at most phi0 exp(-(1+rho)²x²/2), and hence also integrates to at most one. Consequently

$$
E[\mathbf1\{1<X\le u\}S_X(V)]
\le \frac8{\pi\sqrt3}+2<\frac{18}5.
$$

Using pi>3, sqrt(3)>5/3 and Q(1)<phi(1)<1/3, (2) bounds the desired expectation by 9/5+1/6<2, which is stronger than (1). The argument includes rho=0 without division by rho.

## High correlation: 1/2<=rho<1

Set delta=1-rho and gamma=delta/sigma=sqrt((1-rho)/(1+rho)). For fixed x>=1, split the v integral into [0,x], (x,infinity), [-x,0], and (-infinity,-x).

The sum of the two positive-v pieces has exact x-integrand

$$
J_+(x)=\frac{\phi0}{\rho}\{Q(\gamma x)-Q(x/\sigma)\}
 +\phi0 e^{-\delta^2x^2/2}\Phi(\rho\gamma x).
$$

Since Phi(rho gamma x)<=Phi(gamma x),

$$
J_+(x)\le\phi0\{1+(\delta/\rho)Q(\gamma x)\}.
$$

Using integral_0^infinity Q(gamma x)dx=phi0/gamma and delta/gamma=sigma gives

$$
\int_1^u J_+(x)dx\le\phi0u+\phi0^2\sigma/\rho.\tag{3}
$$

For -x<=v<=0 the exact integrand is

$$
J_{-,A}(x)=\frac{\phi0}{\rho}
\{Q(x/\sigma)-Q((1+\rho)x/\sigma)\}
\le\frac{\phi0}{\rho}Q(x/\sigma),
$$

whose x>=1 integral is at most phi0² sigma/rho. For v<-x the exact integrand is

$$
J_{-,B}(x)=\phi0 e^{-(1+\rho)^2x^2/2}
Q\left(\frac{\rho(1+\rho)x}{\sigma}\right),
$$

whose x>=1 integral is at most 1/[4(1+rho)]. Therefore

$$
E[\mathbf1\{1<X\le u\}S_X(V)]
\le\phi0u+2\phi0^2\sigma/\rho+\frac1{4(1+\rho)}
\le\phi0u+\frac56.
$$

The last bound uses sigma/rho<=2, phi0²<1/6, and rho>=1/2. Equation (2) and Q(1)<1/3 now yield a bound phi0 u/2+7/12, stronger than (1).

## Degenerate correlations and leading optimality

Couple V_rho=rho X+sqrt(1-rho²)E with E independent standard Gaussian. For each finite u, the integrand converges almost surely as rho increases to 1, except at null-probability X endpoints. Fatou and the uniform upper bound prove (1) at rho=1; evenness handles rho=-1. No precision or independence assertion for the limiting pair is required.

At V=X, the admissible choice a=X on 1<X<=u gives

$$
M_X(X)\ge e^{-X^2/2}\cosh(X^2)\ge\tfrac12 e^{X^2/2}.
$$

Hence the expectation is at least phi0(u-1)/2. Together with (1), its ratio to u tends to phi0/2. This is optimality only for this auxiliary Gaussian-pair lemma, not a sharpness claim for a BH model.

## Possible application and remaining boundary

In a source-block population model, an actual isolated-block crossing can bound the full maximum-BH statistic cutoff C by a(Y1)/rmax on Y1>1, with a(Y1)<=Y1, and by o(1/rmax) on Y1<1. Other block null ratios then have limiting envelopes M_(beta_j Y1)(Yj), beta_j<=1. The lemma could give the two-sided half coefficient uniformly in correlations between factors, by splitting Y1 at u_q=Q^-1(q), using the strip bound on [1,u_q] and FDP<=1 on the remaining tail. These contact and limit assertions require their own proof; (1) does not supply a cutoff witness for arbitrary Gaussian arrays, and no general conjecture resolution follows from it.
