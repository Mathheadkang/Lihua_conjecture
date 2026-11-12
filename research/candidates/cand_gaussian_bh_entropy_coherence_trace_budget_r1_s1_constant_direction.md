---
type: candidate
title: Perfectly duplicated true nulls at the zero-coherence-deficit boundary
status: failed
target_asset: gaussian_bh_entropy_coherence_trace_budget
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 282de99c92b14dd593f40c0583da4cc65ddd227e11dcc3d261ec31f0e3456ce2
performed_by: unknown
created_at: '2026-11-08T07:12:17.023Z'
extension_version: 0.0.4
---

## Object

For any finite positive integer $N$, take $d=1$, $v_i=1$ and $\theta_i=m\le0$ for every $i$. Let $0<q\le\overline\Phi(3)$, put $U=\overline\Phi^{-1}(q)$ and $H=h(U)$, and use the exact ordinary BH rule. Both $N$ and the finite number $m$ may depend arbitrarily on $q$.

## Checks

### H1

All directions have unit norm. The Gram covariance is the all-ones matrix, which is positive semidefinite with unit diagonal, including its rank-one degeneracy.

### H2

Every original mean is nonpositive, hence every hypothesis is a true null. All p-values equal $\overline\Phi(G+m)$. If this common value is at most $q$, rank $N$ qualifies and is the largest rank. Otherwise no rank qualifies, since $qr/N\le q$. Thus
$$
R=N\mathbf1_{\{G\ge U-m\}},\qquad
f=\mathbf1_{\{G\ge U-m\}},\qquad B=f/H.
$$
This retains multiplicities and the non-strict inequalities; their boundaries have Gaussian measure zero.

### H3

The whole interval $0<q\le\overline\Phi(3)$ is allowed, with arbitrary finite $N$ and $m\le0$. In particular, the family includes $q\downarrow0$, $m=0$ and $m\to-\infty$ through finite values.

### H4

The actual FDR is $F=\overline\Phi(U-m)>0$. The terminal tilt is the normal law conditioned on this half-line, so $D=\log(1/F)<\infty$. Since $B=f/H$ pointwise, convolution preserves this equality and gives $a(t,z)=1/H$ for every $t<1,z$. Consequently $K_t=0$, the absolute trace integral is zero, $x=1$ and $M=0$.

### NOT

The claimed bound becomes $0\le Cq\sqrt{1+D}\,0$ and holds with equality for every $C>0$. Thus neither exact zero deficit nor arbitrarily small positive FDR in this family violates the lemma. The formal $m=-\infty$ limit is not a finite model, and an all-positive-mean model would have $F=0$ and be outside the stipulated tilt domain.

## Failure

NOT fails: exact maximal coherence makes the heat posterior constant and its signed trace identically zero.
