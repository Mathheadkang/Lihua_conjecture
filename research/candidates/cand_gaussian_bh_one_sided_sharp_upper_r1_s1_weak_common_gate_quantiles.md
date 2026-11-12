---
type: candidate
title: Weak common gates with finite one-sided source quantile blocks
status: failed
target_asset: gaussian_bh_one_sided_sharp_upper
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: idea_9692ea16c23a
statement_digest: 03b9629ae9bd4a6f3de6d1b9c08dfb86fb31a1aa0b7c62a1844a84111ad32086
performed_by: unknown
created_at: '2026-11-04T10:02:28.774Z'
extension_version: 0.0.4
---

## Object

This instantiates the assigned common-gated family in the weak-coupling regime, using deterministic quantiles of the one-sided source design. It includes strictly negative true-null means. No original scalar first-crossing map is assumed to survive the loading replacement.

Let $p(c)=\overline\Phi(c)$ and, for sufficiently small $q$, put
$$
L=\log(1/q),\quad B=\lceil q^{-1}\rceil,\quad
\alpha=q/B,\quad k=\lceil\alpha^{-2}\rceil,\quad r=1/k,
$$
$$
\epsilon=L^{-1/2},\quad s=\sqrt{1-\epsilon^2},\quad
m=k^{k^3},\quad N=Bm,\quad y=\sqrt{2\log(1/\alpha)},\quad\eta=1/y.
$$
The source one-sided parameters at local level $\alpha$ are
$$
b=rp^{-1}(r^2),\quad
W_r(a)=\frac{(1-\alpha e^{a^2/2})p(a/r)}\alpha,
\quad b\leq a\leq y,
$$
$$
\tau=W_r(b),\quad \pi_0=1-r-\tau,\quad
c_0=p^{-1}\!\left(\frac{\alpha(r+\tau)}{1-\alpha\pi_0}\right).
$$
The secondary probability measure $\nu$ on $[b,y]$ has survival function $\nu([a,y])=W_r(a)/\tau$. These formulas and the NONNULL loading $-1$ are taken from the native source `lei2026_gaussian_bh`, PDF page 44, equations (146)–(151), as used by `lei2026_one_sided_fdr_lower`.

Every block has $n_p=mr=m/k$ primary coordinates of mean $\mu_p=c_0+b$, and $n_s=\lceil m\tau\rceil$ secondary coordinates. Let $a_h$ be the $((h-1/2)/n_s)$ quantile of $\nu$; the $h$th secondary mean is $\mu_h=a_h/r+a_h$. The remaining $m_0=m-n_p-n_s$ coordinates are null: give the first $\lfloor m_0/2\rfloor$ mean zero and the rest mean $-q$. These shifts explicitly remain true nulls under the project's one-sided convention.

Let $W,Z_1,\ldots,Z_B$ and all $E_{ji}$ be mutually independent standard normals, and define $Y_j=\epsilon Z_j+sW$. In block $j$ use
$$
T_{ji}=\theta_{ji}+rZ_j+\sqrt{1-r^2}E_{ji},\quad\theta_{ji}\in\{0,-q\},
$$
for its nulls, and $\mu_p-Y_j$ or $\mu_h-Y_j$ for its primary or secondary nonnulls. Apply ordinary BH ONCE to all $N$ p-values $\overline\Phi(T_i)$ at level $q$.

The integers above are mathematical definitions; this construction requires no allocation or numerical simulation of the enormous arrays.

## Checks

### H1

$B,k,m,N,n_p,n_s,m_0$ are finite integers at each $q$. Since $r\sim\alpha^2$, $\tau\leq r^2/\alpha=O(\alpha^3)$, so $m_0>0$ for small $q$. The primary count $mr$ is an exact integer.

### H2

All means and type counts are deterministic. All primary and secondary means are positive for small $q$, while the null means are zero or negative. Thus the stated nulls are exactly $I_0^{(1)}=\{i:\theta_i\leq0\}$; negative nulls are not removed or relabeled.

### H3

Use common factors $(W,Z_1,\ldots,Z_B)$. Null loadings have norm $r$ and residual variance $1-r^2$. Every nonnull in block $j$ has unit loading $-s e_W-\epsilon e_j$ and residual variance zero. Hence the covariance is a Gram matrix plus a nonnegative residual diagonal and has unit diagonal. It is admissible even with singular repeated nonnull coordinates.

### H4

Every observation is an affine function of the displayed independent normals, so the whole vector is exactly jointly Gaussian with deterministic mean and covariance.

### H5

Use one-sided p-values, the largest qualifying global BH rank, all ties, and $\mathbb E[V/(R\vee1)]$. Conditional on the common factors all null p-values are independent and all nonnull p-values are deterministic. The argument below does not add local block FDRs.

### NOT

Fail. The exact finite-array FDR is $O(q)$ and therefore has zero normalization by $q\sqrt{\log(1/q)}$.

**A source-secondary cap without null assistance.** Put
$$
\mathcal H=\{|W|\leq2y,\ \max_j|Z_j|\leq2y\},\qquad
\mathcal G=\{\min_jY_j\leq y-2\eta\}.
$$
On $\mathcal H\cap\mathcal G$, let $Y_*=\min_jY_j$ and set
$$
A=\eta+(Y_*)_+,\quad C=A/r,\quad
d=\frac{A+rY_*}{1+r},\quad h=\frac{A-Y_*}{1+r},
$$
so that $d/r=C-h$. Uniformly on these events, for small $q$,
$$
b\ll\eta/2\leq d\leq A\leq y-\eta,
\quad h\geq\eta/(1+r),\quad h/C=O(ry^2)=o(1).
$$
Indeed $Y_*\geq-3y$ on $\mathcal H$, $ry^2\to0$, and $b=O(r\sqrt{\log(1/r)})\ll\eta$. A secondary source mean indexed by $a$ satisfies $a/r+a-Y_*\geq C$ exactly when $a\geq d$.

The midpoint-quantile secondary design has tail proportion at least $W_r(d)-1/m$. This follows from deterministic quantile discrepancy at most $1/n_s$ and $n_s/m\geq\tau$. Also
$$
1-\alpha e^{d^2/2}\geq1-e^{-1/2}=:c_1>0
$$
for small $q$, and $mW_r(y-\eta)\to\infty$: its negative logarithm is $O(y^2/r^2)=O(k^2\log(1/\alpha))$, whereas $\log m=k^3\log k$ is larger by an unbounded factor. Thus this tail proportion is at least $W_r(d)/2$, uniformly over the displayed range.

The contribution from that single block's secondary coordinates to the GLOBAL normalized crossing at $C$ is at least
$$
\frac{\alpha W_r(d)}{2p(C)}
\geq\frac{c_1}2\frac{p(C-h)}{p(C)}
\geq\frac{c_1}2\exp\!\left(\frac{\eta^2}{4r}\right)>1.
$$
For the last bound integrate the normal hazard $\lambda(t)\geq t$ over $[C-h,C]$, using $C\geq\eta/r$ and $h/C=o(1)$. This proves an exact nonnull-only BH cap $C_{\rm BH}\leq A/r$, with the same cap after setting any null p-value to zero. Neither empirical-null concentration nor a population FDR limit is needed.

**The discarded factor events cost $o(q)$.** Since every $Y_j$ is standard normal,
$$
\mathbb P(\mathcal G^c)\leq p(y-2/y)=O(\alpha/y)=o(q).
$$
The factor union bound gives
$$
\mathbb P(\mathcal H^c)\leq2(B+1)p(2y)
=O((B+1)\alpha^4/y)=o(q).
$$

**An integrable cap for every null block.** For a null in block $j$, choose a different block $\ell$ and put $V_j=(Y_j+Y_\ell)/2$. Its variance is $v^2=1-\epsilon^2/2\in[1/2,1]$, and $U_j=V_j/v$ is standard normal with
$$
\operatorname{Corr}(Z_j,U_j)=\frac{\epsilon}{2\sqrt{1-\epsilon^2/2}}
\leq\rho_0:=1/\sqrt2<1.
$$
The global cap gives $rC_{\rm BH}\leq\eta+(V_j)_+\leq1+|U_j|$, also for every null leave-one-out count. For a negative null mean, its conditional upper-tail CDF is bounded above by the corresponding zero-mean null CDF. Uniformly on $\mathcal H$, for any relevant cutoff $c\geq p^{-1}(q)$ and $a=rc\leq y$, the Mills bounds therefore give
$$
\frac{\mathbb P(T_i\geq c\mid W,Z)}{p(c)}
\leq2e^{-a^2/2+aZ_j}.
$$
The relative prefactor error is $o(1)$ and the exponent error is $O(r^2y^2)=o(1)$; this uses $r\sim\alpha^2$ and the displayed growing factor bounds.

There is a finite constant $K$ uniform over every standard Gaussian pair $(Z,U)$ with correlation in $[0,\rho_0]$ such that
$$
\mathbb E\sup_{0\leq a\leq1+|U|}e^{-a^2/2+a|Z|}\leq K.
$$
To check finiteness uniformly, set $x=|Z|,t=|U|$. The supremum is at most $e^xK_0(x,t)$, where $K_0=e^{x^2/2}$ if $x\leq t$ and $K_0=e^{-t^2/2+xt}$ otherwise. The folded Gaussian density is bounded by a fixed constant times $\exp[-(x^2+t^2-2\rho xt)/(2(1-\rho^2))]$. On $x\leq t$ its exponent after multiplying by $K_0$ equals $-(t-\rho x)^2/(2(1-\rho^2))$, which is bounded above by a negative fixed multiple of $x^2+t^2$. On $x>t$ the resulting precision matrix has positive determinant $(1-\rho)/(1+\rho)$ and positive trace, uniformly away from degeneracy on $[0,\rho_0]$. The extra factor $e^x$ is integrable against both uniform Gaussian bounds.

Finally condition on all common factors and set each null p-value to zero in turn. The exact BH leave-one-null identity bounds its expected FDP contribution by $q/N$ times the conditional null CDF-to-threshold ratio at that leave-one-out threshold. The nonnull cap above applies to all these thresholds. Summing the displayed envelope over all null coordinates and integrating yields
$$
\mathbb E[\operatorname{FDP}\,\mathbf1_{\mathcal H\cap\mathcal G}]
\leq2Kq.
$$
Adding the $o(q)$ discarded-event probabilities proves $\operatorname{FDR}\leq2Kq+o(q)$ for the exact finite Gaussian arrays. Hence their target normalization tends to zero.

## Failure

NOT fails: even at $\epsilon\asymp1/\sqrt{\log B}$, the retained one-sided source secondary means force an early global crossing; averaging two block gates gives a uniformly nonparallel Gaussian cap and an integrable null-tail envelope, so this prescribed fast-small-loading quantile family has FDR $O(q)$.
