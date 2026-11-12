---
type: candidate
title: Growing singular Gaussian blocks with level-dependent alternative means
status: failed
target_asset: gaussian_bh_two_sided_sharp_upper
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
statement_digest: 2aaf3b157d839619c9429607bf182d896b1dacb3bc592c3dc8041bc442b8ed40
performed_by: unknown
created_at: '2026-11-04T08:34:06.454Z'
extension_version: 0.0.4
---

## Object

For $q\in(0,1/2)$ put $B=\lceil(\log(1/q))^2\rceil$, $m=\lceil\exp(1/q)\rceil$, $N=2Bm$, and $z_q=\Phi^{-1}(1-q/2)$. For independent standard normal $Z_1,\ldots,Z_B$, block $b$ has $m$ null coordinates equal to $Z_b$ and $m$ alternative coordinates equal to $Z_b+(-1)^b z_q$. Thus its mean vector has the specified zero and nonzero entries, and its covariance is block diagonal with $B$ all-ones blocks of size $2m$. Apply the specified two-sided p-values and ordinary BH procedure at level $q$.

## Checks

### H1

Pass: $N=2Bm$ is finite and positive for each $q$; both the dimension and the covariance rank $B$ diverge as $q\downarrow0$.

### H2

Pass: the means are real, with exactly $Bm$ zero entries. The nonzero means $(-1)^bz_q$ depend on $q$ as permitted.

### H3

Pass: the independent-normal representation gives an exact jointly Gaussian law. Every diagonal covariance entry is one, and for any $x$ its covariance quadratic form is the sum, over blocks, of the square of the sum of the entries of $x$ in that block. The covariance is positive semidefinite and singular.

### H4

Pass: all $m$ null p-values in block $b$ equal the uniform variable $U_b=2\overline\Phi(|Z_b|)$. If $R$ is the BH rejection count, that block's false-discovery contribution is
$$
D_b=\frac{m}{R\vee1}\mathbf1\{\text{null block }b\text{ rejected}\}.
$$
On a false rejection, $U_b\leq qR/N\leq q$ and $R\geq m$, so
$$
D_b\leq\min\!\left(1,\frac{qm}{NU_b}\right)\mathbf1\{U_b\leq q\}.
$$
Writing $w=m/N=1/(2B)$ and integrating against the marginal uniform distribution gives
$$
\mathbb E D_b\leq\int_0^q\min(1,qw/u)\,du
=qw\bigl(1+\log(1/w)\bigr).
$$
This calculation uses no conditional independence, and allows the alternatives to influence the BH rejection count arbitrarily.

### NOT

Fail: summing the contributions yields
$$
\operatorname{FDR}^{(2)}_{\rm BH}(q)
\leq\frac q2\bigl(1+\log(2B)\bigr)
=O\bigl(q\log\log(1/q)\bigr).
$$
Its ratio to $q\sqrt{\log(1/q)}$ tends to zero. More generally, whenever the true-null p-values form $B$ groups with a common uniform p-value in each group, put $w_b=(\text{null count in group }b)/N$ and $\pi_0=\sum_b w_b\leq1$. The same argument gives
$$
\operatorname{FDR}\leq q\sum_b w_b\bigl(1+\log(1/w_b)\bigr)
\leq q\pi_0\bigl(1+\log(B/\pi_0)\bigr)
\leq q(1+\log B).
$$
Thus every such family with $\log B=o(\sqrt{\log(1/q)})$ fails to refute the target, regardless of means or dependence among groups.

## Failure

NOT fails: the entropy bound rules out this growing-rank singular family and every grouped-null family with subexponential-in-square-root-log block count.
