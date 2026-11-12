---
type: idea
title: >-
  Uniform-dimensional isotropic angular maximal envelope via noncentral chi
  density caps
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - boundary_degenerate
---

Round4 slot1 exact analytic check for the joint-dimension isotropic boundary. This extends the fixed-d observation idea_6785334fa9ae by proving a dimension-uniform maximal envelope bound, rather than assuming a general frozen-ray conjecture or asserting that a maximal envelope is realized by the actual BH rank. No candidate is written: a continuum isotropic angular measure is not a finite Gaussian testing model, and finite directional discretization, finite loading and rare-alternative largest-crossing transfer are not supplied here.

Definitions. Let d>=2 be any integer, let sigma_d be uniform probability measure on S^{d-1}, and set L_d(a,R)=exp(-a^2/2) integral exp(aR v_1)sigma_d(dv), a>=0. Let M_d(R)=sup_{a>=0}L_d(a,R), and let f_d be the density of the central chi_d radius ||G_d||. All quantities are deterministic functions of d,a,R; the supremum is outside the angular integral.

Exact radial density identity. For each a>=0, f_d(R)L_d(a,R) is exactly the noncentral chi_d radial density with Gaussian mean vector of length a. This follows by integrating the likelihood ratio exp(a v.G-a^2/2) over radial directions. The noncentral chi-square Poisson mixture, with K~Poisson(a^2/2), yields the exact density formula

f_d(R)L_d(a,R)=sum_{k>=0} Pr(K=k) f_{d+2k}(R).

It can also be checked directly from the chi-square moment generating function (1-2t)^(-d/2)exp(a^2 t/(1-2t)) by expanding the last factor as the Poisson generating series, then changing variable from radius squared to radius.

Universal radial density cap, proved here. For every integer n>=2, the central chi_n density has log-density ell_n(R)=constant+(n-1)log R-R^2/2 and mode m_n=sqrt(n-1). On R>=m_n, ell_n'(m_n)=0 and ell_n''(R)=-(n-1)/R^2-1>=-2. Therefore ell_n(m_n+t)>=ell_n(m_n)-t^2 for every t>=0. Integrating the density over this half-line gives

1>=f_n(m_n) integral_0^infinity exp(-t^2)dt=f_n(m_n)sqrt(pi)/2.

Thus f_n(R)<=C=2/sqrt(pi) uniformly in n,R. Every Poisson mixture above has the same cap. Taking its supremum in a proves the exact pointwise inequality

f_d(R)M_d(R)<=C

for every d>=2 and R>0. This is specific to isotropic angular mixing and is not inferred for arbitrary angular measures.

Uniform central radial width. The standard chi-square Chernoff rate at s>0 is I_d(s)=(s-d-d log(s/d))/2. For s=(sqrt(d)+B)^2, its value is B^2/2+sqrt(d)B-d log(1+B/sqrt(d))>=B^2/2. For 0<B<sqrt(d), at s=(sqrt(d)-B)^2 it is B^2/2-sqrt(d)B-d log(1-B/sqrt(d))>=B^2/2; for B>=sqrt(d) the lower-tail event is empty. Consequently Pr(|R-sqrt(d)|>B)<=2exp(-B^2/2), uniformly in d.

Dimension-uniform capped maximal integral. For every alpha in (0,1), split the radial integral at the interval |R-sqrt(d)|<=B. Its length is at most 2B, so the preceding exact inequalities yield

E min(1,alpha M_d(||G_d||))
=integral_0^infinity min(f_d(R),alpha f_d(R)M_d(R))dR
<=2C alpha B+2exp(-B^2/2).

Choose B=sqrt(2log(1/alpha)) to obtain the fully explicit bound

E min(1,alpha M_d(||G_d||))<=[4sqrt(2)/sqrt(pi)] alpha sqrt(log(1/alpha))+2alpha,

uniformly over every integer d>=2. Hence any joint choice d=d(q) cannot create an unbounded normalized envelope merely by using isotropic angular mass in this limiting small-loading curve. For any fixed lambda>0, substitute alpha=lambda q when lambda q<1. No asymptotic interchange between d and q is used.

Boundary still open. The original finite Gaussian nulls r v_i.G+sqrt(1-r^2)epsilon_i have a finite empirical angular measure and an exact finite-r conditional tail curve; they are not literally L_d(a,R). Neither a uniform replacement error over all relevant score cutoffs nor a finite angular approximation with all original multiplicities has been proved here. Alternative survival profiles and original largest BH crossings cannot be chosen by equating them to the maximizing a after seeing G without a valid Gaussian construction. Arbitrary nonuniform angular measures are entirely outside this exact isotropic density identity. This observation therefore provides a scoped isotropic maximal gate and blocks the proposed dimension-only isotropic limiting-envelope counterexample mechanism; it does not establish or refute the main finite-model FDR target and requires independent verification before reuse as an established result.
