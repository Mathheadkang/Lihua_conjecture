---
type: idea
title: >-
  The unrefined FDR-linking inequality loses the square-root-log scale even for
  independent Gaussian nulls
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_sharp_upper
  - gaussian_bh_two_sided_sharp_upper
tags:
  - verified_primary_source
  - method_barrier
  - joint_gaussian_constraint
---

Scoped primary-source check, not a new theorem or an approved dependency: Weijie J. Su, The FDR-Linking Theorem, arXiv:1812.08965v1 (submitted 21 Dec 2018), https://arxiv.org/abs/1812.08965; original PDF https://arxiv.org/pdf/1812.08965, Theorem 1 / (1.1), printed p.2. The checked inequality is FDR <= pi0*q + pi0*q*integral_{pi0*q}^1 FDR0(x)/x^2 dx, where FDR0 is BH applied only to the true-null p-values at critical values x*j/m0. It allows arbitrary dependence, including null/non-null dependence, and superuniform nulls. Theorem 3 / (1.2), printed p.5, gives q[1+log(1/q)] under PRDN; this is not asserted for every Gaussian covariance. Inference for this project: centered independent standard-Gaussian nulls have independent uniform p-values and FDR0(x)=x, so the displayed linking RHS equals pi0*q[1+log(1/(pi0*q))]. For fixed pi0>0 it is order q log(1/q), which is too large for either desired square-root-log sharp bound. Therefore an unrefined null-only linking reduction discards essential information about the joint Gaussian alternatives; a sharper plan would need an independently proved refinement retaining that information. The source's sharp PRDN adversary is not a jointly Gaussian counterexample to our targets. Metadata/title/author/year/identifier and the exact passage were checked against the arXiv record and original PDF; Scholar access failed, so verification used the primary arXiv route. No whole-bibliography or retraction audit was run, and no manuscript reference was added.
