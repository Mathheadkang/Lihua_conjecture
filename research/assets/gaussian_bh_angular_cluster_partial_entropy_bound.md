---
type: lemma
schema_version: 2
title: Partial entropy bound for one angular null cluster at scale 1/u
status: approved
source:
  kind: original
depends_on: []
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_multifactor_representation
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags:
  - current_phase
  - universal_order
  - one_sided
  - angular_chaining_route
---

# Partial entropy bound for one angular null cluster at scale 1/u

## Statement

Let $m,d$ be positive integers, $\theta\in\mathbb R^m$, let $w_1,\ldots,w_m$ be unit vectors in $\mathbb R^d$, let $Z\sim\mathcal N_d(0,I_d)$, and put $T_i=\theta_i+w_i^{\mathsf T}Z$. This is the [Gaussian multifactor representation](../definitions/gaussian_multifactor_representation.md) with loadings $a_i=w_i$ of unit norm and no residual, hence a [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md) with covariance $\Sigma_{ij}=w_i^{\mathsf T}w_j$; singular covariance is allowed. Use the one-sided [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md) $p_i=\overline\Phi(T_i)$ and $I_0=\{i:\theta_i\le0\}$. For $0<q<1/2$ let $\mathcal R_q$ be the rejection set of the [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md) applied to all of $p_1,\ldots,p_m$ at level $q$ (largest qualifying rank, multiplicities, non-strict comparisons), $R=|\mathcal R_q|$, and $u=\overline\Phi^{-1}(q)>0$.

For $\kappa>0$, an angular cluster at scale $\kappa$ is a pair $(G,v)$ with $\varnothing\ne G\subseteq I_0$ and $v\in\mathbb R^d$ a unit vector such that
$$
\|w_i-v\|\le\kappa/u\qquad\text{for every }i\in G.
$$
Put
$$
\pi_G=\frac{|G|}{m},\qquad Y_G=v^{\mathsf T}Z,\qquad b_G=\overline\Phi^{-1}(q\pi_G)\ge u,\qquad V_G=|\mathcal R_q\cap G|.
$$

For every $\kappa\in(0,1]$ and every $C\ge1$ there exist finite constants $A_1=A_1(\kappa,C)$ and $q_1=q_1(\kappa,C)\in(0,1/2)$, depending only on $\kappa$ and $C$, such that for every $0<q\le q_1$, every such $m,d,\theta,w_1,\ldots,w_m$, and every angular cluster $(G,v)$ at scale $\kappa$ with $\pi_G\ge q^C$:

(a) (off-strip part)
$$
\mathbb E\!\left[\frac{V_G\,\mathbf 1\{Y_G\le u\}}{R\vee1}\right]
+\mathbb E\!\left[\frac{V_G\,\mathbf 1\{Y_G>b_G\}}{R\vee1}\right]
\le A_1\,q\,\pi_G;
$$

(b) (strip part)
$$
\mathbb E\!\left[\frac{V_G\,\mathbf 1\{u<Y_G\le b_G\}}{R\vee1}\right]
\le A_1\,q\,\pi_G\Bigl(1+\log\frac1{\pi_G}\Bigr).
$$

Here $R\vee1=\max\{R,1\}$, the [false discovery rate](../definitions/false_discovery_rate.md) conventions apply, and the logarithm is natural. The counts $V_G$ and $R$ always refer to the same unmodified BH procedure on all $m$ coordinates, with the original null labels. The constants do not depend on $m$, $d$, $\theta$, the directions of coordinates outside $G$, the alternative means, or the number of other clusters.

## Proof

Write $\phi(y)=(2\pi)^{-1/2}e^{-y^2/2}$ and $\Phi=1-\overline\Phi$. We prove (a) and (b) with the explicit choices
$$
q_1=\overline\Phi(3),\qquad \kappa'=\kappa\sqrt{2(C+1)},\qquad A_1(\kappa,C)=1+A^*(\kappa'),
$$
where, for $k\ge0$,
$$
K_0(k)=k\Phi(k)+\phi(k),\qquad K_1(k)=\tfrac12\bigl((k^2+1)\Phi(k)+k\phi(k)\bigr),\qquad A^*(k)=2(k+1)K_0(k)+4K_1(k).
$$
These depend only on $\kappa$ and $C$, and $q_1\approx0.00135$ lies in $(0,1/2)$. The argument adapts the proof of the approved [angular-cluster entropy bound](gaussian_bh_angular_cluster_entropy_bound.md), but it is self-contained: with unit loadings every p-value is a function of $Z$, so the leave-one-out reduction is replaced by a deterministic bound (Step 4). The pathwise bound of Step 4 has infinite expectation on its own, because $\int_u^\infty\phi/\overline\Phi=\infty$. It is therefore used only on events where the integral is finite: on the bounded strip $\{u\le X_i\le b_G\}$, or together with an indicator $\{Y_G\le u\}$ or $\{Y_G\le b_G\}$ whose conditional probability decays in the null's own score.

**Step 1 (elementary Gaussian facts).**

(i) *Hazard inequality:* $\phi(y)\le(y+1)\overline\Phi(y)$ for all $y\ge0$. For $y>0$, Gordon's bound $\overline\Phi(y)=\int_y^\infty\phi(x)\,dx<\int_y^\infty\frac xy\phi(x)\,dx=\phi(y)/y$ holds, strictly since $x/y>1$ for $x>y$. Let $\mu=\overline\Phi/\phi$. Since $\phi'(y)=-y\phi(y)$, $\mu'(y)=y\mu(y)-1$, which is $<0$ for $y>0$ by Gordon's bound and equals $-1$ at $0$. So $\mu$ is strictly decreasing on $[0,\infty)$, with $\mu(0)=\sqrt{\pi/2}>1$ and $\mu(y)<1/y\to0$. Hence there is a unique $y_0>0$ with $\mu>1$ on $[0,y_0)$ and $\mu<1$ on $(y_0,\infty)$. Put $g(y)=(y+1)\overline\Phi(y)-\phi(y)$. Then $g'(y)=\overline\Phi(y)-(y+1)\phi(y)+y\phi(y)=\phi(y)(\mu(y)-1)$, so $g$ increases on $[0,y_0]$ and decreases on $[y_0,\infty)$. Also $g(0)=\frac12-\frac1{\sqrt{2\pi}}>0$ and $g(y)\to0$ as $y\to\infty$, because $0\le(y+1)\overline\Phi(y)\le(y+1)\phi(y)/y\to0$. So $g\ge g(0)>0$ on $[0,y_0]$, and $g\ge\lim_{s\to\infty}g(s)=0$ on $[y_0,\infty)$.

(ii) *Chernoff bound:* for $t\ge0$ and $N\sim\mathcal N(0,1)$, Markov's inequality applied to $e^{tN}$ gives $\overline\Phi(t)=\mathbb P(N\ge t)\le e^{-t^2}\mathbb E e^{tN}=e^{-t^2/2}$.

(iii) *The constants.* For $k\ge0$ put $\widetilde K_0(k)=\int_0^\infty\Phi(k-s)\,ds$ and $\widetilde K_1(k)=\int_0^\infty s\,\Phi(k-s)\,ds$. These are finite, since $\Phi(k-s)=\overline\Phi(s-k)\le e^{-(s-k)^2/2}$ for $s\ge k$ by (ii). With $x=k-s$, $\widetilde K_0(k)=\int_{-\infty}^k\Phi(x)\,dx$ and $\widetilde K_1(k)=\int_{-\infty}^k(k-x)\Phi(x)\,dx$. Let $h_0(x)=x\Phi(x)+\phi(x)$. Then $h_0'=\Phi+x\phi-x\phi=\Phi$, and $h_0(x)\to0$ as $x\to-\infty$, because $0\le|x|\Phi(x)=|x|\overline\Phi(|x|)\le\phi(x)$ by Gordon's bound. Hence $\widetilde K_0=h_0=K_0$. Next, $\frac{d}{dk}K_1(k)=\frac12\bigl(2k\Phi+(k^2+1)\phi+\phi-k^2\phi\bigr)=k\Phi(k)+\phi(k)=K_0(k)$. Differentiating under the integral (the integrand of $\widetilde K_1$ vanishes at $x=k$) gives $\widetilde K_1'(k)=\int_{-\infty}^k\Phi(x)\,dx=K_0(k)$. As $k\to-\infty$, $\widetilde K_1(k)\to0$ by dominated convergence: for $k\le0$ the integrand is at most $s\,\overline\Phi(s)$, which is integrable. Also $K_1(k)\to0$, since $k^2\Phi(k)\le|k|\phi(k)\to0$. So $\widetilde K_1=K_1$ on $\mathbb R$, in particular on $[0,\infty)$. Both are nonnegative as integrals of nonnegative functions. Both are nondecreasing in $k$, since $\Phi$ is increasing. Hence $A^*$ is finite, nonnegative and nondecreasing on $[0,\infty)$, as $(k+1)K_0(k)$ is a product of nonnegative nondecreasing functions.

**Step 2 (level facts for $0<q\le q_1$).** Since $\overline\Phi$ is strictly decreasing and $q\le\overline\Phi(3)$, we have $u=\overline\Phi^{-1}(q)\ge3$.

(i) By Step 1(i), $q=\overline\Phi(u)\ge\phi(u)/(u+1)$, so
$$
\log\frac1q\le\frac{u^2}2+\log\bigl(\sqrt{2\pi}\,(u+1)\bigr)\le u^2 .
$$
For the last inequality, the function $f(u)=u^2/2-\log(\sqrt{2\pi}(u+1))$ satisfies $f(3)=4.5-\log(4\sqrt{2\pi})\ge4.5-2.31>0$, and $f'(u)=u-1/(u+1)>0$ for $u\ge3$.

(ii) Since $0<\pi_G\le1$, $q\pi_G\in(0,q]\subset(0,1)$, so $b_G=\overline\Phi^{-1}(q\pi_G)$ is well defined. Because $\overline\Phi$ is a continuous strictly decreasing bijection $\mathbb R\to(0,1)$, $\overline\Phi(b_G)=q\pi_G$ and $b_G\ge u>0$.

(iii) Put $t=\sqrt{2\log(1/(q\pi_G))}>0$. By Step 1(ii), $\overline\Phi(t)\le q\pi_G=\overline\Phi(b_G)$, so $b_G\le t$. Since $\pi_G\ge q^C$, $\log(1/\pi_G)\le C\log(1/q)$, hence by (i)
$$
\log\frac1{q\pi_G}\le(C+1)\log\frac1q\le(C+1)u^2,\qquad\text{so}\qquad b_G\le\sqrt{2(C+1)}\,u .
$$
This is the only use of the hypothesis $\pi_G\ge q^C$.

**Step 3 (angular geometry).** For $i\in G$ put $X_i=w_i^{\mathsf T}Z$, $\rho_i=w_i^{\mathsf T}v$ and $\sigma_i=\sqrt{1-\rho_i^2}$. Since $w_i,v$ are unit vectors, $X_i,Y_G\sim\mathcal N(0,1)$, $\rho_i\le1$ by Cauchy-Schwarz, and $\|w_i-v\|^2=2-2\rho_i$. The cluster condition, $\kappa\le1$ and $u\ge3$ give $2-2\rho_i\le\kappa^2/u^2\le1/9$, so $\rho_i\ge1-\frac1{18}\ge\frac12$. Moreover
$$
\sigma_i^2=(1-\rho_i)(1+\rho_i)\le2(1-\rho_i)=\|w_i-v\|^2,\qquad\text{so}\qquad\sigma_i\le\kappa/u\le\tfrac13 .
$$
If $\rho_i<1$, then $\sigma_i>0$ and $(1-\rho_i)/\sigma_i=\sqrt{(1-\rho_i)/(1+\rho_i)}\le\sqrt{(1-\rho_i)(1+\rho_i)}=\sigma_i$, which is equivalent to $1\le(1+\rho_i)^2$. In that case $E_i':=Y_G-\rho_iX_i$ is a linear function of $Z$ with $\operatorname{Cov}(E_i',X_i)=\rho_i-\rho_i=0$ and $\operatorname{Var}(E_i')=1-2\rho_i^2+\rho_i^2=\sigma_i^2$. By joint Gaussianity $E_i'$ is independent of $X_i$ with law $\mathcal N(0,\sigma_i^2)$. Hence for every $c\in\mathbb R$ and every Borel $f\ge0$,
$$
\mathbb E\bigl[f(X_i)\mathbf1\{Y_G\le c\}\bigr]=\int_{-\infty}^\infty\phi(x)f(x)\,\Phi\!\Bigl(\frac{c-\rho_ix}{\sigma_i}\Bigr)dx,
\tag{1}
$$
by Fubini for nonnegative integrands (the value $+\infty$ is allowed). If $\rho_i=1$, then $\|w_i-v\|=0$, so $w_i=v$ and $Y_G=X_i$ identically.

**Step 4 (deterministic per-null bound).** Let $i\in I_0$. We show that, pointwise on every outcome,
$$
\frac{\mathbf1\{i\in\mathcal R_q\}}{R\vee1}\le\frac qm\,\frac{\mathbf1\{X_i\ge u\}}{\overline\Phi(X_i)} .
\tag{2}
$$
Write $\widehat k=\widehat k_q(p)$. If $\widehat k=0$, then $\mathcal R_q=\varnothing$ and the left side is $0$. Let $\widehat k\ge1$. Then $p_{(1)},\ldots,p_{(\widehat k)}\le p_{(\widehat k)}\le q\widehat k/m$, so at least $\widehat k$ coordinates belong to $\mathcal R_q$ and $R\ge\widehat k\ge1$. If $i\in\mathcal R_q$, then $p_i\le q\widehat k/m$. Since $\theta_i\le0$ and $\overline\Phi$ is decreasing,
$$
\overline\Phi(X_i)\le\overline\Phi(\theta_i+X_i)=p_i\le\frac{q\widehat k}m\le q=\overline\Phi(u),
$$
so $X_i\ge u$, and $\frac1{R\vee1}\le\frac1{\widehat k}\le\frac q{m\,\overline\Phi(X_i)}$. If $i\notin\mathcal R_q$ the left side of (2) is $0$. This proves (2), including all ties and the case $R=0$. Summing over $i\in G\subseteq I_0$,
$$
\frac{V_G}{R\vee1}\le\frac qm\sum_{i\in G}\frac{\mathbf1\{X_i\ge u\}}{\overline\Phi(X_i)} .
\tag{3}
$$
Here $R$ and $V_G$ are those of the unmodified procedure on all $m$ coordinates. Nothing about the other coordinates is used, and only $\theta_i\le0$ is used for $i\in G$. The right side of (3) has infinite expectation, so (3) is only ever multiplied by indicators that make the resulting integrals finite.

**Step 5 (part (a), upper off-strip term).** If $R\ge1$ then $V_G\le R$, and if $R=0$ then $V_G=0$; so $0\le V_G/(R\vee1)\le1$. As $Y_G\sim\mathcal N(0,1)$, Step 2(ii) gives
$$
\mathbb E\!\left[\frac{V_G\,\mathbf1\{Y_G>b_G\}}{R\vee1}\right]\le\mathbb P(Y_G>b_G)=\overline\Phi(b_G)=q\pi_G .
$$

**Step 6 (part (a), lower off-strip term).** Multiply (3) by $\mathbf1\{Y_G\le u\}$ and take expectations of the nonnegative terms:
$$
\mathbb E\!\left[\frac{V_G\,\mathbf1\{Y_G\le u\}}{R\vee1}\right]\le\frac qm\sum_{i\in G}E_i,\qquad E_i=\mathbb E\!\left[\frac{\mathbf1\{X_i\ge u,\ Y_G\le u\}}{\overline\Phi(X_i)}\right].
$$
If $\rho_i=1$, then $Y_G=X_i$, the event is $\{X_i=u\}$, which is a null set, and $E_i=0$. If $\rho_i<1$, apply (1) with $c=u$ and $f(x)=\mathbf1\{x\ge u\}/\overline\Phi(x)$, then substitute $x=u+t$:
$$
E_i=\int_u^\infty\frac{\phi(x)}{\overline\Phi(x)}\,\Phi\!\Bigl(\frac{u-\rho_ix}{\sigma_i}\Bigr)dx
=\int_0^\infty\frac{\phi(u+t)}{\overline\Phi(u+t)}\,\Phi\!\Bigl(u\frac{1-\rho_i}{\sigma_i}-\frac{\rho_it}{\sigma_i}\Bigr)dt .
$$
By Step 3, $u(1-\rho_i)/\sigma_i\le u\sigma_i\le\kappa$, and $\rho_it/\sigma_i\ge t/(2\sigma_i)$ since $\rho_i\ge\frac12$. By Step 1(i), $\phi(u+t)/\overline\Phi(u+t)\le u+1+t$, because $u+t\ge0$. Since $\Phi$ is increasing, the substitution $t=2\sigma_is$ gives
$$
E_i\le\int_0^\infty(u+1+t)\,\Phi\!\Bigl(\kappa-\frac t{2\sigma_i}\Bigr)dt=2\sigma_i(u+1)K_0(\kappa)+4\sigma_i^2K_1(\kappa)\le2(\kappa+1)K_0(\kappa)+4K_1(\kappa)=A^*(\kappa),
$$
using Step 1(iii), $K_0,K_1\ge0$, $\sigma_i(u+1)\le\kappa(1+1/u)\le\kappa+1$ and $\sigma_i^2\le1$. So $E_i\le A^*(\kappa)$ for every $i\in G$, and the first term of (a) is at most $\frac qm|G|A^*(\kappa)=q\pi_GA^*(\kappa)$.

**Step 7 (part (b)).** Multiply (3) by $\mathbf1\{u<Y_G\le b_G\}$ and take expectations:
$$
\mathbb E\!\left[\frac{V_G\,\mathbf1\{u<Y_G\le b_G\}}{R\vee1}\right]\le\frac qm\sum_{i\in G}S_i,\qquad S_i=\mathbb E\!\left[\frac{\mathbf1\{X_i\ge u,\ u<Y_G\le b_G\}}{\overline\Phi(X_i)}\right].
$$
Split according to $u\le X_i\le b_G$ and $X_i>b_G$.

*Bounded strip.* On $\{u\le X_i\le b_G\}$ drop the condition on $Y_G$. Since $X_i\sim\mathcal N(0,1)$, Step 2(ii) gives
$$
\mathbb E\!\left[\frac{\mathbf1\{u\le X_i\le b_G\}}{\overline\Phi(X_i)}\right]=\int_u^{b_G}\frac{\phi(x)}{\overline\Phi(x)}\,dx=\log\frac{\overline\Phi(u)}{\overline\Phi(b_G)}=\log\frac q{q\pi_G}=\log\frac1{\pi_G}.
$$
This is a finite integral over the bounded interval $[u,b_G]$.

*Beyond the strip.* On $\{X_i>b_G\}$ keep only $Y_G\le b_G$. If $\rho_i=1$, then $Y_G=X_i$ and $\{X_i>b_G,\ Y_G\le b_G\}=\varnothing$, so the contribution is $0$. If $\rho_i<1$, apply (1) with $c=b_G$ and $f(x)=\mathbf1\{x>b_G\}/\overline\Phi(x)$, then substitute $x=b_G+t$:
$$
\mathbb E\!\left[\frac{\mathbf1\{X_i>b_G,\ Y_G\le b_G\}}{\overline\Phi(X_i)}\right]=\int_0^\infty\frac{\phi(b_G+t)}{\overline\Phi(b_G+t)}\,\Phi\!\Bigl(b_G\frac{1-\rho_i}{\sigma_i}-\frac{\rho_it}{\sigma_i}\Bigr)dt .
$$
By Steps 2(iii) and 3, $b_G(1-\rho_i)/\sigma_i\le b_G\sigma_i\le\sqrt{2(C+1)}\,u\cdot\kappa/u=\kappa'$, and $\rho_it/\sigma_i\ge t/(2\sigma_i)$. By Step 1(i), $\phi(b_G+t)/\overline\Phi(b_G+t)\le b_G+1+t$, since $b_G>0$. Hence, with $t=2\sigma_is$,
$$
\le\int_0^\infty(b_G+1+t)\,\Phi\!\Bigl(\kappa'-\frac t{2\sigma_i}\Bigr)dt=2\sigma_i(b_G+1)K_0(\kappa')+4\sigma_i^2K_1(\kappa')\le2(\kappa'+1)K_0(\kappa')+4K_1(\kappa')=A^*(\kappa'),
$$
using $\sigma_ib_G\le\kappa'$ and $\sigma_i\le1$. This bound holds trivially when $\rho_i=1$.

The two pieces cover $\{X_i\ge u\}$, so $S_i\le\log(1/\pi_G)+A^*(\kappa')$ for each $i\in G$, and the strip term is at most $q\pi_G\bigl(\log(1/\pi_G)+A^*(\kappa')\bigr)$.

**Step 8 (constants and conclusion).** Since $C\ge1$, $\sqrt{2(C+1)}\ge2$, so $\kappa'\ge\kappa$, and $A^*(\kappa)\le A^*(\kappa')$ by Step 1(iii). Steps 5 and 6 give
$$
\mathbb E\!\left[\frac{V_G\mathbf1\{Y_G\le u\}}{R\vee1}\right]+\mathbb E\!\left[\frac{V_G\mathbf1\{Y_G>b_G\}}{R\vee1}\right]\le q\pi_G\bigl(1+A^*(\kappa)\bigr)\le A_1q\pi_G,
$$
which is (a). Step 7 gives
$$
\mathbb E\!\left[\frac{V_G\mathbf1\{u<Y_G\le b_G\}}{R\vee1}\right]\le q\pi_G\Bigl(\log\frac1{\pi_G}+A^*(\kappa')\Bigr)\le A_1q\pi_G\Bigl(1+\log\frac1{\pi_G}\Bigr),
$$
because $A^*(\kappa')\le A_1$, $\log(1/\pi_G)\ge0$ and $A_1\ge1$. This is (b).

The constants $q_1=\overline\Phi(3)$ and $A_1=1+A^*(\kappa\sqrt{2(C+1)})$ involve only $\kappa$ and $C$. Steps 4-7 use nothing about $m$, $d$, the means outside $G$ (only $\theta_i\le0$ on $G$), the loadings outside $G$, or other clusters. Singular covariance is allowed, since only the laws of the scalar projections $X_i$, $Y_G$ and $Y_G-\rho_iX_i$ of $Z$ were used. The case $\rho_i=1$ is treated separately, so there is no division by $\sigma_i=0$. Every expectation above is of a nonnegative quantity, so Tonelli/Fubini apply throughout. The bound (3) is integrated only against $\{Y_G\le u\}$ (Step 6), over the bounded strip $\{u\le X_i\le b_G\}$, and against $\{X_i>b_G,\ Y_G\le b_G\}$ (Step 7). Each of these integrals is finite, even though $\mathbb E[\mathbf1\{X_i\ge u\}/\overline\Phi(X_i)]=\infty$. $\blacksquare$
