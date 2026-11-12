---
type: candidate
title: Singular antipodal blocks with vanishing negative null means
status: failed
target_asset: gaussian_bh_one_sided_sharp_upper
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  H7: pass
  NOT: fail
mode: refute
round: 1
slot: 2
direction: boundary_degenerate
statement_digest: 03b9629ae9bd4a6f3de6d1b9c08dfb86fb31a1aa0b7c62a1844a84111ad32086
performed_by: unknown
created_at: '2026-11-04T10:02:28.774Z'
extension_version: 0.0.4
---

## Object

For every $q\in(0,1/4)$ let $m(q)=\lceil q^{-1}\rceil$, $N(q)=2m(q)$, and
$$
z_q=\overline\Phi^{-1}(q/2),\qquad a_q=z_q^{-1}.
$$
Let $s\in\{-1,1\}^{N(q)}$ have its first $m(q)$ entries equal to $1$ and its remaining entries equal to $-1$. Set
$$
\theta(q)=-a_q\mathbf 1,\qquad \Sigma(q)=ss^{\mathsf T},\qquad T=sZ-a_q\mathbf 1,\quad Z\sim\mathcal N(0,1).
$$
Apply the ordinary one-sided BH procedure at level $q$. This tests an unbounded dimension, exact singularity, perfect positive and negative correlations, ties of diverging multiplicity, and true-null means approaching zero from below.

## Checks

### H1

The testing levels range over $(0,1/4)$ and may tend to zero through any sequence. All model parameters are specified separately at each level, as the uniform quantifiers permit.

### H2

$m(q)$ and $N(q)=2m(q)$ are positive finite integers for every $q>0$, although $N(q)\to\infty$.

### H3

Since $q/2<1/2$, $z_q>0$ and $a_q$ is finite and positive. Thus $\theta(q)\in\mathbb R^{N(q)}$. Every mean is strictly negative, so every coordinate belongs to the composite one-sided true-null set. Also $a_q\to0$.

### H4

$\Sigma=ss^{\mathsf T}$ is symmetric, has diagonal entries one, and satisfies
$$
x^{\mathsf T}\Sigma x=(s^{\mathsf T}x)^2\ge0.
$$
It has rank one. For every $b\in\mathbb R^{N(q)}$,
$$
b^{\mathsf T}(T-\theta)=(b^{\mathsf T}s)Z
$$
is centered normal with variance $(b^{\mathsf T}s)^2=b^{\mathsf T}\Sigma b$, including variance zero. This is an admissible exactly jointly Gaussian model.

### H5

Use the prescribed one-sided p-values. The two tied blocks have values
$$
p_+(Z)=\overline\Phi(Z-a_q),\qquad p_-(Z)=\overline\Phi(-Z-a_q).
$$
The true-null set is all of $[N(q)]$.

### H6

The larger of $p_+$ and $p_-$ equals $\overline\Phi(-|Z|-a_q)>1/2>q$. Therefore no rank above $m(q)$ can qualify for BH. Among the first $m(q)$ equal p-values, at least one rank qualifies if and only if their common value is at most $q/2$, in which case rank $m(q)$ qualifies: the largest threshold in that block is $qm(q)/N(q)=q/2$. Consequently BH rejects exactly the smaller block when
$$
|Z|\ge z_q+a_q,
$$
and rejects nothing otherwise. The non-strict inequality and all multiplicities are respected.

### H7

All discoveries are false. With the prescribed zero-rejection convention, the FDP is the indicator of the preceding event. Hence
$$
\operatorname{FDR}_{\mathrm{BH}}^{(1)}(q;N(q),\theta(q),\Sigma(q))
=2\overline\Phi(z_q+z_q^{-1}).
$$

### NOT

The proposed counterexample does not violate the target. The exact expression gives
$$
0\le\operatorname{FDR}_{\mathrm{BH}}^{(1)}\le2\overline\Phi(z_q)=q,
$$
so its ratio to $q\sqrt{\log(1/q)}$ tends to zero. More precisely, the normal-tail asymptotic $\overline\Phi(t)\sim\phi(t)/t$ yields
$$
\frac{2\overline\Phi(z_q+z_q^{-1})}{q}
=\frac{\overline\Phi(z_q+z_q^{-1})}{\overline\Phi(z_q)}
\longrightarrow e^{-1}.
$$
A light scalar calculation of the exact formula gives FDR divided by $q$ equal to approximately $0.303615$, $0.335946$, $0.346779$, and $0.352162$ at $q=10^{-2},10^{-4},10^{-6},10^{-8}$, respectively; the corresponding ratios to $q\sqrt{\log(1/q)}$ are $0.141482$, $0.110696$, $0.093297$, and $0.082052$.

The entire rank-one covariance family is also excluded, even with arbitrary alternative means and arbitrary negative true-null means. Indeed, write $T_i=s_iZ+\theta_i$ with $s_i\in\{-1,1\}$. For a true null, $\theta_i\le0$ implies $p_i\ge\overline\Phi(s_iZ)$. Any false rejection has $p_i\le q\widehat k/N\le q$, hence $s_iZ\ge\overline\Phi^{-1}(q)$. For $q<1/2$ this confines any false rejection to the two disjoint tail events with total probability $2q$. Thus every such model has FDR at most $2q$, uniformly in all its q-dependent parameters, and its normalized ratio tends to zero.

## Failure

NOT fails: the exact antipodal-block FDR is at most $q$, and every rank-one Gaussian model has FDR at most $2q$, both negligible on the proposed scale.
