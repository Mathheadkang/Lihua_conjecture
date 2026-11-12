---
type: candidate
title: Growing orthogonal zero-null cloud at small fixed common loading
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
slot: 3
direction: drop_hypothesis
statement_digest: 559f931c8cf870c13d2afe6f41bae6c492b9b6e20edb09e35b2275ac15e3ed5d
performed_by: unknown
created_at: '2026-11-09T05:23:23.080Z'
extension_version: 0.0.4
---

## Object

For every sample size $m\ge1$, set $q=1/4$, $\sigma=1/100$, $N=d=m^2$, $v_i=e_i$, $\theta_i=0$, and $\ell_i=1$ for $1\le i\le N$. Let $G\sim N_N(0,I_N)$ and $Z\sim N(0,1)$ be independent. Set $\tau=\sqrt{1-\sigma^2}$ and $T_i=\tau G_i+\sigma Z$. Draw $I_1,\ldots,I_m$ independently uniformly on $[N]$, independently of the Gaussians, and run the prescribed BH procedures on the original array and its exact-copy sampled multiset.

This probes the simultaneous boundary of zero null means and unbounded residual rank: there are $m^2$ distinct residual carriers, rather than a single rare active index or a finite collection of tied score atoms. The proposed failure mechanism is persistent disagreement of the zero-versus-positive rejection events even when both rejection fractions are microscopic.

## Checks

### H1

Pass. The level $q=1/4$ is fixed and belongs to $(0,1/2)$.

### H2

Pass. The common loading $\sigma=1/100$ is fixed in $(0,1)$; it does not tend to zero with $m$.

### H3

Pass. For each $m$, the dimensions $N=d=m^2$ are positive integers and the deterministic vectors $v_i=e_i$ have norm one. The residual Gram matrix is the identity.

### H4

Pass. All tags equal one and all means equal zero, so $\ell_i=1\Rightarrow\theta_i\le0$. There are no alternative-tagged points.

### H5

Pass. The displayed independent Gaussian variables give exactly the stipulated score representation, with every marginal score variance $\tau^2+\sigma^2=1$.

### H6

Pass. The index sample is iid uniform and independent of $(G,Z)$; repeated indices retain the identical score $T_i$.

### H7

Pass. Both procedures use the actual largest qualifying non-strict finite BH rank and their original denominators. Since every tag is true, $D_j=\mathbf1_{\{\rho_j>0\}}$, for $j\in\{N,m\}$, including zero rejection.

### NOT

Fail. The proposed persistent error vanishes. The following bounds cover this concrete family for all $m$.

Conditional on $G$, put $A_i=\tau G_i$, and let $\Delta$ be the supremum over upper thresholds of the absolute difference between the sampled and original empirical tails of $A$. Tagged tails equal total tails here. Symmetrization followed by ordering the sampled values bounds
$$
\mathbb E_I[\Delta\mid G]
\le {2\over m}\mathbb E_{I,\varepsilon}\sup_t\left|\sum_{j=1}^m\varepsilon_j\mathbf1_{\{A_{I_j}\ge t\}}\right|
\le {4\over\sqrt m}.
$$
Indeed, after ordering, every upper threshold selects a prefix (possibly only selected prefix lengths when there are ties), and Doob's $L^2$ maximal inequality bounds the expected maximum absolute Rademacher prefix sum by $2\sqrt m$. Thus the event $E=\{\Delta\le\gamma\}$ satisfies
$$
\mathbb P(E^c)\le {4\over\gamma\sqrt m}=:p_m.
$$
Crucially $E$ is independent of $Z$.

Fix $0<a<1$ and $0<\gamma<a/2$, and put
$$
u_q(r)=S^{-1}(qr),\qquad
L_{q,a}=\sup_{a/2\le r\le1}|u_q'(r)|,\qquad h=L_{q,a}\gamma/\sigma.
$$
On $E$, a qualifying rank $r\ge a$ for either empirical law at $z$ produces a qualifying continuous rank $r-\gamma$ for the other law at $z+h$. In fact
$$
u_q(r-\gamma)-\sigma(z+h)\le u_q(r)-\sigma z,
$$
and the tail discrepancy is at most $\gamma$. Continuous-rank qualification also implies a qualifying finite-grid rank at least as large: if the count at $r'$ is $k/M\ge r'$, then the count at $k/M$ is at least $k/M$. Conversely every finite-grid qualifying rank is a continuous qualifying rank. Hence the actual finite BH ranks satisfy this transfer.

Write $f_j(z)=\rho_j(z)$ and $\delta_j(z)=f_j(z+h)-f_j(z)\ge0$. The functions $f_j$ are nondecreasing and lie in $[0,1]$. On $E$, the transfer gives
$$
|\rho_N-\rho_m|\le a+\gamma+\delta_N+\delta_m.
$$
For any bounded nondecreasing $f:\mathbb R\to[0,1]$, its Stieltjes measure gives
$$
\mathbb E_Z[f(Z+h)-f(Z)]\le h/\sqrt{2\pi}.
$$
Conditioning on $G,I$, then averaging, therefore yields
$$
\mathbb E|\rho_N-\rho_m|\le a+\gamma+{2h\over\sqrt{2\pi}}+p_m.
$$

The microscopic bound of the approved common-loading continuity statement applies both to the full finite array and, conditional on $I$, to its exact-copy finite sampled array. Thus
$$
\mathbb P(0<\rho_N\le a)+\mathbb P(0<\rho_m\le a)\le2B_{q,\sigma}(a).
$$
Outside these two microscopic events, a disagreement of the all-null FDP indicators means that one rank exceeds $a$ and the other is zero. On $E$, transfer forces the zero-rank procedure's increment over $[z,z+h]$ to be at least $a-\gamma$. Bounding the two possible orientations and integrating the same monotone increments gives
$$
\mathbb E|D_N-D_m|
\le2B_{q,\sigma}(a)+{2h\over(a-\gamma)\sqrt{2\pi}}+p_m.
$$
Consequently
$$
\mathbb E\bigl[|D_N-D_m|+|\rho_N-\rho_m|\bigr]
\le a+\gamma+2B_{q,\sigma}(a)
+{2h\over\sqrt{2\pi}}\left(1+{1\over a-\gamma}\right)
+{8\over\gamma\sqrt m}.
$$
For each fixed $a$, choose $\gamma=m^{-1/4}$ for all sufficiently large $m$. The limit superior is at most $a+2B_{q,\sigma}(a)$, which tends to zero as $a\downarrow0$ by the approved microscopic-rank conclusion. Thus even a growing cloud of boundary nulls with small fixed positive common loading cannot realize the proposed nonvanishing discrepancy. This calculation is confined to all-true tags; it does not compare general mixed FDPs.

## Failure

NOT fails: the common shift controls positive-rank disagreement, while the approved microscopic-rank bound makes the all-null zero-versus-positive mismatch probability vanish, uniformly for this growing orthogonal family.
