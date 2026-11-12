---
type: candidate
title: Vanishing false seed with two opposing macroscopic null blocks
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
round: 4
slot: 2
direction: small_cases
statement_digest: 559f931c8cf870c13d2afe6f41bae6c492b9b6e20edb09e35b2275ac15e3ed5d
performed_by: unknown
created_at: '2026-11-09T05:30:58.332Z'
extension_version: 0.0.4
---

## Object

Fix any admissible level and common loading, for example $q=1/4$ and $\sigma=1/2$, and put $\tau=\sqrt{1-\sigma^2}$. For each sampling size $m\ge4$, take $N=2m$ and $d=2$. Two indices have parameters $(\theta,v,\ell)=(m,e_1,0)$, and each of the remaining two blocks of $m-1$ indices has parameters $(0,e_2,1)$ or $(0,-e_2,1)$. Thus the three scores are
$$
T_0=m+\tau G_1+\sigma Z,\qquad
T_+=\tau G_2+\sigma Z,\qquad
T_-=-\tau G_2+\sigma Z.
$$
The alternative seed has population mass $p=1/m$; each null block has mass $(1-p)/2$. Sample exactly as in the target. Let $w_0,w_+,w_-$ be the sampled block frequencies and let
$$
\delta=|w_0-p|+|w_+-(1-p)/2|+|w_--(1-p)/2|.
$$
The seed is absent with probability $(1-1/m)^m\to e^{-1}$. This is a seed-triggered null-cascade test, rather than the previous sole-active-index test: the other blocks can make macroscopic rejections. The vanishing seed mass and diverging mean test a regime for which a finite-prefix estimate involving the least atom mass would not directly be uniform.

## Checks

### H1

The fixed choices satisfy $0<q<1/2$ and $0<\sigma<1$.

### H2

$N=2m$ and $d=2$ are positive integers; the three deterministic directions $e_1,e_2,-e_2$ all have norm one. Repetition is allowed.

### H3

The null blocks have tag one and mean zero. The seed has tag zero and mean $m>0$. The sign restrictions hold, and the tags are canonical.

### H4

Take independent $G=(G_1,G_2)\sim N_2(0,I_2)$ and $Z\sim N(0,1)$. The displayed scores have precisely the target's common-loading representation and marginal variance one.

### H5

Draw $I_1,\ldots,I_m$ independently and uniformly from the $2m$ indices, independently of $(G,Z)$. Consequently $(mw_0,mw_+,mw_-)$ is multinomial with probabilities $(p,(1-p)/2,(1-p)/2)$ and
$$
\mathbb E\delta\le\sum_{j\in\{0,+,-\}}\sqrt{p_j(1-p_j)/m}\le\frac{3}{2\sqrt m}.
$$

### H6

Every draw uses the original score, mean and tag. All sampled occurrences of a block are exact copies, without additional noise.

### H7

Use the ordinary largest non-strict BH ranks and the full tagged FDPs. The calculation below uses exact prefix ranks and includes zero rejection and the terminal rank one.

### NOT

The proposed nonvanishing discrepancy fails. Here is a bound uniform in the vanishing seed mass of this family.

Let $E$ be the event that the seed residual score $m+\tau G_1$ exceeds both null residual scores. Gaussian tail bounds give
$$
\mathbb P(E^c)\le3\exp\{-m^2/(8\tau^2)\}.
$$
Indeed $E$ holds if $\tau G_1\ge-m/2$ and $\tau|G_2|<m/2$. On $E$, order the two null blocks by their realized scores. Their upper residual score is $\tau|G_2|$ and their lower residual score is $-\tau|G_2|$.

Let $B=\{\delta\le1/8\}$. Since $m\ge4$, both sampled null masses on $B$ are at least $1/4$, and
$$
\mathbb P(B^c)\le8\mathbb E\delta.
$$
The original rank including exactly the upper null block is
$$
r_1=p+(1-p)/2=(1+p)/2,
$$
and the corresponding sampled rank is $s_1=w_0+w_{\mathrm{upper}}$. Both are at least $1/4$, and $|r_1-s_1|\le\delta$.

For $u_q(r)=S^{-1}(qr)$, set
$$
L=\sup_{1/4\le r\le1}|u_q'(r)|<\infty.
$$
The first-null crossing thresholds in the common variable $z$ are exactly
$$
c_1=\frac{u_q(r_1)-\tau|G_2|}{\sigma},\qquad
c'_1=\frac{u_q(s_1)-\tau|G_2|}{\sigma}.
$$
Their distance is at most $L\delta/\sigma$. Both arrays have the identical terminal crossing threshold
$$
c_2=\frac{u_q(1)+\tau|G_2|}{\sigma}.
$$
These are exact finite BH checks: if a tied block is rejected, its last index qualifies, and the largest qualifying prefix is the actual rejection set. On $E\cap B$, the arrays can choose different null-containing prefixes only when $Z$ lies between $c_1$ and $c'_1$. Conditional on $G$ and the sampled indices, this interval has probability at most $L\delta/(\sigma\sqrt{2\pi})$. Non-strict endpoints have zero conditional Gaussian probability; their exact inclusion does not affect the estimate.

Outside that interval, both arrays have the same macro-prefix type. If both reject all indices, their rank difference is zero and their FDP difference is $|p-w_0|\le\delta$. If both select the first null prefix, the rank difference is at most $\delta$, and their FDPs are
$$
1-p/r_1,\qquad1-w_0/s_1.
$$
Since $r_1,s_1\ge1/4$, their FDP difference is bounded by
$$
\left|p/r_1-w_0/s_1\right|
\le4|p-w_0|+16w_0|r_1-s_1|\le20\delta.
$$
If neither array rejects a null block, both FDPs are zero and their ranks are each either zero or the seed mass. Their rank difference is at most $p+w_0$. These statements also cover a sampled seed count of zero.

The sum of the two discrepancies is always at most two. Combining the bounds and using $\mathbb Ew_0=p=1/m$ therefore yields
$$
\mathbb E\bigl[|D_m-D_N|+|\rho_m-\rho_N|\bigr]
\le\left(37+\frac{2L}{\sigma\sqrt{2\pi}}\right)\mathbb E\delta
+\frac2m+6\exp\{-m^2/(8\tau^2)\}
\longrightarrow0.
$$
For $q$ in a compact subset of $(0,1/2)$ the same bound is uniform, since the supremum defining $L$ is then uniformly finite. Missing the rare false seed with probability tending to $e^{-1}$ therefore does not create a persistent full-FDP or rank discrepancy: a macroscopic null cascade can change only inside a shrinking common-Gaussian window.

## Failure

NOT fails: even with a frequently missing false seed, macroscopic null-cascade changes occur only inside common-shift windows of expected width $O(m^{-1/2})$, and seed-only rejections have zero FDP and vanishing rank.
