---
type: candidate
title: Correlated two-group mixed labels with the false-null group selected
status: failed
target_asset: gaussian_bh_rare_clone_mills_variation
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  H7: pass
  NOT: fail
mode: refute
round: 4
slot: 3
direction: small_cases
statement_digest: c7939c23ae577add03c56534f1a6ec07179140d4317ffdd0a9a1aaf699a67fea
performed_by: unknown
created_at: '2026-11-09T00:16:03.040Z'
extension_version: 0.0.4
---

## Object

Take $N=2$, $q=S(1)$, $\theta=(1,0)$, $\Sigma_{12}=\Sigma_{21}=1/2$, and select $i=1$. Use $G=(G_1,G_2)\sim N_2(0,I_2)$, $v_1=(1,0)$ and $v_2=(1/2,\sqrt3/2)$. Thus
$$
T_1=1+G_1,\qquad T_2=G_1/2+\sqrt3G_2/2,\qquad (\ell_1,\ell_2)=(0,1).
$$
Put $a=S^{-1}(q/2)>1$, $U=1$, $L=2\{h(1)-1\}$ and $c=1-m(1)>0$. Use precisely the definition's offset law and midpoint arrays. Fix
$$
0<\varepsilon<\varepsilon_0:=\min\{1/(2L),1/2,(a-1)/4\},
$$
and take $K\to\infty$ before $\varepsilon\downarrow0$.

This is a distinct test from the board's independent mixed pairs: the selected group is false-null, the background group is true-null, and their correlation is nonzero. In particular the conditional null-score law changes with $T_1$, so the independent-pair calculation cannot be reused as a factorization. The signed face jump below takes both signs; the all-alternative zero-FDP obstruction does not apply.

## Checks

### H1

Pass. The fixed finite size is the positive integer $N=2$.

### H2

Pass. $q=S(1)\in(0,1/2)$ and $U=1$.

### H3

Pass. The fixed mean vector $(1,0)$ is allowed, and its actual one-sided labels are $(0,1)$.

### H4

Pass. The covariance is unit diagonal and positive definite: its eigenvalues are $1/2$ and $3/2$.

### H5

Pass. The displayed finite-dimensional representation has unit row vectors and inner product $1/2$, and hence realizes exactly the specified covariance.

### H6

Pass. The selected index $i=1$ belongs to $[2]$.

### H7

Pass. All original data are fixed throughout both limits. For the displayed positive $\varepsilon$, $\varepsilon L<1$ and $\varepsilon/U<\theta_1=1$. The downward offsets therefore preserve the false-null label of every selected copy. Every background copy remains a zero-mean true null.

### NOT

Fail. All four conclusions hold in this object, as follows.

**Offset law and copying.** Integration of $(\phi(v)/v)'=-\phi(v)-\phi(v)/v^2$ on $[1,\infty)$ gives
$$
\int_1^\infty\frac{\phi(v)}{v^2}\,dv=\phi(1)-S(1)>0.
$$
Consequently the law has atom $1-\varepsilon L$ at zero and continuous mass $\varepsilon L$ on $(0,\varepsilon)$, with no atom at $\varepsilon$. Its quantiles obey $Q_\varepsilon(1-\varepsilon L)=0$ and $0\le d_b<\varepsilon$. All clone scores use the unchanged Gaussian directions, have unit marginal variance, and have precisely labels $(0,1)$ groupwise. At zero offset ordinary largest-rank BH selects complete groups; its expanded rejection rank is $K$ times the original rank, giving exactly the original FDP for each $K$.

**Actual population and finite-copy limit.** Here is an explicit way to check the possible common crossings rather than select ranks separately. Write
$$
z(v)=\frac2q\left\{\frac{\phi(v)}v-S(v)\right\},\qquad v\ge1.
$$
Then $z$ decreases continuously from $L$ to zero, and the selected group's offset CDF at a positive offset $\varepsilon(1-1/v)$ is $1-\varepsilon z(v)$. On a smooth branch where the background count is $b\in\{0,1\}$, any nonsaturated positive crossing has the form
$$
x=b+1-\varepsilon z(v),\qquad
t_1=\psi_{b,\varepsilon}(v):=u(b+1-\varepsilon z(v))+\varepsilon(1-1/v).
$$
Only branches satisfying the actual background indicator at $x$ are used. The qualification inequality on this branch is $t_1\ge\psi_{b,\varepsilon}(v)$, not an independently optimized rank prescription. Differentiating gives
$$
\psi'_{b,\varepsilon}(v)=\frac{\varepsilon}{v^2}
\left\{1-\frac{\phi(v)}{\phi(u(b+1-\varepsilon z(v)))}\right\}.
$$
All relevant quantiles are positive. Its unique zero is $v=u(b+1-\varepsilon z(v))$, equivalently
$$
S(v)+\varepsilon\{\phi(v)/v-S(v)\}=q(b+1)/2.
$$
The left side has derivative $-\phi(v)(1+\varepsilon/v^2)<0$; its value at $v=1$ exceeds the right side and its limit at infinity is zero. Thus each branch has exactly one minimum and each horizontal level has at most two intersections. The other pieces of $H_\varepsilon-x$ are affine with slope $-1$, separated by the two atom activations and the selected-group saturation boundary. There are therefore only finitely many contacts for each realization.

Tangencies require $t_1$ to equal one of the two fixed minima. Atom/contact coincidences and endpoint changes require equality on a curve in $(t_1,t_2)$: for example $t_2=u(x)$ at an analytic root, or $t_1=u(b+1-\varepsilon L)$ at zero-offset activation, or $t_1=u(b+1)+\varepsilon$ at saturation. These sets have two-dimensional Lebesgue measure zero. The nonsingular bivariate Gaussian law gives them probability zero. This argument includes the branch boundaries $v=1,\infty$.

More explicitly, the midpoint empirical offset CDF differs from $P_\varepsilon([0,d])$ by at most $1/(2K)$ at every $d$. Hence $H_{K,\varepsilon}$ and $V_{K,\varepsilon}$ converge uniformly to their population counterparts, with error at most $1/(2K)$. Away from the exceptional contacts just listed, a positive largest crossing is approached from the left by a strict qualifying interval, while larger compact intervals have a strict negative gap; thus the largest qualifying grid ranks converge to that largest crossing. A sufficiently small interval near zero has $H=H_K=0$, since both realized scores are finite. Endpoint $x=2$ is included and is stable whenever both $t_2>1$ and $t_1>1+\varepsilon$; the equality boundaries have probability zero. These observations also handle absence of a positive crossing.

For completeness $H$ is nondecreasing with upward jumps, so a positive supremum $\rho$ is attained: along qualifying points increasing to $\rho$, $H(\rho)\ge\rho$. If $H(\rho)>\rho$ and $\rho<2$, monotonicity would qualify a slightly larger point, contradicting the supremum. At $\rho=2$, $H\le2$ gives equality. Thus always $H(\rho)=\rho$ at a positive largest crossing, including the endpoint. Uniform convergence of $V_K$, together with convergence of positive ranks, gives the FDP ratio $V(\rho)/\rho$ with its actual fractional denominator. Finite FDPs are bounded by one, so dominated convergence proves the asserted inner FDR limit.

**Signed first variation, including partial groups.** For the original two-group model, the FDP is one when $t_2\ge a,t_1<1$, one half when $t_2\ge1,t_1\ge1$, and zero otherwise (irrelevant equality choices have probability zero). The selected false-null coordinate has no FDP jump at $u_1=a$. At $u_2=1$ its jump is
$$
\Delta_{1,2}(t_2)=\tfrac12\mathbf1_{[1,a)}(t_2)-\tfrac12\mathbf1_{[a,\infty)}(t_2).
$$
Conditional on $T_1=1$, $T_2\sim N(0,3/4)$. Therefore the actual signed face coefficients are
$$
\mu_{1,1}(E_1)=0,\qquad
\mu_{1,2}(E_1)=\frac{\phi(0)}2
\left\{S(2/\sqrt3)-2S(2a/\sqrt3)\right\}.
$$
This uses the conditional correlated face law, retaining its negative-jump region.

Only $t_1\in[1,1+\varepsilon]$ can change the FDP: below it selected clones never join a rejection containing the background group, and above it all clones pass the terminal threshold whenever the background passes. If $t_2<1$, FDP is always zero. The additional strip
$$
1\le t_2<u(2-\varepsilon L)
$$
has width $O(\varepsilon)$, and its intersection with the $t_1$ strip has probability $O(\varepsilon^2)$ because the joint density is bounded.

For all remaining $t_2\ge u(2-\varepsilon L)$, the background group is present throughout every possible rank $x\in[2-\varepsilon L,2]$. Consequently a crossing containing selected clones exists exactly when
$$
t_1\ge\tau_\varepsilon:=\min_{v\ge1}\psi_{1,\varepsilon}(v).
$$
This is a minimum inside the single actual common-crossing problem; it is valid here because the background indicator equals one throughout the entire candidate interval. Its minimizer $v_\varepsilon$ solves the preceding strictly decreasing equation with $b=1$. Implicit differentiation at $(v,\varepsilon)=(1,0)$ yields
$$
v_\varepsilon=1+c\varepsilon+O(\varepsilon^2),\qquad
\tau_\varepsilon=1+c\varepsilon+O(\varepsilon^2).
$$
When this crossing exists, its actual largest rank lies in $[2-\varepsilon L,2]$, so its FDP is $1/x=1/2+O(\varepsilon)$. This fractional-FDP error is integrated only over the $t_1$ strip, giving $O(\varepsilon^2)$. Before that crossing exists the FDP is exactly one for $t_2\ge a$, and zero for $u(2-\varepsilon L)\le t_2<a$; these are the original lower-face values. The actual population change is therefore the original signed jump delayed by $\tau_\varepsilon-1$, up to integrated $O(\varepsilon^2)$. The bivariate Gaussian density and its $t_1$ derivative have bounded integrals over $t_2$ near this fixed face. Integration gives
$$
\mathbb E f_{\mathrm{pop},\varepsilon}(T)-F
=-c\varepsilon\mu_{1,2}(E_1)+O(\varepsilon^2).
$$
Since $u_2=U=1$ and $\mu_{1,1}=0$, this is exactly
$$
-\varepsilon\sum_{r=1}^2\{1/U-m(u_r)\}\mu_{1,r}(E_1)+O(\varepsilon^2).
$$
The inner limit has already been justified independently, so the iterated derivative agrees with the target.

**Parameter-measure bounds.** The distinct directions separate the two original parameter atoms. Continuous perturbation moves mass exactly $\varepsilon L/2=\varepsilon\{h(1)-1\}$ away from the selected original atom, so $d_{\mathrm{TV}}(\pi_\varepsilon,\pi)=\varepsilon L/2$. If $M_K$ is the number of strictly positive midpoint offsets, then
$$
|M_K/K-\varepsilon L|\le1/(2K),\qquad
d_{\mathrm{TV}}(\pi_{K,\varepsilon},\pi)=M_K/(2K)
\le\varepsilon L/2+1/(4K)\le\varepsilon L/2+1/(2K).
$$
Couple each displaced parameter with its original selected atom. Each moved unit travels less than $\varepsilon=\varepsilon/U$ and all other mass remains fixed, proving both stated $W_1$ bounds with the target's (slightly weaker) rounding allowance.

## Failure

NOT fails: this fixed positively correlated mixed-label model satisfies the actual common-largest-crossing limit and the signed derivative; correlated conditional face weights and a sign-changing terminal jump do not create an extra first-order fractional-FDP term in this case.
