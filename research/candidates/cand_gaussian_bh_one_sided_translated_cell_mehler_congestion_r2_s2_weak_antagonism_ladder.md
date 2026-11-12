---
type: candidate
title: Weak-antagonism rank-two ladder with vanishing positive-width cells
status: failed
target_asset: gaussian_bh_one_sided_translated_cell_mehler_congestion
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  NOT: fail
mode: refute
round: 2
slot: 2
direction: extremal
statement_digest: d49b6ceedd94063add2326953562443ef9d47a5aaa10af748c68abcc336945a7
performed_by: unknown
created_at: '2026-11-10T23:11:57.722Z'
extension_version: 0.0.4
---

## Object

For every integer $N\ge2$, every $0<q\le S(1)$, and every $0<\varepsilon\le1/2$, let $d=2$, $u_r=S^{-1}(qr/N)$, and set
$$
a_1=(1,0),\qquad \theta_1=0,\qquad
a_j=(-\varepsilon,\sqrt{1-\varepsilon^2}),\quad
\theta_j=(1+\varepsilon)u_j\quad(2\le j\le N).
$$
Use all $N$ physical p-values $S(\theta_j+\langle a_j,Z\rangle)$, where $Z\sim N_2(0,I_2)$, and the stated ordinary BH procedure. Thus $I_0=\{1\}$, including when $N$ and $\varepsilon$ vary arbitrarily with $q$. This differs from the excluded collinear ladder: the directions span dimension two, and intermediate translated cells have positive planar measure. Define
$$
W(y)=-\varepsilon y_1+\sqrt{1-\varepsilon^2}\,y_2,
\qquad \Delta_r=u_r-u_{r+1}>0.
$$

## Checks

### H1

Pass. $N\ge2$ and $d=2$ are finite positive integers for each member. No bound on their dependence on $q$ is assumed.

### H2

Pass. All means are finite deterministic real numbers and every displayed direction has Euclidean norm one. Since $u_j\ge u_N\ge1$, every $\theta_j$, $j\ge2$, is strictly positive, whereas $\theta_1=0$. Hence the original null labels are exactly $I_0=\{1\}$.

### H3

Pass. The observation uses $Z\sim N_2(0,I_2)$ and the stated Gram representation. Its covariance is PSD with unit diagonal; repeated alternative directions create permitted singularities.

### H4

Pass. The parameter range is precisely $0<q\le S(1)$. In particular $L=\log(1/q)>1$, $u_r\ge1$, and all thresholds exist.

### H5

Pass. Retain every physical alternative and replace only $p_1$ by zero. The alternatives are ordered by $j$ because their direction is identical and $\theta_j$ strictly decreases in $j$. At the translated point $z=y+u_r a_1$, rank $\ell\ge2$ qualifies for forced BH exactly when its $(\ell-1)$-st alternative qualifies, namely
$$
(1+\varepsilon)u_\ell-\varepsilon u_r+W(y)\ge u_\ell
\quad\Longleftrightarrow\quad
W(y)\ge\varepsilon(u_r-u_\ell).
$$
For fixed $r$, the right-hand thresholds increase with $\ell$. The exact largest-rank masks are consequently
$$
\{R_1(y+u_1a_1)=1\}=\{W<\varepsilon\Delta_1\},
$$
$$
\{R_1(y+u_ra_1)=r\}=\{0\le W<\varepsilon\Delta_r\}
\quad(2\le r<N),
$$
$$
\{R_1(y+u_Na_1)=N\}=\{W\ge0\}.
$$
The strict upper inequalities express exclusion of the next qualifying rank under non-strict BH thresholds; thus ties are retained correctly. These are full forced-rank cells, with no independent optimization or relabeling. In particular the translated density is exactly
$$
H_q(y)=\mathbf1_{\{y_1\ge0\}}
\left[
e^{-u_1y_1-u_1^2/2}\mathbf1_{\{W<\varepsilon\Delta_1\}}
+\sum_{r=2}^{N-1}\frac{e^{-u_ry_1-u_r^2/2}}r
\mathbf1_{\{0\le W<\varepsilon\Delta_r\}}
+\frac{e^{-u_Ny_1-u_N^2/2}}N\mathbf1_{\{W\ge0\}}
\right].
$$
The middle sum is empty if $N=2$.

### H6

Pass. Use exactly $\tau=1/L$, $\sigma^2=1-e^{-2/L}$, independent $G\sim N_2(0,I_2)$, and $Y=e^{-\tau}x+\sigma G$ for arbitrary $x\in\mathbb R^2$. Both $(Y_1,W(Y))$ have variance $\sigma^2$ and their correlation is $-\varepsilon$. Their joint density is everywhere at most
$$
\frac{1}{2\pi\sigma^2\sqrt{1-\varepsilon^2}}.
$$
No assumption on the mean $e^{-\tau}x$ enters this bound.

### NOT

Fail. Both conclusions hold throughout this family, uniformly including $\varepsilon\downarrow0$ and $N\to\infty$.

For part (a), Gaussian change of variables in the exact defining density gives
$$
\int H_q\,d\gamma_2
=\sum_{r=1}^N\frac1r\Pr\{R_1(Z)=r,\ Z_1\ge u_r\}.
$$
If forced BH has rank $r$ and the restored p-value is at most $qr/N$, restoring it preserves qualifying rank $r$ and cannot create a larger rank. Conversely, replacing a rejected p-value by zero preserves its original rank: every higher threshold already counted that rejected p-value. These facts hold with non-strict ties. Thus the summands are exactly the disjoint events that the sole null is rejected and original BH has rank $r$. The displayed integral equals the actual FDR.

For part (b), Mills' inequality gives $\phi(u)/u\le2S(u)$ for $u\ge1$. A marginal Gaussian density is bounded by $1/(\sqrt{2\pi}\sigma)$, so the first and last terms of $H_q$ each have expectation at most $2q/(N\sigma)$, uniformly in $x$. For every middle rank, integrate the joint-density bound over $y_1\ge0$ and $0\le W<\varepsilon\Delta_r$. Its expectation is at most
$$
\frac{\varepsilon\Delta_r}{2\pi\sigma^2\sqrt{1-\varepsilon^2}}
\frac{e^{-u_r^2/2}}{r u_r}
\le \frac{q\varepsilon\Delta_r}{N\sigma^2},
$$
because $\sqrt{2/\pi}/\sqrt{1-\varepsilon^2}\le\sqrt{8/(3\pi)}<1$. Hence, for $N\ge3$,
$$
\sup_x\mathbb E H_q(Y)
\le\frac{4q}{N\sigma}
+\frac{q\varepsilon(u_2-u_N)}{N\sigma^2}.
$$
Put $\kappa=1-e^{-2}$. Concavity gives $\sigma^2\ge\kappa/L$. The Gaussian hazard satisfies $\phi(t)/S(t)\ge t$ for $t>0$, whence
$$
u_2-u_N\le\frac{\log(N/2)}{u_N}.
$$
The lower Mills bound $S(u)\ge\phi(u)u/(u^2+1)$, and $u\ge1$, imply $\log(1/S(u))\le3u^2$: indeed $\log(u+1/u)\le\log2+\log u\le\log2+(u^2-1)/2$. In particular $u_N\ge\sqrt{L/3}$. Therefore
$$
\frac{\sup_x\mathbb E H_q(Y)}{q\sqrt L}
\le\frac4{N\sqrt\kappa}
+\frac{\sqrt3\,\varepsilon\log(N/2)}{N\kappa}<8.
$$
Here one may use $\log(N/2)/N\le1$ and $\varepsilon\le1/2$. For $N=2$ the middle term is absent and the same constant holds. Consequently $C=8$ works on this entire family for every $q\le S(1)$, and thus also for an admissible universal $q_0\le\min\{S(1),e^{-1}\}$. Positive-width intermediate cells shrink proportionally to $\varepsilon\Delta_r$; their total contribution cannot produce an inverse-loading divergence.

## Failure

NOT fails: the exact weak-antagonism ladder obeys the mass identity and the uniform bound $\sup_x T_{1/L}H_q(x)\le8q\sqrt L$, even for arbitrary vanishing $\varepsilon(q)$ and growing finite $N(q)$.
