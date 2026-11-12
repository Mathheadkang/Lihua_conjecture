---
type: candidate
title: Singular background tie at a BH threshold
status: failed
target_asset: gaussian_bh_block_deficit_curve_reduction
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  NOT: fail
mode: refute
round: 1
slot: 3
direction: drop_hypothesis
statement_digest: f1dda2f50a23bcb44d5591faa42a4ed7c15018980386fbefca5819ed441dbef8
performed_by: unknown
created_at: '2026-11-06T21:22:09.796Z'
extension_version: 0.0.4
---

## Object

Set $N=4$, $q=1/2$, $i=1$, $B_1=\{1,2\}$, and $B_2=\{3,4\}$. Write $p(u)=2\overline\Phi(u)$ and $u_k=p^{-1}(k/8)$. Take independent standard normal factors $Z_1,Z_2$ and independent standard normal residuals, all loadings equal to $1$, and
$$
T_1=Z_1,\qquad T_2=u_4+Z_1,\qquad T_3=T_4=u_3+Z_2.
$$
The proposed edge is the permitted realization $Z_1=Z_2=0$ (residual values are immaterial). Then the mate ties the last BH threshold and both background coordinates tie the third threshold:
$$
(P_1,P_2,P_3,P_4)=(1,1/2,3/8,3/8).
$$
The potential obstruction being tested is a simultaneous downward jump in $D$ together with a mate exactly on the final threshold. This is a pointwise tie test; the realization is not asserted to have positive probability.

## Checks

### H1

Pass: the model consists of two independent one-factor blocks, has admissible endpoint loadings $1$, and coordinate $i=1$ has mean zero. Its covariance is the positive semidefinite block diagonal matrix with two $2\times2$ all-ones blocks, so every marginal variance is $1$. Singularity is allowed.

### H2

Pass: the p-values are $p(|T_j|)$ and $t_k=k/8$ is strictly increasing for $1\le k\le4$. At the stated realization the p-values have precisely the values displayed above.

### H3

Pass: the two background coordinates give
$$
(\beta(1),\beta(2),\beta(3),\beta(4))=(0,0,2,2).
$$
These are nondecreasing integers between $0$ and $N-|B_1|=2$. The whole background vector depends only on $Z_2$, independently of $Z_1$ and the block-1 residuals.

### H4

Pass: the single mate gives
$$
(M(1),M(2),M(3),M(4))=(0,0,0,1),
$$
a nondecreasing integer count.

### H5

Pass: using exactly the stipulated definitions gives
$$
D=(0,1,0,1),\qquad D^*=(0,0,0,1).
$$
Thus the proposed object includes the actual suffix minimum, rather than replacing it by a freely chosen curve.

### H6

Pass: closed threshold inequalities count both background ties at $t_3$ and the mate tie at $t_4$. After forcing the null p-value to zero, the ordered p-values are $(0,3/8,3/8,1/2)$, with largest qualifying rank $4$. With the mate additionally removed from the counts, they are $(0,3/8,3/8,1)$, with largest qualifying rank $3$.

### NOT

Fail: the proposed rank/curve contradiction does not occur. Directly,
$$
\max\{k:M(k)\ge D(k)\}=4
=\max\{k:M(k)\ge D^*(k)\},
\qquad
\max\{k:D(k)\le0\}=3.
$$
The curve $D^*=(0,0,0,1)$ is nondecreasing with increments $(0,0,1)$, satisfies $D^*\le D\le k-1$, and is nonpositive exactly at $k\le3$. Thus its flat rank and reduced rank agree with the direct BH ranks, including both exact-threshold ties. The independent block data also satisfy the asserted independence of $D^*$ from the block-1 factors and residuals. This edge realization supplies no violation of the conclusion.

## Failure

NOT fails: the singular simultaneous background tie and final-threshold mate tie preserve both ranks under the suffix-minimum reduction.
