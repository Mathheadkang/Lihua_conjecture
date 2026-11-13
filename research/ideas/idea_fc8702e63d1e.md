---
type: idea
title: >-
  Complete derivation of the bounded-spectrum Gaussian Simes estimate: size at
  most 16 times the covariance norm times q
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_simes_one_sided_uniform_linear_bound
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - global-null-simes
  - side-chat-20261112
  - unverified-derivation
---

Suggested by this chat; saved at the researcher's request. This is a draft observation containing the complete calculation discussed in chat. It is not an approved asset or a native proof-verification verdict. It develops the first milestone of [the fixed-level proof program](idea_10f14a1fa91d.md).

## Claim and scope

Let $N\ge1$, let $\Sigma$ be a positive-semidefinite correlation matrix, let $Z\sim N_N(0,\Sigma)$, and put $p_i=\bar\Phi(Z_i)$, where $\bar\Phi$ is the standard normal survival function. Write $p_{(k)}$ for the ordered p-values including multiplicities, put $K=\|\Sigma\|_{\mathrm{op}}$, and define
$$
E_q=\{\exists k\in\{1,\ldots,N\}:p_{(k)}\le qk/N\}.
$$
The calculation proves
$$
\Pr(E_q)\le \min(1,16Kq)\qquad(0<q\le1/4).
$$
The constant is uniform in dimension, signs and singularity, subject to the displayed dependence on $K$.

## Exceedance-count variance

For $u\in\mathbb R$, put $p=\bar\Phi(u)$ and $C_u=\sum_i1_{\{Z_i\ge u\}}$. Let $H_\ell$ denote the normalized Hermite polynomials, so that for a standard normal $G$, $\mathbb E H_\ell(G)H_m(G)=1_{\{\ell=m\}}$. Expand in $L^2$ of the standard Gaussian law:
$$
1_{\{x\ge u\}}-p=\sum_{\ell\ge1}b_\ell H_\ell(x),
\qquad \sum_{\ell\ge1}b_\ell^2=p(1-p).
$$
The joint Gaussian Hermite identity, valid also at correlations $\pm1$ by continuity, gives
$$
\operatorname{Var}(C_u)
=\sum_{\ell\ge1}b_\ell^2\,\mathbf1^{\mathsf T}\Sigma^{\circ\ell}\mathbf1.
$$
Here $\Sigma^{\circ\ell}$ is its entrywise power. Every such matrix satisfies $0\preceq\Sigma^{\circ\ell}\preceq KI$. The base case is the definition of $K$. If it holds for $\ell$, the Schur product theorem and order preservation give
$$
0\preceq\Sigma\circ\Sigma^{\circ\ell}
\preceq\Sigma\circ(KI)=KI.
$$
Thus
$$
\operatorname{Var}(C_u)\le KNp(1-p).
$$

## Dyadic crossing ranks

For each $r=2^j\le N$, set
$$
t_r=q\min(2r,N)/N,\qquad D_r=\#\{i:p_i\le t_r\}.
$$
If a Simes crossing occurs at a rank $r\le k<2r$, then $qk/N\le t_r$, so $D_r\ge k\ge r$. Consequently $E_q\subseteq\bigcup_r\{D_r\ge r\}$. Marginal uniformity gives
$$
\mathbb ED_r=Nt_r\le2qr\le r/2,\qquad
\operatorname{Var}(D_r)\le KNt_r\le2Kqr.
$$
Chebyshev gives $\Pr(D_r\ge r)\le8Kq/r$. Since the sum of $1/r$ over dyadic $r\le N$ is less than $2$, summation proves the claim. All comparisons include equality; no covariance inverse is used.

## Why this does not prove the unrestricted conjecture

$K$ can grow as large as $N$. For complete correlation, $\Sigma=\mathbf1\mathbf1^{\mathsf T}$ and $K=N$, even though the true rejection probability is exactly $q$. Thus the spectral loss is an obstruction to this estimate, not evidence against a universal linear bound. A uniform fixed-level acceptance estimate for unbounded $K$ is still missing. See [the amplification observation](idea_7d0a17e5c13c.md).
