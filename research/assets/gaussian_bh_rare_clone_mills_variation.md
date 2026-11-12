---
type: lemma
title: Rare downward-mean clone variation with inverse-Mills rank coefficients
status: approved
source:
  kind: original
depends_on:
  - gaussian_bh_correlated_clone_first_variation
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
  - gaussian_bh_rare_downward_mean_clone_model
tags:
  - gaussian_bh
  - rare_clones
  - inverse_mills
  - signed_variation
  - finite_model
---

## Statement

Fix all original finite-model data in the [rare downward-mean clone model](../definitions/gaussian_bh_rare_downward_mean_clone_model.md): $N\ge1$, $q\in(0,1/2)$, arbitrary means $\theta$, positive-definite unit-diagonal $\Sigma$, a finite unit-direction representation $T_j=\theta_j+v_j\cdot G$, and any chosen coordinate $i\in[N]$. In particular $\theta_i=0$ is permitted. Use the original one-sided true-null labels $\ell_j=\mathbf1_{\{\theta_j\le0\}}$, $S=\overline\Phi$, $\phi$, $m=S/\phi$, $h=1/m$, $U=S^{-1}(q)$, $u_r=S^{-1}(qr/N)$, and $L=N\{h(U)/U-1\}$ as defined there. The assertions below concern sufficiently small positive $\varepsilon$ satisfying $\varepsilon L<1$ and, when $\theta_i>0$, $\varepsilon/U<\theta_i$.

1. **Offset normalization, quantiles and actual labels.** The displayed candidate $P_\varepsilon$ is a probability measure, $0<L<\infty$, and
$$
\int_U^\infty\frac{\phi(v)}{v^2}\,dv=\frac{\phi(U)}U-S(U),\qquad
P_\varepsilon(\{0\})=1-\varepsilon L,\qquad
P_\varepsilon((0,\varepsilon/U))=\varepsilon L.
$$
There is no atom at $\varepsilon/U$ and no mass outside $[0,\varepsilon/U)$. The left inverse convention is exactly $Q_\varepsilon(p)=\inf\{a\ge0:P_\varepsilon([0,a])\ge p\}$, including $Q_\varepsilon(1-\varepsilon L)=0$. Its midpoint array satisfies $0\le d_b<\varepsilon/U$. Every finite $NK$-coordinate clone array is jointly Gaussian with unit marginal variances and the original directions unchanged. Its actual one-sided null labels are exactly $\ell_j$ for all $K$ copies of group $j$, also at $\theta_i=0$. At zero offset, exact copying gives the original FDR $F$ for every $K$.

2. **Actual common-largest-crossing limit.** For every sufficiently small fixed $\varepsilon>0$, the inner finite-copy limit exists and is represented by the globally largest population crossing defined above:
$$
\lim_{K\to\infty}F_{K,\varepsilon}
=\mathbb E\,f_{\mathrm{pop},\varepsilon}(T).
$$
On a probability-one set, every positive $\rho_\varepsilon(T)$ is a qualifying largest crossing and satisfies $H_\varepsilon(\rho_\varepsilon(T);T)=\rho_\varepsilon(T)$. Thus its FDP uses $V_\varepsilon(\rho_\varepsilon;T)/\rho_\varepsilon$, without replacing a fractional denominator below one by one. This representation and the limiting assertion are conclusions of the lemma, not assumptions on the clones. They retain the atom at zero, the exact background groups, the non-strict BH inequalities, and the endpoint $\rho_\varepsilon=N$; the event $H_\varepsilon(N;T)=N$ is not excluded.

3. **Signed inverse-Mills variation.** Use precisely the original-coordinate face measures from the approved [correlated-clone right-variation identity](gaussian_bh_correlated_clone_first_variation.md). For clarity, write
$$
E_i=\{y:v_i\cdot y=0\},\quad a_r=u_r-\theta_i,\quad
\rho_{ji}=v_j\cdot v_i,\quad v_j^\perp=v_j-\rho_{ji}v_i.
$$
Let $\gamma_{E_i}$ be standard Gaussian probability measure on $E_i$ (point mass at zero if $E_i$ is zero-dimensional). Let $f(t)$ be the original ordinary largest-rank BH FDP with the original labels, and define
$$
t^{i,r}(x,y)_i=x,\qquad
t^{i,r}(x,y)_j=\theta_j+\rho_{ji}a_r+v_j^\perp\cdot y\quad(j\ne i),
$$
$$
\Delta_{i,r}(y)=\lim_{\eta\downarrow0}
\{f(t^{i,r}(u_r+\eta,y))-f(t^{i,r}(u_r-\eta,y))\},
\qquad \mu_{i,r}(B)=\phi(a_r)\int_B\Delta_{i,r}(y)\,\gamma_{E_i}(dy).
$$
Only coordinate $i$ varies in this jump. The other coordinates stay at their displayed face values; each FDP uses its actual largest BH rank, including all rank cascades. The signed measures are not replaced by their positive parts. Then
$$
\lim_{\varepsilon\downarrow0}
\frac{\lim_{K\to\infty}F_{K,\varepsilon}-F}{\varepsilon}
=-\sum_{r=1}^N\left\{\frac1U-m(u_r)\right\}\mu_{i,r}(E_i).
$$
The order of limits is part of the statement. This includes negative means, a zero-mean chosen true null and all original label patterns.

4. **Parameter-measure comparison costs.** With the measures, total-variation convention and transport cost specified in the definition, put
$$
b_{K,\varepsilon}=\varepsilon\{h(U)/U-1\}+\frac1{NK},\qquad
b_\varepsilon=\varepsilon\{h(U)/U-1\}.
$$
Then
$$
d_{\mathrm{TV}}(\pi_{K,\varepsilon},\pi)\le b_{K,\varepsilon},\qquad
W_1(\pi_{K,\varepsilon},\pi)\le\frac\varepsilon U b_{K,\varepsilon},
$$
$$
d_{\mathrm{TV}}(\pi_\varepsilon,\pi)\le b_\varepsilon,\qquad
W_1(\pi_\varepsilon,\pi)\le\frac\varepsilon U b_\varepsilon.
$$
The $1/(NK)$ term accounts for midpoint-quantile rounding of the nonzero minority count. These bounds compare each perturbed measure with the original measure; they do not assert total-variation convergence of the discrete quantile measures to the continuous offset measure.

## Proof obligations

This is a new unproved target extracted from the rare downward-mean proposal and the third autonomous reassessment of 8 November 2026. The preceding approved finite-copy identity supplies the signed face measures and exact-copy baseline only. It does not establish this iterated limit.

Prove normalization, label preservation and the quantile convention first. Establish the actual finite-copy FDR limit with the common global largest crossing, including atom contacts, exact background atoms, endpoint rank $N$, possible small positive fractional ranks, root births, root switches and ties. Justify passage through expectation and the treatment of every exceptional face intersection under the fixed positive-definite original model. Do not import a strict inequality $H_\varepsilon(N)<N$ from a private-Gaussian-noise construction.

The suggested local contact calculation uses
$$
A_r=\frac1{r h(u_r)},\qquad z(v)=\frac Nq\left\{\frac{\phi(v)}v-S(v)\right\}\quad(v\ge U).
$$
It proposes
$$
\inf_{v\ge U}\{A_r z(v)+1/U-1/v\}=1/U-m(u_r),
$$
with minimizer $v=u_r$ (including the endpoint $u_N=U$). This calculation is a proof obligation, and even its verification must be linked to a proved global largest-crossing comparison before yielding the signed derivative. Independent optimization of different ranks is not a replacement for the common BH crossing. Fractional FDP changes and signed face contributions must be controlled at the stated order, including the all-null and zero-null-label boundary cases. No zero-null upward compensation is used.

The original data $N,q,\theta,\Sigma$ remain fixed throughout both limits; no dimension-uniform error rate or singular-original-covariance extension is claimed. The parameter-measure inequalities alone establish neither FDR continuity, a complete optimization space, applicability of Ekeland's principle, a quantitative near-extremizer comparison, nor a $q$-scaled payment for the unmatched boundary mean flux at zero-null coordinates. No extremizer or conditional rank order is assumed. Neither unrestricted main FDR bound nor the mixed trace-budget target follows from the scaffold.

## Proof

All constants below may depend on the fixed original model and $q$. Restrict $\varepsilon>0$ further whenever needed, in particular so that $\varepsilon L<1/2$. An estimate $O(\varepsilon^2)$ is uniform over sufficiently small positive $\varepsilon$ for this fixed model only. For a deterministic vector $t$, abbreviate the population functions by $C(x),H(x),V(x)$ and their largest crossing by $\rho$. Write
$$
n(x)=\sum_{j\ne i}\mathbf1_{\{t_j\ge u(x)\}},\qquad
v(x)=\sum_{j\ne i}\ell_j\mathbf1_{\{t_j\ge u(x)\}},\qquad
A(x)=-u'(x)=\frac{q}{N\phi(u(x))}=\frac1{x h(u(x))}.
$$
Thus $A_r=A(r)$, and $u(x)>0$ for $0<x\le N$. We prove the empirical and crossing arguments directly; no private-noise limit or fixed-copy derivative is used.

### 1. The offset law, quantiles, labels and exact copies

Differentiation gives $(\phi(v)/v)'=-\phi(v)-\phi(v)/v^2$. Integrating from $U$ to infinity gives
$$
\int_U^\infty\frac{\phi(v)}{v^2}\,dv=\frac{\phi(U)}U-S(U)>0.
$$
Since $S(U)=q>0$, this proves $0<L<\infty$ and that the continuous term in $P_\varepsilon$ has mass $\varepsilon L$. The map $v\mapsto\varepsilon(1/U-1/v)$ is strictly increasing from zero towards $\varepsilon/U$. The measure being pushed forward has a density, so contributes no mass at zero or at any other singleton; the upper endpoint is not attained. Consequently $P_\varepsilon$ is a probability measure with precisely the atom and support asserted in part 1. In particular $Q_\varepsilon(p)=0$ when $p\le1-\varepsilon L$, including equality. When $1-\varepsilon L<p<1$, its value is in $(0,\varepsilon/U)$, so every midpoint offset has the stated bounds.

For completeness put $D(a)=P_\varepsilon([0,a])$, with $D(a)=0$ for $a<0$. For $a\ge0$,
$$
Q_\varepsilon(p)\le a\quad\Longleftrightarrow\quad p\le D(a).
$$
Indeed the reverse implication follows from the infimum defining $Q_\varepsilon$. For the forward implication, right continuity of $D$ implies $D(Q_\varepsilon(p))\ge p$: approximate the infimum by points in the defining set from above and take their limit. Monotonicity now gives $D(a)\ge p$. Nonemptiness of that defining set follows from $D(a)\to1$. This proves the equivalence also at the zero atom.

Every clone is an affine function of the same Gaussian vector $G$, with direction $v_j$ of norm one. Its mean is unchanged except for $\theta_i-d_b$. If $\theta_i\le0$ this is nonpositive for every $b$, also at $\theta_i=0$. If $\theta_i>0$, it is positive because $d_b<\varepsilon/U<\theta_i$. Thus all actual labels are exactly $\ell_j$. At zero offset every original p-value is copied $K$ times. If the original largest rank is $r$, rank $Kr$ qualifies. Conversely, if expanded rank $l$ qualifies, $s=\lceil l/K\rceil$ satisfies $p_{(s)}\le ql/(NK)\le qs/N$, so $s\le r$ and $l\le Kr$. Hence the expanded largest rank is exactly $Kr$, including ties, and its FDP is the original FDP. This establishes the baseline $F$ directly.

### 2. Exact empirical ranks and deterministic population roots

Let $P_K=K^{-1}\sum_b\delta_{d_b}$, $C_K(x)=P_K([0,t_i-u(x)])$, $H_K=n+C_K$ and $V_K=v+\ell_i C_K$. Counting midpoint grid points with the preceding quantile equivalence gives
$$
\sup_{a\in\mathbb R}|P_K([0,a])-D(a)|\le K^{-1},\qquad
\sup_{0<x\le N}(|H_K(x)-H(x)|\vee|V_K(x)-V(x)|)\le K^{-1}.
$$
At expanded rank $l$, the number of p-values below the non-strict threshold is $K H_K(l/K)$. Therefore the expanded BH rank divided by $K$ is
$$
x_K=\max\bigl(\{0\}\cup\{l/K:1\le l\le NK,\ H_K(l/K)\ge l/K\}\bigr).
$$
If the count at a positive maximizing rank $l$ were an integer $M>l$, monotonicity of the threshold would make rank $M$ qualify, a contradiction. Thus $H_K(x_K)=x_K$ at a positive rank, the actual count is $Kx_K$, and its FDP is $V_K(x_K)/x_K$; its FDP is zero at $x_K=0$. This proves the empirical identities without a restriction on ties.

For fixed $t$, choose $a(t)>0$ small enough that $u(x)>\max_j t_j$ for $0<x<a(t)$. Nonnegative offsets then give $H_K(x)=H(x)=0$ throughout this interval, simultaneously for all $K$. There is no small-rank tail to control.

The function $H$ is nondecreasing, bounded by $N$, right continuous and upper semicontinuous on each compact subinterval of $(0,N]$. Indeed its only jumps are upward CDF jumps with their right values, composed with the continuous increasing cutoff $t_i-u(x)$, together with the finitely many upward background jumps. If $\rho>0$, a sequence of qualifiers tending to its supremum gives $H(\rho)\ge\rho$ by monotonicity. If $\rho<N$ and the inequality were strict, any $x\in(\rho,\min\{H(\rho),N\}]$ would qualify. If $\rho=N$, $H\le N$ already forces equality. Hence in every case
$$
H(\rho)=\rho\quad(\rho>0).
$$
For any $b>\rho$ the upper semicontinuous function $H(x)-x$ attains a strictly negative maximum on $[b,N]$ when that interval is nonempty. This assertion also holds when $\rho=0$.

The chosen fraction is either zero or in $[1-\varepsilon L,1]$. An equality root with $C=0$ is therefore an integer $k$ with $n(k)=k$. Every equality root with $C>0$ belongs to a unique layer $[r-\varepsilon L,r]$, $r\in[N]$, and has $n=r-1$. The layers are disjoint, and every positive equality root is at least $1-\varepsilon L$.

### 3. The entire layer profile and its Mills minimum

For $v\ge U$ set
$$
z(v)=\frac Nq\left\{\frac{\phi(v)}v-S(v)\right\},\qquad
c(v)=\frac1U-\frac1v,\qquad x_r(v)=r-\varepsilon z(v),\qquad
g_r(v)=u(x_r(v))+\varepsilon c(v).
$$
Here $z'(v)=-(N/q)\phi(v)/v^2<0$, $z(U)=L$, and $z(v)\to0$. Direct integration of the offset density gives
$$
P_\varepsilon([0,\varepsilon c(v)])=1-\varepsilon z(v).
$$
Thus $x_r(v)$ parametrizes every unsaturated equality of $r-1+C(x)=x$, including the left endpoint $C=1-\varepsilon L$. Saturation $C=1$ gives $x=r$, which is an equality precisely when $t_i\ge u_r+\varepsilon/U$. For finite $v$, the equality is exactly $t_i=g_r(v)$.

The derivatives are
$$
x_r'(v)=\varepsilon\frac Nq\frac{\phi(v)}{v^2}>0,\qquad
g_r'(v)=\frac{\varepsilon}{v^2}
\left[1-\frac{\phi(v)}{\phi(u(r-\varepsilon z(v)))}\right].
$$
The function $v-u(x_r(v))$ is strictly increasing, since its derivative is $1+A(x_r(v))x_r'(v)>0$. At $v=U$ it is negative: $r-\varepsilon L<N$ and hence $u(r-\varepsilon L)>U$, also when $r=N$. It tends to infinity as $v\to\infty$. Since both arguments of $\phi$ are positive, $g_r'$ is negative before the unique solution
$$
v_{*,r}=u(r-\varepsilon z(v_{*,r}))
$$
and positive after it. Put $\beta_r=g_r(v_{*,r})$. Its increasing branch tends to $u_r+\varepsilon/U$. Consequently for every $t_i\in[\beta_r,u_r+\varepsilon/U)$ there is a unique point on that branch with $g_r(v)=t_i$. Define $x_r^+(t_i)=x_r(v)$ there and $x_r^+(t_i)=r$ for $t_i\ge u_r+\varepsilon/U$. This is the largest scalar equality in the layer, and
$$
0\le\delta_r(t_i):=r-x_r^+(t_i)\le\varepsilon L,\qquad
\delta_r(t_i)=0\quad(t_i\ge u_r+\varepsilon/U).
$$
Every scalar equality requires $t_i\ge\beta_r$; any lower-branch equality precedes $x_r^+(t_i)$. If an actual equality has $n=r-1$ at that lower point, monotonicity of $n$ shows that $x_r^+(t_i)$ is a qualifier even if background jumps intervene. Therefore an actual largest crossing in a positive-chosen-mass layer must equal its upper scalar root. This is a statement about the common largest crossing, rather than separate choices of rank.

Uniform Taylor expansion on $[r-\varepsilon L,r]$, for the finitely many positive integers $r$, yields
$$
g_r(v)=u_r+\varepsilon\{A_r z(v)+c(v)\}+O(\varepsilon^2)
\quad\hbox{uniformly for }v\ge U.
$$
The derivative of the expression in braces is
$$
\frac1{v^2}\left[1-\frac{\phi(v)}{\phi(u_r)}\right],
$$
because $A_r=q/(N\phi(u_r))$. It is negative for $U\le v<u_r$ and positive for $v>u_r$; for $r=N$ it is nonnegative starting at $U=u_N$. Its minimum is
$$
A_r z(u_r)+c(u_r)
=\frac1{u_r}-m(u_r)+\frac1U-\frac1{u_r}
=:\kappa_r=\frac1U-m(u_r).
$$
Taking infima in the uniform expansion gives
$$
\beta_r=u_r+\varepsilon\kappa_r+O(\varepsilon^2).
$$
This includes the endpoint minimizer $u_N=U$; the exact positive-$\varepsilon$ minimizer still has $v_{*,N}>U$. Moreover $u_r\le\beta_r\le u_r+\varepsilon/U$, since $u(x_r(v))\ge u_r$, $c(v)\ge0$, and the upper bound follows by taking $v\to\infty$. Thus, for small $\varepsilon$, $\beta_1>\cdots>\beta_N$, and $\beta_{r+1}<u_r$ whenever $r<N$. Finally the bounded marginal density of $T_i$ and the interval of length at most $\varepsilon/U$ supporting a nonzero deficit imply
$$
\mathbb E[\delta_r(T_i)\mathbf1_{\{T_i\ge\beta_r\}}]
\le \varepsilon L\,\mathbb P\{\beta_r\le T_i<u_r+\varepsilon/U\}
=O(\varepsilon^2).
$$

### 4. Regular contacts and the actual finite-copy limit

Fix a sufficiently small positive $\varepsilon$ throughout this part. First discard the null events $T_j=u_r$ for $j\ne i$, $r\in[N]$. In particular no background jump location in $(0,N]$ is an integer or equals $N$. Condition on $W=T_{-i}$. Positive definiteness gives $T_i\mid W$ a nondegenerate Gaussian density; this also holds with empty $W$ when $N=1$.

Discard the finitely many conditional values
$$
T_i=\beta_r,\quad T_i=u_r+\varepsilon/U,\quad
T_i=u(r-\varepsilon L)\qquad(r\in[N]).
$$
They remove layer tangencies, equality at saturation, and equality at the chosen zero atom. At a fixed background jump $a=(N/q)S(W_j)\in(0,N]$, also discard $T_i=u(a)$, so that the chosen CDF has no simultaneous jump there. Let $k$ be either the left or right background count at $a$. An equality at that side would require $C(a)=a-k$. The values zero and one would require $a$ to be an integer, already excluded. The value $1-\varepsilon L$ requires the single value $T_i=u(a)$, already discarded. For any value strictly between $1-\varepsilon L$ and one, the offset CDF is strictly increasing on $(0,\varepsilon/U)$, so at most one further conditional $T_i$ gives that equality. Values in $(0,1-\varepsilon L)$ are impossible. Discard these finitely many further values for both $k$. All exclusions have conditional probability zero and hence unconditional probability zero. They exclude both $H(a)=a$ and $H(a-)=a$ at each background jump.

On the remaining regular set, a positive largest root below $N$ is away from background jumps and the chosen atom and saturation contacts. If its chosen mass is strictly between $1-\varepsilon L$ and one, part 3 shows that it is on the increasing branch, strictly above the minimum. In an atom-free neighborhood where $n=r-1$, qualification at $x=x_r(v)$ is equivalent to $T_i\ge g_r(v)$. Strict increase of $g_r$ on this branch therefore gives strict qualifiers immediately to the left of the root. If its chosen mass is zero or one, the count is constant in a neighborhood and the equality is an integer; here also $H(x)-x>0$ immediately to its left. A root with chosen mass exactly $1-\varepsilon L$ was excluded. Thus every positive largest root below $N$ has strict qualifiers arbitrarily close from the left. By part 2 it also has a compact negative gap any positive distance above it.

If $\rho=N$, the equality $H(N)=N$ forces all $N-1$ background groups to satisfy $T_j\ge U$ and the chosen mass to equal one. Regularity makes these $T_j>U$ and $T_i>U+\varepsilon/U$. Every empirical clone then also exceeds $U$, since $d_b<\varepsilon/U$. Hence $x_K=N$ for every $K$ on this regular endpoint event. This proves the terminal case directly and retains its possibly positive probability.

For $0<\rho<N$, choose a small interval of strict qualifiers arbitrarily close below $\rho$; a lattice point lies in that interval for all large $K$. Uniform convergence from part 2 makes it an empirical qualifier. The compact negative gap excludes every empirical qualifier any fixed positive distance above $\rho$. Therefore $x_K\to\rho$. The background selected set is eventually constant because $\rho$ is not a background jump, and $C$ is continuous at $\rho$ because it is not the chosen atom. Uniform CDF approximation then gives
$$
V_K(x_K)\longrightarrow V(\rho),\qquad
\frac{V_K(x_K)}{x_K}\longrightarrow\frac{V(\rho)}\rho.
$$
If $\rho=0$, the common zero-count interval $(0,a(t))$ and the compact negative gap on $[a(t),N]$ show $x_K=0$ eventually, after decreasing $a(t)$ if needed. The same FDP conclusion follows with value zero. At $\rho=N$ it was already exact.

These functionals are measurable on the regular set. Indeed there $\rho$ is the supremum of zero and the rational $x\in(0,N)$ for which $H(x)>x$, with the endpoint $N$ included when $H(N)=N$. The strict-left argument proves this representation, and the count functions are Borel. The displayed FDP thus has a measurable version, agreeing with the defined one almost surely. Every empirical and population FDP is in $[0,1]$, since $0\le V_K\le H_K=x_K$ or $0\le V\le H=\rho$ at its positive maximum. Bounded convergence now proves, for this fixed $\varepsilon$,
$$
F_{\infty,\varepsilon}:=\lim_{K\to\infty}F_{K,\varepsilon}
=\mathbb E f_{\mathrm{pop},\varepsilon}(T).
$$
The exceptional null set may depend on $\varepsilon$. No interchange of limits has occurred.

### 5. Routing the common largest crossing to one surrogate

Now let $\varepsilon\downarrow0$ after the inner limit. Write $n_r=n(r)$ and $B_r=\mathbf1_{\{T_i\ge\beta_r\}}$, and define
$$
R^*=\max\bigl(\{0\}\cup\{r\in[N]:n_r+B_r\ge r\}\bigr).
$$
Both $n_r$ and $B_r$ are nondecreasing with $r$. At a positive maximum $r$, $n_r+B_r=r$: otherwise rank $r+1$ would qualify by monotonicity, unless $r=N$, where a count above $N$ is impossible. Define $f_\varepsilon^*$ to select the unchanged labels with $T_j\ge u_r$ and the chosen label exactly when $B_r=1$, and to divide their null count by $r$. Put it equal to zero at $R^*=0$. It selects exactly $r$ labels at positive rank.

Let $E_H$ be the union over $r\in[N]$, $j\ne i$ of
$$
\{T_i\ge\beta_r,\quad u_r\le T_j\le u(x_r^+(T_i))\}.
$$
Its interval length is at most $C\delta_r(T_i)$, since $u'$ is bounded on the layer near the positive integer $r$. Positive definiteness gives $T_j\mid T_i$ variance $1-\Sigma_{ji}^2>0$ and a density bounded independently of $T_i$. The integrated deficit in part 3 proves
$$
\mathbb P(E_H)\le C\sum_r\mathbb E[\delta_r(T_i)\mathbf1_{\{T_i\ge\beta_r\}}]
=O(\varepsilon^2).
$$
Empty unions have probability zero, and including interval endpoints causes no problem.

We give all routing cases outside $E_H$ and the null set from part 4. Any actual equality root with positive chosen mass in layer $l$ has $n=l-1$, requires $B_l=1$, and has $n_l\ge l-1$. Hence surrogate rank $l$ qualifies. Its upper scalar root is a qualifier by monotonicity of the background count, as proved in part 3; an actual largest root in that layer equals this upper root. A background-only root is an integer $k$ with $n_k=k$, and surrogate rank $k$ qualifies. These implications retain the entire global largest-rank rule.

If $R^*=0$, a positive actual maximum of either type would contradict these implications, so $\rho=0$ and both FDPs vanish.

If $R^*=r>0$ and $B_r=1$, then $n_r=r-1$. Off $E_H$, exactly these unchanged groups survive the threshold $u(x_r^+(T_i))$, with precisely the same labels; no new group can appear because that threshold is at least $u_r$. Thus $H(x_r^+)=x_r^+$, including the saturated case $x_r^+=r$. An actual largest root in layer $l$ must have $l\le r$ by the qualification implication. If $l<r$, it is at most $r-1<x_r^+$. If $l=r$, the scalar upper root is the last possible equality with count $r-1$, so it is at most $x_r^+$. A background-only root $k$ must have $k\le r$; equality $k=r$ would require $n_r=r$, contradicting $n_r=r-1$, and $k<r$ is again earlier. Consequently
$$
\rho=x_r^+(T_i).
$$
This includes $r=N$ and $x_N^+=N$ without an endpoint exclusion.

If $R^*=r>0$ and $B_r=0$, then $n_r=r$, necessarily $r\le N-1$. Maximality at $r+1$, together with $n_{r+1}\ge r$, forces $B_{r+1}=0$. Since $\beta_{r+1}<u_r$, we obtain $T_i<\beta_{r+1}<u_r$ and hence $C(r)=0$. Thus $r$ itself is an actual background-only qualifier. An actual largest root in layer $l\le r$ is at most $r$, and $l>r$ contradicts its surrogate qualification. A background-only root $k>r$ likewise contradicts surrogate maximality. It follows that $\rho=r$, with exactly the surrogate's selected labels. These cases exhaust every possible positive crossing.

### 6. Fractional FDP costs

In the positive-chosen case let $v$ be the number of selected unchanged true nulls and $\delta=\delta_r(T_i)$. The two FDPs are
$$
f_{\mathrm{pop},\varepsilon}=\frac{v+\ell_i(1-\delta)}{r-\delta},\qquad
f_\varepsilon^*=\frac{v+\ell_i}{r}.
$$
For $r\ge2$ their difference in absolute value is
$$
\frac{\delta|v-(r-1)\ell_i|}{r(r-\delta)}\le C\delta.
$$
For $r=1$, $v=0$ and both FDPs are exactly $\ell_i$, even when $r-\delta<1$. The background-only case has exactly equal FDPs. On $E_H$ use the bound one. Integration therefore gives
$$
\mathbb E|f_{\mathrm{pop},\varepsilon}-f_\varepsilon^*|=O(\varepsilon^2).
$$
In particular every all-null model has FDP one at each positive rank, every empty-null model has FDP zero, and mixed labels use this same algebra. The label $\ell_i=1$ at $\theta_i=0$ has been the actual label throughout.

### 7. Signed original-coordinate faces and the outer derivative

For a fixed unchanged vector $w$ define
$$
\lambda_r(w)=f(u_r+,w)-f(u_r-,w),\qquad |\lambda_r(w)|\le1,
$$
where only the chosen coordinate varies and both values use the original full BH largest rank and fixed labels. Let $d_r=\beta_r-u_r=\varepsilon\kappa_r+O(\varepsilon^2)\ge0$. For small $\varepsilon$, the intervals $[u_r,\beta_r]$ lie in pairwise disjoint neighborhoods of the original thresholds. Outside them, every $B_r$ agrees with $\mathbf1_{\{T_i\ge u_r\}}$, so $f_\varepsilon^*=f(T)$. Inside the $r$th interval only qualification $r$ differs. The complete two qualification vectors are exactly those for the original chosen score just above and just below $u_r$ with all other scores frozen at $w$. The exact selected-count identity at the maximum applies to both vectors. Therefore the change of FDP there is $-\lambda_r(w)$, including any cascade of the selected rank. Boundary values have Gaussian probability zero.

Put
$$
L_r(t)=\phi(t-\theta_i)\mathbb E[\lambda_r(W)\mid T_i=t].
$$
We establish its local Lipschitz regularity rather than assuming a face-continuity theorem. For $N\ge2$, let $a=\Sigma_{-i,i}$ and $C_0=\Sigma_{-i,-i}-aa^{\mathsf T}$. The conditional density $p_t$ of $W$ is Gaussian with positive-definite covariance $C_0$ and mean $\theta_{-i}+a(t-\theta_i)$. Direct differentiation gives
$$
\partial_t p_t(w)=p_t(w)\,a^{\mathsf T}C_0^{-1}
(w-\theta_{-i}-a(t-\theta_i)),\qquad
\int|\partial_t p_t(w)|\,dw\le\sqrt{a^{\mathsf T}C_0^{-1}a}.
$$
The inequality follows by Cauchy--Schwarz applied to this centered Gaussian linear form. Integrating in $t$ gives an $L^1$ Lipschitz bound for $p_t$, hence a Lipschitz bound for the conditional integral of bounded $\lambda_r$. Multiplication by the smooth marginal density preserves it locally. If $N=1$, $W$ is empty and $\lambda_r$ is a fixed scalar, so the same assertion is immediate. This also justifies the conditioning and integration below even at intersections of original threshold faces; no pointwise continuity of $\lambda_r$ on such intersections is needed.

The exact band identity now gives
$$
\mathbb E f_\varepsilon^*-F
=-\sum_{r=1}^N\int_{u_r}^{\beta_r}L_r(t)\,dt
=-\sum_{r=1}^N d_r L_r(u_r)+O\left(\sum_r d_r^2\right).
$$
In the target's orthogonal coordinates, conditioning on $T_i=u_r$ is conditioning on $Z=v_i\cdot G=a_r$. The independent residual $Y=G-Zv_i$ has law $\gamma_{E_i}$ and yields exactly the face scores
$$
T_j=\theta_j+\rho_{ji}a_r+v_j^\perp\cdot Y\quad(j\ne i).
$$
Consequently $\lambda_r(W)=\Delta_{i,r}(Y)$ in this conditional law and
$$
L_r(u_r)=\phi(a_r)\int_{E_i}\Delta_{i,r}(y)\,\gamma_{E_i}(dy)=\mu_{i,r}(E_i).
$$
These are precisely the original-coordinate signed face masses, with all other scores held fixed within each jump. They are finite since $|\Delta_{i,r}|\le1$; no positive part has been taken. Combining parts 4--6 with the last two displays proves
$$
F_{\infty,\varepsilon}-F
=-\varepsilon\sum_{r=1}^N\left\{\frac1U-m(u_r)\right\}\mu_{i,r}(E_i)
+O(\varepsilon^2).
$$
Dividing by $\varepsilon$ establishes part 3 in the required order of limits. When $N=1$ the preceding classification reduces to $\rho>0$ exactly when $T_i\ge\beta_1$, up to a null event, and its positive FDP is $\ell_i$; thus it explicitly covers both $\theta_i=0$ and either sign of $\theta_i$. No nonzero-mean compensation was used.

### 8. Parameter-measure costs

Let $M_K=\#\{b:d_b>0\}$. The midpoint equivalence at $a=0$, including its equality convention, gives
$$
\left|\frac{M_K}{K}-\varepsilon L\right|\le\frac1K.
$$
Couple each unchanged group parameter to itself and each chosen clone parameter $(\theta_i-d_b,v_i,\ell_i)$ to $(\theta_i,v_i,\ell_i)$. The mass on which these two coupled points differ is $M_K/(NK)$, at most $\varepsilon L/N+1/(NK)=b_{K,\varepsilon}$. For any Borel set $B$, the difference of its two indicators is zero off that mass and has absolute value at most one, proving $d_{\mathrm{TV}}(\pi_{K,\varepsilon},\pi)\le b_{K,\varepsilon}$ with the stipulated supremum convention. Each moved point costs $d_b<\varepsilon/U$, since the direction and label agree. This coupling gives $W_1(\pi_{K,\varepsilon},\pi)\le(\varepsilon/U)b_{K,\varepsilon}$.

Use the identical coupling with $a\sim P_\varepsilon$ for the continuous chosen group. Its moved mass is exactly $\varepsilon L/N=b_\varepsilon$, and its cost per moved point is at most $\varepsilon/U$. The same two arguments give the asserted continuous total-variation and transport bounds. No comparison in total variation between the quantile measure and the continuous offset law is involved.

All definitions used here are approved in the current context pack. Every crossing, limit, label and metric assertion has been established above; no draft definition or additional unproved result is assumed. The statement and draft status are unchanged, pending independent verification.
