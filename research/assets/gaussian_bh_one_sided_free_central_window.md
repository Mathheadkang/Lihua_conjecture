---
type: lemma
title: One-sided free central window lemma C
status: draft
source:
  kind: original
  location: "plan_gaussian_bh_one_sided_free_center_pooled_shell_20261106, Progress, Steps 1–3 (source lines 202–217)"
depends_on: []
uses_definitions:
  - gaussian_multifactor_representation
  - gaussian_null_loading_coefficients
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags:
  - gaussian
  - one_sided
  - central_window
  - extracted_unverified
---

## Source notation and scope

The following setup is copied from the source plan's Plan and Progress. Write $\phi(y)=(2\pi)^{-1/2}e^{-y^2/2}$, $\overline\Phi(y)=\int_y^\infty\phi(x)dx$, and $(x)_+=\max\{x,0\}$. Use the one-sided testing track, so $I_0=\{i:\theta_i\le0\}$, $\pi_0=|I_0|/N$, and $\overline\gamma_0=N^{-1}\sum_{i\in I_0}\gamma_i$ from the approved [Gaussian null loading coefficients](../definitions/gaussian_null_loading_coefficients.md) definition.

Notation. $0<q<1/2$, $U=\overline\Phi^{-1}(q)>0$, $t_k=qk/N$, $u_k=\overline\Phi^{-1}(t_k)\ge U$ ($u_N=U$), $k(w)=N\overline\Phi(w)/q$ (the BH line in level space). For $r\in[0,1)$, $s=\sqrt{1-r^2}$, $\gamma_r=\sqrt{(1-r)/(1+r)}$ and $\theta\le0$,

$$
\rho^\theta_r(v,y)=\frac{\overline\Phi((v-\theta-ry)/s)}{\overline\Phi(v)}\le\rho_r(v,y):=\rho^0_r(v,y),\qquad \rho_1(v,y)=\frac{\mathbf 1\{y\ge v\}}{\overline\Phi(v)},\quad\rho_0\equiv1 .
$$


Notation as in `## Plan`; $N$ tests, $0<q<1/2$, $U=\overline\Phi^{-1}(q)$, $t_k=qk/N$, $u_k=\overline\Phi^{-1}(t_k)\ge U$. All statements are for an arbitrary [Gaussian multifactor representation](../definitions/gaussian_multifactor_representation.md) $T_i=\theta_i+a_i^{\mathsf T}Z+s_i\varepsilon_i$, $r_i=\|a_i\|$, $s_i=\sqrt{1-r_i^2}$; $\mathfrak B_1$ is the special case of step 0.

The block class $\mathfrak B_1$ mentioned in the copied text is only a special case; none of Steps 1–3 assumes the block structure. For the central contribution Ce, the source uses $Y_i=-\infty$ at $r_i=0$ only as an event-label convention; the kernel at zero loading is independent of its second argument.

## Statement

For $r\in[0,1)$, $s=\sqrt{1-r^2}$, all real $y$ and all $v\ge U$:

$$
\phi(y)\rho_r(v,y)\le\frac1s\phi\Big(\frac{(rv-y)_+}{s}\Big)\le\frac1{s\sqrt{2\pi}},\qquad\int_{-\infty}^U\phi(y)\sup_{v\ge U}\rho_r(v,y)\,dy\le\frac12+\frac{\gamma_rU}{\sqrt{2\pi}} .
$$


*Consequences.* (i) For $0<q\le1/10$ and every multifactor model, $\mathrm{Ce}\le\frac qN\sum_{i\in I_0}(\frac12+\frac{\gamma_iU}{\sqrt{2\pi}})$: for $r_i>0$ bound $\rho_{r_i}(u_{R_i},Y_i)\mathbf 1\{Y_i\le U\}\le\sup_{v\ge U}\rho_{r_i}(v,Y_i)\mathbf 1\{Y_i\le U\}$ (as $u_{R_i}\ge U$) and integrate against the standard normal law of $Y_i$; for $r_i=0$, $\rho_0\equiv1$ and $1\le\frac12+\frac U{\sqrt{2\pi}}$ because $q\le1/10<\overline\Phi(\sqrt{\pi/2})$. (ii) One-sided deterministic DCL: for any (random or deterministic) threshold map, $\int_{y\le U}\phi(y)[\rho_r(u(y),y)-\rho_r(u_f,y)]dy\le\frac12+\frac{\gamma_rU}{\sqrt{2\pi}}$, dropping the nonnegative baseline. Linearity of the BH line is never used.

## Proof

gap: The extra deterministic-DCL consequence (ii) does not explicitly state the range of its threshold maps. Its unrestricted-real reading is not established. The proposed counterexample is excluded if the local domain $u(y)\ge U$ is inherited; no range assumption is inserted here. The kernel and BH central-contribution core is selected separately under a new asset ID.

Copied verbatim from [the source plan](../plans/plan_gaussian_bh_one_sided_free_center_pooled_shell_20261106.md), Progress, “Steps 1–3 (written out in full; settle checklist items 1, 2, 3)”, source lines 204–217. The extraction carries no independent verification verdict.

Notation as in `## Plan`; $N$ tests, $0<q<1/2$, $U=\overline\Phi^{-1}(q)$, $t_k=qk/N$, $u_k=\overline\Phi^{-1}(t_k)\ge U$. All statements are for an arbitrary [Gaussian multifactor representation](../definitions/gaussian_multifactor_representation.md) $T_i=\theta_i+a_i^{\mathsf T}Z+s_i\varepsilon_i$, $r_i=\|a_i\|$, $s_i=\sqrt{1-r_i^2}$; $\mathfrak B_1$ is the special case of step 0.

**Step 1 (forced-zero identity).** Fix $p\in[0,1]^N$ and $i$. For any vector $p'$ write $R(p')=\widehat k_q(p')$ (BH definition). *Claim 0:* $R(p')=|\{j:p'_j\le qR(p')/N\}|$. Indeed, if $k=R(p')\ge1$ then $p'_{(k)}\le qk/N$ so at least $k$ coordinates are $\le qk/N$; if $c>k$ coordinates were $\le qk/N$, then $p'_{(c)}\le qk/N\le qc/N$ and $c$ would qualify, contradicting maximality; for $k=0$ the rejection set is empty by definition. Let $p^{(i)}$ be $p$ with $p_i$ replaced by $0$ and $R_i=R(p^{(i)})$. Then $p^{(i)}_{(1)}=0\le q/N$, so $R_i\ge1$; $R_i$ is a function of $(p_j)_{j\ne i}$; and $R_i\ge R:=R(p)$, because lowering a coordinate does not increase any order statistic, so every rank qualifying for $p$ qualifies for $p^{(i)}$. *Identity:* $\mathbf 1\{i\in\mathcal R_q\}/(R\vee1)=\mathbf 1\{p_i\le t_{R_i}\}/R_i$. If $i\in\mathcal R_q$ then $R\ge1$ and $p_i\le t_R$; with $k=R_i$, $p^{(i)}$ has at least $k$ coordinates $\le t_k$ (Claim 0), and restoring $p_i\le t_R\le t_k$ keeps them $\le t_k$, so $k$ qualifies for $p$, $k\le R$, hence $R_i=R$ and both sides equal $1/R$. If $i\notin\mathcal R_q$ but $p_i\le t_{R_i}$, restoring $p_i$ keeps at least $R_i$ coordinates $\le t_{R_i}$, so $R\ge R_i$, $R=R_i\ge1$ and $p_i\le t_R$, i.e. $i\in\mathcal R_q$, a contradiction. So both sides vanish. This covers ties, threshold equalities and $R=0$. $\square$

**Step 2 (conditional formula; one-sided composite domination).** (a) For $s>0$ put $\rho^\theta_r(v,y)=\overline\Phi((v-\theta-ry)/s)/\overline\Phi(v)$; for $r=1$, $\rho^\theta_1(v,y)=\mathbf 1\{\theta+y\ge v\}/\overline\Phi(v)$. Let $Y_i=a_i^{\mathsf T}Z/r_i$ if $r_i>0$ (any fixed unit-vector projection if $r_i=0$). Given $Z$ the coordinates are independent, so $p_i=\overline\Phi(T_i)$ and $R_i$ (a function of $(p_j)_{j\ne i}$) are conditionally independent. Since $\overline\Phi$ is a continuous strictly decreasing bijection $\mathbb R\to(0,1)$, $\{p_i\le t\}=\{T_i\ge\overline\Phi^{-1}(t)\}$, whose conditional probability given $Z$ is $\overline\Phi((\overline\Phi^{-1}(t)-\theta_i-r_iY_i)/s_i)$ ($s_i>0$) or $\mathbf 1\{\theta_i+Y_i\ge\overline\Phi^{-1}(t)\}$ ($s_i=0$). Taking $t=t_{R_i}=\overline\Phi(u_{R_i})$ in step 1 and conditioning first on $(Z,(\varepsilon_j)_{j\ne i})$:

$$
\mathbb E\Big[\frac{\mathbf 1\{i\in\mathcal R_q\}}{R_q\vee1}\Big|Z\Big]=\mathbb E\Big[\frac{\overline\Phi(u_{R_i})\rho^{\theta_i}_{r_i}(u_{R_i},Y_i)}{R_i}\Big|Z\Big]=\frac qN\mathbb E\big[\rho^{\theta_i}_{r_i}(u_{R_i},Y_i)\big|Z\big],
$$

using $\overline\Phi(u_k)/k=q/N$. *Domination:* $\theta_i\le0$ gives $(v-\theta_i-ry)/s\ge(v-ry)/s$, and $\overline\Phi$ is decreasing, so $\rho^{\theta_i}_r\le\rho_r:=\rho^0_r$; at $r=1$, $\{\theta_i+y\ge v\}\subset\{y\ge v\}$. (b) If $R'$ is a random rank independent of $Y_i$ and of $\varepsilon_i$, then conditioning on $R'$ and using $r_iY_i+s_i\varepsilon_i\sim N(0,1)$, $\mathbb E[\rho^{\theta_i}_{r_i}(u_{R'},Y_i)\mid R']=\overline\Phi(u_{R'}-\theta_i)/\overline\Phi(u_{R'})\le1$ (equality iff $\theta_i=0$). $\square$
Consequence used below: with $\mathrm{Ce}=\sum_{i\in I_0}\mathbb E[\frac{\mathbf 1\{i\in\mathcal R_q\}}{R_q\vee1}\mathbf 1\{Y_i\le U\}]$ and $\mathrm{Sh}$ the same with $\mathbf 1\{Y_i>U\}$ (for $r_i=0$ we put $Y_i:=-\infty$, so these nulls are in Ce), $\mathrm{FDR}=\mathrm{Ce}+\mathrm{Sh}$ exactly, and since $Y_i$ is $Z$-measurable, $\mathrm{Ce}\le\frac qN\sum_{i\in I_0}\mathbb E[\rho_{r_i}(u_{R_i},Y_i)\mathbf 1\{Y_i\le U\}]$, likewise for Sh.

**Step 3 (Lemma C).** *Claim.* For $r\in[0,1)$, $s=\sqrt{1-r^2}$, all real $y$ and all $v\ge U$:

$$
\phi(y)\rho_r(v,y)\le\frac1s\phi\Big(\frac{(rv-y)_+}{s}\Big)\le\frac1{s\sqrt{2\pi}},\qquad\int_{-\infty}^U\phi(y)\sup_{v\ge U}\rho_r(v,y)\,dy\le\frac12+\frac{\gamma_rU}{\sqrt{2\pi}} .
$$

*Proof.* The standard bivariate normal density with correlation $r$ factors both ways, $\phi(x)s^{-1}\phi((y-rx)/s)=\phi(y)s^{-1}\phi((x-ry)/s)$; integrating over $x\ge v$ gives $\phi(y)\overline\Phi((v-ry)/s)=\int_v^\infty\phi(x)s^{-1}\phi((y-rx)/s)dx$. For $x\ge v$, $|y-rx|\ge(rx-y)_+\ge(rv-y)_+$ ($r\ge0$), and $\phi$ is decreasing in $|\cdot|$, so the integral is $\le s^{-1}\phi((rv-y)_+/s)\overline\Phi(v)$; divide by $\overline\Phi(v)$. For $v\ge U$, $(rv-y)_+\ge(rU-y)_+$, so $\sup_{v\ge U}\phi(y)\rho_r(v,y)\le s^{-1}\phi((rU-y)_+/s)$ (the supremum is measurable: $\rho_r(\cdot,y)$ is continuous, take rational $v$). Then $\int_{-\infty}^{rU}s^{-1}\phi((rU-y)/s)dy=\frac12$ and $\int_{rU}^U s^{-1}(2\pi)^{-1/2}dy=\frac{(1-r)U}{s\sqrt{2\pi}}=\frac{\gamma_rU}{\sqrt{2\pi}}$, since $(1-r)/\sqrt{1-r^2}=\sqrt{(1-r)/(1+r)}$. This includes $r=0$ ($s=1$). At $r=1$, $\rho_1(v,y)=0$ for $y<U\le v$, so the integral is $0$. $\square$
*Consequences.* (i) For $0<q\le1/10$ and every multifactor model, $\mathrm{Ce}\le\frac qN\sum_{i\in I_0}(\frac12+\frac{\gamma_iU}{\sqrt{2\pi}})$: for $r_i>0$ bound $\rho_{r_i}(u_{R_i},Y_i)\mathbf 1\{Y_i\le U\}\le\sup_{v\ge U}\rho_{r_i}(v,Y_i)\mathbf 1\{Y_i\le U\}$ (as $u_{R_i}\ge U$) and integrate against the standard normal law of $Y_i$; for $r_i=0$, $\rho_0\equiv1$ and $1\le\frac12+\frac U{\sqrt{2\pi}}$ because $q\le1/10<\overline\Phi(\sqrt{\pi/2})$. (ii) One-sided deterministic DCL: for any (random or deterministic) threshold map, $\int_{y\le U}\phi(y)[\rho_r(u(y),y)-\rho_r(u_f,y)]dy\le\frac12+\frac{\gamma_rU}{\sqrt{2\pi}}$, dropping the nonnegative baseline. Linearity of the BH line is never used.
- [x] Step 1 proved above. [x] Step 2 proved above (recheck of the one-sided kernel done: only the one-tail event $\{T_i\ge u\}$ enters). [x] Step 3 proved above.

