---
type: candidate
title: Tangent reserve block with growing paired driver groups
status: survived
target_asset: gaussian_bh_positive_p_path_jump_budget
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: pass
mode: refute
round: 4
slot: 3
direction: drop_hypothesis
statement_digest: 301a9fdf2ecda11e42541631b84ac56c2ad1d8a75b5cf72d593e5cd71674b0e2
performed_by: unknown
created_at: '2026-11-09T21:45:10.832Z'
extension_version: 0.0.4
---

## Object

This family has two macroscopic blocks and a number of distinct driver groups growing with dimension. The independent reserve block produces repeated macroscopic rank changes; neither increasing clone multiplicities alone nor a fixed number of effective groups produces these changes.

Write $S=\overline\Phi$, $u=S^{-1}$, and $\phi$ for the standard normal density. Fix
$$
q=S(1),\qquad a=-\frac45,\qquad b=\frac35,
\qquad \alpha=\frac1{100},\quad \beta=\frac8{100},\quad \gamma=\frac{91}{100}.
$$
Set
$$
r_0=\frac{S(2)}q,\qquad
\lambda=\frac{\phi(2)}q,\qquad
d=\frac{\lambda}{1-a},\qquad
h=\frac{r_0-\alpha-\beta}{d},\qquad H=2+h,
$$
and
$$
x_0=u(q\alpha)+\frac1{10},\qquad
K=[x_0-1/20,x_0+1/20].
$$
For orientation, $r_0\approx0.1433935$, $\lambda\approx0.3403037$, $d\approx0.1890576$, $h\approx0.2824192$, and $\gamma/d\approx4.8133$. The construction and arguments use the exact constants above.

Let $N$ tend to infinity through multiples of $200$. Put
$$
m=\frac{91N}{200},\qquad \Delta_N=\frac2{dN},\qquad
v_j=H-(j-1/2)\Delta_N\quad(1\le j\le m).
$$
For independent standard normals $X,U$, the full original score vector consists of:

- $\alpha N$ selected true-null scores $X$;
- $\beta N$ reserve scores $2+U$;
- $m$ positive-slope driver scores $v_j+aU+b(X-x_0)$;
- $m$ negative-slope driver scores $v_j+aU-b(X-x_0)$.

All scores, all means, all labels, and the ordinary non-strict largest-rank BH procedure are retained. In particular, any driver with nonpositive mean is also a true null; its nonnegative budget is simply omitted from the lower bound below.

## Checks

### H1

$N\in200\mathbb N$ is finite for every model, and the four group sizes sum to $N$. The number of distinct driver means grows linearly with $N$.

### H2

The selected means are zero, the reserve means are $2$, and the driver means are the finite real numbers $v_j\mp bx_0$. Thus all selected coordinates belong to the actual original set $I_0=\{i:\theta_i\le0\}$. No negative driver mean is relabeled or replaced.

### H3

The centered score loadings on $(X,U)$ are respectively
$$
(1,0),\quad(0,1),\quad(b,a),\quad(-b,a).
$$
They all have Euclidean norm one. Their Gram matrix is positive semidefinite, has unit diagonal, and has rank two. This is an exactly jointly Gaussian admissible model, including all singularities and ties.

### H4

The fixed level $q=S(1)$ belongs to the required interval $0<q\le S(1)$. A divergent sequence at this single admissible level suffices to refute a constant universal over all levels.

### H5

For each selected null, conditioning in the finite identity leaves precisely the independent residual $U$. Write $x=u(t)$, so the conditional full original scores are exactly those in Object with $X=x$. Its original weight is $g_i(t)=1$ because $\theta_i=0$.

For $x\in K$, one has $x>u(q\alpha)$, hence $t=S(x)<q\alpha$; the selected block alone makes the rank $\alpha N$ qualify. Consequently $R_i(t)\ge\alpha N$, and throughout this interval the original clipped quantity is the unclipped expression
$$
A_i(t)=\frac{t}{q(R_i(t)/N)}.
$$
The following calculation uses actual one-sided largest ranks and records their net jumps. It does not count separate simultaneous auxiliary events.

### NOT

We show that the selected-null contribution alone grows at least as a positive constant times $\sqrt N$.

**A residual set of probability of order $N^{-1/2}$.** Define
$$
r(U)=\frac{S(2+U)}q,\qquad
k(U)=\lceil Nr(U)\rceil,\qquad
z(U)=k(U)-Nr(U),\qquad y_k=u(qk/N).
$$
Let
$$
I_N=\left[\sqrt{\frac{0.565}{\lambda N}},\sqrt{\frac{0.585}{\lambda N}}\right],
\qquad
E_N=\{U\in I_N:0.63\le z(U)\le0.67\}.
$$
The length of $I_N$ is $c_I/\sqrt N$ for an exact constant $c_I>0$. Uniformly on this interval,
$$
F_N(U):=N\{r_0-\lambda U-r(U)\}
=-\lambda NU^2+O(NU^3)\in[-0.60,-0.55]
$$
for all sufficiently large $N$.

The set $E_N$ has Lebesgue measure at least $0.005|I_N|$ for all sufficiently large $N$. Here is a direct phase-count justification: $-r'(U)=\phi(2+U)/q$ lies between $\lambda/2$ and $2\lambda$ on $I_N$; the range of $Nr(U)$ contains at least $(\lambda/2)N|I_N|-2$ full unit cells. In each full cell the phase condition $z\in[0.63,0.67]$ has a preimage interval of length at least $0.04/(2\lambda N)$. Multiplying gives $0.01|I_N|-0.04/(\lambda N)\ge0.005|I_N|$ eventually. Since the density of $U$ is bounded below near zero, there is $c_E>0$ independent of $N$ with
$$
\mathbb P(U\in E_N)\ge\frac{c_E}{\sqrt N}.
$$

**Exact integer count at the reserve's first possible rank.** Fix $U\in E_N$ and abbreviate $k=k(U)$. At the threshold $y_k$, put
$$
V_N(U)=\frac{H+aU-y_k}{\Delta_N}+\frac12,
\qquad W_N(x)=\frac{b(x-x_0)}{\Delta_N}.
$$
For $x\in K$, both floor arguments $V_N\pm W_N$ lie strictly between $0$ and $m$ for all sufficiently large $N$: their underlying score offsets converge to $h\pm b(x-x_0)$, which lie in $[h-0.03,h+0.03]\subset(0,\gamma/d)$. Thus there is no clipping at $0$ or $m$ at this rank. The exact number of scores above $y_k$, including the selected and reserve blocks, is
$$
C_N(k,x,U)=(\alpha+\beta)N
+\lfloor V_N+W_N(x)\rfloor+\lfloor V_N-W_N(x)\rfloor.
$$
Define its smooth upper count at a real rank $\ell\ge k$ by
$$
\mathcal C_N(\ell,U)
=(\alpha+\beta)N+dN\{H+aU-u(q\ell/N)\}+1.
$$
Then $\mathcal C_N(k,U)=(\alpha+\beta)N+2V_N$. The surplus
$$
e_N(U)=\mathcal C_N(k,U)-k
$$
obeys the following uniform expansion. Since $z\in[0.63,0.67]$,
$$
y_k=2+U-\frac{qz}{N\phi(2+U)}+O(N^{-2}),
$$
and therefore
$$
e_N(U)=F_N(U)+1-
\left(1-\frac{dq}{\phi(2+U)}\right)z+O(N^{-1}).
$$
Now $dq/\phi(2)=1/(1-a)=5/9$. The displayed bounds on $F_N$ and $z$ imply, for all sufficiently large $N$,
$$
0.09\le e_N(U)\le0.18.
$$
Because $(\alpha+\beta)N$ and $k$ are integers, the two-floor formula gives exactly
$$
C_N(k,x,U)=
\begin{cases}
k,&\{V_N+W_N(x)\}\le e_N(U),\\
k-1,&\{V_N+W_N(x)\}>e_N(U),
\end{cases}
$$
apart from harmless equality values at the switching points; braces denote fractional part.

**The largest BH rank really switches macroscopically.** For every $\ell\ge k$, the exact threshold count is at most $\mathcal C_N(\ell,U)$. Indeed, the driver floor arguments stay positive as the threshold decreases, and any upper clipping at $m$ only decreases the count. The selected and reserve blocks are both above these thresholds. Moreover,
$$
\frac{\partial\mathcal C_N}{\partial\ell}
=\frac{dq}{\phi(u(q\ell/N))}\le0.6
$$
uniformly for $k\le\ell\le N$ and $U\in E_N$, for all sufficiently large $N$. To see the uniformity, $u(q\ell/N)$ ranges from $1$ to $y_k\to2$, and $\phi$ is decreasing on the positive half-line, so the maximum tends to $5/9<0.6$.

It follows that for every integer $\ell\ge k+1$,
$$
\mathcal C_N(\ell,U)-\ell
\le0.18-0.4(\ell-k)<0.
$$
Thus no rank above $k$ qualifies, at any $x\in K$. When the displayed exact count is $k$, the actual largest BH rank is exactly $k$. When that count is $k-1$, no rank at least $k$ qualifies. For every rank below $k$, the reserve block is absent because its score is $2+U< u(q\ell/N)$. Monotonicity of a threshold count and the absence of the $\beta N$ reserve scores then give
$$
R(x)\le k-\beta N-1
$$
in the low state. As already checked, the low rank is also at least $\alpha N$. These are actual largest-rank conclusions for the full original vector, not proposed ranks.

**Linearly many net positive charges conditional on this residual set.** The phase $V_N+W_N(x)$ increases with slope $bdN/2$ in $x$. Hence on the interval $K$, of length $1/10$, there are at least $bdN/20-2$ complete high-to-low transitions as $x$ increases. At each such transition the actual rank changes from $k$ to at most $k-\beta N-1$. Since $x=u(t)$ decreases as $t$ increases, these are downward net jumps of $A_i$ in the $t$ direction, exactly the positive charges in $B_i$.

Put $x_+=x_0+1/20$. For large $N$, $k/N<0.2$, and the charge at each transition is at least
$$
\frac{S(x_+)}q
\left\{\frac1{R_{\rm low}/N}-\frac1{k/N}\right\}
\ge\frac{S(x_+)}q\frac{\beta}{0.2^2}
=:j_0>0.
$$
The one-sided low state has the asserted rank gap even if additional threshold events coincide; thus this is a bound for the actual merged net discontinuity. The selected-null original weight is exactly one. Consequently, for some $c_B>0$ and every sufficiently large $N$,
$$
B_i(U)\ge c_BN\qquad(U\in E_N)
$$
for every selected null $i$.

There are $\alpha N$ such nulls, and all other true-null budgets are nonnegative. Therefore
$$
\frac1N\sum_{i\in I_0}\mathbb E B_i
\ge\alpha c_BN\,\mathbb P(U\in E_N)
\ge\alpha c_Bc_E\sqrt N\longrightarrow\infty.
$$
Since $q=S(1)$ is fixed, division by $\sqrt{\log(1/q)}$ does not change divergence. This passes NOT for the specified concrete legal family.
