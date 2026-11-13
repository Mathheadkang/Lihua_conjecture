---
type: search_round
title: >-
  Refute search round 1, slot 1 (boundary and degenerate cases) for the
  rare-direction cap
target_asset: gaussian_bh_rare_direction_cap
mode: refute
round: 1
directions:
  - boundary_degenerate
candidates:
  - cand_gaussian_bh_rare_direction_cap_r1_s1_augmented_residual_cluster
  - cand_gaussian_bh_rare_direction_cap_r1_s1_one_direction_duplicate_cluster
  - cand_gaussian_bh_rare_direction_cap_r1_s1_replicated_orthogonal_staircases
statement_digest: 9afb59906629533a14999f6caaf3ad9532b3838891de891a2f9d6b5299480a12
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T06:03:41.507Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Obstructions

- Any counterexample to this lemma also violates the universal order bound $F_1(q)\le C_1q\sqrt{\log(1/q)}$ of the main target (gaussian_bh_one_sided_universal_order_upper), since the rare contribution is at most the FDR and $q(1+u)\asymp q\sqrt{\log(1/q)}$. Refuting the lemma therefore means refuting the main conjecture.
- Small models have no rare nulls: $\mu_i\ge1/m$, so $I_{\mathrm{rare}}=\varnothing$ whenever $m\le q^{-C_2}$, and also at the equality $\mu_i=q^{C_2}$. Every exhaustive small case is vacuous.
- A rare set made of exact duplicates in one direction (any $d$, any alternatives) contributes at most $q\mu(1+\log(1/\mu))\le q$ with $\mu<q^{C_2}$. Single-direction harmonic staircases, including the one-null staircase of idea_75d71c7756b4, cannot work.
- Replicating anticorrelated staircases across many separated directions fails whenever the alternatives' means are at least $2u$. The alternatives of every inactive block are rejected by default, so $R\ge m/4$ with probability $1-e^{-K/8}$ and the left side is at most $22q$. Competition through the single BH cutoff kills the harmonic gain; simulation shows FDR/$q$ falling to about $1/N$ once $K\ge3$.
- The rare set depends on the representation, not on the law. Law-preserving augmentation, $a_i\mapsto(a_i,\sqrt{1-r_i^2}\,e_{d+i})$, makes every null with $r_i<\cos(\kappa_2/u)$ rare (for $m>q^{-C_2}$). Any rare set that is a single-direction residual cluster in some representation is still bounded by the approved entropy bound, at most $(5/2+A_1(0))q(1+u)$. The one-factor pseudo-cluster lower family, of order $qu$, is the reason for the factor $(1+u)$ and does not exceed it.

## Limitations

- Not covered: replicated staircases whose alternatives have means below $2u$ (not rejected by default), and alternatives shared across many rare directions through sign-cube or simplex loadings with negative null-alternative correlations.
- Not covered: chains or multi-scale (ultrametric) arrangements of many tiny clusters at angle about $1/u$, where neighbourhood rarity holds but the clusters act jointly at a coarser scale.
- The round notes name a small-null-loading lower family; that node was not looked up. Only the tiny-loading and augmentation degenerations above were treated.
- The periodic artefact of $\cos(\kappa_2/u)$ for $\kappa_2/u>\pi/2$ is harmless only because $q_2$ may be chosen small. No numerical triage beyond small Monte Carlo runs was done.
