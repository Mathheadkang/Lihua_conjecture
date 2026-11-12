---
type: candidate
title: Vanishing mass at diverging alternative means with perfectly shared residuals
status: failed
target_asset: gaussian_bh_common_loading_wasserstein_fdr_continuity
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
statement_digest: c7c3378df201906f905a39cc98232cebf031e1b6084f86c0a75c836910b8f564
performed_by: unknown
created_at: '2026-11-09T00:42:21.565Z'
extension_version: 0.0.4
---

## Object

Fix $q=1/4$, $\sigma=1/2$, $\mathcal H=\mathbb R$, and the unit direction $v=1$. Let $\xi,Z$ be independent standard normals and put $G=\sqrt{3}\xi/2+Z/2$. For every positive integer $n$, set
$$
\varepsilon_n=(n+1)^{-2},\qquad M_n=n+1,\qquad
\pi=\delta_{(0,1,1)},\qquad
\pi_n=(1-\varepsilon_n)\delta_{(0,1,1)}+\varepsilon_n\delta_{(M_n,1,0)}.
$$
The alternative means diverge while their mass and contribution to the first moment vanish. The two scores share their entire residual and common Gaussian noise; hence their finite-array covariance is singular. This object tests whether a vanishing, increasingly strong alternative component produces a discontinuous full FDR or a false-discovery contribution at microscopic ranks.

## Checks

### H1

Pass: the fixed testing level $q=1/4$ lies in $(0,1/2)$.

### H2

Pass: the fixed loading $\sigma=1/2$ lies in $(0,1)$, with $\tau=\sqrt{3}/2$.

### H3

Pass: $\mathcal H=\mathbb R$ is nonzero and separable; every residual direction equals the unit vector $1$.

### H4

Pass: all laws are deterministic Borel laws with lawful tags. The only true-null mean is zero and the alternative mean $M_n$ is strictly positive. The first moments are
$$
\int|\theta|\,d\pi=0,\qquad
\int|\theta|\,d\pi_n=\varepsilon_n M_n=(n+1)^{-1}<\infty.
$$

### H5

Pass: the specified one-dimensional series gives $X(1)=\xi$. The scores are exactly $G$ for the true atom and $M_n+G$ for the alternative atom, with unit marginal variance and the required independent common $Z$. All ranks and numerators below use the actual largest non-strict crossing and the original full mixed-label FDP.

### H6

Pass: since the second marginal is the point mass $\pi$, the coupling is unique and
$$
W_1(\pi_n,\pi)=\varepsilon_n(M_n+1)=(n+1)^{-1}+(n+1)^{-2}\longrightarrow0.
$$

### NOT

Fail: the full FDR converges, with an exact formula. Write $b(t)=S^{-1}(t)$. Since the alternative score strictly exceeds the true score, the only possible positive largest ranks are $\varepsilon_n$ and $1$. In detail,
$$
\rho_{\pi_n}=
\begin{cases}
1,&G\ge b(q),\\
\varepsilon_n,&G<b(q)\ \text{and}\ G+M_n\ge b(q\varepsilon_n),\\
0,&\text{otherwise}.
\end{cases}
$$
To check exhaustiveness, if $G\ge b(q)$ both atoms qualify at rank one. Otherwise the true atom has $p>q$ and therefore cannot qualify at any $r\le1$; the count is either zero or $\varepsilon_n$, whose largest possible qualifying rank is exactly $\varepsilon_n$.

At rank one the true-tag numerator is $1-\varepsilon_n$; at the positive microscopic rank only the alternative atom is rejected, so the numerator is zero. Consequently,
$$
D_{\pi_n}=(1-\varepsilon_n)\mathbf1_{\{G\ge b(q)\}},\qquad
F_{\pi_n}=(1-\varepsilon_n)q.
$$
For the limit law, $D_\pi=\mathbf1_{\{G\ge b(q)\}}$ and $F_\pi=q$. Thus
$$
|F_{\pi_n}-F_\pi|=q\varepsilon_n\longrightarrow0.
$$
Moreover, for every $a\in(0,1)$, the microscopic-rank false-discovery contribution is exactly zero for every $n$:
$$
\mathbb E[D_{\pi_n}\mathbf1_{\{0<\rho_{\pi_n}\le a\}}]=0.
$$

## Failure

NOT fails: the FDR difference equals $q\varepsilon_n$ and vanishes, while microscopic ranks reject only alternatives.
