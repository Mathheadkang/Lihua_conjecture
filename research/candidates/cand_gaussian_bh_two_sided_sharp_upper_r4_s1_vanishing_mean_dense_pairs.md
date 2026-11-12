---
type: candidate
title: >-
  Dense vanishing-mean pairs at singular covariance and superpolynomial
  dimension
status: failed
target_asset: gaussian_bh_two_sided_sharp_upper
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 4
slot: 1
direction: boundary_degenerate
statement_digest: 2aaf3b157d839619c9429607bf182d896b1dacb3bc592c3dc8041bc442b8ed40
performed_by: unknown
created_at: '2026-11-04T09:28:59.375Z'
extension_version: 0.0.4
---

## Object

This candidate tests the zero-mean boundary with a dense set of nonnulls, exactly singular dependence, and a superpolynomial number of independent null types. The growing maximum of the null coordinates can amplify a vanishing mean into a nonvanishing multiplicative p-value change. It differs from a sparse single-alternative gate and from the diverging-mean cyclic family.

For every $q\in(0,e^{-4})$, put
$$
L=\log(1/q),\qquad m=\lceil e^{L^2}\rceil,\qquad
N=2m,\qquad \mu=\frac1L.
$$
Let $Z_1,\ldots,Z_m$ be independent standard normal variables, and define
$$
T_i=Z_i,\qquad T_{m+i}=\mu-Z_i,\qquad 1\le i\le m.
$$
Thus the mean vector and covariance are
$$
\theta=(0_m,\mu 1_m),\qquad
\Sigma=
\begin{pmatrix}
I_m&-I_m\\
-I_m&I_m
\end{pmatrix}.
$$
Use the prescribed two-sided p-values for all $2m$ coordinates and ordinary BH at level $q$ on the whole vector. All parameters are finite deterministic functions of $q$; no population or numerical approximation defines the object.

## Checks

### H1

For each specified $q$, $N$ is a positive finite integer and $\theta\in\mathbb R^N$. In particular $\mu>0$ for every finite $q$, although $\mu\to0$ as $q\downarrow0$. Arbitrary $q$-dependence of the dimension and means is allowed.

### H2

With $A=(I_m,-I_m)^{\mathsf T}$, interpreted as the vertical concatenation of $I_m$ and $-I_m$, the observation is $T=\theta+AZ$. This proves joint Gaussianity and $\Sigma=AA^{\mathsf T}$. More directly,
$$
(x,y)^{\mathsf T}\Sigma(x,y)=\|x-y\|^2\ge0.
$$
Every diagonal entry equals one. The covariance has rank $m$, with eigenvalues zero and two, each of multiplicity $m$; singularity is permitted.

### H3

Because $\mu>0$, the exact two-sided true-null set is $[m]$. Write
$$
U_i=2\overline\Phi(|Z_i|),\qquad
P_i=2\overline\Phi(|\mu-Z_i|).
$$
The null p-values $U_1,\ldots,U_m$ are independent uniforms on $(0,1)$. The actual full p-value vector is $(U_1,\ldots,U_m,P_1,\ldots,P_m)$ and uses the required transform at every coordinate.

### H4

Use the largest qualifying global BH rank with thresholds $qr/(2m)$, retaining multiplicities and non-strict inequalities. Let $R$ and $V$ denote its global rejection and false-rejection counts. The comparison below concerns the event of at least one global rejection and does not add local block FDRs.

### H5

The FDR is exactly $\mathbb E[V/(R\vee1)]$ under the preceding finite Gaussian law. In particular
$$
\operatorname{FDR}_{\rm BH}^{(2)}\le\mathbb P(R>0).
$$
There are $m$ nonnulls as well as $m$ true nulls; no nonnull coordinate is reclassified as a true null merely because its mean tends to zero.

### NOT

The asymptotic conclusion does not fail. Define
$$
\mathcal E=\left\{\max_{1\le i\le m}|Z_i|\le2L\right\}.
$$
A union bound, $m\le2e^{L^2}$, and the standard normal Chernoff bound yield
$$
\mathbb P(\mathcal E^c)
\le 2m e^{-2L^2}
\le4e^{-L^2}\le e^{-2L}=q^2,\qquad L>4.
$$
The elementary Mills bound $\phi(x)/\overline\Phi(x)\le x+1$ for $x\ge0$ gives
$$
\frac{\overline\Phi(x+\mu)}{\overline\Phi(x)}
\ge\exp\{-\mu(x+1)-\mu^2/2\},\qquad x\ge0.
$$
For completeness, the Mills bound follows by setting $f(x)=(x+1)\overline\Phi(x)-\phi(x)$. The ratio $\overline\Phi(x)/\phi(x)=\int_0^\infty e^{-xt-t^2/2}\,dt$ decreases strictly from $\sqrt{\pi/2}>1$ to zero, so $f'(x)=\overline\Phi(x)-\phi(x)$ first is positive and then negative. Since $f(0)>0$ and $f(x)\to0$, $f\ge0$. Integrating the resulting logarithmic derivative proves the displayed tail-ratio inequality.

On $\mathcal E$, use $|\mu-Z_i|\le|Z_i|+\mu$ and $\mu=1/L$ to get
$$
P_i\ge2\overline\Phi(|Z_i|+\mu)
\ge e^{-3}U_i,
$$
because
$$
\mu(2L+1)+\mu^2/2
=2+1/L+1/(2L^2)<3,\qquad L>4.
$$
The null coordinate $U_i$ is also at least $e^{-3}U_i$. Hence, coordinate by coordinate, the full p-vector on $\mathcal E$ dominates $e^{-3}$ times the duplicated vector
$$
D=(U_1,\ldots,U_m,U_1,\ldots,U_m).
$$
It follows from monotonicity of order statistics that a global BH rejection for the actual p-vector implies a BH rejection for $D$ at level $\alpha=e^3q<1$. For the duplicated vector the existence of a qualifying rank is equivalent to
$$
\text{there exists }s\in[m]\text{ with }U_{(s)}\le\frac{\alpha s}{m}.
$$
Indeed an odd qualifying rank always gives the next even qualifying rank with the same duplicated order statistic. For independent uniforms the probability of this event is exactly $\alpha$.

The last equality can also be checked directly with ordinary BH on $U$ at level $\alpha$. For each $i$, replace $U_i$ by zero and let $R_i\ge1$ be the new BH rejection count. The step-up rule implies that $i$ is rejected in the original vector exactly when $U_i\le\alpha R_i/m$, and then the original count equals $R_i$. Since $R_i$ is independent of $U_i$, the expected contribution of null $i$ to FDP is $\alpha/m$. Summing over all $m$ nulls gives $\mathbb P(\text{at least one rejection})=\alpha$.

Combining the global comparison with the exceptional-event bound gives the finite-$q$ estimate
$$
\operatorname{FDR}_{\rm BH}^{(2)}
\le\mathbb P(R>0)
\le e^3q+q^2.
$$
Consequently
$$
0\le\frac{\operatorname{FDR}_{\rm BH}^{(2)}}{q\sqrt{\log(1/q)}}
\le\frac{e^3+q}{\sqrt L}\longrightarrow0.
$$
This is an exclusion of the specified dense paired family and its scaling, not of arbitrary vanishing-mean Gaussian models. It does not rule out FDR inflation above $q$ at a fixed level and makes no claim about unresolved weak common-gate designs.

## Failure

NOT fails: the largest global BH crossing is dominated outside an event of probability at most $q^2$ by duplicate-independent-uniform BH at level $e^3q$, giving FDR $O(q)=o(q\sqrt{\log(1/q)})$.
