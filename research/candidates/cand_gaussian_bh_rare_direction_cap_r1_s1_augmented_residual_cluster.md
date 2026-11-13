---
type: candidate
title: >-
  Law-preserving augmentation that makes a one-direction residual null cluster
  rare
status: failed
target_asset: gaussian_bh_rare_direction_cap
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 9afb59906629533a14999f6caaf3ad9532b3838891de891a2f9d6b5299480a12
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T06:03:41.507Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

Start from a one-factor law: $m_0$ nulls $T_i=\rho Z_0+s\,\varepsilon_i$ ($\theta_i=0$, $0<\rho<1$, $s=\sqrt{1-\rho^2}$), plus $m-m_0$ alternatives with arbitrary means $\theta_j>0$, arbitrary loadings on $(Z_0,Z_1,\dots,Z_{d-1})$ and independent residuals. For example, take the anticorrelated staircase alternatives $T_j=c_j-Z_0$; this is the pseudo-cluster family whose FDR heuristically reaches order $qu$. This is a degenerate representation choice: the rare set depends on the representation, not on the law. Use the representation of dimension $d+m_0$ with null loadings $a_i'=\rho e_0+s\,e_{d+i}$ ($r_i'=1$, zero residual), and leave the alternatives' loadings padded with zeros. The joint law of $T$ is unchanged. Take $\rho^2<\cos(\kappa_2/u)$ (e.g. $\rho=1/\sqrt2$ and $q$ small) and $m>q^{-C_2}$.

## Checks

### H1

The augmented loadings have unit norm, and the law is identical to the original: $\rho Z_0+sZ_{d+i}$ has the law of $\rho Z_0+s\varepsilon_i$, jointly with everything else.

### H2

$I_0$ is the set of the $m_0$ nulls; one-sided p-values.

### H3

BH at level $q\le q_2$. Nothing to check.

### H4

In the augmented representation, $w_i'^{\mathsf T}w_k'=\rho^2<\cos(\kappa_2/u)$ for distinct nulls, so each neighbourhood is a singleton, $\mu_i=1/m<q^{C_2}$, and $I_{\mathrm{rare}}=I_0$. In the original representation all nulls share one direction, $\mu_i=m_0/m$, and the same nulls need not be rare.

### NOT

The left side $\mathbb E[|\mathcal R_q\cap I_0|/(R\vee1)]$ depends only on the law and the index set, so it can be evaluated in the original representation. Apply the approved [angular-cluster entropy bound](../assets/gaussian_bh_angular_cluster_entropy_bound.md) there, with $I_*=C_1=I_0$, $v_1=e_0$, cosines $\rho_i=a_i^{\mathsf T}v_1/r_i=1$, $\kappa=0$, $\beta_1=u$, $\pi_1=\pi_0$ and $\gamma_i=\sqrt{(1-\rho)/(1+\rho)}\le1$:
$$
\mathbb E\frac{|\mathcal R_q\cap I_{\mathrm{rare}}|}{R\vee1}\le q\pi_0\bigl(\tfrac32+A_1(0)\bigr)+q+\frac{qu}{\sqrt{2\pi}}\pi_0\le\bigl(\tfrac52+A_1(0)\bigr)q(1+u).
$$
So the conclusion holds with $A_2\ge\frac52+A_1(0)$, whatever the alternatives are. The $u$ term is genuinely needed here: this family is the reason the target allows $q(1+u)$ rather than $q$.

## Failure

NOT fails: an augmented rare set that is a single-direction residual cluster in another representation of the same law is bounded by the approved entropy bound, at most $(5/2+A_1(0))q(1+u)$.
