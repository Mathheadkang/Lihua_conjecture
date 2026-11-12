---
type: lemma
title: One-sided free central window kernel and BH central-contribution bound
status: approved
source:
  kind: original
  location: >-
    plan_gaussian_bh_one_sided_free_center_pooled_shell_20261106, Progress Steps
    1, 2(a), Ce definition, and 3 through Consequence (i)
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

## Statement

### Source notation and scope

In all copied passages below, `## Plan`, `step 0`, and the unused label $\mathfrak B_1$ refer only to the [source plan's Plan and step 0](../plans/plan_gaussian_bh_one_sided_free_center_pooled_shell_20261106.md). They add no assumption to the arbitrary multifactor scope stated here.

Write $\phi(y)=(2\pi)^{-1/2}e^{-y^2/2}$ and $(x)_+=\max\{x,0\}$. Use the one-sided testing track, $I_0=\{i:\theta_i\le0\}$, and $\gamma_i=\sqrt{(1-r_i)/(1+r_i)}$ from [Gaussian null loading coefficients](../definitions/gaussian_null_loading_coefficients.md). All finite multifactor dimensions, means and loadings allowed by the cited definition are included.

Notation. $0<q<1/2$, $U=\overline\Phi^{-1}(q)>0$, $t_k=qk/N$, $u_k=\overline\Phi^{-1}(t_k)\ge U$ ($u_N=U$), $k(w)=N\overline\Phi(w)/q$ (the BH line in level space). For $r\in[0,1)$, $s=\sqrt{1-r^2}$, $\gamma_r=\sqrt{(1-r)/(1+r)}$ and $\theta\le0$,

$$
\rho^\theta_r(v,y)=\frac{\overline\Phi((v-\theta-ry)/s)}{\overline\Phi(v)}\le\rho_r(v,y):=\rho^0_r(v,y),\qquad \rho_1(v,y)=\frac{\mathbf 1\{y\ge v\}}{\overline\Phi(v)},\quad\rho_0\equiv1 .
$$


Notation as in `## Plan`; $N$ tests, $0<q<1/2$, $U=\overline\Phi^{-1}(q)$, $t_k=qk/N$, $u_k=\overline\Phi^{-1}(t_k)\ge U$. All statements are for an arbitrary [Gaussian multifactor representation](../definitions/gaussian_multifactor_representation.md) $T_i=\theta_i+a_i^{\mathsf T}Z+s_i\varepsilon_i$, $r_i=\|a_i\|$, $s_i=\sqrt{1-r_i^2}$; $\mathfrak B_1$ is the special case of step 0.

Let $Y_i=a_i^{\mathsf T}Z/r_i$ if $r_i>0$ (any fixed unit-vector projection if $r_i=0$).

Consequence used below: with $\mathrm{Ce}=\sum_{i\in I_0}\mathbb E[\frac{\mathbf 1\{i\in\mathcal R_q\}}{R_q\vee1}\mathbf 1\{Y_i\le U\}]$ and $\mathrm{Sh}$ the same with $\mathbf 1\{Y_i>U\}$ (for $r_i=0$ we put $Y_i:=-\infty$, so these nulls are in Ce), $\mathrm{FDR}=\mathrm{Ce}+\mathrm{Sh}$ exactly, and since $Y_i$ is $Z$-measurable, $\mathrm{Ce}\le\frac qN\sum_{i\in I_0}\mathbb E[\rho_{r_i}(u_{R_i},Y_i)\mathbf 1\{Y_i\le U\}]$, likewise for Sh.

The source uses $Y_i:=-\infty$ at $r_i=0$ as the event-label convention in Ce; the kernel at $r_i=0$ is independent of its second argument.

For any vector $p'$ write $R(p')=\widehat k_q(p')$ (BH definition). Let $p^{(i)}$ be $p$ with $p_i$ replaced by $0$ and $R_i=R(p^{(i)})$. 

### Claim

For $r\in[0,1)$, $s=\sqrt{1-r^2}$, all real $y$ and all $v\ge U$:

$$
\phi(y)\rho_r(v,y)\le\frac1s\phi\Big(\frac{(rv-y)_+}{s}\Big)\le\frac1{s\sqrt{2\pi}},\qquad\int_{-\infty}^U\phi(y)\sup_{v\ge U}\rho_r(v,y)\,dy\le\frac12+\frac{\gamma_rU}{\sqrt{2\pi}} .
$$


At $r=1$, $\rho_1(v,y)=0$ for $y<U\le v$, so the integral is $0$.

*Consequences.* (i) For $0<q\le1/10$ and every multifactor model, $\mathrm{Ce}\le\frac qN\sum_{i\in I_0}(\frac12+\frac{\gamma_iU}{\sqrt{2\pi}})$: for $r_i>0$ bound $\rho_{r_i}(u_{R_i},Y_i)\mathbf 1\{Y_i\le U\}\le\sup_{v\ge U}\rho_{r_i}(v,Y_i)\mathbf 1\{Y_i\le U\}$ (as $u_{R_i}\ge U$) and integrate against the standard normal law of $Y_i$; for $r_i=0$, $\rho_0\equiv1$ and $1\le\frac12+\frac U{\sqrt{2\pi}}$ because $q\le1/10<\overline\Phi(\sqrt{\pi/2})$.

## Proof

### Step 1: scope and measurability

Fix $0<q<1/2$ and write $U=\overline\Phi^{-1}(q)>0$. For $1\le k\le N$, $0<t_k=qk/N\le q<1$; consequently $u_k=\overline\Phi^{-1}(t_k)\ge U$ and $u_N=U$. For $0\le r<1$ put $s=\sqrt{1-r^2}>0$. The numerator and positive denominator defining $\rho_r(v,y)$ are continuous, so this kernel is a continuous nonnegative function of the finite real variables $(v,y)$. Continuity in $v$ implies

$$
\sup_{v\ge U}\rho_r(v,y)=\sup_{v\in(\mathbb Q\cap[U,\infty))\cup\{U\}}\rho_r(v,y).
$$

The right side is a countable supremum of continuous functions of $y$, hence Borel measurable. At $r=1$ a direct maximization gives $\sup_{v\ge U}\rho_1(v,y)=\mathbf1\{y\ge U\}/\overline\Phi(y)$: when $y\ge U$ the denominator decreases up to the admissible endpoint $v=y$, and when $y<U$ every indicator vanishes. This is Borel measurable as well. Thus all nonnegative scalar integrals below are defined without an a priori integrability assumption.

### Step 2: the density identity

For all real $x,y$, direct expansion using $s^2=1-r^2$ gives

$$
x^2+(y-rx)^2/s^2=(x^2+y^2-2rxy)/s^2=y^2+(x-ry)^2/s^2.
$$

The normalizing factors on both sides coincide, so $\phi(x)s^{-1}\phi((y-rx)/s)=\phi(y)s^{-1}\phi((x-ry)/s)$. Integrating this nonnegative identity on $[v,\infty)$, and substituting $z=(x-ry)/s$ on its right side, proves

$$
\int_v^\infty\phi(x)s^{-1}\phi((y-rx)/s)\,dx=\phi(y)\overline\Phi((v-ry)/s).
$$

This holds for every real $v,y$ and every $0\le r<1$, including $r=0$.

### Step 3: the pointwise inequalities

For $x\ge v$ and $r\ge0$, $|y-rx|\ge(rx-y)_+\ge(rv-y)_+$. Since $\phi$ is even and decreases on the nonnegative half-line, step 2 yields

$$
\phi(y)\overline\Phi((v-ry)/s)\le s^{-1}\phi((rv-y)_+/s)\int_v^\infty\phi(x)\,dx.
$$

Dividing by $\overline\Phi(v)>0$ gives $\phi(y)\rho_r(v,y)\le s^{-1}\phi((rv-y)_+/s)\le1/(s\sqrt{2\pi})$. This proof imposes no restriction on the real value $y$ and holds for every $v\ge U$ and $0\le r<1$.

### Step 4: the central integral and scalar endpoints

For $v\ge U$ we have $(rv-y)_+\ge(rU-y)_+$. Taking the supremum in step 3 therefore gives

$$
\phi(y)\sup_{v\ge U}\rho_r(v,y)\le s^{-1}\phi((rU-y)_+/s).
$$

Because $rU\le U$, the integral of this envelope over $(-\infty,U]$ splits at $rU$. Substitution $z=(rU-y)/s$ gives $\int_{-\infty}^{rU}s^{-1}\phi((rU-y)/s)\,dy=\int_0^\infty\phi(z)\,dz=1/2$. On $[rU,U]$ the envelope is the constant $1/(s\sqrt{2\pi})$, so its integral is $(1-r)U/(s\sqrt{2\pi})$. Since $(1-r)/s=\sqrt{(1-r)/(1+r)}=\gamma_r$, this proves

$$
\int_{-\infty}^U\phi(y)\sup_{v\ge U}\rho_r(v,y)\,dy\le\tfrac12+\frac{\gamma_rU}{\sqrt{2\pi}}.
$$

At $r=0$, $s=1$, $\gamma_r=1$ and $\rho_0(v,y)=1$ for every finite $y,v$, so the actual integral is $1-\overline\Phi(U)$ and the same envelope computation applies. At $r=1$, step 1 shows the supremum is zero for $y<U$; its value $1/q$ at $y=U$ does not affect the integral. The central integral is then exactly zero. No degenerate density or limiting argument is needed.

### Step 5: the deterministic forced-zero identity

For deterministic $p\in[0,1]^N$ put $K=\widehat k_q(p)$. If $K\ge1$, at least $K$ p-values are at most $t_K$. If their count were $c>K$, then $p_{(c)}\le t_K\le t_c$, contradicting the maximality of $K$. Thus the rejection count is exactly $K$; if $K=0$ it is zero by definition. These finite comparisons also show that the BH rank and rejection indicators are Borel functions.

Fix $i$ and put $R_i=\widehat k_q(p^{(i)})$, where only coordinate $i$ is set to zero. The first rank qualifies, so $R_i\ge1$. Lowering a coordinate cannot increase any order statistic, so $R_i\ge K$; clearly $R_i\le N$ and $R_i$ is a function only of $(p_j)_{j\ne i}$. If $p_i\le t_{R_i}$, at least $R_i$ coordinates of $p^{(i)}$ lie below $t_{R_i}$ and restoring $p_i$ preserves this property. Consequently $K\ge R_i$, hence $K=R_i\ge1$ and $i$ is rejected. Conversely, if $i$ is rejected then $K\ge1$ and $p_i\le t_K\le t_{R_i}$; the preceding implication then gives $K=R_i$. Therefore, writing $R_q=R_q(p)$,

$$
\frac{\mathbf1\{i\in\mathcal R_q\}}{R_q\vee1}=\frac{\mathbf1\{p_i\le t_{R_i}\}}{R_i}.
$$

All inequalities are non-strict at the testing thresholds. Thus this proof includes ties, equality at a threshold, $N=1$ and $R_q=0$.

### Step 6: conditional calculation and composite-null domination

Fix an arbitrary admissible multifactor model with finite positive integers $N,d$. Put $s_i=\sqrt{1-r_i^2}$. For $r_i>0$ define $Y_i=a_i^{\mathsf T}Z/r_i$. Since this linear functional is centered Gaussian with variance $\|a_i\|^2/r_i^2=1$, it has the standard normal marginal law, regardless of the covariance of the full testing vector. Let $\mathcal G_i=\sigma(Z,(\varepsilon_j)_{j\ne i})$. Every $p_j$ for $j\ne i$ is measurable for this sigma-field, hence so is $R_i$. The residual $\varepsilon_i$ is independent of $\mathcal G_i$ by the model definition. This is the conditional independence needed for the random rank; no independence of $Y_i$ and $R_i$ is claimed.

For $0<r_i<1$, the strict monotonicity of $\overline\Phi$ gives $\{p_i\le t_{R_i}\}=\{T_i\ge u_{R_i}\}$. Conditioning on $\mathcal G_i$ thus gives

$$
\mathbb E\!\left[\left.\frac{\mathbf1\{i\in\mathcal R_q\}}{R_q\vee1}\right|\mathcal G_i\right]=\frac{\overline\Phi((u_{R_i}-\theta_i-r_iY_i)/s_i)}{R_i}=\frac qN\rho^{\theta_i}_{r_i}(u_{R_i},Y_i).
$$

Here step 5 and $\overline\Phi(u_k)=qk/N$ were used. If $i\in I_0$, then $\theta_i\le0$, so the argument of the numerator tail is at least $(u_{R_i}-r_iY_i)/s_i$. Its decreasing tail is therefore no larger than the zero-mean numerator. This proves $\rho^{\theta_i}_{r_i}(u_{R_i},Y_i)\le\rho_{r_i}(u_{R_i},Y_i)$. The same pointwise monotonicity proves the target's displayed composite domination for all finite $v,y$ and $0\le r<1$.

For $r_i=1$, $T_i=\theta_i+Y_i$ is $\mathcal G_i$-measurable. The conditional expectation is $\mathbf1\{\theta_i+Y_i\ge u_{R_i}\}/R_i$. For $\theta_i\le0$ this is at most $\mathbf1\{Y_i\ge u_{R_i}\}/R_i=(q/N)\rho_1(u_{R_i},Y_i)$.

For $r_i=0$, $a_i=0$ and $T_i=\theta_i+\varepsilon_i$. The conditional expectation is instead $\overline\Phi(u_{R_i}-\theta_i)/R_i\le\overline\Phi(u_{R_i})/R_i=q/N$ for every true null. This computation does not use a factor projection or an infinite argument in the finite-variable composite kernel. In the target's zero-loading event convention, use $Y_i=-\infty$ only to label the central event; the dominating kernel is the constant $\rho_0=1$.

Finally any central or shell indicator is $Z$-measurable, hence $\mathcal G_i$-measurable. Multiplying each equality or inequality above by that indicator and taking expectations establishes exactly the target's asserted central/shell dominations, for both nondegenerate and degenerate conditional coordinates.

### Step 7: decomposition and the three loading classes

Write $C_i=\mathbf1\{Y_i\le U\}$, with $C_i=1$ at zero loading according to the event-label convention; its complement is the shell indicator. Summing the two complementary contributions over $I_0=\{i:\theta_i\le0\}$ gives $\mathrm{Ce}+\mathrm{Sh}=\mathbb E[\sum_{i\in I_0}\mathbf1\{i\in\mathcal R_q\}/(R_q\vee1)]=\mathrm{FDR}$. Step 6 gives

$$
\mathrm{Ce}\le\frac qN\sum_{i\in I_0}\mathbb E[\rho_{r_i}(u_{R_i},Y_i)C_i],
$$

and the same inequality with $1-C_i$ for the shell. At zero loading the kernel on this display means the constant $1$, independent of the event label.

For $0<r_i<1$, the standard normal marginal law established in step 6 and $u_{R_i}\ge U$ give

$$
\mathbb E[\rho_{r_i}(u_{R_i},Y_i)C_i]\le\int_{-\infty}^U\phi(y)\sup_{v\ge U}\rho_{r_i}(v,y)\,dy\le\tfrac12+\frac{\gamma_iU}{\sqrt{2\pi}}.
$$

Only the marginal law is used; the possibly dependent random rank has been removed pointwise by the supremum. At $r_i=1$, the product $\rho_1(u_{R_i},Y_i)C_i$ can be nonzero only if $Y_i\ge u_{R_i}\ge U$ and $Y_i\le U$. This implies $Y_i=U$, an event of probability zero. The product is finite for every realization, since its denominator is one of the finite positive $t_k$. Its expectation is therefore zero, which is at most $1/2+\gamma_iU/\sqrt{2\pi}=1/2$. At $r_i=0$, the dominating contribution equals $1$ and step 6 bounds the actual central contribution by $q/N$. This case does not use a standard normal law for the artificial label $Y_i=-\infty$.

### Step 8: exact small-level certificate and conclusion

For $z\ge0$ set $h(z)=1-z+z^2/2-e^{-z}$. Then $h(0)=h'(0)=0$ and $h''(z)=1-e^{-z}\ge0$, so $e^{-z}\le1-z+z^2/2$. Put $a=\sqrt{\pi/2}$ and integrate this inequality with $z=x^2/2$ over $[0,a]$. Since $a/\sqrt{2\pi}=1/2$, this gives

$$
\int_0^a\phi(x)\,dx\le\frac{a-a^3/6+a^5/40}{\sqrt{2\pi}}=\tfrac12(1-\pi/12+\pi^2/160).
$$

Consequently $\overline\Phi(a)\ge f(\pi)$, where $f(p)=p/24-p^2/320$. For $157/50\le p\le4$, $f'(p)=1/24-p/160\ge1/60>0$. The elementary bounds $157/50<\pi<4$ therefore give the exact strict certificate

$$
\overline\Phi(\sqrt{\pi/2})\ge f(\pi)>f(157/50)=\frac{240053}{2400000}>\frac1{10}.
$$

This certificate follows from explicit integration and rational arithmetic. If $0<q\le1/10$, decreasingness of the normal tail implies $U>\sqrt{\pi/2}$, so $1<1/2+U/\sqrt{2\pi}$. Thus the zero-loading contribution from step 7 obeys its required bound because $\gamma_i=1$. Combining it with the $0<r_i<1$ and $r_i=1$ bounds and summing over the finite null set yields

$$
\mathrm{Ce}\le\frac qN\sum_{i\in I_0}\left(\tfrac12+\frac{\gamma_iU}{\sqrt{2\pi}}\right).
$$

If the null set is empty both sides are zero. The scalar proof above uses only $0<q<1/2$; the restriction $q\le1/10$ has been used only for this BH consequence. All finite model dimensions, arbitrary alternative means, nonpositive null means, loading orientations and admissible singular covariances were retained throughout.

## Extracted proof awaiting native execution

Notation as in `## Plan`; $N$ tests, $0<q<1/2$, $U=\overline\Phi^{-1}(q)$, $t_k=qk/N$, $u_k=\overline\Phi^{-1}(t_k)\ge U$. All statements are for an arbitrary [Gaussian multifactor representation](../definitions/gaussian_multifactor_representation.md) $T_i=\theta_i+a_i^{\mathsf T}Z+s_i\varepsilon_i$, $r_i=\|a_i\|$, $s_i=\sqrt{1-r_i^2}$; $\mathfrak B_1$ is the special case of step 0.

**Step 1 (forced-zero identity).** Fix $p\in[0,1]^N$ and $i$. For any vector $p'$ write $R(p')=\widehat k_q(p')$ (BH definition). *Claim 0:* $R(p')=|\{j:p'_j\le qR(p')/N\}|$. Indeed, if $k=R(p')\ge1$ then $p'_{(k)}\le qk/N$ so at least $k$ coordinates are $\le qk/N$; if $c>k$ coordinates were $\le qk/N$, then $p'_{(c)}\le qk/N\le qc/N$ and $c$ would qualify, contradicting maximality; for $k=0$ the rejection set is empty by definition. Let $p^{(i)}$ be $p$ with $p_i$ replaced by $0$ and $R_i=R(p^{(i)})$. Then $p^{(i)}_{(1)}=0\le q/N$, so $R_i\ge1$; $R_i$ is a function of $(p_j)_{j\ne i}$; and $R_i\ge R:=R(p)$, because lowering a coordinate does not increase any order statistic, so every rank qualifying for $p$ qualifies for $p^{(i)}$. *Identity:* $\mathbf 1\{i\in\mathcal R_q\}/(R\vee1)=\mathbf 1\{p_i\le t_{R_i}\}/R_i$. If $i\in\mathcal R_q$ then $R\ge1$ and $p_i\le t_R$; with $k=R_i$, $p^{(i)}$ has at least $k$ coordinates $\le t_k$ (Claim 0), and restoring $p_i\le t_R\le t_k$ keeps them $\le t_k$, so $k$ qualifies for $p$, $k\le R$, hence $R_i=R$ and both sides equal $1/R$. If $i\notin\mathcal R_q$ but $p_i\le t_{R_i}$, restoring $p_i$ keeps at least $R_i$ coordinates $\le t_{R_i}$, so $R\ge R_i$, $R=R_i\ge1$ and $p_i\le t_R$, i.e. $i\in\mathcal R_q$, a contradiction. So both sides vanish. This covers ties, threshold equalities and $R=0$. $\square$

**Step 2 (conditional formula; one-sided composite domination).** (a) For $s>0$ put $\rho^\theta_r(v,y)=\overline\Phi((v-\theta-ry)/s)/\overline\Phi(v)$; for $r=1$, $\rho^\theta_1(v,y)=\mathbf 1\{\theta+y\ge v\}/\overline\Phi(v)$. Let $Y_i=a_i^{\mathsf T}Z/r_i$ if $r_i>0$ (any fixed unit-vector projection if $r_i=0$). Given $Z$ the coordinates are independent, so $p_i=\overline\Phi(T_i)$ and $R_i$ (a function of $(p_j)_{j\ne i}$) are conditionally independent. Since $\overline\Phi$ is a continuous strictly decreasing bijection $\mathbb R\to(0,1)$, $\{p_i\le t\}=\{T_i\ge\overline\Phi^{-1}(t)\}$, whose conditional probability given $Z$ is $\overline\Phi((\overline\Phi^{-1}(t)-\theta_i-r_iY_i)/s_i)$ ($s_i>0$) or $\mathbf 1\{\theta_i+Y_i\ge\overline\Phi^{-1}(t)\}$ ($s_i=0$). Taking $t=t_{R_i}=\overline\Phi(u_{R_i})$ in step 1 and conditioning first on $(Z,(\varepsilon_j)_{j\ne i})$:

$$
\mathbb E\Big[\frac{\mathbf 1\{i\in\mathcal R_q\}}{R_q\vee1}\Big|Z\Big]=\mathbb E\Big[\frac{\overline\Phi(u_{R_i})\rho^{\theta_i}_{r_i}(u_{R_i},Y_i)}{R_i}\Big|Z\Big]=\frac qN\mathbb E\big[\rho^{\theta_i}_{r_i}(u_{R_i},Y_i)\big|Z\big],
$$

using $\overline\Phi(u_k)/k=q/N$. *Domination:* $\theta_i\le0$ gives $(v-\theta_i-ry)/s\ge(v-ry)/s$, and $\overline\Phi$ is decreasing, so $\rho^{\theta_i}_r\le\rho_r:=\rho^0_r$; at $r=1$, $\{\theta_i+y\ge v\}\subset\{y\ge v\}$.
Consequence used below: with $\mathrm{Ce}=\sum_{i\in I_0}\mathbb E[\frac{\mathbf 1\{i\in\mathcal R_q\}}{R_q\vee1}\mathbf 1\{Y_i\le U\}]$ and $\mathrm{Sh}$ the same with $\mathbf 1\{Y_i>U\}$ (for $r_i=0$ we put $Y_i:=-\infty$, so these nulls are in Ce), $\mathrm{FDR}=\mathrm{Ce}+\mathrm{Sh}$ exactly, and since $Y_i$ is $Z$-measurable, $\mathrm{Ce}\le\frac qN\sum_{i\in I_0}\mathbb E[\rho_{r_i}(u_{R_i},Y_i)\mathbf 1\{Y_i\le U\}]$, likewise for Sh.

**Step 3 (Lemma C).** *Claim.* For $r\in[0,1)$, $s=\sqrt{1-r^2}$, all real $y$ and all $v\ge U$:

$$
\phi(y)\rho_r(v,y)\le\frac1s\phi\Big(\frac{(rv-y)_+}{s}\Big)\le\frac1{s\sqrt{2\pi}},\qquad\int_{-\infty}^U\phi(y)\sup_{v\ge U}\rho_r(v,y)\,dy\le\frac12+\frac{\gamma_rU}{\sqrt{2\pi}} .
$$

*Proof.* The standard bivariate normal density with correlation $r$ factors both ways, $\phi(x)s^{-1}\phi((y-rx)/s)=\phi(y)s^{-1}\phi((x-ry)/s)$; integrating over $x\ge v$ gives $\phi(y)\overline\Phi((v-ry)/s)=\int_v^\infty\phi(x)s^{-1}\phi((y-rx)/s)dx$. For $x\ge v$, $|y-rx|\ge(rx-y)_+\ge(rv-y)_+$ ($r\ge0$), and $\phi$ is decreasing in $|\cdot|$, so the integral is $\le s^{-1}\phi((rv-y)_+/s)\overline\Phi(v)$; divide by $\overline\Phi(v)$. For $v\ge U$, $(rv-y)_+\ge(rU-y)_+$, so $\sup_{v\ge U}\phi(y)\rho_r(v,y)\le s^{-1}\phi((rU-y)_+/s)$ (the supremum is measurable: $\rho_r(\cdot,y)$ is continuous, take rational $v$). Then $\int_{-\infty}^{rU}s^{-1}\phi((rU-y)/s)dy=\frac12$ and $\int_{rU}^U s^{-1}(2\pi)^{-1/2}dy=\frac{(1-r)U}{s\sqrt{2\pi}}=\frac{\gamma_rU}{\sqrt{2\pi}}$, since $(1-r)/\sqrt{1-r^2}=\sqrt{(1-r)/(1+r)}$. This includes $r=0$ ($s=1$). At $r=1$, $\rho_1(v,y)=0$ for $y<U\le v$, so the integral is $0$. $\square$
*Consequences.* (i) For $0<q\le1/10$ and every multifactor model, $\mathrm{Ce}\le\frac qN\sum_{i\in I_0}(\frac12+\frac{\gamma_iU}{\sqrt{2\pi}})$: for $r_i>0$ bound $\rho_{r_i}(u_{R_i},Y_i)\mathbf 1\{Y_i\le U\}\le\sup_{v\ge U}\rho_{r_i}(v,Y_i)\mathbf 1\{Y_i\le U\}$ (as $u_{R_i}\ge U$) and integrate against the standard normal law of $Y_i$; for $r_i=0$, $\rho_0\equiv1$ and $1\le\frac12+\frac U{\sqrt{2\pi}}$ because $q\le1/10<\overline\Phi(\sqrt{\pi/2})$.

## Provenance

Selected verbatim from [the free-center pooled-shell plan](../plans/plan_gaussian_bh_one_sided_free_center_pooled_shell_20261106.md), Progress: the Step 3 kernel claim and Consequence (i), with Step 1, Step 2(a) and its composite domination, the Ce definition, and Step 3 through Consequence (i) as the proof. The unrelated Step 2(b) exogenous-rank assertion is omitted. The original range $0<q\le1/10$ for the BH central-contribution bound and the source zero-loading event convention are retained. Source Plan supplies the local kernel notation. Consequence (ii) about deterministic DCL is outside this core selection; the original compound draft remains preserved under its original ID. Only display-math line breaks are normalized. No independent verification verdict is asserted.
