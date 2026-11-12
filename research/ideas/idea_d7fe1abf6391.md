---
type: idea
title: >-
  Exclude full-private-noise nulls and uniformly bounded dimension from
  fixed-floor counterexamples
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_private_noise_floor_order
tags:
  - gaussian-bh
  - fixed-private-noise-floor
  - search-obstruction
---

Two elementary reductions isolate the unresolved counterexample regime for gaussian_bh_one_sided_private_noise_floor_order. They are boundary checks, not a proof of the full statement.

1. If every true null has s_i=1, unit marginal variance forces a_i=0. These null test statistics depend only on their distinct private noises, so their p-values are mutually independent and independent of the whole alternative block, even when that block is singular, tied, or q-dependent. The ordinary largest-rank BH leave-one-out identity and superuniform null p-values give FDR <= (m_0/N) q; for zero null means the identity is equality. Thus all such full-private-noise-null models have FDR/[q sqrt(log(1/q))] <= 1/sqrt(log(1/q)). This includes s_0=1 and also endpoint models admissible for any smaller fixed floor. The first and third round-one candidates belong to this same family.

2. For arbitrary dependence and N<=M with M fixed, any false rejection has a null p-value at most q because the BH cutoff q R/N is at most q. Superuniformity and the union bound yield FDR <= P(V>0) <= m_0 q <= M q. Consequently the normalized ratio tends to zero uniformly within every fixed dimension bound. This excludes the two-null family without requiring its particular covariance calculation.

A counterexample family that makes the normalized ratio unbounded must therefore allow unbounded N and some true null loading a_i != 0 while preserving one fixed positive private-noise floor. Neither reduction bounds the general class when N grows and 0<s_0<1. These proof steps have not been independently verified or promoted to an approved result.
