---
type: candidate
title: Exponentially many sparse orthogonal global gates at exact singularity
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
round: 4
slot: 3
direction: drop_hypothesis
statement_digest: 2aaf3b157d839619c9429607bf182d896b1dacb3bc592c3dc8041bc442b8ed40
performed_by: unknown
created_at: '2026-11-04T09:28:59.375Z'
extension_version: 0.0.4
---

## Object

For $q\in(0,e^{-4})$, write
$$
L=\log(1/q),\qquad a=\frac1{4e\sqrt\pi},\qquad
s=\left\lceil e^{a\sqrt L}\right\rceil,\qquad
m=2\lceil e^{L^2}\rceil+2s+1,\qquad N=m+s.
$$
Let $Z_0,\ldots,Z_{m-1}$ be independent standard normal variables. Define $m$ null coordinates by $T_{i+1}=Z_i$. Define $s$ alternative coordinates by
$$
A_{ji}=\sqrt{\frac2m}\cos\!\left(\frac{2\pi ji}m\right),
\quad 1\leq j\leq s,\quad0\leq i\leq m-1,
$$
$$
\mu_j=(-1)^j\left(\sqrt{2L}+\frac{j}{s+1}\right),\qquad
T_{m+j}=\mu_j+\sum_{i=0}^{m-1}A_{ji}Z_i.
$$
Every alternative is a dense global linear gate. There are exponentially many gates on the square-root-log scale, their means diverge with both signs, their proportion vanishes, and their joint covariance is exactly singular. This changes the earlier one-alternative boundary to a diverging collection of distinct global gates.

## Checks

### H1

At each fixed $q$, $m,s,N$ are finite positive integers and $m>2s$. The model dimension may depend arbitrarily on $q$.

### H2

The mean vector has its first $m$ entries zero and its remaining entries equal to the displayed finite nonzero $\mu_j$. Thus it belongs to $\mathbb R^N$, even though its nonzero entries diverge as $q\downarrow0$.

### H3

The discrete trigonometric identities give
$$
\sum_{i=0}^{m-1}\cos\!\left(\frac{2\pi ji}m\right)
\cos\!\left(\frac{2\pi ki}m\right)=\frac m2\mathbf 1_{\{j=k\}},
\qquad 1\leq j,k\leq s.
$$
Indeed, expand the product as half the sum of cosines at frequencies $j-k$ and $j+k$. The nonzero frequencies have absolute values less than $m$ because $2s<m$, so their sums over the $m$ equally spaced points vanish. Therefore $AA^{\mathsf T}=I_s$ and
$$
\Sigma=\begin{pmatrix}I_m&A^{\mathsf T}\\A&I_s\end{pmatrix}
=\begin{pmatrix}I_m\\A\end{pmatrix}
\begin{pmatrix}I_m&A^{\mathsf T}\end{pmatrix}
$$
is positive semidefinite with unit diagonal. Its rank is $m<N$. All coordinates are affine functions of the independent Gaussian vector $Z$, so the joint distribution is exactly Gaussian. Individual null-alternative correlations have absolute values at most $\sqrt{2/m}$; their smallness does not require independence between the two groups.

### H4

Use $p_i=2\overline\Phi(|T_i|)$, exactly as required. The true-null set is $\{1,\ldots,m\}$, and its p-values $U_1,\ldots,U_m$ are independent Uniform$(0,1)$ variables. The alternative p-values are allowed to depend on all these null p-values.

### H5

Use ordinary BH on all $N$ p-values, with its largest qualifying rank and its full rejection set. Write $R,V$ for its total and false-rejection counts and $D=V/(R\vee1)$ for its FDP. The rejection count equals the largest qualifying rank: if more coordinates than that rank fell below its cutoff, their larger rank would itself qualify. Hence on $R>0$ the BH cutoff is $qR/N$.

### NOT

The proposed violation fails. The following bound holds for any collection of at most $s$ arbitrarily dependent alternatives when the $m$ null p-values are independent.

First, $R\leq V+s$. Consequently, on $V>0$,
$$
D=\frac VR\geq\frac V{V+s}\geq\frac1{s+1}=:b.
$$
For $t\in[b,1]$, the event $D>t$ implies that for some integer $k=V\geq1$,
$$
U_{(k)}\leq\frac{qR}N<\frac{qk}{Nt}.
$$
For all sufficiently small $q$, $q(s+1)<1$, so these p-value thresholds are less than one. Independence and a union bound over the subsets of $k$ null coordinates yield
$$
\Pr\{D>t\}
\leq\sum_{k=1}^m\binom mk\left(\frac{qk}{Nt}\right)^k
\leq\sum_{k=1}^m\left(\frac{eq}{t}\right)^k
\leq\frac{eq}{t(1-eq(s+1))}.
$$
Here $\binom mk\leq(em/k)^k$, $m/N\leq1$, and $t\geq b$ were used. The denominator is positive for all sufficiently small $q$ because $q(s+1)\to0$.

For the low-$t$ range, use $R\leq V+s\leq(s+1)V$ on $V>0$. The same subset bound gives
$$
\Pr\{D>0\}\leq
\sum_{k=1}^m\Pr\!\left\{U_{(k)}\leq\frac{q(s+1)k}N\right\}
\leq\frac{eq(s+1)}{1-eq(s+1)}.
$$
Integrating the tail of $D\in[0,1]$ and using these two bounds, without conditioning on the alternative coordinates, gives
$$
\operatorname{FDR}
=\int_0^1\Pr\{D>t\}\,dt
\leq\frac{eq}{1-eq(s+1)}\{1+\log(s+1)\}.
$$
The displayed bound handles every global BH crossing, rather than selecting one crossing or treating gates separately. Since $\log(s+1)/\sqrt L\to a$,
$$
\limsup_{q\downarrow0}\frac{\operatorname{FDR}}{q\sqrt L}
\leq ea=\frac1{4\sqrt\pi}<\frac1{2\sqrt\pi}.
$$
This only excludes the specified sparse-gate schedule and, more generally, independent-null models with $\limsup\log(s+1)/\sqrt L<1/(2e\sqrt\pi)$. It gives no exclusion for arbitrary alternative growth or dependent nulls.

## Failure

NOT fails: an independent-null binomial envelope bounds this exponentially growing, exactly singular sparse-gate family's normalized FDR by $1/(4\sqrt\pi)$, strictly below the proposed constant.
