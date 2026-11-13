---
type: candidate
title: >-
  Global null on the regular simplex (equicorrelation -1/(m-1)) with singleton
  rare clusters
status: failed
target_asset: gaussian_bh_separated_rare_cluster_cap
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
statement_digest: 41a2d96d4641af88c2627a7dc0e53cf74e3004654a2cb9353183aff244b71a7d
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T07:17:56.260Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

Global-null Simes instance of the cap at the most negative exchangeable correlation. Given the asserted constants, take $q\le\min(q_2,\overline\Phi(1))$, so $u\ge1\ge\kappa_2$, and an integer $m\ge\max\{10,\ \log(1/q),\ \lfloor q^{-C_2}\rfloor+1\}$. Put $d=m$, $c=\sqrt{m/(m-1)}$, $w_i=c\,(e_i-\tfrac1m\mathbf 1)$, $\theta=0$. Then $\Sigma_{ii}=1$, $\Sigma_{ij}=-1/(m-1)$ for $i\ne j$. Partition: singletons $G_i=\{i\}$, $v_i=w_i$, $H=m$.

## Checks

### H1

$\|w_i\|^2=c^2(1-1/m)=1$; $T=WZ$ is the unit-loading model, $\Sigma=WW^{\mathsf T}$ (rank $m-1$, singular). Pass.

### H2

$0<q\le q_2$. Pass.

### H3

$I_0=[m]$; the singletons partition it; $v_i=w_i$ are unit vectors. Pass.

### H4

$\|w_i-v_i\|=0$. Pass.

### H5

$\|v_i-v_j\|^2=2-2\Sigma_{ij}=2+2/(m-1)>1\ge(\kappa_2/u)^2$. Pass.

### NOT

$\pi_i=1/m<q^{C_2}$, so all clusters are rare; with no alternatives $V=R$ and the left side is $P(R>0)$, the size of the Simes test on $T$. Bound it.

Coupling: let $X\sim\mathcal N_m(0,I_m)$, $\bar X=\frac1m\sum_iX_i$, and $T_i=c(X_i-\bar X)$; this has the law of $T$, and $\bar X\sim\mathcal N(0,1/m)$ is independent of $T$. The event $E(t)=\{\text{BH on }\overline\Phi(t)\text{ rejects}\}$ is increasing in $t$. On $\{\bar X\ge0\}$, $cX_i=T_i+c\bar X\ge T_i$, so
$$
P(E(T))=2P(E(T),\bar X\ge0)\le2P(E(cX)).
$$
For the independent p-values $p'_i=\overline\Phi(cX_i)$ with common CDF $F(t)=\overline\Phi(y/c)$, $y=\overline\Phi^{-1}(t)$: by the leave-one-out identity ($i$ rejected iff $p'_i\le qR'_i/m$ with $R'_i$ the BH count at $p'_i=0$, independent of $p'_i$, and then $R=R'_i$),
$$
P(E(cX))=\sum_i\mathbb E\!\left[\frac{F(qR'_i/m)}{R'_i}\right]\le\lambda q,\qquad \lambda=\sup_{q/m\le t\le q}\frac{F(t)}{t}.
$$
For $t\in[q/m,q]$, $y>0$ and $y^2\le2\log(m/q)$ (from $\overline\Phi(y)\le e^{-y^2/2}$). With $\delta=y(1-1/c)\le y(c^2-1)/2=y/(2(m-1))$ and the hazard $h=\varphi/\overline\Phi$ increasing with $h(y)\le y+1$ (Birnbaum's Mills-ratio bound $h(y)<(y+\sqrt{y^2+4})/2$),
$$
\log\frac{F(t)}{t}=\int_{y-\delta}^{y}h\le\delta(y+1)\le\frac{y^2+y}{2(m-1)}\le\frac{2y^2+1}{2(m-1)}\le\frac{4\log(m/q)+1}{2(m-1)}\le5,
$$
using $m\ge10$ ($\log m/(m-1)\le0.26$) and $m\ge\log(1/q)$ ($\log(1/q)/(m-1)\le10/9$). Hence $P(R>0)\le2e^5q$, so the cap holds for this family with any $A_2\ge2e^5$. Fail.

## Failure

NOT fails: the simplex global null is dominated (on the half-space $\bar X\ge0$, independent of $T$) by an independent model with variance $m/(m-1)$, whose Simes size is $O(q)$; extreme exchangeable negative correlation inflates Simes by at most a constant.
