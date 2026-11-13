---
type: candidate
title: Global-null simplex frame with singleton clumps (Simes reduction of the cap)
status: failed
target_asset: gaussian_bh_subexponential_rare_clump_bracket_cap
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
statement_digest: d66c527595f7967458383519a22868df0977fdbc6933b1f63f69cb380debf465
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T06:53:04.402Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

# Global-null simplex frame with singleton clumps

## Object

$q\le\overline\Phi(e)$, $u=\overline\Phi^{-1}(q)$, $m\ge e^u$ large, $d=m$, $\theta=0$, and the simplex frame $w_i=c(e_i-\tfrac1m\mathbf 1)$ with $c=\sqrt{m/(m-1)}$, so $\Sigma_{ij}=-1/(m-1)$ for $i\ne j$ (the most negative exchangeable correlation). $S=[m]$, singleton clumps $K_i=\{i\}$, $c_i=i$.

## Checks

### H1
Unit vectors, $u\ge e>1$. Pass.

### H2
$\theta_i=0\in(-a_q,0]$. Pass.

### H3
Singletons partition $S$. Pass.

### H4
Radius $0$. Pass.

### H5
$\|w_i-w_j\|^2=2+2/(m-1)>\kappa^2/u^2$ for $i\ne j$, so each neighbourhood count is $1\le e^{-u}m$. Pass.

### NOT

**Singleton reduction (holds for every singleton system).** With $K_l=\{i\}$: $R_{i,0}=R_{i,*}$ is BH with $p_i\to0$, $D_i=1$. Then $p_i\le qR_{i,0}/m$ iff $i\in\mathcal R$, and in that case $R=R_{i,0}\ge mp_i/q$. So $\Psi_i=\mathbf 1\{i\in\mathcal R\}/R$ and
$$
\sum_{i\in S}\Psi_i=\frac{|\mathcal R\cap S|}{R\vee1}.
$$
In the global null with $S=[m]$ this is $\mathbf 1\{R>0\}$, so the cap contains the global-null Gaussian Simes bound $P(R>0)\le A_3q(1+u)$ for every neighbourhood-sparse direction set (each $\kappa/u$-ball holding at most $e^{-u}m$ directions), negative correlations included. That is the global-null case of the project's main order bound, and it is weaker than the draft $Cq$ Simes lemma.

**This object.** $T_i=c(Z_i-\bar Z)$ with $Z_i$ iid. On $\{|\bar Z|\le\eta\}$, $\eta=m^{-1/3}$, $T_i\ge t_k:=\overline\Phi^{-1}(qk/m)$ implies $Z_i\ge t_k/c-\eta$. Then $\alpha_k:=\overline\Phi(t_k/c-\eta)\le (qk/m)e^{\delta_k(t_k+\delta_k)}$ with $\delta_k=\eta+t_k(1-1/c)\le\eta+t_k/m$ and $t_k\le\sqrt{2\log(m/q)}$, so $\alpha_k\le(1+\epsilon_m)qk/m$ with $\epsilon_m\to0$. Simes for iid uniforms at level $q'$ has size exactly $q'$, so
$$
P(R>0)\le(1+\epsilon_m)q+P(|\bar Z|>m^{-1/3})\le(1+\epsilon_m)q+2e^{-m^{1/3}/2},
$$
which is $\le 2q\le A_3q(1+u)$ for large $m$ whenever $A_3\ge1/2$. Fail.

## Failure

NOT fails: with singleton clumps the charge is $|\mathcal R\cap S|/(R\vee1)$, and the simplex frame's negative correlation $-1/(m-1)$ is too weak to move Simes size off $q(1+o(1))$.
