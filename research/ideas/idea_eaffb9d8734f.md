---
type: idea
title: >-
  Test deterministic fold recovery in two Gaussian directions with the
  moving-minimum correction
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_diffuse_fold_deformation_recovery
  - gaussian_bh_common_loading_wasserstein_fdr_continuity
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - random-fold
  - deterministic-transport
---

Suggested by the teaching chat; agent-origin approach for the next step after the isolated diffuse-fold prototype. All BH asymptotic formulas below are candidate calculations for independent verification, not approved results. Do not replace the current target or infer the universal bound from this test.

## Purpose

A deterministic parameter-law perturbation must work for all residual Gaussian realizations. It is not permissible to condition on X and then choose a different law pi_X. The cheap deformation of a fold at a fixed mean location may lose its cost advantage when the critical mean location is random. Test this in an explicit two-direction population before generalizing a one-direction fold balance.

## An explicit local geometry

Use fixed common loading sigma in (0,1), tau=sqrt(1-sigma^2). Two unit directions have inner product rho in (-1,1), yielding standard jointly Gaussian G_1,G_2. The null group has mass p in (0,1) and theta uniform on [m_1-L/2,m_1+L/2] strictly below zero; the alternative group has mass 1-p and theta uniform on [m_2-L/2,m_2+L/2] strictly above zero. Scores are theta+tau G_j+sigma Z.

Where both shifted score intervals overlap and the relevant tail quantile lies in that overlap, the residual-score tail quantile is exactly
Q(r,G)=p m_1+(1-p)m_2+tau[pG_1+(1-p)G_2]+L(1/2-r).
Write c(r)=barPhi^{-1}(qr) and b(r,G)=[c(r)-Q(r,G)]/sigma.
Choose r_* in (0,1) and L=q/phi(c(r_*)). Then b_r(r_*)=0 and
kappa=b_rr(r_*)=L^2 c(r_*)/sigma>0.
The corresponding original null mean at the crossing is
U(G)=Q(r_*,G)-tau G_1=C-tau(1-p)(G_1-G_2),
so U has a smooth nondegenerate Gaussian density.

This only establishes a LOCAL fold shape. It does not show that this fold creates the actual largest BH crossing. Before using any FDR formula, exhibit a compact background region with a fixed overlap margin, a separated competing old branch, and a nonzero signed full-FDP jump. Contributions outside that region must also be retained or controlled.

## Deterministic needle deformation and a necessary correction

For a fixed null-mean location a strictly inside its interval, take k in C_c^infinity and transport that group by
theta -> theta+h^2 k((theta-a)/h).
The directions and labels do not change. For small h this is a valid monotone transport within the negative mean interval, with
W1(pi_h,pi) <= (p/L) h^3 integral |k(s)| ds.

The minimizing rank moves by order h; evaluating the perturbation only at r_* misses a leading term. Write r=r_*+h x. The proposed local expansion for the birth level is
b_{*,h}(G)-b_*(G)=h^2 Delta_k((U(G)-a)/h)+o(h^2),
where
Delta_k(s)=inf_x {kappa x^2/2-(p/sigma)k(s-Lx)}.
Verify uniformity of the expansion in the selected background region and justify that no other rank becomes the minimizer.

In general Delta_{-k} is NOT -Delta_k. Thus an up-bump and a down-bump need not produce opposite birth shifts. A wide flat bump is a useful initial check, but its edge and new-minimum terms must be included.

## Averaged full-FDP response, not pathwise optimization

Let J(G)=D_after-D_before be the signed full-FDP jump of the actual largest crossing at this fold, and let E be the verified isolation region. Define the signed density
g(a)=d/da E[J(G) phi(b_*(G)) 1_E 1{U(G)<=a}].
If the required continuity and domination hold, the candidate fold-boundary contribution is
Delta F_fold = -h^3 g(a) integral Delta_k(s) ds + o(h^3).
A conditional birth shift is order h^2, but a fixed mean window hits only an order-h proportion of backgrounds. Its averaged gain is therefore order h^3, the SAME order as W1 cost.

The regular-branch contribution can also be order h^3. It cannot be discarded, nor can its sign be replaced by its positive part. The meaningful next object is the combined averaged signed response to one deterministic perturbation. This calculation does not justify J(G)=0 for each background or a sublinear-cost improvement after averaging.

## Executable next task

1. Verify the quantile algebra and choose a concrete parameter/background region where the fold is relevant to the actual maximum crossing.
2. Derive the moving-minimum Delta_k term, testing both k and -k.
3. Compute the COMPLETE order-h^3 response, including regular branches, other selected folds, region boundaries, and the complement of E.
4. Recover finite canonical competitors only AFTER fixing h: use the approved continuity theorem to approximate each endpoint to o(h^3). Do not differentiate a finite approximation and then exchange its derivative with atomization.
5. Feed the resulting averaged response into an Ekeland inequality with its actual transport cost. A same-order cost is still useful when the Ekeland slope parameter tends to zero.

Method reference only: Lee, Yu and Yang, Reparameterization Gradient for Non-differentiable Models, NeurIPS 2018, separates smooth-region and boundary contributions. It does not prove the BH expansion or its uniformity:
https://proceedings.neurips.cc/paper_files/paper/2018/file/b096577e264d1ebd6b41041f392eec23-Paper.pdf .
