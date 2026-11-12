---
type: candidate
title: Exponentially many Gaussian coordinates with vanishing independent noise
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

For $q\in(0,1/2)$ set $N=\lceil\exp(1/q)\rceil$, $a=\sqrt{1-q^2}$ and $\theta=0$. Take $Z,\varepsilon_1,\ldots,\varepsilon_N$ independent standard normal variables and define
$$
T_i=aZ+q\varepsilon_i,\qquad
\Sigma=(1-q^2)\mathbf1\mathbf1^{\mathsf T}+q^2 I_N.
$$
Use the specified two-sided Gaussian p-values and ordinary BH at level $q$.

## Checks

### H1

Pass: $N$ is a positive finite integer at every $q$ and may grow arbitrarily under the target's quantifiers.

### H2

Pass: $\theta=0\in\mathbb R^N$, so all coordinates are true nulls.

### H3

Pass: the displayed independent-normal representation is an exact jointly Gaussian law. Its covariance is symmetric and has diagonal one; $x^{\mathsf T}\Sigma x=(1-q^2)(\sum_i x_i)^2+q^2\sum_i x_i^2>0$ for nonzero $x$. Its smallest eigenvalue $q^2$ tends to zero while its rank $N$ diverges.

### H4

Pass: all-null FDR equals $\mathbb P(R_q>0)$. Any BH rejection implies $\min_i p_i\leq q$, and hence $\max_i|T_i|\geq z_q$, where $z_q=\Phi^{-1}(1-q/2)$. Put
$$
b_q=\sqrt{2\log(2N/q^2)},\qquad
x_q=\frac{z_q-qb_q}{\sqrt{1-q^2}}.
$$
The Gaussian exponential tail bound and a union bound give
$$
\mathbb P\left(\max_i|\varepsilon_i|>b_q\right)
\leq 2N e^{-b_q^2/2}=q^2.
$$
On the complementary event, $\max_i|T_i|\leq a|Z|+qb_q$, so, for sufficiently small $q$ when $x_q>0$,
$$
\operatorname{FDR}_{\rm BH}^{(2)}(q)
\leq 2\overline\Phi(x_q)+q^2.
$$

### NOT

Fail: $\log N=1/q+o(1)$ implies $b_q\sim\sqrt{2/q}$, whereas $z_q\sim\sqrt{2\log(1/q)}$. Consequently
$$
|x_q-z_q|=O(\sqrt q+q^2z_q),\qquad
z_q|x_q-z_q|\longrightarrow0.
$$
Mills' normal-tail asymptotic gives
$$
\frac{\overline\Phi(x_q)}{\overline\Phi(z_q)}
=\frac{z_q}{x_q}\exp\!\left(\frac{z_q^2-x_q^2}{2}\right)(1+o(1))
\longrightarrow1.
$$
It follows that FDR $\leq q(1+o(1))+q^2$, so this candidate's normalized asymptotic FDR is zero. The same false-rejection event bound permits arbitrary nonnull means for this covariance, since only the null coordinates enter the maximum.

## Failure

NOT fails: exponentially growing dimension and a vanishing independent Gaussian perturbation still give FDR $O(q)$ for this family.
