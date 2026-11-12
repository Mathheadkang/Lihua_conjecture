---
type: candidate
title: Three distinct residual directions with competing mixed-tag prefixes
status: failed
target_asset: gaussian_bh_common_loading_uniform_submodel_compression
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  H7: pass
  NOT: fail
mode: refute
round: 3
slot: 2
direction: small_cases
statement_digest: 559f931c8cf870c13d2afe6f41bae6c492b9b6e20edb09e35b2275ac15e3ed5d
performed_by: unknown
created_at: '2026-11-09T05:23:23.080Z'
extension_version: 0.0.4
---

## Object

Fix $q=1/4$, $\sigma=1/2$, $N=3$, $d=2$, and $\tau=\sqrt{3}/2$. Set
$$
v_1=(1,0),\quad v_2=(0,1),\quad v_3=-(1,1)/\sqrt2,
\qquad (\theta_1,\theta_2,\theta_3)=(0,0,1),
\qquad (\ell_1,\ell_2,\ell_3)=(1,1,0).
$$
Let $G\sim N_2(0,I_2)$ and $Z\sim N(0,1)$ be independent, and use the exact scores $T_i=\theta_i+\tau\langle v_i,G\rangle+\sigma Z$. Sample $m$ independent uniform indices from $\{1,2,3\}$ independently of $(G,Z)$, retaining exact repeated scores. Compare ordinary BH on the original triple and on this sampled multiset.

This uses three different residual directions and all three possible positive original ranks. Its middle prefix can have a different true-tag fraction from either endpoint, so its FDP need not be monotone in the common shift. It is not the board's two-score switching family or a tied-score family.

## Checks

### H1

Pass: $q=1/4\in(0,1/2)$ and $\sigma=1/2\in(0,1)$ are fixed independently of $m$.

### H2

Pass: $N=3$ and $d=2$ are positive integers.

### H3

Pass: all three displayed deterministic vectors have Euclidean norm one. Their residual Gram matrix is positive semidefinite by its Gram representation; its singularity is permitted.

### H4

Pass: indices 1 and 2 have true tag and zero mean, and index 3 has alternative tag and positive mean one.

### H5

Pass: the scores use the specified independent standard $G,Z$ and common loading $\sigma$. In particular, each marginal variance is $\tau^2+\sigma^2=1$.

### H6

Pass: indices are sampled independently and uniformly, independently of both Gaussian variables. Repeated indices retain precisely the same score and tag, with no additional noise.

### H7

Pass: both procedures select the largest qualifying BH rank with non-strict inequalities, including rank zero and rank one, and use the original full tagged FDP.

### NOT

Fail: the expected sum of discrepancies tends to zero. Here is an explicit bound that retains the actual largest crossing and original FDP.

Write $w_i=m^{-1}\#\{j:I_j=i\}$ and
$$
\eta=\sum_{i=1}^3|w_i-1/3|.
$$
Each $mw_i$ has distribution $\operatorname{Binomial}(m,1/3)$, so
$$
\mathbb E\eta\le3\sqrt{\frac{2}{9m}}=\sqrt{2/m},
\qquad \mathbb P(\eta>\delta)\le\frac{\sqrt2}{\delta\sqrt m}.
$$
Fix $0<\delta<1/12$ and condition on $G$. Order the residual scores $A_i=\theta_i+\tau\langle v_i,G\rangle$ decreasingly, using deterministic index order for ties, as $A_{(1)}\ge A_{(2)}\ge A_{(3)}$. Let
$$
W_k=\sum_{j=1}^k w_{(j)},\quad r_k=k/3,\quad
u(r)=S^{-1}(qr),\quad
L=\sup_{1/4\le r\le1}|u'(r)|<\infty.
$$
On $\eta\le\delta$, each $w_i>0$, $|W_k-r_k|\le\delta$, and $W_k\ge1/4$. The original prefix $k$ qualifies precisely when
$$
Z\ge b_k:=\frac{u(r_k)-A_{(k)}}\sigma;
$$
the sampled prefix qualifies precisely when
$$
Z\ge b'_k:=\frac{u(W_k)-A_{(k)}}\sigma.
$$
Their threshold difference is at most $L\delta/\sigma$, and $b'_3=b_3$ exactly since $W_3=1$. In a sampled block of equal scores, qualification of any rank implies qualification of the block's last rank, since the BH threshold increases with rank. Thus considering complete prefixes identifies the actual largest BH rank, with ties retained. This also applies to an original tie. These observations justify the prefix formulas without a uniqueness assumption.

Outside the two intervals
$$
\bigcup_{k=1}^2[b_k-L\delta/\sigma,b_k+L\delta/\sigma],
$$
both laws have exactly the same qualifying prefixes and hence the same largest selected prefix $k$. The conditional probability of this union is at most $4L\delta/(\sigma\sqrt{2\pi})$, because $Z$ is independent of $(G,I)$ and its density is bounded by $1/\sqrt{2\pi}$.

For a common selected positive prefix, write $t_k=\sum_{j\le k}\ell_{(j)}/3$ and $U_k=\sum_{j\le k}w_{(j)}\ell_{(j)}$. Then
$$
\rho_N=r_k,\quad \rho_m=W_k,\quad D_N=t_k/r_k,\quad D_m=U_k/W_k,
$$
$$
|\rho_m-\rho_N|\le\delta,\qquad
|D_m-D_N|
\le\frac{|U_k-t_k|}{W_k}
 +\frac{t_k}{r_k}\frac{|W_k-r_k|}{W_k}
\le8\delta.
$$
For the common zero prefix both quantities vanish. On all remaining events the sum of discrepancies is at most two. Consequently
$$
\mathbb E\left[|D_m-D_N|+|\rho_m-\rho_N|\right]
\le\frac{2\sqrt2}{\delta\sqrt m}
 +\left(9+\frac{8L}{\sigma\sqrt{2\pi}}\right)\delta.
$$
Taking $\delta=m^{-1/4}$ for all sufficiently large $m$ gives an explicit $O(m^{-1/4})$ upper bound. The three-prefix mixed-FDP changes therefore do not violate the target. This calculation is confined to the displayed three-atom family and does not establish uniformity over growing populations.

## Failure

NOT fails: all three original crossing thresholds move by at most a constant times the multinomial frequency error, and Gaussian smoothing plus direct prefix-FDP comparison makes the expected discrepancy vanish.
