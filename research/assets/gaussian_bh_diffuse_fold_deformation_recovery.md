---
type: lemma
title: >-
  Signed sublinear-cost deformation recovery at an isolated diffuse Gaussian BH
  fold
status: approved
source:
  kind: original
depends_on:
  - gaussian_bh_common_loading_wasserstein_fdr_continuity
uses_definitions:
  - gaussian_bh_two_direction_quantile_fold
  - gaussian_bh_common_loading_tagged_population
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags:
  - gaussian_bh
  - diffuse_fold
  - signed_deformation_recovery
  - finite_competitors
---

## Statement

Fix the [two-direction Gaussian quantile-fold model](../definitions/gaussian_bh_two_direction_quantile_fold.md), including its $q\in(0,1/2)$, $\sigma,p\in(0,1)$, distinct unit residual directions $v_0,v_1$, standard jointly Gaussian scores $X_0,Y$ with correlation $\rho\in(-1,1)$, and deterministic tagged law
$$
\pi=p\delta_{(0,v_0,1)}+(1-p)\int_0^1\delta_{(\vartheta(c),v_1,0)}\,dc.
$$
The quantile $\vartheta\in C^3([0,1])$ is strictly decreasing with $\vartheta(1)>0$. In the notation $u(r)=S^{-1}(qr)$, $r(c)=p+(1-p)c$, the barrier $g(c)=u(r(c))-\vartheta(c)$ has its unique global minimum $b=g(c_*)$ at $c_*\in(0,1)$, with $g''(c_*)>0$, and $r_*=r(c_*)$. Use the actual common-cutoff counts $H_\pi,V_\pi$, largest non-strict crossing $\rho_\pi$, full fractional FDP $D_\pi$ and full FDR $F(\pi)$ of the [common-loading tagged population](../definitions/gaussian_bh_common_loading_tagged_population.md). The following conclusions are to be proved.

1. **Actual full-FDR representation.** For the auxiliary forced-true rank
$$
r_\vartheta(y)=\sup\bigl(\{p\}\cup\{r(c):0<c\le1,\ y\ge g(c)\}\bigr),
$$
the true atom is rejected by the actual population BH rule exactly when $X_0\ge u(r_\vartheta(Y))$. On that event $\rho_\pi=r_\vartheta(Y)$ and $D_\pi=p/r_\vartheta(Y)$; on its complement $D_\pi=0$, including any positive false-only actual crossing. Consequently
$$
F(\pi)=\int_{\mathbb R}k(y,r_\vartheta(y))\phi(y)\,dy,\qquad
k(y,r)=\frac p r S\!\left(\frac{u(r)-\rho y}{\sqrt{1-\rho^2}}\right).
$$
This formula is derived from the actual globally largest crossing, not a separately optimized rank. The same assertion applies to each admissible perturbed quantile below.

2. **Both admissible deformations and sublinear cost.** For the fixed bump $\chi$ in the definition there is a finite $K>0$, depending only on the fixed model and $\chi$, such that for each $\delta\in\{-1,+1\}$ and all sufficiently small $\epsilon>0$,
$$
\vartheta_\epsilon^\delta(c)=\vartheta(c)-\delta\epsilon\chi\!\left(\frac{c-c_*}{K\sqrt\epsilon}\right)
$$
is positive and strictly decreasing on $[0,1]$, its barrier $g_\epsilon^\delta=u\circ r-\vartheta_\epsilon^\delta$ has its unique global minimum exactly $b+\delta\epsilon$ at $c_*$, and its tagged law $\pi_\epsilon^\delta$ preserves both directions, all labels and the true zero-mean atom. For the approved tagged Wasserstein metric,
$$
W_1(\pi_\epsilon^\delta,\pi)\le4K(1-p)\epsilon^{3/2}=o(\epsilon).
$$

3. **Signed first variation with all crossing switches retained.** With the signed original conditional-FDP jump $\Delta=k(b,r_*)-k(b,p)$, both one-sided deformation limits exist and satisfy
$$
\lim_{\epsilon\downarrow0}\frac{F(\pi_\epsilon^\delta)-F(\pi)}\epsilon
=-\delta\phi(b)\Delta\qquad(\delta=-1,+1).
$$
In particular the entire signed jump, rather than its positive part or absolute value, occurs. The global largest-crossing comparison must control all competing roots: there is a finite constant $C$ depending only on the fixed model and bump for which the auxiliary ranks can differ only when $|y-b|\le C\epsilon$. In this window, whenever both folds are present (that is, $y\ge\max\{b,b+\delta\epsilon\}$), both auxiliary ranks are within $C\sqrt\epsilon$ of $r_*$. In the birth/death interval between $b$ and $b+\delta\epsilon$, whose length is exactly $\epsilon$, the inactive auxiliary rank is $p$ and the active one tends uniformly to $r_*$. These are global conclusions to establish, including non-strict boundary crossings; they justify the signed formula and the $O(\epsilon^{3/2})$ common-active contribution, rather than assuming a locally chosen branch gives the actual rank.

4. **Ordinary canonical finite recovery.** Use the approved [Wasserstein continuity and canonical finite-approximation theorem](gaussian_bh_common_loading_wasserstein_fdr_continuity.md) as an explicit dependency. For each sign and each sufficiently small $\epsilon>0$, choose a finite rational tagged law
$$
\nu_\epsilon^\delta=\sum_{j=1}^{m_\epsilon^\delta}\frac{k_{\epsilon j}^\delta}{N_\epsilon^\delta}
\delta_{(\theta_{\epsilon j}^\delta,v_{\epsilon j}^\delta,\ell_{\epsilon j}^\delta)},\qquad
N_\epsilon^\delta=\sum_j k_{\epsilon j}^\delta,
$$
where $m_\epsilon^\delta$ and every $k_{\epsilon j}^\delta$ are positive integers, each direction is a unit vector, and the labels are canonical:
$$
\ell_{\epsilon j}^\delta=\mathbf1_{\{\theta_{\epsilon j}^\delta\le0\}},\qquad
\ell_{\epsilon j}^\delta=0\Longrightarrow\theta_{\epsilon j}^\delta>0.
$$
Realize each weight by exactly $k_{\epsilon j}^\delta$ identical copies of $\theta_{\epsilon j}^\delta+\sqrt{1-\sigma^2}X(v_{\epsilon j}^\delta)+\sigma Z$. These are ordinary [finite Gaussian models](../definitions/gaussian_multiple_testing_model.md), possibly with singular covariance, with unit marginal variances and the [canonical one-sided p-values and true-null labels](../definitions/gaussian_test_pvalues.md). Their [ordinary largest-rank BH](../definitions/benjamini_hochberg_step_up.md) [FDR](../definitions/false_discovery_rate.md) at the same $q,\sigma$ is $F(\nu_\epsilon^\delta)$, and they can be chosen to satisfy simultaneously
$$
W_1(\nu_\epsilon^\delta,\pi_\epsilon^\delta)\le\epsilon^2,\qquad
|F(\nu_\epsilon^\delta)-F(\pi_\epsilon^\delta)|\le\epsilon^2.
$$
It follows that
$$
W_1(\nu_\epsilon^\delta,\pi)\le4K(1-p)\epsilon^{3/2}+\epsilon^2=o(\epsilon),\qquad
\lim_{\epsilon\downarrow0}\frac{F(\nu_\epsilon^\delta)-F(\pi)}\epsilon=-\delta\phi(b)\Delta.
$$
The finite test counts may depend arbitrarily on $\epsilon$; they are not restricted to any old rare-clone profile. Recovery uses values after proving the diffuse variation, without passing a finite-copy derivative through a limit.

5. **Conditional finite-comparison balance.** If there is a finite $\lambda\ge0$ such that
$$
F(\nu)\le F(\pi)+\lambda W_1(\nu,\pi)
$$
against every ordinary canonical finite competitor at this fixed $q,\sigma$ (in particular against both recovered families above), then $\Delta=0$. Both signs are needed for this conclusion. Existence of such a comparison point or multiplier is not asserted.

6. **Nonempty hypotheses.** Linear quantiles $\vartheta(c)=M-ac$ with $M>a>0$ and
$$
\frac{q(1-p)}{\phi(u(1))}<a<\frac{q(1-p)}{\phi(u(p))}
$$
give an interior strictly convex barrier minimum and hence satisfy the isolated-fold condition. The interval is nonempty for every fixed $q,p$ in the stated ranges; $M>a$ ensures every alternative mean remains strictly positive.

## Scope and provenance

This is an original scoped supporting target extracted from the local quantile-bump proposal and fifth autonomous reassessment. It is draft and contains no completed proof. Constants may depend on the fixed population and bump. It neither assumes nor proves an Ekeland comparison point, a special-family near-maximizer, a finite positive-definite optimizer, an interchange with a jitter limit, a finite rare-clone derivative extension, arbitrary-population deformation recovery, a uniform $q$-scale boundary payment, or either unrestricted main order bound. The cross-field deformation-lifting source motivates the proposal only and supplies no black-box BH theorem or dependency. Existing approved statements and historical attempts are not revised by this target.

## Proof

Throughout the proof $u(r)=S^{-1}(qr)$, so $u'(r)=-q/\phi(u(r))<0$ for $p\le r\le1$. All constants and smallness thresholds below depend only on the fixed model and bump. The historical scope paragraph above records the target before execution; the proof supplied here establishes exactly its six stated conclusions.

### 1. Actual rejection and the forced-true rank

First fix any continuous positive strictly decreasing quantile $h$ on $[0,1]$, using the same $p$, directions and Gaussian scores as in the statement. This argument will apply to $h=\vartheta$ and to both admissible perturbed quantiles. For fixed $y\in\mathbb R$ put
$$
A_y^h(r)=(1-p)\int_0^1\mathbf1_{\{h(t)+y\ge u(r)\}}\,dt,\qquad H_y^{+,h}(r)=p+A_y^h(r),\quad 0<r\le1.
$$
For $0<c\le1$ and $r=r(c)$ we claim
$$
H_y^{+,h}(r(c))\ge r(c)\quad\Longleftrightarrow\quad h(c)+y\ge u(r(c)).
$$
Indeed, if the right inequality holds, monotonicity of $h$ makes every $t\le c$ qualify, giving $A_y^h(r(c))\ge(1-p)c$. Conversely, if $h(c)+y<u(r(c))$, continuity gives a left neighborhood of $c$ on which the inequality still fails. Since $c>0$, this neighborhood contains an interval of positive length within $[0,c]$; monotonicity makes every $t\ge c$ fail as well. Thus the measure of the qualifying set is strictly less than $c$, and the left inequality fails. This includes $c=1$ and uses non-strict qualification on the right.

Define $g_h(c)=u(r(c))-h(c)$ and $C_h(y)=\{c\in[0,1]:g_h(c)\le y\}$. This is compact, possibly empty. Including $c=0$ adds at most $r(0)=p$, which is included separately, so
$$
R_h(y):=\max\bigl(\{p\}\cup r(C_h(y))\bigr)
=\sup\bigl(\{p\}\cup\{r(c):0<c\le1,\ y\ge g_h(c)\}\bigr).
$$
The forced count qualifies at $p$ because $H_y^{+,h}(p)\ge p$. The preceding equivalence proves that $R_h(y)$ is its attained globally largest qualifying rank: it qualifies whether it equals $p$, lies in $(p,1)$ or equals $1$, and every qualifying rank above $p$ corresponds to a point of $C_h(y)$. In particular $R_h$ is nondecreasing in $y$ and hence measurable.

For a fixed Gaussian realization with $Y=y$, the actual count $H_h$ is bounded by $H_y^{+,h}$. Consequently every actual qualifying rank is at most $R_h(y)$, and the actual largest rank $a=\rho_h$ satisfies $a\le R_h(y)$. Positive actual suprema are attained: for qualifying $a_n\to a>0$, monotonicity of $H_h$ gives $H_h(a)\ge H_h(a_n)\ge a_n$, hence $H_h(a)\ge a$. If $X_0\ge u(R_h(y))$, the true atom is included at $R_h(y)$, so there $H_h=H_y^{+,h}\ge R_h(y)$. Thus $a=R_h(y)$ and the true atom is rejected. Conversely, if the true atom is rejected, then $a>0$ and
$$
X_0\ge u(a)\ge u(R_h(y)).
$$
We have proved the exact rejection equivalence and the pathwise full-FDP identity
$$
D_h=\frac{p}{R_h(Y)}\mathbf1_{\{X_0\ge u(R_h(Y))\}}.
$$
On the complementary event there is no rejected true mass, so this identity also covers positive alternative-only actual crossings and rank zero. It makes no assertion that $a=R_h(Y)$ there.

Conditionally on $Y=y$, $X_0$ is Gaussian with mean $\rho y$ and variance $1-\rho^2>0$. Therefore
$$
\mathbb E[D_h\mid Y=y]=\frac{p}{R_h(y)}S\!\left(\frac{u(R_h(y))-\rho y}{\sqrt{1-\rho^2}}\right)=k(y,R_h(y)).
$$
Integration against the standard normal density of $Y$ yields the claimed actual full-FDR representation, first for $h=\vartheta$ and, once admissibility is established below, for every $h=\vartheta_\epsilon^\delta$. No rankwise optimization of the conditional FDP was used.

### 2. Both admissible quantiles and their cost

The interior minimum gives $g'(c_*)=0$ and
$$
\vartheta'(c_*)=(1-p)u'(r_*)<0.
$$
Taylor expansion at $c_*$, $g''(c_*)>0$, and continuity of $\vartheta'$ allow constants $\eta,\alpha,\beta,m>0$ with $I=[c_*-\eta,c_*+\eta]\subset(0,1)$ such that
$$
\alpha(c-c_*)^2\le g(c)-b\le\beta(c-c_*)^2,\qquad \vartheta'(c)\le-m\quad(c\in I).
$$
Uniqueness of the global minimum and compactness give
$$
d_\eta:=\min_{c\in[0,1],\ |c-c_*|\ge\eta}(g(c)-b)>0.
$$
Choose a fixed $K>0$ with $\alpha K^2>1$ and set $C_0=4\beta K^2+1$. For both signs restrict to a single sufficiently small positive $\epsilon$ regime in which
$$
2K\sqrt\epsilon<\eta,\qquad (C_0+2)\epsilon<d_\eta,\qquad \epsilon<\frac{\vartheta(1)}2,\qquad \frac{\sqrt\epsilon}{K}\|\chi'\|_\infty<\frac m2.
$$
Each $\vartheta_\epsilon^\delta$ is $C^3$, and on $I$ its derivative is
$$
(\vartheta_\epsilon^\delta)'(c)=\vartheta'(c)-\delta\frac{\sqrt\epsilon}{K}\chi'\!\left(\frac{c-c_*}{K\sqrt\epsilon}\right)\le-\frac m2<0.
$$
Outside the bump support $|c-c_*|\le2K\sqrt\epsilon$ it equals $\vartheta$. In particular it agrees with $\vartheta$ near both boundaries of $I$. Strict decrease on $I$ and strict decrease of the unchanged pieces to its left and right, with matching boundary values, prove strict decrease globally. Also $\vartheta_\epsilon^\delta(c)\ge\vartheta(1)-\epsilon>\vartheta(1)/2>0$ everywhere. This justifies applying part 1 to both perturbations.

Write $g_\epsilon^\delta=g+\delta\epsilon\chi((c-c_*)/(K\sqrt\epsilon))$. For $\delta=-1$ one has
$$
g_\epsilon^-(c)\ge g(c)-\epsilon\ge b-\epsilon.
$$
Equality forces $g(c)=b$, hence $c=c_*$; at that point equality indeed holds. For $\delta=+1$, on $|c-c_*|\le K\sqrt\epsilon$ the bump equals one, so $g_\epsilon^+(c)=g(c)+\epsilon\ge b+\epsilon$, with equality only at $c_*$. On the rest of $I$, $|c-c_*|>K\sqrt\epsilon$ and nonnegativity of the bump give
$$
g_\epsilon^+(c)\ge g(c)\ge b+\alpha(c-c_*)^2>b+\alpha K^2\epsilon>b+\epsilon.
$$
Outside $I$ it is at least $b+d_\eta>b+\epsilon$. Thus the global minimum is uniquely at $c_*$ and equals $b+\delta\epsilon$ for either sign.

The perturbed tagged law is deterministic, has bounded means, and preserves the two directions, every tag and the true zero-mean atom. Couple the true atoms identically and couple each alternative indexed by $c$ to the perturbed alternative at the same $c$. Under the tagged cost in the approved [common-loading tagged Gaussian population definition](../definitions/gaussian_bh_common_loading_tagged_population.md), only the mean difference contributes. Hence
$$
W_1(\pi_\epsilon^\delta,\pi)\le(1-p)\epsilon\int_0^1\chi\!\left(\frac{c-c_*}{K\sqrt\epsilon}\right)dc\le4K(1-p)\epsilon^{3/2}=o(\epsilon).
$$

### 3. Global sublevel sets and all crossing switches

Put $R(y)=r_\vartheta(y)$ and $R_\epsilon^\delta(y)=r_{\vartheta_\epsilon^\delta}(y)$. On $J_\epsilon=\{c\in[0,1]:|c-c_*|\le2K\sqrt\epsilon\}\subset I$, the quadratic upper bound gives
$$
g(c)\le b+4\beta K^2\epsilon,\qquad g_\epsilon^\delta(c)\le g(c)+\epsilon\le b+C_0\epsilon.
$$
For every $y\ge b+C_0\epsilon$ all of $J_\epsilon$ is in both sublevel sets; outside $J_\epsilon$ the barriers agree. Therefore, as sets over the entire parameter interval,
$$
\{c\in[0,1]:g(c)\le y\}=\{c\in[0,1]:g_\epsilon^\delta(c)\le y\}\qquad(y\ge b+C_0\epsilon).
$$
Below $b-\epsilon$ both sublevel sets are empty by their exact minimum heights. Their largest auxiliary ranks are thus identical outside
$$
W_\epsilon=[b-\epsilon,b+C_0\epsilon],
$$
and above its upper endpoint the equality holds including the endpoint. This argument includes any roots or higher wells away from $c_*$, regardless of their number or local geometry.

For $y\in W_\epsilon$, if $c$ qualifies for either barrier, then $g(c)\le y+\epsilon\le b+(C_0+1)\epsilon<b+d_\eta$. Hence $|c-c_*|<\eta$, and the quadratic lower bound gives
$$
|c-c_*|\le L\sqrt\epsilon,\qquad L:=\sqrt{\frac{C_0+1}{\alpha}}.
$$
When a given fold is active, namely $y\ge b$ for the original or $y\ge b+\delta\epsilon$ for the perturbed barrier, its point $c_*$ qualifies. Its entire qualifying set lies in the displayed neighborhood, so its global largest auxiliary rank satisfies
$$
0\le R_h(y)-r_*\le(1-p)L\sqrt\epsilon.
$$
Here $h$ denotes the corresponding active quantile, and $r_*>p$ ensures that inclusion of $p$ separately cannot alter the maximum. If that fold is inactive its sublevel set is empty and its auxiliary rank is exactly $p$.

More precisely, for $\delta=+1$ the original alone is active on $[b,b+\epsilon)$; for $\delta=-1$ the perturbed fold alone is active on $[b-\epsilon,b)$. The lower endpoints are included because crossings are non-strict. At each upper endpoint both folds are active. Below the respective one-active interval both are inactive, and above it inside $W_\epsilon$ both are active. Choose a fixed
$$
C\ge\max\{1,C_0,(1-p)L\}.
$$
Then rank differences are confined to $|y-b|\le C\epsilon$, and both active-rank estimates have the constant $C$. In the one-active interval the active rank converges uniformly to $r_*$ and the inactive rank is exactly $p$. These conclusions concern the global maxima of the entire sublevel sets, including all competing crossings.

### 4. Signed integration and its remainder

Let $f(y,r)=k(y,r)\phi(y)$. For completeness put $s=\sqrt{1-\rho^2}>0$ and $z=(u(r)-\rho y)/s$. Direct differentiation gives
$$
\partial_r f(y,r)=\phi(y)\left[-\frac p{r^2}S(z)-\frac p r\phi(z)\frac{u'(r)}s\right],
$$
$$
\partial_y f(y,r)=\frac p r\left[-y\phi(y)S(z)+\phi(y)\phi(z)\frac\rho s\right].
$$
Since $p>0$, $u$ is smooth on $[p,1]$, and $s>0$, both derivatives are bounded in absolute value by a finite constant $B$ on $[b-1,b+1]\times[p,1]$. Decrease the common $\epsilon$ threshold so that $W_\epsilon\subset[b-1,b+1]$. Thus $f$ is Lipschitz on this rectangle in both arguments with constant $B$.

Part 1 gives the exact difference of FDR values as the integral of $f(y,R_\epsilon^\delta(y))-f(y,R(y))$. It vanishes outside $W_\epsilon$. On the common-active part of that window, part 3 gives
$$
|f(y,R_\epsilon^\delta(y))-f(y,R(y))|\le B|R_\epsilon^\delta(y)-R(y)|\le2BC\sqrt\epsilon.
$$
The window has length $(C_0+1)\epsilon$, so this part of the integral is $O(\epsilon^{3/2})$. On the common-inactive part the integrands agree exactly.

For $\delta=+1$, on $[b,b+\epsilon)$ the perturbed rank is $p$ and the original active rank is within $C\sqrt\epsilon$ of $r_*$. Consequently, uniformly on this interval,
$$
f(y,R_\epsilon^+(y))-f(y,R(y))
=f(b,p)-f(b,r_*)+O(\sqrt\epsilon)
=-\phi(b)\Delta+O(\sqrt\epsilon).
$$
For $\delta=-1$, on $[b-\epsilon,b)$ the original rank is $p$ and the perturbed rank is active, giving uniformly
$$
f(y,R_\epsilon^-(y))-f(y,R(y))
=f(b,r_*)-f(b,p)+O(\sqrt\epsilon)
=\phi(b)\Delta+O(\sqrt\epsilon).
$$
These errors follow from the displayed Lipschitz bounds, $|y-b|\le\epsilon$ and the uniform active-rank bound; no differentiability of the roots is needed. Each interval has length exactly $\epsilon$. Endpoint singleton levels have zero Gaussian measure, with their non-strict rank values already accounted for in part 3. Combining the pieces proves
$$
F(\pi_\epsilon^\delta)-F(\pi)=-\delta\epsilon\phi(b)\Delta+O(\epsilon^{3/2}),\qquad \delta\in\{-1,+1\}.
$$
Division by $\epsilon$ gives both claimed limits. The computation retains the entire signed $\Delta$, which may be positive, zero or negative.

### 5. Ordinary canonical finite recovery

Use the approved [Wasserstein continuity and canonical finite-approximation theorem](gaussian_bh_common_loading_wasserstein_fdr_continuity.md), conclusions 3 and 4. For each fixed sign and fixed sufficiently small $\epsilon>0$, part 2 shows $\pi_\epsilon^\delta\in\mathcal P_1(\mathcal E)$ at the same $q,\sigma$ and Hilbert space. The theorem supplies a sequence of finite rational tagged laws converging to this fixed law in $W_1$, with their full FDR values also converging to $F(\pi_\epsilon^\delta)$. Choose one index large enough for both errors to be at most $\epsilon^2$ and call the resulting law $\nu_\epsilon^\delta$. Write it as
$$
\nu_\epsilon^\delta=\sum_{j=1}^{m_\epsilon^\delta}\frac{k_{\epsilon j}^\delta}{N_\epsilon^\delta}\delta_{(\theta_{\epsilon j}^\delta,v_{\epsilon j}^\delta,\ell_{\epsilon j}^\delta)},\qquad N_\epsilon^\delta=\sum_j k_{\epsilon j}^\delta,
$$
where the theorem ensures $m_\epsilon^\delta,k_{\epsilon j}^\delta$ are positive integers, $\|v_{\epsilon j}^\delta\|=1$, and
$$
\ell_{\epsilon j}^\delta=\mathbf1_{\{\theta_{\epsilon j}^\delta\le0\}},\qquad \ell_{\epsilon j}^\delta=0\Longrightarrow\theta_{\epsilon j}^\delta>0.
$$
Realize each atom by exactly $k_{\epsilon j}^\delta$ identical coordinates with score $\theta_{\epsilon j}^\delta+\tau X(v_{\epsilon j}^\delta)+\sigma Z$, where $\tau=\sqrt{1-\sigma^2}$. Indexing all copies by $i$, their covariance matrix has entries
$$
\Sigma_{ii'}=\tau^2\langle v_i,v_{i'}\rangle+\sigma^2.
$$
It is symmetric, has diagonal $\tau^2+\sigma^2=1$, and for every real vector $(a_i)$,
$$
\sum_{i,i'}a_i\Sigma_{ii'}a_{i'}=\tau^2\left\|\sum_i a_iv_i\right\|^2+\sigma^2\left(\sum_i a_i\right)^2\ge0.
$$
Joint Gaussianity follows from the finite family of isonormal evaluations and the independent Gaussian $Z$. Thus these are admissible [finite Gaussian models](../definitions/gaussian_multiple_testing_model.md), including possible singular covariance. Their p-values and null labels obey the [canonical one-sided convention](../definitions/gaussian_test_pvalues.md). Conclusion 4 of the dependency identifies their ordinary [largest-rank BH](../definitions/benjamini_hochberg_step_up.md) [FDR](../definitions/false_discovery_rate.md) with $F(\nu_\epsilon^\delta)$. In particular no alternative-tagged zero is used as an ordinary alternative.

The index choice gives simultaneously
$$
W_1(\nu_\epsilon^\delta,\pi_\epsilon^\delta)\le\epsilon^2,\qquad |F(\nu_\epsilon^\delta)-F(\pi_\epsilon^\delta)|\le\epsilon^2.
$$
The triangle inequality and parts 2 and 4 therefore give
$$
W_1(\nu_\epsilon^\delta,\pi)\le4K(1-p)\epsilon^{3/2}+\epsilon^2=o(\epsilon),
$$
$$
\frac{F(\nu_\epsilon^\delta)-F(\pi)}\epsilon=-\delta\phi(b)\Delta+O(\sqrt\epsilon)+O(\epsilon)\longrightarrow-\delta\phi(b)\Delta.
$$
This selects a finite model separately after each diffuse perturbation has been evaluated. The numbers of coordinates can depend arbitrarily on $\epsilon$; only convergence of values is used, with no derivative interchange or finite rare-clone restriction.

### 6. Conditional balance

Assume exactly the finite-comparison inequality in conclusion 5, with one fixed finite $\lambda\ge0$. It applies to each canonical ordinary finite law just constructed, so for each sign
$$
\frac{F(\nu_\epsilon^\delta)-F(\pi)}\epsilon\le\lambda\frac{W_1(\nu_\epsilon^\delta,\pi)}\epsilon\longrightarrow0
$$
on the right. The limit on the left from part 5 yields $-\delta\phi(b)\Delta\le0$. The plus sign gives $\Delta\ge0$ and the minus sign gives $\Delta\le0$, since $\phi(b)>0$. Hence $\Delta=0$. This is conditional on the displayed comparison and fixed multiplier; no existence of such a comparison point, multiplier or optimizer is asserted.

### 7. A nonempty linear family

For $\vartheta(c)=M-ac$, differentiation of the inverse survival function gives
$$
u'(r)=-\frac q{\phi(u(r))},\qquad u''(r)=\frac{q^2u(r)}{\phi(u(r))^2}.
$$
Consequently
$$
g'(c)=a-\frac{q(1-p)}{\phi(u(r(c)))},\qquad g''(c)=\frac{q^2(1-p)^2u(r(c))}{\phi(u(r(c)))^2}>0.
$$
Indeed $0<qr(c)\le q<1/2$, so $u(r(c))>0$. Since $p<1$, one has $u(p)>u(1)>0$, and strict decrease of $\phi$ on $(0,\infty)$ gives $\phi(u(p))<\phi(u(1))$. Thus
$$
\frac{q(1-p)}{\phi(u(1))}<\frac{q(1-p)}{\phi(u(p))},
$$
so the asserted interval for $a$ is nonempty. Choosing $a$ in that interval gives $g'(0)<0<g'(1)$. Continuity and strict positivity of $g''$ give a unique zero $c_*\in(0,1)$ of $g'$, which is the unique global minimum and is nondegenerate. Finally $M>a>0$ makes $\vartheta$ strictly decreasing, smooth and bounded below by $M-a>0$. These models meet the hypotheses of parts 1–6. All definitions and the sole theorem dependency used above are approved; no draft definition or additional unproved research claim is assumed.
