---
type: candidate
title: Three-coordinate mixed-sign path with two distinct opposite net jumps
status: failed
target_asset: gaussian_bh_finite_signed_p_path_identity
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  NOT: fail
mode: refute
round: 4
slot: 2
direction: small_cases
statement_digest: d7a8a4f0b24ea902729e5f1f7788367f78c722f470f62ba2b0bf55c676594eec
performed_by: unknown
created_at: '2026-11-09T20:58:25.271Z'
extension_version: 0.0.4
---

## Object

Let $q=1/4$, $c=1/25$, $e=2/25$, $u=\overline\Phi^{-1}$, and
$$
a=u(e)-u(q)>0,\qquad b=u(c)+u(q)>0.
$$
Take $N=3$, $X\sim N(0,1)$, $\theta=(0,-a,b)$, and
$$
Z=(X,X,-X),\qquad
\Sigma=\begin{pmatrix}1&1&-1\\1&1&-1\\-1&-1&1\end{pmatrix}.
$$
Thus $I_0=\{1,2\}$. This tests a distinct mixed-sign mechanism: a single selected-null path has two separated genuine net jumps of opposite signs, caused by admission and subsequent loss of the third BH rank. It does not turn a removable spike into a jump or discard the upward jump. The additional positive-mean coordinate makes this different from the previously tested two-coordinate comonotone upward-jump family.

Write $x=\overline\Phi(X)$, which is uniform on $(0,1)$. Along the original sample,
$$
p_1=x,\qquad p_2=\overline\Phi(u(x)-a),\qquad
p_3=\overline\Phi(b-u(x)).
$$
The constants satisfy
$$
a\approx0.7305818101,\quad b\approx2.4251758214,
$$
$$
p_2(c)=p_3(e)\approx0.1538395080<1/6,\qquad
p_3(1/6)\approx0.07245414564<1/12.
$$

## Checks

### H1

$N=3$ is a finite positive integer.

### H2

$\theta=(0,-a,b)$ is a finite real vector, since $c,e,q\in(0,1)$.

### H3

Writing $v=(1,1,-1)^{\mathsf T}$ gives $\Sigma=vv^{\mathsf T}$, so the covariance is positive semidefinite with unit diagonal. Its singularity is allowed.

### H4

$0<q=1/4<1/2$.

### H5

$T=\theta+(X,X,-X)$ has the required exactly jointly Gaussian distribution. The p-values above are the specified one-sided Gaussian p-values, and all counts below use non-strict largest-rank ordinary BH.

### H6

The original true-null labels are exactly $1,2$, with $\theta_1=0$ and $\theta_2=-a<0$. Conditioning on either selected null leaves the zero residual vector: both $Z_1$ and $Z_2$ equal $X$, and their correlations with $(Z_1,Z_2,Z_3)$ are $(1,1,-1)$. All three original coordinates and labels are retained.

### NOT

The proposed mixed-sign attack fails. Direct BH evaluation, with endpoint values immaterial to the integrals, gives
$$
R=\begin{cases}
2,&0<x<c,\\
3,&c<x<e,\\
2,&e<x<1/6,\\
1,&1/6<x<1.
\end{cases}
$$
For $x<c$, coordinates $1,2$ qualify at rank $2$, while $p_3>q$. For $c<x<e$, all three p-values are at most $q$. For $e<x<1/6$, coordinates $1,3$ qualify at rank $2$, while $p_2>q$. Beyond $1/6$, only coordinate $3$ can be rejected, and it qualifies at rank $1$ by the displayed inequality and monotonicity. Thus
$$
F_1=\frac c2+\frac{e-c}{3}+\frac{1/6-e}{2}
=\frac{23}{300},\qquad
F_2=\frac c2+\frac{e-c}{3}=\frac1{30}.
$$

For label $1$, the selected p-path parameter is $t=x$. On $(0,q)$,
$$
A_1(t)=\begin{cases}
6t,&0<t<c,\\
4t,&c<t<e,\\
6t,&e<t<1/6,\\
1,&1/6<t<q.
\end{cases}
$$
Consequently the actual net jumps are $c,e$, with signed sizes $2c$ and $-2e$. The rank change at $1/6$ produces no net jump. Since $g_1=1$, the identity gives
$$
\frac q3[1+2c-2e]
=\frac1{12}\left(1-\frac2{25}\right)
=\frac{23}{300}=F_1.
$$

For label $2$, put
$$
s=p_2,\qquad h(x)=\overline\Phi(u(x)-a),\qquad \ell=h(c).
$$
Then $h(e)=q$, and $s\in(0,q)$ corresponds exactly to $x\in(0,e)$. Its actual BH count is $2$ below $\ell$ and $3$ above $\ell$, so
$$
A_2(s)=\begin{cases}3s/(2q),&s<\ell,\\s/q,&s>\ell.\end{cases}
$$
There is one downward net jump of size $\ell/(2q)$. Let $g=g_2$ and
$$
G(s)=\int_0^s g(v)\,dv=\overline\Phi(u(s)+a).
$$
The equality for $G$ follows directly by Gaussian change of variables; in particular $G(\ell)=c$ and $G(q)=e$. Elementary integration on the two affine intervals gives the target baseline
$$
g(q)-\int A_2\,dg
=\frac{e+c/2-\ell g(\ell)/2}{q}.
$$
Adding the signed jump contribution $\ell g(\ell)/(2q)$ and multiplying by $q/3$ yields
$$
\frac{e+c/2}{3}=\frac1{30}=F_2.
$$
Here $g(\ell)\approx0.3634387459$, and the baseline is approximately $0.28818$, within $[0,1]$. Label $1$ has baseline $1$.

Both paths have the specified endpoint limits and the claimed derivatives on their affine pieces: slopes $6,4,6,0$ for label $1$, and $3/(2q),1/q$ for label $2$, exactly the selected-null rejection indicator divided by $qR/3$. Every score path is nonconstant; each threshold has at most one crossing, making event sets finite. All objects are deterministic continuous or finite-piece measurable functions of the selected path parameter, since the residual vector is zero. All jump sums are finite deterministic quantities and hence absolutely integrable. Non-strict values at isolated thresholds have no effect on these calculations. The positive-part inequality also holds: the direct full FDR is $23/300+1/30=11/100<q(2/3)$ even before adding either nonnegative positive-jump budget.

## Failure

NOT is the first failing check: both null-label contributions satisfy the exact signed identity, including the distinct positive and negative jump corrections; no conclusion is violated by this mixed-sign three-coordinate object.
