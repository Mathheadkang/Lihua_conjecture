---
type: idea
title: Large BH ranks cost only order q through a null-fraction entropy bound
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_two_sided_sharp_upper
  - gaussian_bh_one_sided_sharp_upper
tags:
  - exact-finite-array
  - entropy
  - rank-split
  - distribution-free
---

New elementary finite-array reduction reconstructed during primary-target planning; not yet a native approved lemma. Let there be N hypotheses, m actual true nulls, pi0=m/N, ordinary largest-rank BH at q, and superuniform marginal p-values on actual nulls, with arbitrary dependence and arbitrary alternative p-values. This includes both Gaussian tests with their exact true-null labels, including negative one-sided means. If m=0 the FDR is zero. If m=N the event R>m is empty. For 0<m<N,
E[FDP * 1{R>m}] <= q*pi0*[1+H_N-H_{m+1}] <= q*pi0*[1+log(1/pi0)] <= q.

Proof: put a=q/N. For each actual true null i, on rejection with R>m one has p_i<=aR and R>=m+1. Consequently its contribution 1{i rejected,R>m}/R is bounded by the decreasing step function psi(p_i): psi(t)=1/(m+1) for 0<=t<=a(m+1); psi(t)=1/k for a(k-1)<t<=ak, k=m+2,...,N; psi(t)=0 for t>q. Superuniformity bounds E psi(p_i) by its uniform integral, which equals a[1+sum_{k=m+2}^N 1/k]=a[1+H_N-H_{m+1}]. Sum over m nulls. Integral comparison gives H_N-H_{m+1}<=log(N/(m+1))<=log(N/m); p[1+log(1/p)]<=1 for 0<p<=1. This retains actual largest BH and needs no Gaussian assumption, nonsingularity, or independence; ties satisfy the same inequality. The universal leading-constant problem reduces to its LOW-RANK term E[FDP * 1{1<=R<=m}], since the large-rank term is o(q sqrt(log(1/q))).

This fixes the algebraic failure of a pure pi0-proportional allocation in the earlier single-null staircase: its large-rank harmonic cost can be paid by the entropy correction, rather than a false O(q*pi0*sqrt(log(1/q))) per-anchor bound. It does NOT construct the still-missing Gaussian signed forest/transport allocation for R<=m, nor prove either original conjecture. A new proof plan must supply a concrete low-rank Gaussian mechanism, not merely assume that residual estimate or reuse refuted pointwise capacities. The primary native plan assessment found no such universal mechanism yet. This observation and its exact binning proof should be independently checked before promotion.
