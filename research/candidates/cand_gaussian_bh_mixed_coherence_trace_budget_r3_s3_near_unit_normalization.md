---
type: candidate
title: Near-unit variance perturbation violates the model normalization
status: failed
target_asset: gaussian_bh_mixed_coherence_trace_budget
checks:
  H1: pass
  H2: fail
  H3: unknown
  H4: unknown
  H5: unknown
  NOT: unknown
mode: refute
round: 3
slot: 3
direction: drop_hypothesis
statement_digest: 3c4f7eca379603e53ffd48c73869d12508d38f68f5f792a85af33304907ad513
performed_by: unknown
created_at: '2026-11-08T10:09:57.508Z'
extension_version: 0.0.4
---

## Object

For every $0<q\le\overline\Phi(3)$, set $N=d=1$, $\theta_1=0$, and $v_1=\lambda=1+q$ in the scalar latent representation $T_1=\lambda G$, $G\sim N(0,1)$. This is a deliberate drop of exact unit normalization, with $\lambda\downarrow1$ as $q\downarrow0$.

This does not repeat the board's constant-posterior trace obstruction as an attempted positive-trace construction. It tests a different conclusion, the normalization $x\le1$, under an arbitrarily small violation of a hypothesis. It supplies no admissible counterexample.

## Checks

### H1

**pass.** The dimensions $N=d=1$ are positive integers, $\theta_1=0$ is finite, and the construction is available at arbitrarily small positive levels. In particular it can be restricted to $0<q\le q_0$ for any proposed positive $q_0\le\overline\Phi(3)$.

### H2

**fail.** The target requires every $v_i$ to have norm exactly one. Here
$$
\|v_1\|=1+q>1,\qquad \Sigma_{11}=(1+q)^2\ne1.
$$
Joint Gaussianity itself holds, but the covariance has the wrong diagonal. The failure persists for every positive $q$, even though its magnitude tends to zero.

The following calculation explains why this hypothesis matters; it is a normalization diagnostic, not a later formal conclusion check. If the displayed formulas for the fields are mechanically applied to this inadmissible object, write $U=\overline\Phi^{-1}(q)$, $H=h(U)$, and $c=U/\lambda$. The one-coordinate rejection event is $\{G\ge c\}$, so
$$
f(z)=\mathbf1_{\{z\ge c\}},\qquad
B(z)=\frac{\lambda}{H}\mathbf1_{\{z\ge c\}},\qquad
F=\overline\Phi(c)>0.
$$
Heat convolution cancels the common indicator probability, giving $a(t,z)=\lambda/H$ at every $t<1,z$. Consequently the formal integrated coherence is $x=\lambda^2=(1+q)^2>1$, while $K_t=0$ and the formal signed trace is zero. Thus dropping exact normalization can already destroy the coherence range without any positive-trace mechanism. The board's observation $B=fb\Rightarrow K=0$ is respected.

### H3

**unknown.** Formal checks terminate at H2. This check would verify the prescribed one-sided p-values and true-null labels within an admissible model.

### H4

**unknown.** Formal checks terminate at H2. This check would verify ordinary BH with its largest qualifying rank and all multiplicities.

### H5

**unknown.** Formal checks terminate at H2. This check would verify the positive-F tilt and prescribed heat-field conventions within an admissible model.

### NOT

**unknown.** Formal checks terminate at H2. The normalization diagnostic above is not a refutation of the target, whose unit-vector hypothesis this object violates.

## Failure

H2 fails: the scalar vector has norm $1+q$, so the Gaussian covariance is not unit diagonal.
