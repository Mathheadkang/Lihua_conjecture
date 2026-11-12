---
type: candidate
title: Growing singular regular-simplex null array with negative equicorrelation
status: failed
target_asset: gaussian_bh_two_sided_sharp_upper
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 2
slot: 4
direction: boundary_degenerate
statement_digest: 2aaf3b157d839619c9429607bf182d896b1dacb3bc592c3dc8041bc442b8ed40
performed_by: unknown
created_at: '2026-11-04T08:53:53.945Z'
extension_version: 0.0.4
---

## Object

For $0<q<e^{-4}$ set $L=\log(1/q)$ and $N=\lceil q^{-4}\rceil$. Let $Z_1,\ldots,Z_N$ be independent standard normals, $\overline Z=N^{-1}\sum_i Z_i$, and
$$
T_i=\frac{Z_i-\overline Z}{\sqrt{1-1/N}},\qquad \theta_i=0.
$$
The covariance matrix is
$$
\Sigma=\frac{I_N-\mathbf 1\mathbf 1^{\mathsf T}/N}{1-1/N}.
$$
Apply one global ordinary BH procedure to $p_i=2\overline\Phi(|T_i|)$ at level $q$. This is the singular maximally negative equicorrelation boundary, with rank $N-1$ and all hypotheses null. It is distinct from low-rank repetition: all $N$ null p-values are distinct almost surely, and $\log N\sim4L$, beyond the previously reported small grouped-null entropy regime.

## Checks

### H1

For each $q$, $N=\lceil q^{-4}\rceil$ is a finite positive integer and $\theta=0\in\mathbb R^N$. All parameters are deterministic functions of $q$.

### H2

The vector $T$ is a deterministic linear image of independent standard normal variables, so is jointly Gaussian. The matrix $I_N-\mathbf 1\mathbf 1^{\mathsf T}/N$ is an orthogonal projection of rank $N-1$, hence positive semidefinite. Its diagonal is $1-1/N$, so $\Sigma_{ii}=1$. Its off-diagonal entries are $-1/(N-1)$, the smallest admissible equicorrelation. Singularity is permitted by the target.

### H3

Every $T_i$ has mean zero and variance one. Thus every index is a true two-sided null and $p_i=2\overline\Phi(|T_i|)$ is the stipulated Gaussian p-value. Each marginal p-value is uniform, although the p-values are dependent.

### H4

Use the largest qualifying rank from all $N$ p-values, exactly as in the definition of ordinary BH; no blockwise rule is substituted. Since every hypothesis is null, $V=R$ and the exact FDR is $\Pr(R>0)$.

### NOT

This family fails to violate the conclusion: in fact its FDR is at most $q(1+o(1))$.

Here is a finite-$N(q)$ global-BH coupling bound. Put
$$
U=\sqrt{2\log(2N/q^3)},\qquad s=\sqrt{8L/N},\qquad d=2U/N+2s.
$$
On the event
$$
E=\left\{\max_i|Z_i|\le U,\ |\overline Z|\le s\right\},
$$
write $a=(1-1/N)^{-1/2}$. Since $a\le2$ and $a-1\le2/N$,
$$
\max_i|T_i-Z_i|\le (a-1)U+as\le d.
$$
A union bound and normal exponential tails give the explicit estimate
$$
\Pr(E^c)\le2N e^{-U^2/2}+2e^{-Ns^2/2}=q^3+2q^4.
$$
For $u\ge0$, the normal hazard rate obeys the elementary bound
$$
\frac{\phi(u)}{\overline\Phi(u)}\le5(u+1).
$$
Indeed,
$$
\frac{\overline\Phi(u)}{\phi(u)}
=\int_0^\infty e^{-uv-v^2/2}\,dv
\ge\frac{e^{-3/2}}{u+1},
$$
by integrating over $0\le v\le1/(u+1)$, and $e^{3/2}<5$. Consequently, with
$$
\eta=5(U+d+1)d,
$$
the mean-value theorem for $\log(2\overline\Phi(u))$ gives, simultaneously on $E$,
$$
2\overline\Phi(|Z_i|)\le e^\eta 2\overline\Phi(|T_i|),\qquad i\in[N].
$$
Thus any qualifying global BH rank for $T$ at level $q$ is also a qualifying rank for the independent p-values $P_i=2\overline\Phi(|Z_i|)$ at level $q'=qe^\eta$. This implication uses the coordinatewise inequalities followed by order statistics, and is valid even when the selected rank depends on the whole vector.

For completeness, the independent-uniform global BH probability is exactly $q'$ for $0<q'<1$. If $R_i$ is the BH count after replacing $P_i$ by zero, then $R_i\ge1$ is independent of $P_i$ and the step-up identity is
$$
\frac{\mathbf1\{i\text{ rejected}\}}{R\vee1}
=\frac{\mathbf1\{P_i\le q'R_i/N\}}{R_i}.
$$
Conditioning on $R_i$ and summing over $i$ gives $\Pr(R>0)=q'$. Therefore for the present singular Gaussian array,
$$
\operatorname{FDR}_{\mathrm{BH}}^{(2)}(q;N,0,\Sigma)
\le qe^\eta+q^3+2q^4.
$$
As $q\downarrow0$, $\log N=4L+o(1)$, $U=O(\sqrt L)$, $d=O(q^2\sqrt L)$, and $\eta=O(q^2L)=o(1)$; in particular $q'<1$ eventually. The displayed finite-dimensional inequality therefore proves
$$
\frac{\operatorname{FDR}_{\mathrm{BH}}^{(2)}(q;N,0,\Sigma)}{q\sqrt{\log(1/q)}}
\le\frac{e^\eta+q^2+2q^3}{\sqrt L}\longrightarrow0.
$$

## Failure

NOT fails: this growing-rank singular negative-equicorrelation family has global BH FDR at most $q(1+o(1))$, so its normalized FDR tends to zero.
