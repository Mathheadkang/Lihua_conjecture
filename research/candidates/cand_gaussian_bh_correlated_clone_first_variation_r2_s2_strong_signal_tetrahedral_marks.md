---
type: candidate
title: Strong-signal extreme with four transverse clone marks
status: failed
target_asset: gaussian_bh_correlated_clone_first_variation
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  H7: pass
  H8: pass
  H9: pass
  H10: pass
  H11: pass
  NOT: fail
mode: refute
round: 2
slot: 2
direction: extremal
statement_digest: 680547805d2575723444c5de508a946ed17ed1f6ae88a68bfd490ee4a27dda26
performed_by: unknown
created_at: '2026-11-08T22:14:53.420Z'
extension_version: 0.0.4
---

## Object

Take $N=4$, $K=4$, $q=1/10$, $d=4$, $\Sigma=I_4$, $\theta=(0,8,8,8)$, $v_j=e_j$, and $i=1$. Write $G=(Z,Y_2,Y_3,Y_4)$ with independent standard normal coordinates and identify $E_1$ with $\mathbb R^3$. Take all $c_b=0$ and
$$
w_1=e_2,\quad w_2=e_3,\quad w_3=e_4,\quad
w_4=-\frac{e_2+e_3+e_4}{\sqrt3}.
$$
Thus
$$
g(y)=\min\{y_2,y_3,y_4,-(y_2+y_3+y_4)/\sqrt3\}.
$$
All four marks have norm one, so the minimum perturbed score is exactly
$$
H_1^\varepsilon=\frac{Z+\varepsilon g(Y)}{\sqrt{1+\varepsilon^2}}.
$$
The other reduced scores are $8+Y_j$. This tests an unbalanced strong-signal configuration with a multidimensional four-cone minimum, rather than a scalar split, an antipodal pair, or a nearly singular covariance. The three finite signal means are kept finite throughout: no deterministic-signal replacement is made.

## Checks

### H1

$N=4$ is a positive integer.

### H2

$K=4$ is a positive integer.

### H3

$q=1/10\in(0,1/2)$.

### H4

$\theta\in\mathbb R^4$, and $I_4$ is symmetric, positive definite, and unit diagonal. The displayed $T_j=\theta_j+G_j$ is exactly jointly Gaussian with those parameters.

### H5

The representation has finite dimension four and unit rows $v_j=e_j$, with $v_j\cdot v_k=\delta_{jk}$.

### H6

Use exactly $p_j=\overline\Phi(T_j)$. The actual one-sided true-null set is $I_0=\{1\}$.

### H7

Use ordinary BH at level $1/10$, with its largest qualifying rank and non-strict inequalities, for both the original four scores and all sixteen clones.

### H8

$i=1\in[4]$, $Z=G_1$, and $Y=(0,G_2,G_3,G_4)\in E_1$. These Gaussian variables are independent and have the stipulated distributions.

### H9

The four displayed $w_b$ are fixed vectors in $E_1$, each of norm one; the four $c_b$ are fixed real numbers.

### H10

Since $\theta_1=0$, the required boundary restriction is $c_b\le0$. All four are zero and satisfy it.

### H11

The perturbed group means remain zero and the other group means remain eight for every $\varepsilon\ge0$. Thus all sixteen labels remain exactly $I_0\times[4]$, with unit marginal variances and jointly Gaussian expanded scores. The nonzero-mean sign-preservation requirement for the perturbed coordinate is vacuous.

### NOT

All four assertions hold for this object, so NOT fails.

For the exact-copy assertion, order any deterministic original p-values, including ties. If expanded rank $\ell$ qualifies at exact copying, original rank $r=\lceil\ell/4\rceil$ qualifies because
$$
p_{(r)}\le \frac{q\ell}{16}\le\frac{qr}{4}.
$$
Then expanded rank $4r$ also qualifies. Conversely each qualifying original rank $r$ gives a qualifying expanded rank $4r$. The largest expanded rank is consequently four times the largest original rank, with exactly the copied rejection set and the same FDP.

For the reduction assertion, write $h_\ell=\overline\Phi^{-1}(q\ell/16)$, $1\le\ell\le16$, and
$$
\delta=\min_{1\le\ell<16}(h_\ell-h_{\ell+1})>0.
$$
The spread of the four perturbed clones is at most $2\varepsilon\|Y\|$. If a partial perturbed group were rejected at rank $\ell=4m+s$, $1\le s\le3$, its largest rejected score would be at least $h_\ell$. When the spread is strictly below $\delta$, all four clones exceed $h_{\ell+1}\ge h_{4(m+1)}$; the other $4m$ rejected scores also exceed that latter threshold. Thus rank $4(m+1)$ would qualify, contradicting maximality of $\ell$. Every other group is exact and cannot be partially rejected. Outside the spread exception every group is all or none, and a full rank $4r$ qualifies exactly when reduced rank $r$ qualifies, proving equality of rejection sets.

The possible exceptional event is contained in $\{\|Y\|\ge\delta/(2\varepsilon)\}$. Since $\|Y\|^2\sim\chi^2_3$, Markov's inequality using $\mathbb E e^{\|Y\|^2/4}=2^{3/2}$ gives the explicit bound
$$
\mathbb P(\text{reduction fails})\le 2^{3/2}
\exp\!\left(-\frac{\delta^2}{16\varepsilon^2}\right).
$$
The required FDR error bound follows from FDP being in $[0,1]$.

It remains to check the measures and the derivative using every original rank. Set $u_r=\overline\Phi^{-1}(qr/4)$ and define the measurable integer
$$
r_*(y)=\max\left\{r\in[4]:
\#\{j\in\{2,3,4\}:8+y_j\ge u_r\}\ge r-1\right\}.
$$
The set is nonempty because $r=1$ always qualifies. For fixed $y$, a coordinate value $x\ge u_{r_*(y)}$ makes rank $r_*(y)$ qualify. No larger rank can qualify, because it would require at least $r-1$ other coordinates above its threshold, contradicting the definition of $r_*$. If $x<u_{r_*}$, coordinate 1 cannot be rejected at a smaller rank either, since those ranks have higher thresholds; larger ranks are again impossible. Hence, including deterministic ties,
$$
f(x,8+y_2,8+y_3,8+y_4)
=\frac{\mathbf1\{x\ge u_{r_*(y)}\}}{r_*(y)}.
$$
In particular the exact signed jumps are
$$
\Delta_{1,r}(y)=\frac{\mathbf1\{r_*(y)=r\}}r.
$$
Thus $\mu_{1,r}(dy)=\phi(u_r)\mathbf1\{r_*=r\}\gamma_3(dy)/r$; its total variation and first moments obey exactly the asserted bound, and $|g(y)|\le\|y\|$ ensures absolute integrability.

Independence of $Z,Y$ now gives the exact reduced FDR
$$
\mathbb E f(H^\varepsilon)
=\mathbb E\left[\frac1{r_*(Y)}
\overline\Phi\!\left(\sqrt{1+\varepsilon^2}\,
u_{r_*(Y)}-\varepsilon g(Y)\right)\right].
$$
For $0\le\varepsilon\le1$, the derivative of this integrand is bounded in absolute value by $(2\pi)^{-1/2}(\max_r|u_r|+\|Y\|)$, an integrable bound. Differentiation at zero is therefore justified and yields
$$
\left.\frac d{d\varepsilon}\mathbb E f(H^\varepsilon)
\right|_{0+}
=\mathbb E\left[\frac{g(Y)\phi(u_{r_*(Y)})}{r_*(Y)}\right]
=\sum_{r=1}^4\int g\,d\mu_{1,r}.
$$
The exponentially small reduction error divided by $\varepsilon$ tends to zero. Together with exact-copy invariance this proves that the actual expanded FDR has precisely the asserted right derivative for this object.

The strong-signal extreme does not conceal lower ranks: $r_*(Y)=4$ exactly when all three $8+Y_j\ge u_4$. Its complement has probability at most $3\Phi(u_4-8)$, and all those events remain in the exact formulas above. Finally $g\le0$ everywhere and $g<0$ almost surely, so the computed derivative is strictly negative on both sides of the proposed identity.

## Failure

NOT fails: the finite strong-signal model with four non-antipodal transverse marks satisfies exact copying, the explicit exponential reduction bound, finite face moments, and the stated right derivative while retaining every original rank.
