---
type: candidate
title: Interval-swap uniform copula underlying an arbitrary-dependence BH pathology
status: failed
target_asset: gaussian_bh_signed_label_halfline_stein_identity
checks:
  H1: pass
  H2: fail
  H3: unknown
  H4: unknown
  H5: unknown
  NOT: unknown
mode: refute
round: 2
slot: 4
direction: known_counterexamples
statement_digest: d3fb61916137dfc085bea1f638521abd2a8ea4841b661d5f9f84d49785283ab4
performed_by: unknown
created_at: '2026-11-07T05:29:57.144Z'
extension_version: 0.0.4
---

## Object

Set $N=2$, $\theta=(0,0)$, and $q=1-\Phi(1)$. Let $V$ be uniform on $(0,1)$ and define the measure-preserving interval swap
$$
T(v)=\begin{cases}
v+q,&0<v<q/2,\\
v-q,&q<v<3q/2,\\
v,&\text{otherwise}.
\end{cases}
$$
Set $p_1=V$, $p_2=T(V)$, and $Z_i=\Phi^{-1}(1-p_i)$. This is a concrete arbitrary-dependence uniform-marginal copula ansatz, rather than the singular Gaussian pair tested previously. Values at the interval endpoints can be assigned arbitrarily.

## Checks

### H1

Pass: $N=2$ is a finite positive integer and $\theta\in\mathbb R^2$.

### H2

Fail: the score vector must be jointly Gaussian. Both scores are standard normal marginally because $T$ swaps two intervals of equal length by translations and fixes their complement. However,
$$
\mathbb P(Z_1-Z_2=0)=1-q\in(0,1).
$$
Indeed $T(V)=V$ exactly outside the two swapped intervals, whose total length is $q$, and the strict monotonicity of $\Phi^{-1}(1-v)$ makes the difference nonzero inside them. A univariate Gaussian random variable either has no atom or is constant. Thus $Z_1-Z_2$ is not Gaussian, ruling out joint Gaussianity.

### H3

Unknown: the required positive-definite unit-diagonal Gaussian covariance assumption is not checked after H2 fails.

### H4

Unknown: the allowed level interval is not checked after H2 fails.

### H5

Unknown: the stipulated Gaussian p-values, fixed original labels, and BH translation construction are not checked after H2 fails.

### NOT

Unknown: the conclusion is not checked after H2 fails. No violation of the signed-label lemma is asserted.

## Failure

H2 fails: the Gaussian score transform of this interval-swap copula is not jointly Gaussian, because its coordinate difference has an atom of probability strictly between zero and one.
