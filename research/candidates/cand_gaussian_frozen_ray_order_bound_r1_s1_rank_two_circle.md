---
type: candidate
title: >-
  Singular rank-two correlation with equally spaced directions on a circle,
  uniform weights
status: failed
target_asset: gaussian_frozen_ray_order_bound
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
statement_digest: 282dae85ea4644795f6594864fde635d6b47cfbb089d6aaaa5923db5d8b578ac
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T04:30:23.002Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

The next degenerate rank after rank one, chosen to defeat the union bound of the rank-one candidate (many hypotheses, $n\gg c$). Let $g\sim\mathcal N_2(0,I_2)$, write $g=r(\cos\phi,\sin\phi)$, and for $n\geq1$ put $\theta_j=2\pi j/n$, $a_j=(\cos\theta_j,\sin\theta_j)$, $Z_j=\langle a_j,g\rangle=r\cos(\phi-\theta_j)$, $\omega_j=1/n$. Then $\Sigma_{jk}=\cos(\theta_j-\theta_k)$, rank two for $n\geq3$. Level $c\geq2$ arbitrary; the interesting regime is $n>c$.

## Checks

### H1

$n\geq1$.

### H2

$\Sigma=AA^{\mathsf T}$ with rows $a_j$ of unit length: symmetric, PSD, unit diagonal, singular for $n\geq3$; $Z=Ag\sim\mathcal N_n(0,\Sigma)$.

### H3

$\omega_j=1/n\geq0$, total mass $1$.

### H4

$c\geq2$.

### NOT

Fails. For $n\leq c$ the general bound of the rank-one candidate gives $\mathbb E\min\{c,\Lambda\}\leq1+\pi^{-1/2}(\sqrt{\log c}+\sqrt{\log c})$. Let $n>c$.

Riemann-sum step: $f(\theta)=e^{x\cos\theta}$ ($x=wr\geq0$) is even, unimodal on the circle. For equally spaced points with gap $h=2\pi/n$, each point $\theta$ with $h\leq|\theta-\phi|\leq\pi$ satisfies $f\leq h^{-1}\int$ of $f$ over the gap on its side nearer the mode; these gaps are disjoint, and at most two points lie within $h$ of the mode. Hence
$$
L_w=\frac1n\sum_je^{wr\cos(\phi-\theta_j)-w^2/2}\leq I_0(wr)e^{-w^2/2}+\frac2ne^{wr-w^2/2}.
$$
Use $I_0(x)\leq C_0e^x/\sqrt{1+x}$ (universal $C_0$; $I_0(x)\sim e^x/\sqrt{2\pi x}$) and $wr-w^2/2=r^2/2-(w-r)^2/2$. If $|w-r|\geq r/2$ the first term is at most $C_0e^{3r^2/8}$; otherwise $wr\geq r^2/2$ and it is at most $C_0e^{r^2/2}/\sqrt{1+r^2/2}$. So
$$
\Lambda\leq C_1\frac{e^{r^2/2}}{1+r}+\frac2ne^{r^2/2},
$$
with universal $C_1$. Since $r^2/2\sim\mathrm{Exp}(1)$, $P(e^{r^2/2}>s)=\min(1,1/s)$.

Second term: $\mathbb E\min\{c,\tfrac2ne^{r^2/2}\}=\int_0^c\min(1,\tfrac2{nt})dt\leq\tfrac2n(1+\log(nc/2))\leq\tfrac2n(1+2\log n)\leq 4$ for $n>c\geq2$.

First term: for $t\geq eC_1$, $C_1e^{r^2/2}/(1+r)>t$ forces $r\geq\rho_t=\sqrt{2\log(t/C_1)}$ and $e^{r^2/2}>(t/C_1)(1+\rho_t)$, so $P\leq C_1/(t(1+\rho_t))$, and $\int_{eC_1}^c\frac{C_1\,dt}{t\sqrt{2\log(t/C_1)}}\leq C_1\sqrt{2\log c}$. Hence $\mathbb E\min\{c,\Lambda\}\leq eC_1+C_1\sqrt{2\log c}+4\leq C\sqrt{\log c}$, uniformly in $n$.

Mechanism: angular spreading costs exactly the factor $(1+r)^{-1}$ (Laplace width $r^{-1/2}$ of the cap, times the prefactor $r^{-1/2}$ of $I_0$), which converts the $\chi^2_2$ tail $1/s$ back into the one-dimensional tail $1/(s\sqrt{\log s})$. The same Laplace count on $S^{k-1}$ with uniform weights gives $\Lambda\lesssim e^{r^2/2}r^{-(k-1)}$ against $P(r>\rho)\asymp\rho^{k-2}e^{-\rho^2/2}$, again tail $\asymp1/(s\sqrt{\log s})$, though with $k$-dependent constants that were not tracked.

## Failure

NOT fails: for $n\leq c$ the union bound applies, and for $n>c$ the Riemann-sum comparison with $I_0(wr)e^{-w^2/2}$ gives $\Lambda\lesssim e^{r^2/2}/(1+r)+\tfrac2ne^{r^2/2}$, whose truncated mean is $O(\sqrt{\log c})$ uniformly in $n$.
