---
type: candidate
title: >-
  Antithetic rank-one Gaussian construction with an explicit positive FDR
  increment
status: survived
target_asset: gaussian_bh_negative_null_mean_nonmonotonicity
checks:
  P1: pass
  P2: pass
  P3: pass
  P4: pass
  P5: pass
  P6: pass
mode: construct
round: 1
slot: 2
direction: adapt_known
statement_digest: 9f2cf4094f405ea7ab6e91647d7c2eae547e583022c0a0ab42e0071b8242fa50
performed_by: unknown
created_at: '2026-11-04T12:37:56.077Z'
extension_version: 0.0.4
---

## Object

Adapt the standard rank-one Gaussian coupling with two comonotone coordinates and an antithetic third coordinate. Fix any $q\in(0,1/2)$ and write $\Phi$ for the standard normal distribution function. Define explicitly
$$
a=\Phi^{-1}(1-q/3),\qquad d=\Phi^{-1}(1-2q/3),\qquad e=\Phi^{-1}(1-q),\qquad \varepsilon=\frac{d-e}{4}.
$$
Thus $0<e<d<a$ and $\varepsilon>0$. Set
$$
c=a+\frac{d+e}{2}=a+e+2\varepsilon,\qquad h_A=a-e,\qquad h_B=a-e+\varepsilon,
$$
$$
b=-h_A,\qquad b'=-h_B,\qquad v=(1,1,-1)^{\mathsf T},\qquad \Sigma=vv^{\mathsf T}=
\begin{pmatrix}1&1&-1\\1&1&-1\\-1&-1&1\end{pmatrix}.
$$
For one standard normal variable $Z$, take
$$
T^J=(Z,\ Z-h_J,\ c-Z),\qquad J\in\{A,B\}.
$$
Use the one-sided p-values and ordinary three-test BH at level $q$ exactly as specified.

For the formulas below, put
$$
S=c-a=\frac{d+e}{2},\qquad W=c-d=a-2\varepsilon,\qquad U=c-e=a+2\varepsilon,
$$
$$
L_A=a,\qquad L_B=a+\varepsilon,\qquad D_J=d+h_J=L_J+4\varepsilon,
$$
and define $[x]_+=\max(x,0)$. Every quantity is an explicit function of $q$ through the three displayed normal quantiles.

## Checks

### P1

The matrix $\Sigma=vv^{\mathsf T}$ has diagonal entries one and satisfies $x^{\mathsf T}\Sigma x=(v^{\mathsf T}x)^2\geq0$. For any $u\in\mathbb R^3$, the centered linear combination $u^{\mathsf T}(T^J-\theta^J)=(u_1+u_2-u_3)Z$ is normal, with variance $u^{\mathsf T}\Sigma u$. Hence both observation vectors are exactly jointly Gaussian, have unit marginal variances, and have the same admissible correlation matrix.

### P2

The means are $(0,-h_A,c)$ and $(0,-h_B,c)$. Since $a>e$, $h_A>0$; since $\varepsilon>0$, $h_B>h_A$. Therefore $b'<b<0$. Also $c=a+(d+e)/2>0$. Only the second mean changes, and both one-sided true-null sets are exactly $\{1,2\}$.

### P3

The BH statistic thresholds for ranks one, two, and three are respectively $a$, $d$, and $e$: the event $p_i\leq kq/3$ is exactly $T_i\geq\Phi^{-1}(1-kq/3)$. Applying the largest qualifying rank gives the following complete partition. An interval $[d,W]$ is interpreted as empty when $W<d$.

| Values of $Z$ | Rejection set | $R_J$ | $V_J$ | FDP |
| --- | --- | --- | --- | --- |
| $(-\infty,S]$ | $\{3\}$ | $1$ | $0$ | $0$ |
| $[d,W]$ | $\{1,3\}$ | $2$ | $1$ | $1/2$ |
| $[a,L_J)\ \cup\ (U,D_J)$ | $\{1\}$ | $1$ | $1$ | $1$ |
| $[L_J,U]$ | $\{1,2,3\}$ | $3$ | $2$ | $2/3$ |
| $[D_J,\infty)$ | $\{1,2\}$ | $2$ | $2$ | $1$ |
| $(S,a)\setminus[d,W]$ | $\varnothing$ | $0$ | $0$ | $0$ |

To verify all rows, observe first that
$$
S<d<a\leq L_J<U<D_J,\qquad W<a.
$$
All three statistics exceed the rank-three threshold $e$ precisely when $Z\in[L_J,U]$, because $T_2^J\geq e$ is $Z\geq L_J$ and $T_3^J\geq e$ is $Z\leq U$; then $T_1^J\geq e$ automatically. The pair $\{1,3\}$ exceeds $d$ precisely on $[d,W]$. On this interval $Z<a\leq L_J$, so $T_2^J<e$ and rank three is impossible. The pair $\{1,2\}$ exceeds $d$ precisely when $Z\geq D_J>U$, so rank three is again impossible. If $\{2,3\}$ both exceed $d$, then $T_1^J>T_2^J\geq d$ too, so rank three already qualifies; this produces no additional rank-two region. Outside these rank-two and rank-three regions, the first statistic individually exceeds $a$ precisely for $Z\geq a$, and the third individually exceeds $a$ precisely for $Z\leq S$. A rank-one rejection of the second statistic alone is impossible because $T_1^J>T_2^J$. These observations establish every row, including the zero-rejection row and all threshold endpoints.

In particular the expectation is the full specified FDR. Integrating the nonzero FDP rows gives
$$
\begin{aligned}
F_J(q)
={}&\Phi(L_J)-\Phi(a)+\Phi(D_J)-\Phi(U)
 +\overline\Phi(D_J)\\
&+\frac12[\Phi(W)-\Phi(d)]_+
 +\frac23\{\Phi(U)-\Phi(L_J)\}\\
={}&\frac q3+\frac12[\Phi(W)-\Phi(d)]_+
 -\frac13\{\Phi(U)-\Phi(L_J)\}.
\end{aligned}
$$

### P4

Substituting $L_A=a$ and $L_B=a+\varepsilon$ into the full FDR formula yields
$$
F_B(q)-F_A(q)=\frac13\{\Phi(a+\varepsilon)-\Phi(a)\}>0.
$$
The inequality holds for every $q\in(0,1/2)$ because $a$ is finite, $\varepsilon>0$, and $\Phi$ is strictly increasing. Pointwise, the only FDP change occurs on $[a,a+\varepsilon)$: the first model rejects all three tests with FDP $2/3$, while the second rejects just test one with FDP $1$. Everywhere else the FDPs agree (although an additional pure-null rank-two region can become a rank-one region, both having FDP one).

### P5

Since $\Phi(W)\leq1$,
$$
0\leq[\Phi(W)-\Phi(d)]_+\leq1-\Phi(d)=\frac{2q}{3}.
$$
Also $U>L_J$, so the final term of the full FDR formula is negative. Consequently, for each $J$,
$$
F_J(q)\leq\frac q3+\frac12\frac{2q}{3}=\frac{2q}{3}<q.
$$
This bound is valid on the entire required interval and proves both nominal-control inequalities.

### P6

The exact finite-level formulas, with all Gaussian arguments displayed, are
$$
F_A(q)=\frac q3+\frac12[\Phi(a-2\varepsilon)-\Phi(d)]_+
 -\frac13\{\Phi(a+2\varepsilon)-\Phi(a)\},
$$
$$
F_B(q)=\frac q3+\frac12[\Phi(a-2\varepsilon)-\Phi(d)]_+
 -\frac13\{\Phi(a+2\varepsilon)-\Phi(a+\varepsilon)\},
$$
$$
F_B(q)-F_A(q)=\frac13\{\Phi(a+\varepsilon)-\Phi(a)\},
$$
where $a=\Phi^{-1}(1-q/3)$, $d=\Phi^{-1}(1-2q/3)$, $e=\Phi^{-1}(1-q)$, and $\varepsilon=(d-e)/4$. The positive part simply accounts for the possibility that the explicit pair-rejection interval $[d,a-2\varepsilon]$ is empty; it introduces no implicit parameter. The complete rejection-count partition and its integration in P3 include $R=0,1,2,3$, and P4 and P5 give analytic proofs throughout $(0,1/2)$ without numerical or asymptotic approximations.
