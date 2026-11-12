---
type: candidate
title: Unbalanced independent constant block with a strongly negative null
status: failed
target_asset: gaussian_bh_finite_signed_p_path_identity
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 2
slot: 2
direction: extremal
statement_digest: d7a8a4f0b24ea902729e5f1f7788367f78c722f470f62ba2b0bf55c676594eec
performed_by: unknown
created_at: '2026-11-09T20:29:53.809Z'
extension_version: 0.0.4
---

## Object

Take $N=1001$, $q=1/4$, $\theta_1=-8$, and $\theta_j=8$ for $2\le j\le N$. Let $X,Y$ be independent standard normals and set $Z_1=X$, $Z_j=Y$ for $j\ge2$. Thus $\Sigma=\operatorname{diag}(1,\mathbf1_{1000}\mathbf1_{1000}^{\mathsf T})$. The unique true null is $i=1$.

The prospective failure mechanism is an extensive perfectly tied block that is independent of the null: after conditioning, all 1000 alternatives have constant score paths. This is a rank-two, random constant-block gate, rather than a rank-one anticorrelated crossing or an isolated rank spike.

## Checks

### H1

$N=1001$ is finite and positive.

### H2

All means are finite real numbers. Exactly coordinate 1 has nonpositive mean, so $I_0=\{1\}$ and the selected coordinate is an original true null.

### H3

The covariance is positive semidefinite because
$$
v^{\mathsf T}\Sigma v=v_1^2+\left(\sum_{j=2}^{1001}v_j\right)^2\ge0.
$$
Every diagonal entry is one. Its rank is two; this is an admissible singular jointly Gaussian model.

### H4

$q=1/4$ lies strictly between zero and $1/2$.

### NOT

This check fails. Write $S=\overline\Phi$, $u=S^{-1}$, and
$$
G=\{Y\ge u(q)-8\},\qquad \alpha=\Pr(G)=S(u(q)-8).
$$
Conditionally on $Y$, the full original path is $T_1^1(t)=u(t)$ and $T_j^1(t)=8+Y$ for every $j\ge2$. No coordinate is dropped or relabeled. On $G$, every p-value is at most $q$ for $0<t<q$, so actual largest-rank non-strict BH gives $R_1(t)=N$. Off $G$, every alternative p-value exceeds $q$, so none can pass any BH threshold. Hence $R_1(t)=1$ for $t\le q/N$ and $R_1(t)=0$ for $t>q/N$. At $Y=u(q)-8$, non-strict BH assigns the path to $G$, exactly as required.

Consequently,
$$
A_1(t)=\begin{cases}t/q,&G,\\ \min\{Nt/q,1\},&G^c.\end{cases}
$$
Both paths have endpoint limits zero and one, are continuous, and satisfy the stated derivative formula on their affine pieces. For example one may choose $E_1=\{qk/N:1\le k<N\}$, which contains every nonconstant threshold crossing and clipping breakpoint. The constant tied alternatives introduce no additional events. There are no actual net jumps, so $J_1=\varnothing$ and $B_1=0$. These paths and event sets are jointly measurable, being explicit functions of the Borel event $G$; their jump sums vanish and are absolutely integrable.

Put $g(t)=\exp\{-8u(t)-32\}$. This is continuous and increasing with $g(0+)=0$ and $0\le g(t)\le1$ on $(0,q]$. For either $a=q$ or $a=q/N$, integration by parts gives
$$
g(q)-\int_{(0,q)}\min\{t/a,1\}\,dg(t)=\frac1a\int_0^a g(t)\,dt.
$$
This belongs to $[0,1]$. Also the null p-value distribution satisfies
$$
\int_0^a g(t)\,dt=S(u(a)+8).
$$
The claimed signed identity therefore evaluates to
$$
\frac\alpha N S(u(q)+8)+(1-\alpha)S(u(q/N)+8).
$$
Direct actual-BH calculation gives the identical expression: on $G$, the null is rejected exactly when $p_1\le q$, with denominator $N$; off $G$, it is rejected exactly when $p_1\le q/N$, with denominator one. Independence of $X$ and $Y$ supplies the factors $\alpha$ and $1-\alpha$. Since this is the only true null, this also equals the full FDR. Finally, each displayed baseline is at most one, so $F\le q/N=q\pi_0$, consistent with $B_1=0$.

## Failure

NOT is the first failing check: the extensive independent constant block gives a measurable mixture of two continuous clipped-affine paths, and both the signed identity and its FDR bound hold exactly.
