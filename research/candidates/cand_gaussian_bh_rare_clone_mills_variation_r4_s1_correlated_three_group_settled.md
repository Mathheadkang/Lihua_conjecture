---
type: candidate
title: >-
  Fixed correlated three-group mixed-label Mills probe has the asserted iterated
  variation
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
slot: 1
direction: idea_f372a8a1dd2f
statement_digest: c7939c23ae577add03c56534f1a6ec07179140d4317ffdd0a9a1aaf699a67fea
performed_by: unknown
created_at: '2026-11-09T00:16:03.040Z'
extension_version: 0.0.4
---

## Object

This is exactly the previously open object in `idea_f372a8a1dd2f`, not a new parameter variant. Fix

$$
N=3,\quad q=1/5,\quad i=1,\quad
\theta=(0,4/5,-1/2),\qquad G\sim N_3(0,I_3),
$$

$$
v_1=(1,0,0),\quad v_2=(3/5,4/5,0),\quad
v_3=(-2/5,0,\sqrt{21}/5).
$$

Use precisely the target's offset law, left quantiles and midpoint arrays; all original data stay fixed in both limits. Below, $S,\phi,m,h,U,u_r,L$ have the target meanings, and $u(x)=S^{-1}(qx/3)$. All arguments concern sufficiently small positive $\varepsilon$, without a numerical limit claim.

## Checks

### H1

The original size is the fixed finite integer $N=3\ge1$.

### H2

The fixed testing level is $q=1/5\in(0,1/2)$.

### H3

The arbitrary-means hypothesis permits the fixed vector $(0,4/5,-1/2)$. Its actual original labels are $(1,0,1)$.

### H4

The unit-diagonal covariance is

$$
\Sigma=\begin{pmatrix}1&3/5&-2/5\\3/5&1&-6/25\\-2/5&-6/25&1\end{pmatrix}.
$$

The direction matrix is triangular with nonzero diagonal $1,4/5,\sqrt{21}/5$; hence it is invertible and $\Sigma=VV^{\mathsf T}$ is positive definite. In particular $\det\Sigma=336/625>0$.

### H5

The displayed representation has finite dimension three and unit direction rows, and its row inner products are exactly the entries of $\Sigma$.

### H6

The chosen coordinate is $i=1\in[3]$, with the expressly permitted zero mean $\theta_1=0$.

### H7

Only $\varepsilon>0$ with $\varepsilon L<1$ is used. There is no positive-selected-mean restriction because $\theta_1=0$. In the arguments below reduce the fixed upper bound on $\varepsilon$ further when necessary; this does not change any original model data. In particular take $\varepsilon L<1/2$ and make $\varepsilon/U$ smaller than one third of the two positive consecutive threshold gaps. These restrictions leave a nonempty interval of admissible positive parameters.

### NOT

**Fail. All four conclusions hold for this exact object.** The following gives a direct finite-copy convergence argument and a deterministic localization with an $O(\varepsilon^2)$ expectation remainder. Constants are for this fixed object only.

**1. Normalization, labels, baseline and costs.** Integration of $(\phi(v)/v)'=-\phi(v)-\phi(v)/v^2$ gives

$$
\int_U^\infty\phi(v)v^{-2}\,dv=\phi(U)/U-S(U)>0.
$$

Consequently the continuous minority has mass $\varepsilon L$, where $0<L<\infty$, and the zero atom has mass $1-\varepsilon L$. The offset map $v\mapsto\varepsilon(1/U-1/v)$ is strictly increasing from zero to the unattained upper endpoint $\varepsilon/U$; its continuous image part has no atoms. This proves the stated support, endpoint and left-quantile assertions, including $Q_\varepsilon(1-\varepsilon L)=0$ and $0\le d_b<\varepsilon/U$.

The selected copy means are $-d_b\le0$ and its directions do not change. All other copy means and directions stay fixed. Thus joint Gaussianity, unit variances and the actual labels $(1,0,1)$ hold. At zero offset all groups have exact copies. For any deterministic original p-values, an expanded qualifying rank $k$ implies the original rank $\lceil k/K\rceil$ qualifies, whereas any qualifying original rank $r$ gives expanded rank $Kr$. Largest ranks therefore correspond exactly and the FDP baseline is the original $F$ for every $K$.

Let $M_K$ be the number of positive midpoint offsets. The elementary midpoint counting bound is

$$
|M_K/K-\varepsilon L|\le1/(2K).
$$

Couple each clone parameter to its own original group parameter. The fraction moved is $M_K/(3K)\le\varepsilon L/3+1/(3K)$ and every move costs less than $\varepsilon/U$. Unmoved mass cancels in total variation, giving both stated discrete bounds. The continuous coupling has moved fraction $\varepsilon L/3$, giving both continuous bounds. These are bounds against the original measure, not a claim of total-variation convergence of midpoint measures to the continuous law.

**2. Common population crossing is the actual fixed-$\varepsilon$ finite-copy limit.** Write $H=H_\varepsilon$, $V=V_\varepsilon$, and

$$
z(v)=\frac3q\{\phi(v)/v-S(v)\},\qquad z(U)=L,\qquad
z'(v)=-\frac3q\frac{\phi(v)}{v^2}.
$$

For $0<a<\varepsilon/U$, with $v=(1/U-a/\varepsilon)^{-1}$, the selected-group CDF is

$$
P_\varepsilon([0,a])=1-\varepsilon z(v).
$$

It equals zero for $a<0$, equals $1-\varepsilon L$ at zero, and equals one for $a\ge\varepsilon/U$. For any fixed score vector, $H(x)$ is nondecreasing and right continuous, and has only the two background jumps and the selected zero-atom jump. Between these jumps it is continuous and piecewise smooth. Thus $H(x)-x$ is upper semicontinuous on compact subintervals of $(0,3]$. Every positive supremal qualifying crossing $\rho$ qualifies: take qualifying points increasing to $\rho$ and use monotonicity and right continuity. If $\rho<3$ and $H(\rho)>\rho$, monotonicity gives a larger qualifying point, a contradiction. At $\rho=3$ equality follows from $H\le3$. Hence $H(\rho)=\rho$, including the terminal endpoint.

On a smooth minority piece, put $a=t_1-u(x)$ and $v=(1/U-a/\varepsilon)^{-1}$. Since $u'(x)=-q/(3\phi(u(x)))$,

$$
\frac{d}{dx}C_\varepsilon(x;t)=\frac{\phi(v)}{\phi(u(x))}.
$$

Here $v$ strictly increases and $u(x)>0$ strictly decreases with $x$. Thus this derivative strictly decreases. A smooth tangential qualifying root with background count $k\in\{0,1,2\}$ must have $v=u(x)$ and

$$
\frac3q S(v)+\varepsilon z(v)=k+1.
$$

The left side has strictly negative derivative $-(3/q)\phi(v)(1+\varepsilon/v^2)$, so there is at most one corresponding $t_1$ for each $k$. Such tangencies have probability zero because $T_1$ has a density.

Jump contacts also have probability zero. At a background jump $x_j=(3/q)S(t_j)$, contact has the form $x_j=b+C_\varepsilon(x_j;t)$ for some integer $b$. On either flat part of the selected CDF this forces $x_j$ to be an integer and hence $t_j$ to be a fixed threshold. On its strictly increasing minority part, fixing $t_j$ determines at most one $t_1$. The joint law of $(T_1,T_j)$ has a density, so Fubini gives zero probability. Contact at the selected zero-atom jump forces $(3/q)S(t_1)=b+1-\varepsilon L$, another finite list of zero-probability values. Coincident jumps have probability zero by the nondegenerate joint Gaussian laws. Any nonsmooth contact with the minority's upper endpoint can likewise be discarded by the same Fubini argument; away from a simultaneous background jump the CDF has matching derivative zero there and $H-x$ has derivative $-1$.

Consequently, almost surely every positive largest crossing has qualifying points with strictly positive $H(x)-x$ arbitrarily close from its left. Indeed a continuous interior root without such points would be a tangency; a jump contact was excluded; and a constant-CDF root has derivative $-1$. If $\rho=3$, $H(3)=3$ forces both backgrounds present and the whole selected group present. Outside the zero-probability endpoint equality scores these remain present immediately to its left, giving the same strict-margin property.

For the empirical midpoint CDF $C_K$, the generalized-inverse equivalence $Q(p)\le a\iff p\le P([0,a])$ gives, also at the zero atom,

$$
\sup_a|C_K(a)-P_\varepsilon([0,a])|\le1/(2K).
$$

Thus the corresponding $H_K,V_K$ have the same uniform error bound against $H,V$. The actual finite-copy largest rank in group units is

$$
\rho_K=\max\bigl(\{0\}\cup\{l/K:H_K(l/K)\ge l/K,\ 1\le l\le3K\}\bigr),
$$

and $H_K(\rho_K)=\rho_K$ if positive. For any fixed $\delta>0$, upper semicontinuity and absence of a qualifying point on $[\rho+\delta,3]$ give a uniform negative margin there. Uniform approximation excludes those finite-copy ranks for all sufficiently large $K$. A strictly qualifying point arbitrarily close below $\rho$, moved up to the next grid point and using monotonicity, gives a finite-copy crossing for all sufficiently large $K$. Hence $\rho_K\to\rho$ almost surely.

Every positive $\rho_K$ is at least $\min\{1,M_{0,K}/K\}$, where $M_{0,K}=K-M_K$ counts the selected zero-offset copies: a selected rejection includes that atom, and any background rejection includes an entire group. Since $M_{0,K}/K\to1-\varepsilon L>0$, if $\rho=0$ the finite rejection ranks are eventually zero. For $\rho>0$, the excluded jump contacts ensure that $V$ is continuous at $\rho$ (one-sided continuity suffices at $3$), so uniform approximation gives $V_K(\rho_K)\to V(\rho)$. The finite FDP is $V_K(\rho_K)/\rho_K$, because its actual denominator is $K\rho_K\ge1$. Therefore the finite FDP converges almost surely to precisely the stated population FDP, retaining its fractional denominator. Bounded convergence proves

$$
\lim_{K\to\infty}F_{K,\varepsilon}=\mathbb E f_{\mathrm{pop},\varepsilon}(T).
$$

**3. Exact branch contacts and localization.** For $r=1,2,3$ let $v_r^\varepsilon\ge U$ be the unique solution of

$$
\frac3q S(v_r^\varepsilon)+\varepsilon z(v_r^\varepsilon)=r,
\qquad
\tau_r^\varepsilon=v_r^\varepsilon+
\varepsilon(1/U-1/v_r^\varepsilon).
$$

Existence follows because the decreasing left side has value $3+\varepsilon L>r$ at $U$ and tends to zero. At the contact the rank is $x_r^\varepsilon=r-\varepsilon z(v_r^\varepsilon)\in[r-\varepsilon L,r]$. By the implicit function theorem at $(u_r,0)$,

$$
\tau_r^\varepsilon=u_r+\varepsilon c_r+O(\varepsilon^2),\qquad
c_r=\frac1U-\frac1{u_r}+\frac{qz(u_r)}{3\phi(u_r)}
=\frac1U-m(u_r).
$$

These are exact branch activation thresholds, not separately selected replacement BH ranks. To see this, suppose the background count is fixed at $k=r-1$ throughout $[r-\varepsilon L,r]$. Every root on its minority piece is parameterized by

$$
x(v)=r-\varepsilon z(v),\qquad
g_r(v)=u(x(v))+\varepsilon(1/U-1/v),\qquad v\ge U,
$$

where $t_1=g_r(v)$. The endpoint $v=U$ includes contact with the zero atom, and the limit $v\to\infty$ gives $x=r$ and $g_r=u_r+\varepsilon/U$. Direct differentiation gives

$$
g_r'(v)=\frac{\varepsilon}{v^2}\left\{1-\frac{\phi(v)}{\phi(u(x(v)))}\right\}.
$$

Since $x(v)$ strictly increases, $u(x(v))$ strictly decreases, and $u(x(U))>u_r\ge U$, this derivative changes sign exactly once, from negative to positive, at $v=u(x(v))$. Its unique global minimum is therefore exactly $\tau_r^\varepsilon$. This also excludes an earlier atom-only activation. At $t_1=u_r$ the branch is inactive, whereas at $t_1=u_r+\varepsilon/U$ the whole group gives a qualifying rank $r$. Thus $\tau_r^\varepsilon\in[u_r,u_r+\varepsilon/U]$. Every $t_1$ between this minimum and the full-group endpoint has a root by continuity of $g_r$ on its increasing branch; above the endpoint rank $r$ qualifies directly. Before activation no crossing exists on this branch (its positive supremal crossing would itself have to be one of these roots); afterwards its largest crossing lies in $[r-\varepsilon L,r]$.

Here is why these local branches control the common global crossing to first order. Let

$$
I_r=[u_r,u_r+\varepsilon/U],\qquad
B=\frac{Lq}{3\phi(u(1/2))}.
$$

For $x\in[r-\varepsilon L,r]$, $0\le u(x)-u_r\le B\varepsilon$, because $r-\varepsilon L\ge1/2$. Reduce $\varepsilon$ so the strips are disjoint and both $\varepsilon/U$ and $B\varepsilon$ are below one third of the minimum consecutive threshold gap. Define the bad event

$$
\mathcal B_\varepsilon=
\bigcup_{r,s=1}^3\bigcup_{j=2}^3
\{T_1\in I_r,\ |T_j-u_s|\le B\varepsilon\}.
$$

Each pair $(T_1,T_j)$ has bounded density, of maximum at most $(2\pi\sqrt{1-\Sigma_{1j}^2})^{-1}$. Rectangle area bounds consequently give $\mathbb P(\mathcal B_\varepsilon)=O(\varepsilon^2)$.

If $t_1$ is outside all $I_r$, the ordinary largest BH rank for $t$ equals that for $(t_1-\varepsilon/U,t_2,t_3)$, since their selected-coordinate positions relative to every grid threshold coincide. The downward perturbation is sandwiched between these vectors. The population largest crossing equals this common integer rank: a positive common rank qualifies with all its selected copies; and no larger crossing can exceed the ordinary integer largest rank, because $H$ is bounded by the original integer count function and any qualifying real rank for that integer count produces a qualifying integer rank at least as large. The FDP is identical too.

Now take $t_1\in I_r$ outside $\mathcal B_\varepsilon$. Every background has constant classification on each interval $[s-\varepsilon L,s]$. Any positive population root with $C>0$ must lie in one of these intervals, because $C\in[1-\varepsilon L,1]$; a root with $C=0$ is an integer pure-background rank. On intervals indexed by $s<r$, the selected CDF is zero, since $t_1<u_{r-1}$. On intervals indexed by $s>r$, it is one, since $t_1\ge u_r>u_{r+1}+\varepsilon/U$. Thus only the branch indexed by $r$ can change the original largest-rank decision.

If a larger original rank is already qualified, it is unchanged and remains the global maximum. Otherwise, a change at this branch requires exactly $r-1$ backgrounds at threshold $u_r$. If there are fewer, no $r$-branch crossing exists; if there are more, the unchanged larger branch qualifies. When there are exactly $r-1$, activation of this sole remaining branch is at $\tau_r^\varepsilon$. Before activation the global largest rank is the same pure-background rank as just below the original face, including any downward cascade; after activation it is the largest root of this branch. Thus this argument retains the common global maximum and all original rank cascades.

Let $\Delta_r(t_2,t_3)$ denote the signed ordinary FDP jump as only coordinate one crosses $u_r$, holding the backgrounds fixed. On this good set it follows that

$$
f_{\mathrm{pop},\varepsilon}(t)-f(t)
=-\Delta_r(t_2,t_3)
\mathbf1_{\{u_r\le t_1<\tau_r^\varepsilon\}}+e_\varepsilon(t),
\qquad |e_\varepsilon(t)|\le C\varepsilon\mathbf1_{\{t_1\in I_r\}}.
$$

For completeness the error bound is elementary, without assuming an all-or-none approximation. After activation let $k=r-1$ be the background count, $a$ its true-null count, and let $x\in[r-\varepsilon L,r]$ be the selected branch's largest root. Because the selected group is null, its fractional count is $x-k$ and

$$
f_{\mathrm{pop},\varepsilon}=\frac{a+x-k}{x}
=1-\frac{k-a}{x},\qquad
f^+=1-\frac{k-a}{r}.
$$

Their difference is at most $2\varepsilon L/[r(r-\varepsilon L)]\le4L\varepsilon$. Below activation the selected group contributes zero at every lower integer rank, so the lower FDP is exact. In particular $r=1$ correctly gives FDP one for every positive fractional rank; there is no denominator truncation. On the bad event every FDP and signed jump is bounded in absolute value by one. Since $\mathbb P(T_1\in\bigcup I_r)=O(\varepsilon)$, integration gives

$$
\mathbb E[f_{\mathrm{pop},\varepsilon}(T)-f(T)]
=-\sum_{r=1}^3\mathbb E[
\Delta_r(T_2,T_3)\mathbf1_{\{u_r\le T_1<\tau_r^\varepsilon\}}]
+O(\varepsilon^2).
$$

**4. Evaluation against the original signed face measures.** Given $T_1=t$, the two backgrounds are independent normals with means $4/5+(3/5)t$ and $-1/2-(2/5)t$, and standard deviations $4/5$ and $\sqrt{21}/5$. Put $D_r(t)=\mathbb E[\Delta_r(T_2,T_3)\mid T_1=t]$. The jump function is bounded by one. Translating this fixed nondegenerate two-dimensional conditional Gaussian density gives a locally Lipschitz function $D_r$; for example its $L^1$ density difference is bounded by

$$
\sqrt{2/\pi}\sqrt{9/16+4/21}\,|t-s|.
$$

Hence

$$
\begin{aligned}
\mathbb E[\Delta_r(T_2,T_3)\mathbf1_{\{u_r\le T_1<\tau_r^\varepsilon\}}]
&=\int_{u_r}^{\tau_r^\varepsilon}\phi(t)D_r(t)\,dt\\
&=\varepsilon c_r\phi(u_r)D_r(u_r)+O(\varepsilon^2).
\end{aligned}
$$

Here $E_1$ is the plane of the second and third Gaussian coordinates, so the target's original-coordinate face definition gives exactly $\mu_{1,r}(E_1)=\phi(u_r)D_r(u_r)$: only the first score varies when defining the jump; the conditional background scores are held at the face. Thus

$$
\mathbb E f_{\mathrm{pop},\varepsilon}(T)-F
=-\varepsilon\sum_{r=1}^3\{1/U-m(u_r)\}\mu_{1,r}(E_1)
+O(\varepsilon^2).
$$

Together with the fixed-$\varepsilon$ finite-copy limit this proves the asserted iterated derivative for this exact correlated three-group object. No sign of a face measure was discarded. The numerical slopes in the open idea are unnecessary for this argument; it supplies a genuine failed-NOT result for this instance. No dimension-uniform estimate, singular original covariance extension, or unrestricted FDR theorem is asserted.

## Failure

NOT fails: the exact fixed correlated three-group mixed-label object has the actual finite-copy/common-largest-crossing limit, all normalization/label/cost conclusions, and the asserted signed inverse-Mills variation with an $O(\varepsilon^2)$ expectation remainder.
