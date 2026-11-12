---
type: idea
title: >-
  Uniform integrability of signed posterior-selector gradients at a
  private-noise cutoff
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_private_noise_cutoff_signed_transport_variation
  - gaussian_bh_one_sided_universal_order_upper
tags: []
---

Candidate continuation of signed support-function complementarity; not yet a proved result. Fix s,sigma,a,q>0, finite M2, and a deterministic smoothed directing law mu. Bulk mean-transport gradients are bounded by 2/(a s sqrt(2pi)). For an active suffix minimizer t>=a, Q(t)=u(qt)-sigma M(r). Restrict |M|<=B and conditional centre energy integral A_X^2 dmu<=K. Then Q lies in a deterministic compact interval; at least half the centre mass has |A_X|<=sqrt(2K), and private standard deviations lie in [s,sqrt(1-sigma^2)], so the mixed score density h(Q) has a deterministic positive lower bound. Every active posterior therefore assigns a set E at most C(B,K,a,q,s,sigma) mu(E). On the discarded sets, posterior probability<=1, the deterministic total variation bound integral|(chi f)'|<=1+log(1/a), phi(M)<=phi(B) on |M|>B, and P(energy>K)<=C(1+M2)/K. Hence the entire family of signed rank-selector gradients should be uniformly integrable in L1(mu). This gives countably additive weakly compact convex gradient sets (after closure), allowing Hahn-Banach separation to turn the actual maximum's difference-of-support-functions inequality into matched signed mean complementarity. Include the q velocity as one finite coordinate; preserve the one-sided tangent cone at true mean zero and the factor q*u(q) when multiplying the penalized normalized objective. A primary university note was accessed live: https://sites.math.rutgers.edu/courses/592/dunfordpettis.pdf, Theorem 1 on printed p1 and constructive proof pp2-4, which proves UI implies relative weak sequential compactness on a probability space by diagonalization, countable additivity and Radon-Nikodym. It has not been imported or independently checked in this project; either formally verify a supporting source or supply the standard compactness/separation proof inline. The countable-additive framework and active-selection measurability remain proof obligations. No q-scaled total-flux bound follows from UI alone.
