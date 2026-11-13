---
type: candidate
title: >-
  Extreme negative equicorrelation rho = -1/(N-1) on the boundary of the PSD
  cone
status: failed
target_asset: gaussian_simes_dense_crossing_tilt_bound
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 6e714bc6bdb2353b928e977aa5b3c27aa068b24a6df42caf55510b6b8e0b24c8
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T19:14:45.821Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

$N\ge2$ arbitrary (possibly depending on $q$), $\Sigma=\frac{N}{N-1}\bigl(I_N-\frac1N\mathbf 1\mathbf 1^{\mathsf T}\bigr)$, i.e. $\Sigma_{ii}=1$, $\Sigma_{ij}=-1/(N-1)$ for $i\ne j$ (rank $N-1$, the most negative exchangeable correlation). Realize $T=c_N(Z-\bar Z\mathbf 1)$ with $Z\sim\mathcal N_N(0,I_N)$, $\bar Z=\frac1N\sum_iZ_i$, $c_N=(1-1/N)^{-1/2}$. Any $q\in(0,1/4]$, worst boundary $\delta=1$ (all $\delta\in(0,1]$ handled). Run along $q\to0$.

## Checks

### H1
Pass.

### H2
$\Sigma$ is a positive multiple of an orthogonal projection, so symmetric PSD; $\Sigma_{ii}=\frac N{N-1}(1-\frac1N)=1$. Singular (kernel $\mathbf 1$), which is admitted. Pass.

### H3
$\operatorname{Cov}(c_N(Z-\bar Z\mathbf 1))=c_N^2(I-\frac1N\mathbf 1\mathbf 1^{\mathsf T})=\Sigma$. Pass.

### H4
Pass.

### H5
Pass (take $q$ small).

### NOT
Write $v_k=\overline\Phi^{-1}(qk/N)$; on $D_{q,\delta}$ the witness $k$ satisfies $u_q\le v_k\le u_q+\delta\le u_q+1$.

*Regime $N\ge(u_q+1)^2$.* $\bar Z$ is independent of $T$ (Gaussian, uncorrelated with $Z-\bar Z\mathbf 1$), and $Z_i=T_i/c_N+\bar Z$. If $T_i\ge v_k$ and $\bar Z\ge a:=(u_q+1)(1-c_N^{-1})$, then $Z_i\ge v_k-v_k(1-c_N^{-1})+\bar Z\ge v_k$. So $D_{q,\delta}\cap\{\bar Z\ge a\}\subset D^Z$, the same dense Simes event for the i.i.d. vector $Z$, and $\mathbb P(D^Z)\le q$ (Simes equality for independent uniforms). Since $1-\sqrt{1-1/N}\le 1/N$, $a\sqrt N\le (u_q+1)/\sqrt N\le1$, so by independence
$$
\mathbb P(D_{q,\delta})\le \frac{q}{\overline\Phi(1)}\le 6.31\,q .
$$

*Regime $N<(u_q+1)^2$.* $D_{q,\delta}\subset\{\min_ip_i\le q/N\}\cup\{\exists i\ne j:T_i\ge u_q,\ T_j\ge u_q\}$ (a witness $k\ge2$ needs two coordinates above $v_k\ge u_q$). The first has probability $\le q$. For the second, $\rho_{ij}\le0$ and Slepian give $\mathbb P(T_i\ge u_q,T_j\ge u_q)\le q^2$, so
$$
\mathbb P(D_{q,\delta})\le q+N^2q^2\le q\bigl(1+(u_q+1)^4\overline\Phi(u_q)\bigr)\le q\,(1+\sup_{u\ge0}(u+1)^4\overline\Phi(u)),
$$
a universal multiple of $q$ (the supremum is finite, below $3$, attained near $u=1.4$).

Thus $\mathbb P(D_{q,\delta})\le 7q$ uniformly in $N,\delta$; the ratio is bounded. Fail.

## Failure

NOT fails: the singular direction $\mathbf 1$ splits off an independent scalar $\bar Z$ whose favourable half-line costs only a constant factor relative to the i.i.d. Simes bound when $N\gtrsim u_q^2$, and for $N\lesssim u_q^2$ pairwise exceedances are negligible.
