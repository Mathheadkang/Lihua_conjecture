---
type: idea
title: >-
  Exact S plan gate: the single-direction level supremum is not a normalized
  density
status: draft
idea_kind: risk
origin: agent
related_assets:
  - gaussian_bh_one_sided_private_noise_floor_order
  - lehec2015_ou_fixed_time_tail
  - lehec2015_semilogconvex_density_tail
  - gaussian_frozen_ray_independent_equal_weights
tags:
  - private-noise-floor
  - plan-screening
  - Mehler-maximal
  - normalization-gap
---

## Screening disposition

No executable full-target plan is supplied. This is a draft screening observation for [fixed-floor target S](../assets/gaussian_bh_one_sided_private_noise_floor_order.md), retaining exactly its fixed s0 constants C(s0), q0(s0), arbitrary finite N, all null means, loading geometry, alternatives, largest qualifying rank and non-strict BH inequalities. The missing estimate remains the averaged Mehler level-maximal bound S1 in [the original structured program](idea_7727ae2d6679.md); this record neither disproves S nor asserts a new theorem.

## A concrete normalization obstruction

Fix 0<s0<1, choose s in [s0,1), and put r=sqrt(1-s^2)>0. In the legal one-null model T=rG+s epsilon with independent standard normals and theta=0, define rho_x(m)=barPhi((x-rm)/s)/barPhi(x). Every fixed finite x satisfies E[rho_x(G)]=1 by Gaussian convolution. For any fixed finite U, however, on m>=rU choose x=m/r. Then

$$
\sup_{x\ge U}\rho_x(m)\ge \rho_{m/r}(m)=\frac{\overline\Phi(sm/r)}{\overline\Phi(m/r)}\sim\frac1s e^{m^2/2}\quad(m\to\infty).
$$

The asymptotic follows directly from the scalar Mills ratio barPhi(t)~phi(t)/t. Multiplication by the standard Gaussian density shows that the displayed lower bound has nonintegrable positive tail. Consequently E[sup_{x>=U}rho_x(G)]=infinity even with one direction. This calculation is an agent derivation requiring independent checking, not an approved asset. It does not contradict the proposed capped S1 bound: integration only up to m of order sqrt(log c) gives its anticipated sqrt(log c)/s scale. It pinpoints why replacing a family of normalized fixed-level densities by its supremum and applying a normalized-density theorem is invalid. Capping that supremum is not a free cure: its unknown integral is the exact quantity needing proof; smoothness/semilogconvexity of a minimum also cannot be silently assumed.

## Existing tools and adaptation limits

The exact statements of [fixed-time OU regularization](../assets/lehec2015_ou_fixed_time_tail.md) and [normalized semilogconvex density regularization](../assets/lehec2015_semilogconvex_density_tail.md) require an integrable normalized input or density and do not estimate the free-level supremum. Native show found no Proof section for the latter, so no complete source proof is adapted here. The closest library analogues lib_bgl2015_ou_reverse_isoperimetry and lib_chi2024_positive_gaussian_simes provide respectively a pointwise gradient inequality and a nonnegative-correlation/global-null Simes result; their sketches or citation-only arguments do not supply the missing maximal step for arbitrary geometry and full FDR. Native library searches for Gaussian/Mehler/noise floor/compound, then Lehec, frozen, maximal, regularization and likelihood found no applicable indexed maximal theorem.

The complete proof of [independent equal-weight frozen rays](../assets/gaussian_frozen_ray_independent_equal_weights.md) was inspected. Its collective-envelope estimate uses independence explicitly to replace the variance of an average by K^-1 times a scalar variance; its deletion variance and rare-count steps also require a product law. These steps cannot be transferred to arbitrary correlated directions, unequal norms and the Mehler kernel without an actual replacement estimate. No such replacement is constructed in this screening. Thus no source proof is claimed as a successful adaptation.

## Finite BH aggregation and later quantifiers

[The conditional compound-p-value source lead](idea_32fd49aacc73.md) may replace S2 synchronization through the summed conditional CDF envelope, but its source import, extraction and independent verification are not performed in this protected plan stage. It is neither an approved black-box dependency nor a proof of S1. Even if S2 is supplied, the nonintegrable supremum above prevents the fixed-time normalization shortcut for S1. [The common-interval warning](idea_72355836a88b.md) remains a separate later obligation: a fixed-s0 theorem must not be passed to zero noise using uniform C(s0) alone when q0(s0) may shrink.

## First failure gate

Before executing a plan for S, supply a new, checkable argument bounding E min{c,sup_{x>=U} N0^-1 sum_i rho_{i,x}(G)} by C(s0)(1+sqrt(log c)), uniformly over arbitrary legal loading arrays, or another mechanism proving the full actual-BH target without this relaxation. A checklist that merely assumes this estimate repeats the unresolved target and spends an attempt without new information. No plan, asset statement, approval, project configuration, loop state or stage report is changed by this screening.
