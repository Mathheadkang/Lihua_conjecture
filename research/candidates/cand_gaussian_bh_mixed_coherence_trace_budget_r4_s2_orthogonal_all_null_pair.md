---
type: candidate
title: >-
  The orthogonal two-null model satisfies the mixed budget through its rank
  cutoff gap
status: failed
target_asset: gaussian_bh_mixed_coherence_trace_budget
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 4
slot: 2
direction: small_cases
statement_digest: 3c4f7eca379603e53ffd48c73869d12508d38f68f5f792a85af33304907ad513
performed_by: unknown
created_at: '2026-11-08T10:20:56.688Z'
extension_version: 0.0.4
---

## Object

For every $0<q\le\overline\Phi(3)$, take $N=d=2$, $\theta=(0,0)$, $v_1=e_1$, $v_2=e_2$, and $G\sim\gamma_2$. Put
$$
U=\overline\Phi^{-1}(q),\quad A=\overline\Phi^{-1}(q/2),\quad H=h(U),\quad c=\frac1{h(A)},\quad b=\frac1H,\quad r=\frac H{h(A)}.
$$
The board lists this model as having only its FDR and endpoint calculated, with its well-posedness and budget still unchecked. The new calculation below completes both checks; it does not infer a signed trace from its endpoint alone.

Define disjoint regions
$$
E_1=\{z_1\ge A,\ z_2<U\},\quad E_2=\{z_2\ge A,\ z_1<U\},\quad J=\{z_1\ge U,\ z_2\ge U\}.
$$
The boundaries have Gaussian measure zero and the non-strict BH convention is used on them.

## Checks

### H1

The displayed testing level is positive and at most $\overline\Phi(3)$; hence $U\ge3$.

### H2

Both dimensions are finite positive integers, the two observation vectors have norm one, and their Gram matrix is $I_2$. Thus the observation is exactly jointly Gaussian with unit marginal variances.

### H3

The one-sided p-values are $p_i(z)=\overline\Phi(z_i)$ and $I_0=\{1,2\}$, exactly as prescribed.

### H4

Rank two qualifies precisely on $J$. If it does not qualify, rank one selects the first coordinate precisely on $E_1$, or the second precisely on $E_2$. Therefore the actual largest-rank BH fields are
$$
f=\mathbf1_{E_1\cup E_2\cup J},\qquad
B=c e_1\mathbf1_{E_1}+c e_2\mathbf1_{E_2}+\frac b2(e_1+e_2)\mathbf1_J.
$$
Every rejection is a true-null rejection, so the displayed FDP is correct.

### H5

Independence gives
$$
\gamma_2(E_1)=\gamma_2(E_2)=\frac q2(1-q),\qquad \gamma_2(J)=q^2,
$$
and consequently $F=q>0$. All stipulated heat fields and tilted measures are therefore defined. The terminal vector $b_1=(B/f)(W_1)$ has three possible values under $\mathbb Q$: $ce_1$, $ce_2$, and $b(e_1+e_2)/2$. Its squared norm is at most $b^2$.

### NOT

This check fails: uniformly over the displayed small levels the stronger square-root estimate
$$
M_+\le3q\sqrt{1-x}
$$
holds. The proof first establishes every well-posedness and endpoint assertion.

Since $f$ is an indicator and $F=q$, the entropy is exactly $D=\log(1/q)$. To establish the needed change of measure without assuming the target's identities, set $m_t=\mathcal H(t,W_t)/q$. This is the positive density martingale under $\mathbb P$, bounded by $1/q$, with terminal value $f(W_1)/q$. Localized Ito's formula for $m_t\log m_t$ gives
$$
\mathbb E_{\mathbb Q}\int_0^\tau\|\beta_t\|^2dt
=2\mathbb E_{\mathbb P}[m_\tau\log m_\tau].
$$
Continuity of $s\log s$ at zero, boundedness of $m_t$ and martingale convergence justify passage to $\tau\uparrow1$, yielding
$$
\mathbb E_{\mathbb Q}\int_0^1\|\beta_t\|^2dt=2D<\infty.
$$
Girsanov on every compact subinterval and the finite energy show that
$$
Z_t=W_t-\int_0^t\beta_sds
$$
extends to a standard two-dimensional Brownian motion under $\mathbb Q$ on $[0,1]$.

Bayes' rule identifies the prescribed posterior as $a_t=\mathbb E_{\mathbb Q}[b_1\mid\mathcal F_t]$. It is a bounded vector martingale, converging to $b_1$ at time one. Ito's formula applied to its smooth heat expression gives $da_t=K_t\,dZ_t$ for $t<1$. Thus
$$
\mathbb E_{\mathbb Q}\int_0^1\|K_t\|_{\rm HS}^2dt
=\mathbb E_{\mathbb Q}\|b_1\|^2-\|a_0\|^2\le b^2.
$$
The bound $|\operatorname{tr}K_t|\le\sqrt2\|K_t\|_{\rm HS}$ and Cauchy--Schwarz prove absolute trace integrability. Also $\|a_t\|\le b$ gives $0\le x\le1$, and
$$
\mathbb E_{\mathbb Q}\int_0^1|a_t\cdot\beta_t|dt\le b\sqrt{2D}<\infty.
$$
The endpoint integral is absolutely finite since $\|B\|\le b$ and the Gaussian first moment is finite. In fact its value can be checked directly:
$$
\int z\cdot B(z)\gamma_2(dz)
=2c\phi(A)(1-q)+b\phi(U)q
=q(1-q)+q^2=q.
$$
To establish its agreement with the signed heat trace, conditional expectation and the preceding absolute bounds give
$$
\mathbb E_{\mathbb Q}\left[b_1\cdot\int_0^1\beta_tdt\right]
=\mathbb E_{\mathbb Q}\int_0^1a_t\cdot\beta_tdt.
$$
The martingale representation $b_1=a_0+\int_0^1K_t\,dZ_t$ and Ito isometry give
$$
\mathbb E_{\mathbb Q}[b_1\cdot Z_1]
=\mathbb E_{\mathbb Q}\int_0^1\operatorname{tr}K_tdt.
$$
Multiplying by $F=q$ and using $W_1=Z_1+\int_0^1\beta_tdt$ proves exactly the target endpoint identity. Absolute trace integrability also proves agreement with $\lim_{\tau\uparrow1}M_\tau$. Only after these facts are established do we use
$$
M=q\mathbb E_{\mathbb Q}[b_1\cdot Z_1],\qquad
|M|\le q\bigl(\mathbb E_{\mathbb Q}\|b_1\|^2\bigr)^{1/2}
\bigl(\mathbb E_{\mathbb Q}\|Z_1\|^2\bigr)^{1/2}
\le\frac{\sqrt2 q}H.
$$
The terminal law and conditional Jensen give the needed coherence deficit, independently of any drift sign:
$$
x\le H^2\mathbb E_{\mathbb Q}\|b_1\|^2
=(1-q)r^2+\frac q2,
$$
so, writing $\delta=1-x$,
$$
\delta\ge(1-q)(1-r^2)+\frac q2\ge(1-q)(1-r^2).
$$
We now verify a uniform positive lower bound for $H^2\delta$. The elementary Mills inequalities imply
$$
t\le h(t)\le t+\frac1t\qquad(t>0).
$$
Three integrations by parts give the further upper bound
$$
\frac{\overline\Phi(t)}{\phi(t)}\le\frac1t-\frac1{t^3}+\frac3{t^5}.
$$
For $t\ge3$, let $E_t=1-t^{-2}+3t^{-4}\in(0,1)$. The latter inequality gives
$$
h(t)-t\ge\frac{t^{-1}-3t^{-3}}{E_t}
\ge\frac{1-3/t^2}{t}\ge\frac2{3t}.
$$
Since $h'(t)=h(t)(h(t)-t)$ and $h(t)\ge t$, it follows that $h'(t)\ge2/3$ for every $t\ge3$. Also
$$
\log2=\log\frac{\overline\Phi(U)}{\overline\Phi(A)}
=\int_U^A h(t)dt,
$$
which yields
$$
\frac{\log2}{h(A)}\le A-U\le\frac{\log2}{U}.
$$
Consequently
$$
h(A)^2-H^2\ge h(A)(h(A)-H)
\ge\frac23h(A)(A-U)\ge\frac23\log2>\frac49,
$$
and
$$
r\ge\frac{U}{U+(1+\log2)/U}
\ge\frac9{10+\log2}>\frac9{11}>\frac45.
$$
Finally $q\le\overline\Phi(3)\le\phi(3)/3<1/100$. Combining the rational bounds gives
$$
H^2\delta\ge(1-q)r^2\bigl(h(A)^2-H^2\bigr)
>\frac{99}{100}\frac{16}{25}\frac49>\frac14.
$$
Thus $1/H<2\sqrt\delta$ and the established innovation estimate gives
$$
M_+\le|M|\le\frac{\sqrt2 q}H
<2\sqrt2 q\sqrt\delta<3q\sqrt{1-x}.
$$
This implies the proposed mixed budget with $C=3$ throughout this family, because its entropy-linear term is nonnegative. No conclusion about the unrestricted model follows from this fixed two-direction calculation.

## Failure

NOT fails: the finite-dimensional innovation estimate is absorbed by a uniform rank-cutoff contribution $H^2(1-x)>1/4$, giving $M_+\le3q\sqrt{1-x}$.
