---
type: candidate
title: Rank-one sign mixtures including zero-weight endpoints
status: failed
target_asset: gaussian_frozen_ray_maximal_likelihood_ratio_conjecture
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 6ead14fa2488e60475cf2c3f8d05592666ae28d3bf23c28b0047c6eacd43fcbe
performed_by: unknown
created_at: '2026-11-10T22:02:37.013Z'
extension_version: 0.0.4
---

## Object

Take any integer $n\geq1$, deterministic signs $s_i\in\{-1,1\}$, and deterministic weights $\omega_i\geq0$ summing to one. Set $\Sigma=ss^{\mathsf T}$ and $Z_i=s_iX$ for a single $X\sim N(0,1)$. Write $p=\sum_{i:s_i=1}\omega_i\in[0,1]$. Then
$$
L_w=e^{-w^2/2}\{pe^{wX}+(1-p)e^{-wX}\},\qquad w\geq0.
$$
This family covers the scalar case, perfect positive dependence, perfect negative dependence, and arbitrary zero weights. All parameters and both levels $c,\alpha\geq2$ remain arbitrary.

## Checks

### H1

The dimension $n$ is a positive integer by construction.

### H2

The matrix $\Sigma=ss^{\mathsf T}$ is symmetric, satisfies $v^{\mathsf T}\Sigma v=(s^{\mathsf T}v)^2\geq0$, and has diagonal entries $s_i^2=1$. Thus $\Sigma\in\mathcal C_n$, including its singular cases.

### H3

The vector $Z=sX$ is centered jointly Gaussian with covariance $ss^{\mathsf T}$: every linear combination is $(a^{\mathsf T}s)X$.

### H4

The weights are deterministic, nonnegative, and sum to one. Endpoints $p=0,1$ and individual zero weights are allowed.

### H5

The displayed field uses the same $X$, hence the same realization of $Z$, for all $w\geq0$. The truncation and tail levels satisfy $c,\alpha\geq2$.

### NOT

Fail: all three conclusions admit constants uniform over this entire family. Put $U=e^{X^2/2}$ and $\Lambda=\sup_{w\geq0}L_w$. Completing the square for the term with the favorable sign, and bounding the other exponential by one, gives
$$
\Lambda\leq pU+1-p\quad(X\geq0),\qquad
\Lambda\leq(1-p)U+p\quad(X<0).
$$
Let $B$ denote the two weights $p,1-p$, with zero terms omitted. For $b>0$ set $a_b=\sqrt{2\log(c/b)}$. Using
$$
\min(c,1-b+bU)\leq1-b+b\min(c/b,U),
$$
and integrating separately on the two half-lines yields
$$
\mathbb E\min(c,\Lambda)
\leq\frac12+\frac1{\sqrt\pi}\sum_{b\in B}b\sqrt{\log(c/b)}
+c\sum_{b\in B}\overline\Phi(a_b).
$$
The identity behind each term is
$$
\int_0^\infty\min(t,e^{x^2/2})\phi(x)\,dx
=\sqrt{\frac{\log t}{\pi}}+t\overline\Phi(\sqrt{2\log t}),\qquad t>1.
$$
By Jensen's inequality and the binary entropy bound, with $0\log0=0$,
$$
\sum_{b\in B}b\sqrt{\log(c/b)}
\leq\sqrt{\log c-p\log p-(1-p)\log(1-p)}
\leq\sqrt{\log c}+\sqrt{\log2}.
$$
Mills' inequality gives
$$
c\overline\Phi(a_b)\leq\frac{b}{2\sqrt{\pi\log(c/b)}}.
$$
Consequently the sharp strengthening holds throughout the family with
$$
C_{\rm sh}=\frac12+\sqrt{\frac{\log2}{\pi}}+\frac1{2\sqrt{\pi\log2}},
$$
and therefore the order assertion holds with
$$
C_{\rm ord}=\frac1{\sqrt\pi}+\frac{C_{\rm sh}}{\sqrt{\log2}}.
$$
For the tail bound, on the half-line associated with weight $b>0$, the event $\Lambda\geq\alpha$ requires
$$
U\geq A_b:=\frac{\alpha-1+b}{b}\geq\alpha.
$$
Hence
$$
\mathbb P\{\Lambda\geq\alpha\}
\leq\sum_{b\in B}\overline\Phi(\sqrt{2\log A_b})
\leq\frac1{2\sqrt{\pi\log\alpha}}\sum_{b\in B}\frac{b}{\alpha-1+b}
\leq\frac1{2(\alpha-1)\sqrt{\pi\log\alpha}}
\leq\frac1{\alpha\sqrt{\pi\log\alpha}}.
$$
Thus $C_{\rm tail}=1/\sqrt\pi$ works uniformly for this family as well. These calculations exclude the proposed rank-one boundary family only; they do not settle higher-rank geometries.

## Failure

NOT fails: every rank-one sign mixture, including scalar and zero-weight endpoints, satisfies all three asserted bounds with the explicit universal constants above.
