---
type: candidate
title: >-
  Zero-radius identical null clumps against a weak-alternative fog, read as
  separated rare clusters
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

The construction of [the clump-bracket counterexample](../assets/cx_gaussian_bh_subexponential_rare_clump_bracket_cap_r1_s1_identical_clumps_weak_fog.md), unchanged: given the constants $(\kappa_2,C_2,A_2,q_2)$ asserted by the cap, take $q\le\min(q_2,\overline\Phi(e))$, so $u\ge e>1\ge\kappa_2$; integers $X\ge2$, $k=10^4X^3$, $M=kX$; $L$ clumps $K_1,\dots,K_L$ of $k$ coordinates each, $\theta_i=0$ and $w_i=e_l$ for $i\in K_l$; $n=3kL$ alternatives $a$ with private directions $e_a$ and common mean $\vartheta>0$ fixed by $n\overline\Phi(y_M-\vartheta)=M-k/2$, $y_M=\overline\Phi^{-1}(qM/m)$; $m=4kL$, $d=L+n$. Choose $L$ so large that, besides the conditions of that example, $1/(4L)<q^{C_2}$.

Separated partition: $H=L$, $G_l=K_l$, $v_l=e_l$. (Variant: split each $K_l$ into arbitrary sub-clusters with off-loading centres $v=\cos\phi\,e_l+\sin\phi\,f$, $f$ fresh orthonormal directions, $2-2\cos\phi=(\kappa_2/u)^2$; see H5.)

## Checks

### H1

$m,d$ positive integers, $\theta\in\mathbb R^m$, every $w_i$ is a standard basis vector, hence a unit vector; $T=\theta+WZ$ is the unit-loading multifactor model with $\Sigma=WW^{\mathsf T}$ (entries in $\{0,1\}$, singular). Pass.

### H2

$0<q\le q_2<1/2$. Pass.

### H3

$I_0=\{i:\theta_i\le0\}=\bigcup_lK_l$ (alternatives have $\vartheta>0$). The $K_l$ are nonempty and partition $I_0$; each $v_l=e_l$ is a unit vector. Pass.

### H4

$\|w_i-v_l\|=0\le\kappa_2/u$ for $i\in K_l$. Pass.

### H5

$\|v_l-v_{l'}\|=\sqrt2>1\ge\kappa_2/u$ for $l\ne l'$. Pass. (Variant: for centres $v=\cos\phi\,w+\sin\phi\,f$, $v'=\cos\phi\,w'+\sin\phi\,f'$ with $f\perp f'$ both orthogonal to all loadings, $\|v-v'\|^2=2-2\cos^2\phi\,w^{\mathsf T}w'$, which exceeds $2-2\cos\phi=(\kappa_2/u)^2$ because $w^{\mathsf T}w'\le1<1/\cos\phi$; so even identical loadings can sit in different clusters.)

### NOT

All $\pi_l=k/m=1/(4L)<q^{C_2}$, so every cluster is rare and the left side is the whole FDR $\mathbb E[V/(R\vee1)]=\sum_l\mathbb E[V_l/(R\vee1)]$. This is computed exactly, clump by clump.

Fix $l$ and write $s_l=\overline\Phi(Z_l)$ for the common p-value of $K_l$; $s_l\sim U(0,1)$ is independent of all other coordinates. Let $p'$ be $p$ with the $k$ coordinates of $K_l$ set to $0$, and $R_*^l=\widehat k_q(p')$, a function of the other coordinates only. Claim: $K_l\subseteq\mathcal R_q(p)$ iff $s_l\le qR_*^l/m$, and then $R=R_*^l$.
- If $s_l\le q\widehat k_q(p)/m$, then for every $r\ge\widehat k_q(p)$ the counts $\#\{j:p_j\le qr/m\}$ and $\#\{j:p'_j\le qr/m\}$ agree, so $\widehat k_q(p')=\widehat k_q(p)$.
- If $s_l\le q\widehat k_q(p')/m$, then at $r=\widehat k_q(p')$ the two counts agree, so $\widehat k_q(p)\ge\widehat k_q(p')$ and $K_l$ is rejected.
Since $R=\widehat k_q$ for this BH definition, and $qR_*^l/m\le q<1$,
$$
\mathbb E\!\left[\frac{V_l}{R\vee1}\right]=\mathbb E\!\left[\frac{k\,\mathbf 1\{s_l\le qR_*^l/m\}}{R_*^l}\right]=\frac{qk}{m}.
$$
Summing over $l$: the left side of the cap equals $Lqk/m=q/4$ exactly, for every $X$, $L$, $\vartheta$. With any sub-clustering (variant) the left side is still the full FDR $q/4$. So the conclusion holds with any $A_2\ge1/4$. Fail.

## Failure

NOT fails: the clump-bracket charge carried a spurious $\log(R_*/\max(R_0,k))$ term, but the actual BH null share of a clump of identical, mutually independent null blocks is exactly $qk/m$, so the whole null FDR is $q/4\le A_2q(1+u)$.
