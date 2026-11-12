---
type: candidate
title: Independent near-singular signed Gaussian triples with growing dimension
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
slot: 2
direction: small_cases
statement_digest: 2aaf3b157d839619c9429607bf182d896b1dacb3bc592c3dc8041bc442b8ed40
performed_by: unknown
created_at: '2026-11-04T09:28:59.375Z'
extension_version: 0.0.4
---

## Object

For $0<q<e^{-2}$ set
$$
L=\log(1/q),\quad B=\lceil e^{L^2}\rceil,\quad N=3B,
\quad\rho=-\tfrac12+q^2,\quad u=\overline\Phi^{-1}(q/2).
$$
There are $B$ mutually independent three-coordinate blocks. For block $j$, take independent standard normals $E_{j1},E_{j2},E_{j3},W_j$, all independent between blocks. Write $\overline E_j=(E_{j1}+E_{j2}+E_{j3})/3$ and put
$$
G_{jk}=\sqrt{1-\rho}(E_{jk}-\overline E_j)
+\sqrt{(1+2\rho)/3}\,W_j,\qquad k=1,2,3.
$$
The observations in block $j$ are
$$
T_{j1}=G_{j1},\qquad T_{j2}=G_{j2},\qquad
T_{j3}=\mu_j+G_{j3},
$$
$$
\mu_j=(-1)^j u\left(\tfrac14+\frac{j}{2B}\right).
$$
Apply ordinary BH once at level $q$ to all $N$ two-sided p-values.

This tests growing numbers of small dependent Gaussian motifs: their within-block covariances approach a singular negative-correlation boundary and their deterministic signal means vary with the block. There are $2B$ nonidentical random null p-values; dimension and the number of random null values both grow faster than every power of $1/q$.

## Checks

### H1

$B$ and $N$ are finite positive integers at every $q$ and may vary with $q$.

### H2

All means are deterministic real numbers. Since $u>0$ and $1/4+j/(2B)>0$, every $\mu_j$ is nonzero. Exactly the first two coordinates of every block are true nulls, giving $N_0=2B$.

### H3

Each block has covariance
$$
\Sigma_3=(1-\rho)I_3+\rho\mathbf1\mathbf1^{\mathsf T}.
$$
Its eigenvalues are $1-\rho=3/2-q^2$ twice and $1+2\rho=2q^2$ once, all positive in the stated range. Its diagonal is one. The full covariance is the block diagonal matrix with $B$ copies of $\Sigma_3$, hence is positive definite with unit diagonal while its smallest eigenvalue tends to zero.

### H4

The displayed affine representation in mutually independent normals gives an exactly jointly Gaussian observation with this deterministic covariance. In particular block independence holds for the full observations and for their p-values.

### H5

The p-values are $p_i=2\overline\Phi(|T_i|)$ and BH uses the largest qualifying rank among all $N$ coordinates, retaining ties. FDR is $\mathbb E[V/(R\vee1)]$. No blockwise BH procedure is applied.

### NOT

Fail. The exact finite arrays satisfy
$$
\operatorname{FDR}^{(2)}_{\rm BH}\leq2q,
$$
uniformly in their dimension, covariance condition number and displayed means. Thus the target normalization tends to zero.

Here is a complete global-BH argument. Fix a true null coordinate $i$ in a three-coordinate block $D$ and condition on all p-values outside $D$, denoted $v$. For $k=1,2,3$, let $R_k(v)$ be the ordinary global BH count when the block's p-values are replaced by $k$ zeros and $3-k$ ones. Their positions do not matter for the count. Each $R_k(v)$ is deterministic given $v$ and is at least $k$.

If $i$ is rejected in the actual data, let $k$ be the number of rejected coordinates inside $D$. Then
$$
R=R_k(v).
$$
To verify this identity, replace the actual $k$ rejected block p-values by zero and the others by one. At the actual rank $R$, the same $R$ coordinates still satisfy its threshold, so the modified count is at least $R$. For any rank $r>R$, the originally rejected block values were already below $qR/N<qr/N$, so replacing those by zero does not increase the count below the threshold $qr/N$. Replacing the unrejected block values by one can only decrease it. No rank above $R$ can become qualifying, so the modified count equals $R$, which is exactly $R_k(v)$.

Consequently, conditional on $v$,
$$
\begin{aligned}
\mathbb E\!\left[\frac{\mathbf1\{i\text{ rejected}\}}{R\vee1}\,\middle|\,v\right]
&\leq\sum_{k=1}^3\frac1{R_k(v)}
\mathbb P\!\left(p_i\leq\frac{qR_k(v)}N\,\middle|\,v\right)\\
&=\frac{3q}{N}.
\end{aligned}
$$
The equality uses only that $p_i$ is exactly uniform under its standard-normal null and independent of the outside-block vector $v$. It makes no independence claim within the triple and remains valid at singular within-block covariances. Summing over the $2B$ nulls gives $\operatorname{FDR}\leq(2B)(3q/N)=2q$.

More generally, the same calculation gives $(q/N)\sum_{i\in I_0}|D_i|$ for mutually independent blocks $D_i$ with arbitrary dependence inside them and exact uniform null p-values. This is a direct finite-level envelope for this search; no novelty claim or literature attribution is made.

## Failure

NOT fails: independence between the three-coordinate blocks restricts each null's possible global rejection counts to three deterministic values after conditioning on the outside data, forcing FDR at most $2q$ despite the rapidly growing near-singular Gaussian array.
