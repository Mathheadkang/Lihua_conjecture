---
type: lemma
title: >-
  Angular-cluster entropy bound for one-sided Gaussian BH with free truncation
  levels
status: approved
source:
  kind: original
depends_on:
  - lei2026_conditional_fdp_bound
  - lei2026_integrated_conditional_tail_ratios
related_assets:
  - directional_entropy_one_sided_fdr_bound
uses_definitions:
  - gaussian_multifactor_representation
  - gaussian_null_loading_coefficients
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags:
  - parallel-round-20261112
  - route-1
---

## Statement

Take any [Gaussian multifactor representation](../definitions/gaussian_multifactor_representation.md)
$T_i=\theta_i+a_i^{\mathsf T}Z+\sqrt{1-\|a_i\|^2}\,\varepsilon_i$, $1\le i\le m$, with any factor dimension $d$. Use the one-sided [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md) $p_i=\overline\Phi(T_i)$, $I_0=\{i:\theta_i\le0\}$, and the [Gaussian null loading coefficients](../definitions/gaussian_null_loading_coefficients.md) $r_i=\|a_i\|$, $\gamma_i=\sqrt{(1-r_i)/(1+r_i)}$. Run the [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md) at level $0<q<1/2$, with its largest qualifying rank and non-strict comparisons; let $\mathcal R_q$ be its rejection set and $R=|\mathcal R_q|$. Put $u=\overline\Phi^{-1}(q)$.

Fix $\kappa\ge0$. Let $I_*\subseteq I_0$ be partitioned into nonempty sets $C_1,\ldots,C_J$, and let $v_1,\ldots,v_J\in\mathbb R^d$ be unit vectors and $\beta_1,\ldots,\beta_J\ge u$ real levels. Suppose that for every $j$ and every $i\in C_j$ with $r_i>0$, the cosine $\rho_i=a_i^{\mathsf T}v_j/r_i$ satisfies
$$
\rho_i\ge\tfrac12,
\qquad
\beta_j\sqrt{1-\rho_i^2}\le\kappa .
$$
No condition is imposed on members with $r_i=0$. Put $\pi_j=|C_j|/m$. Then, in the sense of the [false discovery rate](../definitions/false_discovery_rate.md) contributions of the same unmodified procedure,
$$
\mathbb E\!\left[\frac{|\mathcal R_q\cap I_*|}{R\vee1}\right]
\le\sum_{j=1}^J\left[q\pi_j\left(\frac32+A_1(\kappa)+\log\frac{q}{\overline\Phi(\beta_j)}\right)+\overline\Phi(\beta_j)\right]
+\frac{qu}{\sqrt{2\pi}}\,\frac1m\sum_{i\in I_*}\gamma_i ,
$$
where $A_1:[0,\infty)\to[0,\infty)$ is a finite nondecreasing function of $\kappa$ alone, independent of $m$, $d$, $J$, the means, the loadings, the vectors $v_j$, the levels $\beta_j$ and $q$.

All true-null means $\theta_i\le0$, arbitrary alternative means and loadings, singular covariance and the endpoint loadings $r_i\in\{0,1\}$ are allowed. With $\rho_i=1$ for all members and $\beta_j=\overline\Phi^{-1}(q\pi_j)$ the right side has the form of the approved [oriented directional-entropy bound](directional_entropy_one_sided_fdr_bound.md) restricted to $I_*$, with the extra constant $A_1(0)$. This lemma asserts no universal order bound by itself.

## Proof

We prove the inequality with the explicit choice
$$
A_1(\kappa)=A^*(\kappa):=2(\kappa+1)\bigl(\kappa\Phi(\kappa)+\phi(\kappa)\bigr)+2\bigl((\kappa^2+1)\Phi(\kappa)+\kappa\phi(\kappa)\bigr),
$$
where $\phi(y)=(2\pi)^{-1/2}e^{-y^2/2}$ and $\Phi=1-\overline\Phi$ are the standard normal density and distribution function. The argument adapts the proof of the approved [oriented directional-entropy bound](directional_entropy_one_sided_fdr_bound.md); the new ingredient is that each null is evaluated along its own direction while each cluster is truncated along the cluster direction, which leaves one off-strip integral.

**Step 1 (partial FDPs and reduction).** Since $0<q<1/2$, $u=\overline\Phi^{-1}(q)>0$, and every $\beta_j\ge u>0$, so $\overline\Phi(\beta_j)\le q$ and $\log(q/\overline\Phi(\beta_j))\ge0$. If $I_*=\varnothing$ then $J=0$ and both sides are zero. Otherwise put
$$
W_j=v_j^{\mathsf T}Z\sim\mathcal N(0,1),\qquad
\operatorname{FDP}_j=\frac{|\mathcal R_q\cap C_j|}{R\vee1},\qquad 1\le j\le J .
$$
Then $0\le\operatorname{FDP}_j\le1$ and $|\mathcal R_q\cap I_*|/(R\vee1)=\sum_j\operatorname{FDP}_j$, because the $C_j$ partition $I_*$. No relation between different $W_j$ is used. We shall prove, for each $j$,
$$
\mathbb E[\operatorname{FDP}_j]\le\overline\Phi(\beta_j)+\frac qm\sum_{i\in C_j}\Bigl(\frac12+\frac{\gamma_iu}{\sqrt{2\pi}}+\log\frac{q}{\overline\Phi(\beta_j)}+A^*(\kappa)\Bigr).
\tag{1}
$$
Summing (1) over $j$ and using $|C_j|/m=\pi_j$ gives
$$
\mathbb E\!\left[\frac{|\mathcal R_q\cap I_*|}{R\vee1}\right]\le\sum_{j=1}^J\left[q\pi_j\Bigl(\frac12+A^*(\kappa)+\log\frac q{\overline\Phi(\beta_j)}\Bigr)+\overline\Phi(\beta_j)\right]+\frac{qu}{\sqrt{2\pi}}\frac1m\sum_{i\in I_*}\gamma_i,
$$
which is at most the stated right side since $\frac12\le\frac32$. Fix $j$ for Steps 2-6.

**Step 2 (cluster split and leave-one-out bound).** On $\{W_j>\beta_j\}$ we use $\operatorname{FDP}_j\le1$:
$$
\mathbb E[\operatorname{FDP}_j\mathbf1\{W_j>\beta_j\}]\le\mathbb P(W_j>\beta_j)=\overline\Phi(\beta_j).
$$
For the complementary event we reproduce the leave-one-out argument of the [Lei conditional leave-one-out FDP bound](lei2026_conditional_fdp_bound.md). For a fixed p-value vector, the BH rejection count $R$ equals the largest qualifying rank $\widehat k_q$: if more than $\widehat k_q$ coordinates were at most $q\widehat k_q/m$, their number would be a larger qualifying rank. Let $R_i$ be the rejection count after replacing $p_i$ by $0$. Then $1\le R_i\le m$, $R_i$ is a function of $(p_k)_{k\ne i}$ alone, and $R_i\ge R$ since lowering one p-value cannot lower any order statistic's qualifying status.

If $i\in\mathcal R_q$, then $R\ge1$ and $p_i\le qR/m$. Suppose $k=R_i>R$. The modified vector has at least $k$ coordinates at most $qk/m$; restoring $p_i$ keeps this, since $p_i\le qR/m\le qk/m$, so $k$ would qualify for the original vector, contradicting maximality of $R$. Hence $R_i=R$. Conversely, if $p_i\le qR_i/m$, then restoring $p_i$ in the modified vector keeps at least $R_i$ values at most $qR_i/m$, so $R\ge R_i$, whence $R=R_i\ge1$ and $i\in\mathcal R_q$. This proves, pointwise and including all threshold ties and the case $R=0$,
$$
\frac{\mathbf1\{i\in\mathcal R_q\}}{R\vee1}=\frac{\mathbf1\{p_i\le qR_i/m\}}{R_i}.
$$

Let $F_{i,Z}$ be the conditional distribution function of $p_i$ given the full vector $Z$. By the [Gaussian multifactor representation](../definitions/gaussian_multifactor_representation.md), the p-values are independent conditional on $Z$ (a coordinate with $r_i=1$ is conditionally deterministic, which is still independent of the others). Hence $p_i$ and $R_i$ are conditionally independent given $Z$, and almost surely
$$
\mathbb E\!\left(\left.\frac{\mathbf1\{i\in\mathcal R_q\}}{R\vee1}\right|Z\right)
=\frac qm\,\mathbb E\!\left(\left.\frac{F_{i,Z}(qR_i/m)}{qR_i/m}\right|Z\right)\le\frac qm\,G_i,
\qquad G_i=\sup_{0<t\le q}\frac{F_{i,Z}(t)}{t},
$$
because $0<qR_i/m\le q$. Summing over $i\in C_j$ only, multiplying by the $Z$-measurable indicator $\mathbf1\{W_j\le\beta_j\}$ and taking expectations,
$$
\mathbb E[\operatorname{FDP}_j\mathbf1\{W_j\le\beta_j\}]\le\frac qm\sum_{i\in C_j}\mathbb E\bigl[G_i\mathbf1\{W_j\le\beta_j\}\bigr].
\tag{2}
$$
All other nulls and all alternatives enter only through $R_i$, over which the supremum $G_i$ has been taken.

**Step 3 (reduction of each null to a scalar factor).** For $r\in[0,1]$, $y,\theta\in\mathbb R$ and $0<t<1$ put
$$
F^\theta_{r,y}(t)=\mathbb P\bigl\{\theta+ry+\sqrt{1-r^2}\,\varepsilon\ge\overline\Phi^{-1}(t)\bigr\},\quad \varepsilon\sim\mathcal N(0,1),
\qquad
M_i(y)=\sup_{0<t\le q}\frac{F^{\theta_i}_{r_i,y}(t)}t,\quad M^0_r(y)=\sup_{0<t\le q}\frac{F^0_{r,y}(t)}t .
$$
For fixed $y$ these CDFs are right-continuous in $t$, so each supremum equals the supremum over $(\mathbb Q\cap(0,q))\cup\{q\}$, and $M_i$, $M^0_r$ are Borel functions of $y$ (also at $r=1$, where $F^0_{1,y}(t)=\mathbf1\{\overline\Phi(y)\le t\}$).

*Members with $r_i>0$.* Put $Y_i=a_i^{\mathsf T}Z/r_i$; since $\|a_i/r_i\|=1$, $Y_i\sim\mathcal N(0,1)$, and $T_i=\theta_i+r_iY_i+\sqrt{1-r_i^2}\,\varepsilon_i$ with $\varepsilon_i$ independent of $Z$. As $p_i\le t$ iff $T_i\ge\overline\Phi^{-1}(t)$, we get $F_{i,Z}(t)=F^{\theta_i}_{r_i,Y_i}(t)$ and $G_i=M_i(Y_i)$. Because $\theta_i\le0$, the event defining $F^{\theta_i}_{r_i,y}(t)$ is contained in that defining $F^0_{r_i,y}(t)$, so $F^{\theta_i}_{r_i,y}\le F^0_{r_i,y}$ and $M_i\le M^0_{r_i}$, including $r_i=1$. The function $F^0_{r,y}(t)$ is exactly the conditional CDF $F^{(1)}_{r,y}(t)$ of $\overline\Phi(X)$ given the scalar factor value $y$ in the one-sided part of the [Lei integrated conditional Gaussian tail-ratio bounds](lei2026_integrated_conditional_tail_ratios.md), with $X=rY+\sqrt{1-r^2}\varepsilon$ for independent standard normal $Y,\varepsilon$. That lemma is a statement about a function of one real variable integrated against $\phi$; its hypotheses are $0<q<1/2$ and $r\in[0,1]$, both satisfied, and the ambient dimension $d$ plays no role. Hence
$$
\int_{-\infty}^u\phi(y)M_i(y)\,dy\le\int_{-\infty}^u\phi(y)M^0_{r_i}(y)\,dy\le\frac12+\frac{\gamma_iu}{\sqrt{2\pi}},
\tag{3}
$$
with the endpoint $r_i=1$ ($\gamma_i=0$, central integral zero) included as stated there.

*Members with $r_i=0$.* Then $F_{i,Z}(t)=\mathbb P(\theta_i+\varepsilon_i\ge\overline\Phi^{-1}(t))\le\mathbb P(\varepsilon_i\ge\overline\Phi^{-1}(t))=t$, so $G_i\le1$ and $\mathbb E[G_i\mathbf1\{W_j\le\beta_j\}]\le1$. By Step 7 below, $A^*(\kappa)\ge A^*(0)=\sqrt{2/\pi}+1>1$, so, with $\gamma_i=1$,
$$
\mathbb E[G_i\mathbf1\{W_j\le\beta_j\}]\le\frac12+\frac{\gamma_iu}{\sqrt{2\pi}}+\log\frac q{\overline\Phi(\beta_j)}+A^*(\kappa).
$$
No angular condition is used for these members.

**Step 4 (three-region split for $r_i>0$).** First, the outer-strip envelope, as in the approved proof: for fixed $r\in[0,1]$ and $0<t\le q$, $y\mapsto F^0_{r,y}(t)$ is nondecreasing since $r\ge0$, and $\int_{-\infty}^\infty\phi(z)F^0_{r,z}(t)\,dz=\mathbb P\{rY+\sqrt{1-r^2}\varepsilon\ge\overline\Phi^{-1}(t)\}=t$, because $rY+\sqrt{1-r^2}\varepsilon$ is standard normal (also at $r\in\{0,1\}$). Therefore, for every finite $y$,
$$
\overline\Phi(y)F^0_{r,y}(t)\le\int_y^\infty\phi(z)F^0_{r,z}(t)\,dz\le t,
\qquad\text{so}\qquad M_i(y)\le M^0_{r_i}(y)\le\frac1{\overline\Phi(y)} .
$$
Now split $\mathbb E[M_i(Y_i)\mathbf1\{W_j\le\beta_j\}]$ according to $Y_i\le u$, $u<Y_i\le\beta_j$, $Y_i>\beta_j$. In the first two regions drop the indicator of $\{W_j\le\beta_j\}$ (the integrand is nonnegative). The first region contributes at most (3). The second contributes at most
$$
\int_u^{\beta_j}\frac{\phi(y)}{\overline\Phi(y)}\,dy=\Bigl[-\log\overline\Phi(y)\Bigr]_u^{\beta_j}=\log\frac{q}{\overline\Phi(\beta_j)},
$$
using $\overline\Phi(u)=q$; it is zero when $\beta_j=u$.

For the third region, $Y_i$ and $W_j$ are linear functions of $Z\sim\mathcal N_d(0,I_d)$ with unit variances and covariance $a_i^{\mathsf T}v_j/r_i=\rho_i$; by Cauchy-Schwarz and the hypothesis, $\tfrac12\le\rho_i\le1$. Put $\sigma_i=\sqrt{1-\rho_i^2}\in[0,\sqrt3/2]$. The variable $W_j-\rho_iY_i$ is a linear function of $Z$, uncorrelated with $Y_i$, hence independent of $Y_i$ by joint Gaussianity, with variance $\sigma_i^2$. If $\rho_i=1$, then $W_j=Y_i$ almost surely and $\mathbf1\{Y_i>\beta_j\}\mathbf1\{W_j\le\beta_j\}=0$ a.s., so the third region contributes $0$. If $\rho_i<1$, then $\sigma_i>0$ and by independence and Fubini
$$
\mathbb E\bigl[M_i(Y_i)\mathbf1\{Y_i>\beta_j,\ W_j\le\beta_j\}\bigr]
=\int_{\beta_j}^\infty\phi(y)M_i(y)\,\Phi\!\Bigl(\frac{\beta_j-\rho_iy}{\sigma_i}\Bigr)dy
\le\int_{\beta_j}^\infty\frac{\phi(y)}{\overline\Phi(y)}\,\Phi\!\Bigl(\frac{\beta_j-\rho_iy}{\sigma_i}\Bigr)dy=:\mathrm{OS}_i .
$$
Consequently, for every $i\in C_j$ with $r_i>0$,
$$
\mathbb E[G_i\mathbf1\{W_j\le\beta_j\}]\le\frac12+\frac{\gamma_iu}{\sqrt{2\pi}}+\log\frac q{\overline\Phi(\beta_j)}+\mathrm{OS}_i,
\tag{4}
$$
with $\mathrm{OS}_i:=0$ when $\rho_i=1$.

**Step 5 (hazard inequality).** We show $\phi(y)\le(y+1)\overline\Phi(y)$ for all $y\ge0$. First, for $y>0$ (Gordon's bound),
$$
\overline\Phi(y)=\int_y^\infty\phi(x)\,dx<\int_y^\infty\frac xy\,\phi(x)\,dx=\frac{\phi(y)}y ,
$$
strictly since $x/y>1$ for $x>y$ and $\phi>0$. Let $\mu(y)=\overline\Phi(y)/\phi(y)$ (the Mills ratio). Using $\phi'(y)=-y\phi(y)$, $\mu'(y)=y\mu(y)-1$, which is $<0$ for $y>0$ by Gordon's bound and equals $-1$ at $y=0$. Thus $\mu$ is strictly decreasing on $[0,\infty)$, with $\mu(0)=\sqrt{\pi/2}>1$ and $\mu(y)<1/y\to0$. So there is a unique $y_0>0$ with $\mu(y_0)=1$, and $\mu>1$ on $[0,y_0)$, $\mu<1$ on $(y_0,\infty)$. Put $g(y)=(y+1)\overline\Phi(y)-\phi(y)$. Then
$$
g'(y)=\overline\Phi(y)-(y+1)\phi(y)+y\phi(y)=\overline\Phi(y)-\phi(y)=\phi(y)\bigl(\mu(y)-1\bigr),
$$
so $g$ increases on $[0,y_0]$ and decreases on $[y_0,\infty)$. Also $g(0)=\tfrac12-\tfrac1{\sqrt{2\pi}}>0$, and $g(y)\to0$ as $y\to\infty$ because $0\le(y+1)\overline\Phi(y)\le(y+1)\phi(y)/y\to0$ and $\phi(y)\to0$. Hence $g\ge g(0)>0$ on $[0,y_0]$ and $g(y)\ge\lim_{s\to\infty}g(s)=0$ on $[y_0,\infty)$. So $\phi(y)/\overline\Phi(y)\le y+1$ for $y\ge0$.

**Step 6 (off-strip constant).** Let $r_i>0$ and $\rho_i<1$. In $\mathrm{OS}_i$ every $y\ge\beta_j>0$, so Step 5 applies. Substitute $y=\beta_j+t$, $t\ge0$:
$$
\frac{\beta_j-\rho_iy}{\sigma_i}=\beta_j\frac{1-\rho_i}{\sigma_i}-\frac{\rho_it}{\sigma_i}.
$$
Here $(1-\rho_i)/\sigma_i=\sqrt{(1-\rho_i)/(1+\rho_i)}\le\sqrt{(1-\rho_i)(1+\rho_i)}=\sigma_i$, which is equivalent to $1\le(1+\rho_i)^2$, true as $\rho_i\ge0$. Since $\beta_j>0$ and $\beta_j\sigma_i\le\kappa$ by hypothesis, the first term is at most $\kappa$; since $\rho_i\ge\frac12$ and $t\ge0$, the second is at least $t/(2\sigma_i)$. As $\Phi$ is increasing,
$$
\mathrm{OS}_i\le\int_0^\infty(\beta_j+1+t)\,\Phi\!\Bigl(\kappa-\frac t{2\sigma_i}\Bigr)dt
=2\sigma_i(\beta_j+1)K_0(\kappa)+4\sigma_i^2K_1(\kappa),
$$
by the substitution $t=2\sigma_is$, where
$$
K_0(\kappa)=\int_0^\infty\Phi(\kappa-s)\,ds,\qquad K_1(\kappa)=\int_0^\infty s\,\Phi(\kappa-s)\,ds .
$$
Closed forms: with $x=\kappa-s$, $K_0(\kappa)=\int_{-\infty}^\kappa\Phi(x)\,dx$ and $K_1(\kappa)=\int_{-\infty}^\kappa(\kappa-x)\Phi(x)\,dx$. Let $h_0(x)=x\Phi(x)+\phi(x)$; then $h_0'=\Phi+x\phi-x\phi=\Phi$, and $h_0(x)\to0$ as $x\to-\infty$ because $0\le|x|\Phi(x)=|x|\overline\Phi(|x|)\le\phi(x)$ by Gordon's bound. Hence $K_0(\kappa)=\kappa\Phi(\kappa)+\phi(\kappa)$. Let $h_1(\kappa)=\frac12\bigl((\kappa^2+1)\Phi(\kappa)+\kappa\phi(\kappa)\bigr)$; then
$$
h_1'(\kappa)=\tfrac12\bigl(2\kappa\Phi+(\kappa^2+1)\phi+\phi-\kappa^2\phi\bigr)=\kappa\Phi(\kappa)+\phi(\kappa)=K_0(\kappa),
$$
while differentiating under the integral, $K_1'(\kappa)=\int_{-\infty}^\kappa\Phi(x)\,dx=K_0(\kappa)$. As $\kappa\to-\infty$, $K_1(\kappa)=\int_0^\infty s\Phi(\kappa-s)ds\to0$ by dominated convergence (for $\kappa\le0$ the integrand is at most $s\,\overline\Phi(s)$, which is integrable), and $h_1(\kappa)\to0$ since $\kappa^2\Phi(\kappa)\le|\kappa|\phi(\kappa)\to0$, $\Phi(\kappa)\to0$, $\kappa\phi(\kappa)\to0$. So $K_1=h_1$. Both $K_0,K_1\ge0$. Using $\sigma_i\le1$ and $\sigma_i\beta_j\le\kappa$,
$$
\mathrm{OS}_i\le2(\sigma_i\beta_j+\sigma_i)K_0(\kappa)+4\sigma_i^2K_1(\kappa)\le2(\kappa+1)K_0(\kappa)+4K_1(\kappa)=A^*(\kappa).
$$
The same bound holds trivially when $\rho_i=1$, since then $\mathrm{OS}_i=0\le A^*(\kappa)$.

**Step 7 (properties of $A^*$).** $A^*(\kappa)=2(\kappa+1)K_0(\kappa)+4K_1(\kappa)$ is finite and nonnegative on $[0,\infty)$ and involves only $\kappa$; it does not depend on $m$, $d$, $J$, the means, the loadings, the $v_j$, the $\beta_j$ or $q$. It is nondecreasing: $K_0'=\Phi\ge0$ and $K_1'=K_0\ge0$, and $(\kappa+1)K_0(\kappa)$ is a product of nonnegative nondecreasing functions. At $\kappa=0$, $K_0(0)=\phi(0)=1/\sqrt{2\pi}$ and $K_1(0)=\frac12\Phi(0)=\frac14$, so $A^*(0)=\sqrt{2/\pi}+1$, used in Step 3.

**Step 8 (assembly).** For each $i\in C_j$: if $r_i>0$, (4) and Step 6 give $\mathbb E[G_i\mathbf1\{W_j\le\beta_j\}]\le\frac12+\frac{\gamma_iu}{\sqrt{2\pi}}+\log\frac q{\overline\Phi(\beta_j)}+A^*(\kappa)$; if $r_i=0$, Step 3 gives the same bound. Inserting this into (2) and adding the bound $\overline\Phi(\beta_j)$ for $\{W_j>\beta_j\}$ from Step 2 proves (1), and Step 1 completes the proof with $A_1=A^*$. The endpoint cases are covered: $r_i=1$ is handled without dividing by $\sqrt{1-r_i^2}$ or $\gamma_i$ (conditionally deterministic $p_i$ in Step 2, the lemma's stated endpoint in (3), the envelope in Step 4); $\rho_i=1$ makes the off-strip term zero; $\beta_j=u$ makes the middle strip empty; $\rho_i=\frac12$ is allowed since Step 6 uses only $\rho_i\ge\frac12$. Singular covariance is allowed since only the representation and the standard normal laws of the scalar projections $Y_i$, $W_j$ and of $W_j-\rho_iY_i$ were used.
