---
type: candidate
title: A microscopic null seed among increasingly negative nulls
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
round: 2
slot: 2
direction: extremal
statement_digest: 559f931c8cf870c13d2afe6f41bae6c492b9b6e20edb09e35b2275ac15e3ed5d
performed_by: unknown
created_at: '2026-11-09T05:17:48.165Z'
extension_version: 0.0.4
---

## Object

Fix any $q\in(0,1/2)$ and $\sigma\in(0,1)$. For each integer $m\ge2$, set $N=m^2$, $d=1$, $v_i=1$ for every $i$, and $\varepsilon=1/N$. Write $u_q(r)=S^{-1}(qr)$ and set
$$
M_m=u_q(\varepsilon)-u_q(1)+m>0,
\qquad \theta_1=0,\qquad \theta_i=-M_m\quad(2\le i\le N).
$$
Every tag equals one. For independent standard normal $G,Z$, put $U=\sqrt{1-\sigma^2}G+\sigma Z$. Thus the active score is $U$ and all other scores are $U-M_m$. Sample the original indices independently and uniformly, and let $K$ count sampled copies of index one. Then $K\sim\operatorname{Binomial}(m,\varepsilon)$ independently of $U$.

This is a two-score family, with a vanishing full-model positive rank and typically no sampled copy of the active score. It differs from the board's one-score families.

## Checks

### H1

Pass. Both $q$ and $\sigma$ are fixed strictly inside their required intervals as $m$ varies.

### H2

Pass. $N=m^2$ and $d=1$ are positive integers; all directions are deterministic unit vectors. Their singular residual Gram matrix is permitted.

### H3

Pass. All means are nonpositive and all tags equal one. There are no alternative-tagged points.

### H4

Pass. The scores have exactly the stipulated representation with independent standard Gaussian $G,Z$. The common variable $U$ is standard normal.

### H5

Pass. The index draws are iid uniform on $[N]$ and independent of both Gaussian variables.

### H6

Pass. Repeated sampled indices use the same original score; no fresh noise is introduced.

### H7

Pass. Use ordinary largest non-strict BH and all-true tagged FDP. Put
$$
A=u_q(\varepsilon),\qquad B=A+m=M_m+u_q(1),\qquad b=S(B),\qquad P_0=(1-\varepsilon)^m.
$$
Here $0<b<q\varepsilon$. All weak scores can be rejected only when their common p-value is at most $q$, equivalently $U\ge B$; on this event the actual rank is one in both laws. Otherwise only the active copies can be rejected. Consequently,
$$
\rho_N=\varepsilon\mathbf1_{\{A\le U<B\}}+\mathbf1_{\{U\ge B\}}.
$$
Conditional on $K=0$, $\rho_m=\mathbf1_{\{U\ge B\}}$. Conditional on $K\ge1$, writing $X=K/m\ge\varepsilon$,
$$
\rho_m=X\mathbf1_{\{u_q(X)\le U<B\}}+\mathbf1_{\{U\ge B\}}.
$$
The same expressions include $K=m$. Since all tags are true, $D_N=\mathbf1_{\{U\ge A\}}$; for $K=0$, $D_m=\mathbf1_{\{U\ge B\}}$, and for $K\ge1$, $D_m=\mathbf1_{\{U\ge u_q(X)\}}$. Equality at any displayed threshold follows the required non-strict convention.

### NOT

Fail. The error of this extremal family vanishes explicitly. For $K=0$, the conditional expected FDP difference is $q\varepsilon-b$; for $K\ge1$ it is $qX-q\varepsilon$. Since $\mathbb EX=\varepsilon$,
$$
\mathbb E|D_m-D_N|=P_0(2q\varepsilon-b)\le2q\varepsilon.
$$
For $K=0$, the conditional expected rank difference is $\varepsilon(q\varepsilon-b)$. For $K\ge1$, it is
$$
X(qX-q\varepsilon)+(X-\varepsilon)(q\varepsilon-b)
=qX^2-q\varepsilon^2-b(X-\varepsilon).
$$
Using $\operatorname{Var}(X)=\varepsilon(1-\varepsilon)/m$ gives the exact identity
$$
\mathbb E|\rho_m-\rho_N|
=\frac{q\varepsilon(1-\varepsilon)}m
+2\varepsilon P_0(q\varepsilon-b).
$$
Thus
$$
\mathbb E\bigl[|D_m-D_N|+|\rho_m-\rho_N|\bigr]
\le\frac{2q}{m^2}+\frac{q}{m^3}+\frac{2q}{m^4}\longrightarrow0.
$$
This is also uniform in $q\in(0,1/2)$. Losing the sole active index usually does not create a persistent FDP discrepancy: its full-model rejection probability is only $q/N$. The calculation rejects this family as a counterexample and does not prove the general compression statement.

## Failure

NOT fails: both discrepancies vanish despite a microscopic rank and a sampling probability tending to zero for the sole active index.
