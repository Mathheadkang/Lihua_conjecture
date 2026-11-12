---
type: candidate
title: Oppositely loaded growing mean ladders with a shared Gaussian gate
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
round: 3
slot: 2
direction: small_cases
statement_digest: 2aaf3b157d839619c9429607bf182d896b1dacb3bc592c3dc8041bc442b8ed40
performed_by: unknown
created_at: '2026-11-04T09:19:50.244Z'
extension_version: 0.0.4
---

## Object

This attempt uses two opposed signal streams to activate both signs of a weak null factor. Unlike the earlier fixed-type families, its number of distinct signal means diverges; no fixed repeated-signal count bound is used. The loading angle may depend arbitrarily on the testing level.

Write $p(c)=2\overline\Phi(c)$, and for sufficiently small $q$ put
$$
r=q^2,\quad u=p^{-1}(q),\quad R=2u,\quad
J=\lceil R\rceil,\quad N=\lceil\exp(q^{-10})\rceil,
$$
$$
b_0=p^{-1}(qr/4),\quad b_j=b_0+j/r\ (0\leq j\leq J),
\quad\delta=rb_0\longrightarrow0.
$$
For $j<J$ set $w_j=2\{p(b_j)-p(b_{j+1})\}/q$, and set $w_J=2p(b_J)/q$. Thus every weight is positive and
$$
\sum_{j=0}^Jw_j=r/2,\qquad
\sum_{\ell=j}^Jw_\ell=2p(b_j)/q.
$$
Set $n_j=\lceil Nw_j\rceil$ and $n_0=N-2\sum_{j=0}^Jn_j$, so $n_0>0$ for small $q$. There is no allocation or numerical evaluation of an array of this size.

Let $Z,W,E_1,\ldots,E_{n_0}$ be independent standard normals. For ANY deterministic schedule $\rho=\rho(q)\in[0,1]$, put $s=\sqrt{1-\rho^2}$ and
$$
Y_+=\rho Z+sW,\qquad Y_-=-\rho Z+sW.
$$
The $n_0$ null coordinates are $T_i=rZ+\sqrt{1-r^2}E_i$. For each sign and each $j$, take $n_j$ copies of
$$
T_{\pm,j}=(1+r)b_j+Y_\pm.
$$
All means and multiplicities are deterministic. Apply ordinary BH once at level $q$ to the $N$ two-sided p-values.

## Checks

### H1

$N,J,n_j,n_0$ are finite integers at every $q$. The total nonnull count is at most $Nr+2(J+1)<N$ for small $q$, so $n_0$ is positive. Both $N$ and the number $2(J+1)$ of mean/loading types grow as $q\downarrow0$.

### H2

Null means are zero; each nonnull mean $(1+r)b_j$ is strictly positive and deterministic. Thus the stated null coordinates are exactly $I_0^{(2)}$.

### H3

Use common-factor loading rows $(r,0)$ for nulls and $(\rho,s)$ or $(-\rho,s)$ for the two signal streams. Null residual variances are $1-r^2$ and signal residual variances are zero. The covariance is the Gram matrix of the loading rows plus that nonnegative residual diagonal, so it is positive semidefinite with unit diagonal. This remains true at $\rho=0,1$ and for arbitrary $q$-dependent $\rho$.

### H4

Every coordinate is an affine function of the displayed independent Gaussian variables. Hence the whole observation is exactly jointly Gaussian, including all singular repeated nonnull coordinates.

### H5

Use $p_i=p(|T_i|)$, the ordinary largest qualifying global BH rank, and $\mathbb E[V/(R\vee1)]$. The argument below uses the global rank directly, with all ties intact; no local or signal-stream FDRs are added.

### NOT

Fail. A finite-array argument gives $\operatorname{FDR}=O(q)$ uniformly over the ENTIRE schedule $\rho(q)\in[0,1]$, so the target normalization tends to zero.

**A cap provided by either signal stream.** Since
$$
\max(Y_+,Y_-)=\rho|Z|+sW\geq-|W|,
$$
on $|W|\leq R$ choose the smallest $j\in\{0,\ldots,J\}$ with $rb_j=\delta+j\geq|W|$. Such a $j$ exists and
$$
rb_j\leq |W|+2
$$
for small $q$. For the stream attaining $\max(Y_+,Y_-)$, every coordinate of type $\ell\geq j$ then has
$$
(1+r)b_\ell+\max(Y_+,Y_-)\geq b_j>0.
$$
The fraction of those nonnull coordinates is at least $\sum_{\ell\geq j}w_\ell=2p(b_j)/q$. Thus the count at Gaussian cutoff $b_j$ itself qualifies for global BH: $qF_N(b_j)/p(b_j)\geq2$. This cap remains valid after setting any null p-value to zero. Accordingly every such leave-one-out BH Gaussian cutoff lies in $[u,b_j]$, and its scaled cutoff $a=rc$ is at most $|W|+2$.

**Null-tail bound on a high-probability factor box.** Put $\mathcal E=\{|Z|\leq R,|W|\leq R\}$. For $\sigma=\sqrt{1-r^2}$, write
$$
h_{r,z}(c)=\overline\Phi((c-rz)/\sigma)+\overline\Phi((c+rz)/\sigma).
$$
Uniformly on $|z|\leq R$, $c\geq u$, and $0\leq a=rc\leq R+2$, the elementary upper and lower Mills bounds give
$$
\frac{h_{r,z}(c)}{p(c)}
\leq\{1+o(1)\}e^{-a^2/2}\cosh(az)
\leq2e^{-a^2/2+a|z|}.
$$
Here $(c\mp rz)/\sigma>0$, the Mills prefactor is $1+O(u^{-2}+r)$, and the difference of the exact Gaussian exponent from $-a^2/2\pm az$ is $O\{r^2(a^2+|az|+z^2)\}=O(r^2u^2)=o(1)$. These bounds are uniform over the displayed growing ranges and do not use $\rho$.

**Integrating the random cap.** Let
$$
K_2(z,w)=\sup_{0\leq a\leq|w|+2}e^{-a^2/2+a|z|}.
$$
Its expectation under INDEPENDENT $Z,W$ is finite. Indeed, for $x=|z|,y=|w|$, put
$K_0=\sup_{0\leq a\leq y}e^{-a^2/2+ax}$; then
$$
K_2\leq e^{2x}K_0,\qquad
K_0=\begin{cases}e^{x^2/2},&x\leq y,\\e^{-y^2/2+xy},&x>y.\end{cases}
$$
Integrating against $(2/\pi)e^{-(x^2+y^2)/2}$ on the positive quadrant yields, for example, the finite bound
$$
\mathbb E K_2\leq C,
\quad C=4e^4\Phi(2)^2+
\sqrt{\frac2\pi}\{e^2\Phi(2)-1/2\}<\infty.
$$
The first term comes from $x>y$ after setting $v=x-y$; the second comes from integrating $0\leq x\leq y$. No independence between the actual selected cutoff and $Z$ has been asserted.

Finally condition on $Z,W$. All null p-values are independent and alternatives are deterministic. For a null $i$, let $R^{(i)}$ be the count after setting its p-value to zero. The exact BH identity gives its conditional expected FDP contribution as $\mathbb E[F_i(qR^{(i)}/N)/R^{(i)}\mid Z,W]$. On $\mathcal E$, the preceding nonnull cap holds for every $R^{(i)}$, so the tail-ratio bound and summation over all nulls give
$$
\mathbb E[\operatorname{FDP}\,\mathbf1_{\mathcal E}]
\leq 2q\frac{n_0}{N}\mathbb E K_2(Z,W)\leq2Cq.
$$
On the complement FDP is at most one, while
$$
\mathbb P(\mathcal E^c)\leq4\overline\Phi(2u)=q^{4+o(1)}=o(q).
$$
Thus $\operatorname{FDR}\leq2Cq+o(q)$ for the exact growing finite arrays, uniformly in $\rho(q)$. In particular
$$
\lim_{q\downarrow0}\frac{\operatorname{FDR}}{q\sqrt{\log(1/q)}}=0.
$$

## Failure

NOT fails: the earlier of the two global signal-ladder crossings bounds the null cutoff by an independent Gaussian factor; the resulting integrated null-tail envelope is finite, giving FDR $O(q)$ despite growing mean-type count and arbitrary changing loading angle.
