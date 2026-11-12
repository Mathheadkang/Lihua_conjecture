---
type: candidate
title: >-
  Independent replication of growing Gaussian blocks cannot amplify finite-level
  pathologies enough
status: failed
target_asset: gaussian_bh_two_sided_sharp_upper
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 4
slot: 4
direction: known_counterexamples
statement_digest: 2aaf3b157d839619c9429607bf182d896b1dacb3bc592c3dc8041bc442b8ed40
performed_by: unknown
created_at: '2026-11-04T09:28:59.375Z'
extension_version: 0.0.4
---

## Object

This tests amplification of a possible low-dimensional dependent-testing pathology by an enormous number of independent blocks, while allowing block size to grow. For $0<q<e^{-16}$ put
$$
L=\log(1/q),\quad d=\lceil L^{1/4}\rceil,\quad B=\lceil e^{L^2}\rceil,\quad N=Bd,\quad \mu=\sqrt{2L}.
$$
For each $b\in[B]$, let $Z_{b,0},Z_{b,1},\varepsilon_{b,1},\ldots,\varepsilon_{b,d-1}$ be independent standard normal variables, with independence also between blocks. For $1\le r\le d-1$, set $\alpha_r=2\pi r/(d-1)$ and define
$$
T_{b,r}=\sqrt{1-q^2}\{\cos(\alpha_r)Z_{b,0}+\sin(\alpha_r)Z_{b,1}\}+q\varepsilon_{b,r},
$$
$$
T_{b,d}=\mu+Z_{b,0}.
$$
Thus each block has $d-1$ true nulls with distinct residuals and one alternative sharing one of their two factors. Apply one ordinary BH procedure to all $N$ two-sided p-values.

The proof below permits arbitrary Gaussian dependence and mean geometry within each block, not merely this ring example. The important new feature is independent replication with $B\asymp e^{L^2}$ and unbounded block size, rather than a bounded number of repeated null p-value types or a single dependent signal in the entire array.

## Checks

### H1

For every $q$, the integers $B,d,N$ are finite, and the deterministic mean vector is zero at coordinates $(b,r)$ with $r<d$ and equals $\mu>0$ at $(b,d)$. No infinite array is substituted for the finite model.

### H2

Every coordinate is an affine linear function of the specified independent Gaussian variables, so the complete vector is jointly Gaussian. The null coordinates have variance $(1-q^2)(\cos^2\alpha_r+\sin^2\alpha_r)+q^2=1$, and each alternative has variance one. Different blocks have zero covariance and are independent.

Each covariance block is positive definite: in a linear combination of its centered coordinates, zero variance forces every null coefficient to vanish because each has an independent residual with nonzero coefficient $q$. The remaining signal coefficient must then vanish because its noise is $Z_{b,0}$ with variance one. Thus the block-diagonal full covariance is positive definite with unit diagonal, as required.

### H3

The exact p-values are $P_{b,r}=2\overline\Phi(|T_{b,r}|)$. The true-null indices are exactly $\{(b,r):r<d\}$. Each true-null p-value is uniform on $(0,1)$. There are $m_0=B(d-1)$ true nulls.

### H4

Use the largest qualifying rank in the entire collection of $N$ p-values, retaining the specified non-strict inequalities. The false discovery proportion is $V/(R\vee1)$ for this single global rejection set. The analysis below does not add local FDRs from separately run tests.

### NOT

NOT fails. In fact a finite-dimensional global-BH bound for these independent blocks is
$$
\operatorname{FDR}_{\mathrm{BH}}^{(2)}\le\frac{m_0}{N}dq\le dq.
$$
Here is a direct proof with no assumptions on the dependence within a block. Fix a block $b$ and condition on all p-values outside it. These outside p-values are independent of each marginal true-null $P_i$ in block $b$.

For $j\in\{1,\ldots,d\}$, let $r_j$ be the global BH count at level $q$ in the deterministic vector consisting of those outside p-values, $j$ synthetic zeros, and $d-j$ synthetic ones. It depends only on the conditioned outside vector and satisfies $j\le r_j\le N$.

Let $J_b$ be the actual number of rejected coordinates in block $b$. On $\{J_b=j\}$ with $j\ge1$, the actual global count equals $r_j$. To see this, replace the $j$ rejected block p-values by zero and the $d-j$ unrejected block p-values by one. This leaves the global BH count unchanged: lowering already rejected values leaves all order statistics above the actual rejection count unchanged, and raising unrejected values creates no new qualifying rank; meanwhile the old rejection count still qualifies. This also handles ties, because the BH rejection set has exactly its largest qualifying rank. Since $q<1$, the synthetic ones cannot be rejected. The resulting vector is precisely the one defining $r_j$, up to the irrelevant positions of the block coordinates.

For a true-null coordinate $i$ in block $b$, its rejection implies $J_b\ge1$ and $P_i\le qR/N$. Consequently, pointwise,
$$
\frac{\mathbf1\{i\text{ is rejected}\}}{R\vee1}
\le\sum_{j=1}^d\frac{\mathbf1\{P_i\le qr_j/N\}}{r_j}.
$$
Conditional on the outside vector, each $r_j$ is deterministic and $P_i$ is uniform. Hence
$$
\mathbb E\!\left[\left.\frac{\mathbf1\{i\text{ is rejected}\}}{R\vee1}\right|P_{-b}\right]
\le\sum_{j=1}^d\frac{qr_j/N}{r_j}=\frac{dq}{N}.
$$
Summing over all $m_0$ true nulls proves the claimed exact global-BH bound. No conditional independence among coordinates of block $b$ was used.

Finally,
$$
\frac{\operatorname{FDR}_{\mathrm{BH}}^{(2)}(q;N,\theta,\Sigma)}{q\sqrt{\log(1/q)}}
\le\frac{\lceil L^{1/4}\rceil}{\sqrt L}\longrightarrow0.
$$
This obstruction covers independent blocks with maximal block size $o(\sqrt{\log(1/q)})$, even when their number, means, and within-block Gaussian covariance matrices vary arbitrarily with $q$. It does not address block sizes comparable to $\sqrt{\log(1/q)}$ or dependence between blocks.

## Failure

NOT fails: independent replication with the specified growing block size has global BH FDR at most $dq=o(q\sqrt{\log(1/q)})$, regardless of the enormous number of blocks.
