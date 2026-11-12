---
type: candidate
title: Scalar Gaussian endpoint with unbounded thresholds
status: failed
target_asset: gaussian_frozen_ray_two_level_tree
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 1
slot: 2
direction: small_cases
statement_digest: 2b5422491f69603ba61bab7fad6c2642d6e692d0f1b1b9e16e8ff8d5ec9e825b
performed_by: unknown
created_at: '2026-11-11T01:00:13.147Z'
extension_version: 0.0.4
---

## Object

For every real parameter $t\geq2$, take $b_1=b_2=1$, $a=0$, mutually independent standard normals $G_1,G_{11}$, and $c=\alpha=t$. Thus $Z_{11}=G_{11}=:G$. Define $L_w$ and $\Lambda$ using this one realization of $G$ at every $w\geq0$.

## Checks

### H1

The branching numbers $b_1=b_2=1$ are positive integers.

### H2

The parameter $a=0$ belongs to $[0,1]$.

### H3

The variables $G_1,G_{11}$ are mutually independent standard normal variables; $Z_{11}=\sqrt a G_1+\sqrt{1-a}G_{11}=G$ is centered Gaussian with variance one.

### H4

For the same realization of $G$ at all $w\geq0$,
$$
L_w=\exp(wG-w^2/2),\qquad \Lambda=\exp((G_+)^2/2).
$$
The maximizer is $w=G_+$, where $G_+=\max(G,0)$. Probabilities and expectations below use the stated standard normal law and natural logarithms.

### H5

Both thresholds $c=\alpha=t$ are real and at least two.

### NOT

Fail. Put $s=\sqrt{2\log t}$ and write $\overline\Phi(s)=\mathbb P(G>s)$. Direct integration gives
$$
\mathbb E\min\{t,\Lambda\}=\frac12+\frac{s}{\sqrt{2\pi}}+t\overline\Phi(s)
=\sqrt{\frac{\log t}{\pi}}+\frac12+t\overline\Phi(s).
$$
The contributions are $1/2$ on $G\leq0$, the integral of the constant $1/\sqrt{2\pi}$ over $(0,s)$, and $t\mathbb P(G>s)$ above $s$. The inequality $\overline\Phi(s)\leq\phi(s)/s$ follows by bounding $1\leq x/s$ inside the Gaussian tail integral. Since $t\phi(s)=1/\sqrt{2\pi}$,
$$
\mathbb E\min\{t,\Lambda\}-\sqrt{\frac{\log t}{\pi}}
\leq\frac12+\frac{1}{2\sqrt{\pi\log t}}<1.
$$
Also,
$$
\mathbb P(\Lambda\geq t)=\overline\Phi(s)
\leq\frac{1}{2\sqrt\pi\,t\sqrt{\log t}}.
$$
Thus the moment excess and normalized maximal tail remain bounded throughout this unbounded-threshold family. It cannot violate the existence of universal constants. The moment excess tends to $1/2$, while $t\sqrt{\log t}\,\mathbb P(\Lambda\geq t)$ tends to $1/(2\sqrt\pi)$.

## Failure

NOT fails: the scalar family satisfies both assertions with $C_{\mathrm{sh}}=1$ and $C_{\mathrm{tail}}=1/(2\sqrt\pi)$.
