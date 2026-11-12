---
type: candidate
title: Source-form common-gated blocks in a primary-cap regime
status: failed
target_asset: gaussian_bh_two_sided_sharp_upper
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 2
slot: 2
direction: idea_9692ea16c23a
statement_digest: 2aaf3b157d839619c9429607bf182d896b1dacb3bc592c3dc8041bc442b8ed40
performed_by: unknown
created_at: '2026-11-04T08:53:53.945Z'
extension_version: 0.0.4
---

## Object

This is one explicit strong-coupling regime of the common-gated growing-block test case, not a claim about all intermediate couplings. The secondary means are retained source-design points and the primary mean is the exact two-sided source mean. The argument below is uniform over the secondary design and uses no finite-to-population FDR transfer.

Write $p(c)=2\overline\Phi(c)$ and let $q$ tend to zero. Put
$$
B=\lceil q^{-2}\rceil,\quad \alpha=q/B,\quad
k=\lceil\alpha^{-2}\rceil,\quad r=1/k,\quad
m=k^{k^3},\quad N=Bm,\quad \epsilon=s=1/\sqrt2.
$$
All of these are mathematical definitions; no array of size $m$ or $N$ is allocated.

Here are the two-sided source parameters at local level $\alpha$. Let
$$
L_a(y)=e^{-a^2/2}\cosh(ay),\quad
M(y)=\sup_{a\geq0}L_a(y),\quad
\alpha M(y_\alpha)=1.
$$
For $y>1$, write $a(y)$ for the positive maximizer and $y(a)$ for its inverse. Set
$$
A_\alpha=a(y_\alpha),\quad b_r=rp^{-1}(r^2),\quad
\tau=\frac{[1-\alpha M\{y(b_r)\}]r^2}{\alpha},\quad
\pi_0=1-r-\tau,
$$
$$
c_{\alpha,r}=p^{-1}\!\left(\frac{\alpha(r+\tau)}{1-\alpha\pi_0}\right),
\qquad \mu_p=c_{\alpha,r}+y(b_r).
$$
These are well-defined for all sufficiently small $q$. The secondary design measure $\nu$ on $[b_r,A_\alpha]$ is determined by
$$
\nu([a,A_\alpha])=\frac{[1-\alpha M\{y(a)\}]p(a/r)}{\alpha\tau}.
$$
The formulas, in particular the positive source loading and the mean $c_{\alpha,r}+y(b_r)$, were checked against supplied TeX `bh_fdr_research/reference_arxiv/FDR_BH_v4.tex`, lines 902–1007, and native source pages 11–12.

Every block has $a_p=m/k=mr$ primary coordinates, $a_s=\lfloor m\tau\rfloor$ secondary coordinates, and $m_0=m-a_p-a_s$ null coordinates. For $h=1,\ldots,a_s$, let $a_h$ be the $((h-1/2)/a_s)$ quantile of $\nu$ and put $\mu_h=a_h/r+y(a_h)$. This is a deterministic quantile discretization; no random mean mixture is used. The proof does not presume that this discretization attains the source lower envelope.

Let $W,Z_1,\ldots,Z_B$ and all residuals be mutually independent standard normals. Set $Y_j=\epsilon Z_j+sW$. In block $j$ the coordinates are
$$
T_{j,i}=rZ_j+\sqrt{1-r^2}\,E_{j,i}
\quad\text{for its }m_0\text{ nulls},
$$
$$
T_{j,i}=\mu_p+Y_j
\quad\text{for its }a_p\text{ primary copies},
\qquad
T_{j,h}=\mu_h+Y_j
\quad\text{for its secondary coordinates}.
$$
Apply ordinary BH once to all $N$ two-sided p-values at level $q$.

## Checks

### H1

$B,k,m,N,a_p,a_s,m_0$ are finite integers, $a_p=mr$ is an exact integer, and $m_0>0$ for small $q$, since $r\to0$ and $0\leq\tau\leq r^2/\alpha\to0$. No dimension is held fixed in the $q$ limit.

### H2

All means and counts are deterministic. The null means are zero, and all source primary and secondary means above are strictly positive for small $q$. Thus the displayed null coordinates are exactly the true nulls.

### H3

Use $B+1$ common factors $(W,Z_1,\ldots,Z_B)$. A null row has loading $r e_j$ and residual variance $1-r^2$. Every nonnull row in block $j$ has loading $s e_W+\epsilon e_j$ and residual variance zero. Consequently
$$
\Sigma=AA^{\mathsf T}+\operatorname{diag}(1-\|A_i\|^2)
$$
is positive semidefinite with unit diagonal, including its singular nonnull copies. In particular each nonnull remains variance one after the common-gate replacement.

### H4

The entire observation is an affine function of the displayed mutually independent Gaussian variables, hence is exactly jointly Gaussian with this deterministic covariance.

### H5

The p-values are $p(|T_i|)$ and BH uses one global rank among all $N$ coordinates. Conditional on all common factors, null p-values are independent and nonnull p-values are deterministic. All ties are retained. No sum of local-block FDRs is used.

### NOT

Fail. In fact this finite-array family has
$$
\operatorname{FDR}^{(2)}_{\rm BH}\leq q\{1+o(1)\}+q^{2+o(1)},
$$
so its normalization by $q\sqrt{\log(1/q)}$ tends to zero.

First set
$$
t_* =q a_p/N=\alpha r,\quad c_*=p^{-1}(t_*),\quad
d_q=\mu_p-c_*.
$$
Since $r\sim\alpha^2$, $\tau/r\leq r/\alpha=O(\alpha)$, and
$$
\frac{p(c_{\alpha,r})}{p(c_*)}
=\frac{1+\tau/r}{1-\alpha\pi_0}=1+O(\alpha).
$$
Normal tail ratios therefore give $c_{\alpha,r}-c_*\to0$. Also $b_r\to0$ and $y(b_r)\to1$, so $d_q\to1$. Finally $c_*\sim\sqrt{6\log(1/\alpha)}$ and $r(c_*+1)\to0$. This checks the local-$\alpha$ calibration rather than substituting a fixed-$\alpha$ remainder.

Consider the factor-measurable event
$$
\mathcal A=\{\max_jY_j\geq-d_q\}.
$$
On $\mathcal A$, some block has $\mu_p+Y_j\geq c_*$, so all of its $a_p$ primary p-values are at most $t_*$. Their rank alone qualifies for global BH, implying $R\geq a_p$. The same lower bound holds after any null p-value is replaced by zero.

Let $\sigma=\sqrt{1-r^2}$ and $h_{r,z}(c)=\mathbb P(|rz+\sigma E|\geq c)$. For $0\leq c\leq c_*$, the Gaussian hazard bound $\phi(x)/\overline\Phi(x)\leq x+1$ for $x\geq0$ gives
$$
\frac{h_{r,z}(c)}{p(c)}
\leq\frac{1+\exp(\kappa|z|)}2,
\qquad \kappa=\frac{r(c_*+1)}\sigma.
$$
Indeed the unfavorable tail is at most $\overline\Phi(c)$, while the favorable tail's argument is at least $c-r|z|/\sigma$; integrating the hazard over that shift bounds its tail ratio by $\exp\{r|z|(c+1)/\sigma\}$.

For completeness, condition on all common factors and replace a null p-value by zero. Let $R^{(i)}$ be the resulting rejection count. The exact BH identity and conditional independence give the $i$th expected FDP contribution
$$
\mathbb E\!\left[\frac{F_i(qR^{(i)}/N)}{R^{(i)}}\,\middle|\,W,Z\right].
$$
On $\mathcal A$, $R^{(i)}\geq a_p$, so its p-value threshold is in $[t_*,q]$ and its Gaussian cutoff lies in $[p^{-1}(q),c_*]$. Applying the preceding tail-ratio bound, summing over all nulls, and integrating the factors yields
$$
\mathbb E[\operatorname{FDP}\,\mathbf1_{\mathcal A}]
\leq q\frac{m_0}{m}
\left\{\frac12+e^{\kappa^2/2}\Phi(\kappa)\right\}
\leq q\{1+o(1)\},
$$
because $\kappa\to0$. This is a finite-$N$ calculation, uniform in the secondary nonnull arrays.

It remains to bound the complementary gate event. With $M_B=\max_jZ_j$ and $s=\epsilon=1/\sqrt2$,
$$
\mathbb P(\mathcal A^c)
=\mathbb E\Phi\!\left(\frac{-d_q-\epsilon M_B}{s}\right)
=B^{-1+o(1)}=q^{2+o(1)}.
$$
To check the logarithmic equivalence, $M_B/\sqrt{2\log B}\to1$; its fixed-relative downward deviation has superpolynomially small probability. Restricting $M_B$ to a fixed-relative band and using the normal tail exponent gives logarithmic rate $-\epsilon^2/s^2=-1$; then let the band's relative width go to zero. The bounded $d_q$ changes only a lower-order term. Since FDP is at most one on $\mathcal A^c$, the asserted FDR bound follows.

## Failure

NOT fails: at $B\asymp q^{-2}$ and $\epsilon=1/\sqrt2$, a global primary cap controls FDR by $q\{1+o(1)\}$ except on a $q^{2+o(1)}$ gate event; secondary-source detail cannot remove this obstruction.
