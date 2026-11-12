---
type: candidate
title: Independent singular antithetic Gaussian blocks with growing rank
status: failed
target_asset: gaussian_simes_one_sided_uniform_linear_bound
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 2
slot: 3
direction: boundary_degenerate
statement_digest: 15d52b3eb80faa8138461b0390ec347f4eb6a5465aae5494d0e050fea1bae614
performed_by: unknown
created_at: '2026-11-09T04:20:28.439Z'
extension_version: 0.0.4
---

## Object

For arbitrary integers $m\ge2$ and $d\ge1$, put $N=2md$. Let $Z_1,\ldots,Z_m$ be independent standard normal variables. Block $j$ consists of $d$ copies of $Z_j$ and $d$ copies of $-Z_j$. Concatenate the blocks to obtain $T$. Allow both $m$ and $d$ to depend on $q$, with $0<q<1/2$.

This tests the singular boundary with exact negative correlations, repeated coordinates, and arbitrarily growing covariance rank. Unlike the board's single rank-one family, its $m$ independent latent directions cannot be represented by one scalar Gaussian; unlike the polygon family, its rank grows without bound.

## Checks

### H1

Pass: $N=2md$ is a positive integer and is unbounded over the family.

### H2

Pass: write $v=(1,\ldots,1,-1,\ldots,-1)\in\mathbb R^{2d}$, with $d$ entries of each sign. Then $\Sigma$ is block diagonal with $m$ copies of $vv^{\mathsf T}$. It is symmetric, positive semidefinite, and has unit diagonal, so $\Sigma\in\mathcal C_N$. Each block has one eigenvalue $2d$ and $2d-1$ zero eigenvalues. Thus $\operatorname{rank}(\Sigma)=m$.

### H3

Pass: $T$ is a deterministic linear transform of $(Z_1,\ldots,Z_m)$, hence is exactly jointly Gaussian with mean zero and covariance $\Sigma$. Every coordinate is a centered unit-variance true null.

### H4

Pass: the calculation below holds for every $0<q<1/2$, including every $0<q\le q_0$ for any proposed $q_0\in(0,1/2)$.

### H5

Pass: use exactly $p_i=\overline\Phi(T_i)$ and the ordinary non-strict Simes comparisons, retaining all $d$ repeated copies. If $U_j=\overline\Phi(Z_j)$, the p-values in block $j$ are $d$ copies each of $U_j$ and $1-U_j$. The $U_j$ are independent uniform variables.

### NOT

Fail: the Simes rejection probability is exactly $q$ for this whole growing-rank family.

To see this, set $V_j=\min(U_j,1-U_j)$ and $W_j=2V_j$. The $W_j$ are independent uniform variables on $[0,1]$. Every Simes threshold is at most $q<1/2$, so only the smaller p-value from each block can participate in a crossing. Sorted participating values are the $V_{(j)}$, each with multiplicity $d$. A crossing within such a group implies a crossing at its final rank $dj$, since the p-value stays fixed and the threshold increases. Consequently the original event is exactly
$$
\left\{\exists j\in\{1,\ldots,m\}: V_{(j)}\le\frac{qdj}{2md}\right\}
=\left\{\exists j\in\{1,\ldots,m\}: W_{(j)}\le\frac{qj}{m}\right\}.
$$

Here is a direct verification that the latter probability equals $q$. Apply ordinary BH to $W_1,\ldots,W_m$ and call its rejection count $K$. For each $j$, let $K_j$ be the rejection count after replacing $W_j$ by zero. Then $K_j\ge1$ and $K_j$ depends only on the other uniforms. Deterministically,
$$
\{j\text{ is rejected}\}=\{W_j\le qK_j/m\},
\qquad K=K_j\quad\text{on this event}.
$$
Indeed, decreasing a rejected coordinate to zero cannot alter order statistics above the original rejection count, so it cannot create a larger crossing. Conversely, if $W_j\le qK_j/m$, restoring that coordinate leaves at least $K_j$ coordinates at or below $qK_j/m$; monotonicity gives equality of counts. Independence and uniformity now give
$$
\mathbb E\left[\frac{\mathbf1\{j\text{ is rejected}\}}{K\vee1}\right]
=\mathbb E\left[\frac{qK_j/m}{K_j}\right]=\frac qm.
$$
Summing over $j$ yields $\mathbb P(K\ge1)=q$. Thus the original rejection-probability-to-level ratio is identically one, even if dimension, replication, and covariance rank grow arbitrarily with $q$. This cannot refute an unspecified finite universal linear bound.

## Failure

NOT fails: independent balanced antithetic blocks reduce exactly to independent-uniform Simes and have rejection probability $q$ at every $0<q<1/2$.
