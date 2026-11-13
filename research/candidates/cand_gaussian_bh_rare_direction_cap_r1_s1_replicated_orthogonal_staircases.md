---
type: candidate
title: One-null harmonic staircase replicated across K orthogonal rare directions
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

Fix $0<q\le q_2$, $K\ge1$, $N\ge2$, $m=KN$, $d=K$, standard basis $e_1,\dots,e_K$. Block $b\in[K]$ has one null $T_{b,0}=Z_b$ ($\theta=0$, $a=e_b$) and $N-1$ alternatives $T_{b,j}=c_j-Z_b$ ($a=-e_b$), $1\le j\le N-1$, with arbitrary means $c_j\ge2u$. The standard choice is the harmonic staircase $c_j=z_j+z_{j+1}$, $z_j=\overline\Phi^{-1}(qj/N)\ge u$ (idea_75d71c7756b4), replicated in every block; the variant $z_j=\overline\Phi^{-1}(qj/m)$ is also covered. All residuals are zero. Take $N>q^{-C_2}$.

## Checks

### H1

Unit loadings $\pm e_b$, zero residuals: a valid representation.

### H2

$I_0=\{(b,0):b\in[K]\}$ since $c_j\ge 2u>0$; one-sided p-values.

### H3

BH at level $q\le q_2$. Nothing to check.

### H4

Null directions are $e_b$. If $\cos(\kappa_2/u)>0$ the neighbourhood of $(b,0)$ is itself and $\mu=1/m$; otherwise it is all $K$ nulls and $\mu=1/N$. In both cases $\mu\le1/N<q^{C_2}$, so $I_{\mathrm{rare}}=I_0$.

### NOT

For $q\ge0.05$ the left side is at most $1\le20q$. Let $q\le0.05$. Then $\overline\Phi^{-1}(q/4)\le2u-1$ (checked numerically at $q=0.05$, where it reads $2.2414\le2.2897$, and the gap grows as $q$ decreases, since $\overline\Phi^{-1}(q/4)-u$ decreases and $u-1$ increases).

Fix $b$. Put $k_0=\lceil m/4\rceil$, $t_0=qk_0/m\ge q/4$, $x_0=\overline\Phi^{-1}(t_0)\le2u-1$. An alternative $(c,j)$ with $c\ne b$ has $p\le t_0$ iff $Z_c\le c_j-x_0$, which holds whenever $Z_c\le1$. Let $M_b=\#\{c\ne b:Z_c\le1\}\sim\mathrm{Bin}(K-1,\Phi(1))$, a function of $Z_{-b}$ only. If $(N-1)M_b\ge k_0$, then $p_{(k_0)}\le t_0$, so $R=\widehat k_q\ge k_0\ge m/4$. Let $F_b=\{(N-1)M_b<k_0\}$; then $F_b$ is independent of $Z_b$, and $F_b\subseteq\{M_b<K/2+1\}$ because $N/(N-1)\le2$.

On $F_b^c$ a rejection of $(b,0)$ forces $p_{b,0}\le q$ and $R\ge m/4$. On $F_b$ a rejection forces $p_{b,0}\le q$. Hence
$$
\mathbb E\frac{\mathbf 1\{(b,0)\in\mathcal R_q\}}{R\vee1}\le\frac{4q}{m}+q\,\mathbb P(F_b),
\qquad
\mathbb E\frac{|\mathcal R_q\cap I_{\mathrm{rare}}|}{R\vee1}\le q\Bigl(\frac4N+K\,\mathbb P(M<K/2+1)\Bigr).
$$
For $K\ge20$, Hoeffding's inequality with deviation $t=0.3413K-1.8413\ge K/4$ gives $\mathbb P\le e^{-K/8}$ and $Ke^{-K/8}\le8/e$. For $K<20$, $K\,\mathbb P\le20$. So the left side is at most $22q$. An exact binomial evaluation for $K<400$ gives $\sup_KK\,\mathbb P=3$, attained at $K=3$. Monte Carlo with 20000 replications confirms the collapse of the harmonic gain: FDR/$q$ is $0.0900$ at $(K,N)=(1,50)$ (exact value $H_{50}/50=0.0900$), $0.0227$ at $(3,50)$ and $0.0201$ at $(20,50)$, all at $q=0.05$, and $0.0055$ at $(10,200)$ with $q=0.01$. The conclusion holds with $A_2\ge22$, even in the sharper form $A_2q$.

## Failure

NOT fails: the anticorrelated staircase alternatives of every inactive block are rejected by default (means $\ge2u$), so $R\ge m/4$ with probability $1-e^{-K/8}$, and the left side is at most $22q$.
