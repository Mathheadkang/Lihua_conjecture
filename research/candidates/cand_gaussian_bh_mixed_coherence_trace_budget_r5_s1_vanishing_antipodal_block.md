---
type: candidate
title: Vanishing minority mass in unequal antipodal null blocks
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
round: 5
slot: 1
direction: boundary_degenerate
statement_digest: 3c4f7eca379603e53ffd48c73869d12508d38f68f5f792a85af33304907ad513
performed_by: unknown
created_at: '2026-11-08T10:31:02.996Z'
extension_version: 0.0.4
---

## Object

Let $m,k$ be arbitrary positive integers, $N=m+k$, $d=1$, and all $N$ means be zero. Take $m$ copies of the vector $+1$ and $k$ copies of $-1$. Let
$$
w=m/N,\quad A=\overline\Phi^{-1}(qw),\quad L=\overline\Phi^{-1}(q(1-w)),\quad c_+=1/h(A),\quad c_-=1/h(L),
$$
where $0<q\le\overline\Phi(3)$ and $U=\overline\Phi^{-1}(q)$, $H=h(U)$. Permit $m,k$ and hence $w$ to depend arbitrarily on $q$, including $w\to0$ or $w\to1$ arbitrarily fast.

**Changed mathematical obstruction.** The named earlier candidate `cand_gaussian_bh_mixed_coherence_trace_budget_r1_s2_antipodal_pair`, read with native `show` to check its scope, treats only $m=k=1$. Its trace calculation uses symmetry of the two tails and its budget uses the fixed logarithmic cutoff gap $\log2$. Neither ingredient is uniform here: as $w\to1$, $A\downarrow U$ and the corresponding cutoff gap $\log(1/w)$ vanishes. Thus the tested new boundary mechanism is vanishing minority mass coupled with an unbounded cutoff on the minority tail, not a change of level in the symmetric pair. The common-true-null-direction obstruction does not apply because both directions occur. The weighted entropy-gap calculation below independently handles this boundary.

## Checks

### H1

$N=m+k$ and $d=1$ are positive finite integers; the means are finite and zero.

### H2

All observation vectors have norm one. Their Gram matrix has entries $v_iv_j$ and is positive semidefinite with unit diagonal and rank one. The observations are jointly Gaussian functions of one standard Gaussian variable.

### H3

$0<q\le\overline\Phi(3)$, so $A,L>U\ge3$.

### H4

All indices are true nulls and the prescribed p-values have two possible values, $\overline\Phi(z)$ and $\overline\Phi(-z)$, whose sum is one. Since $q<1/2$, a BH rejection set cannot contain both blocks: rejection of both values would require both to be at most $q$. If only the positive block qualifies, its largest possible rank is $m$, and within this tied block the largest rank condition is precisely $\overline\Phi(z)\le qm/N=qw$. The analogous negative condition is $\overline\Phi(-z)\le qk/N=q(1-w)$. These events are disjoint. Therefore the actual largest-rank BH rule, with all multiplicities, gives
$$
R(z)=m\mathbf1_{\{z\ge A\}}+k\mathbf1_{\{z\le-L\}},\qquad
f(z)=\mathbf1_{\{z\ge A\}\cup\{z\le-L\}},
$$
$$
B(z)=c_+\mathbf1_{\{z\ge A\}}-c_-\mathbf1_{\{z\le-L\}}.
$$
The equality conventions affect no Gaussian probability.

### H5

The prescribed tilt exists because
$$
F=\overline\Phi(A)+\overline\Phi(L)=q,\qquad D=\log(1/q).
$$
Under $Q$, the upper and lower tails have probabilities $w$ and $1-w$. Put $b=B/f$ on its support. Its two terminal values are $c_+$ and $-c_-$. For $s=1-t$ let
$$
p_+=\overline\Phi((A-z)/\sqrt s),\quad
p_-=\overline\Phi((L+z)/\sqrt s).
$$
The target's unmodified heat fields are
$$
\mathcal H=p_++p_-,\qquad
a(t,z)=\frac{c_+p_+-c_-p_-}{p_++p_-}.
$$

### NOT

**Fails:** all well-posedness assertions hold and $M_+\le\sqrt{18/7}\,q\sqrt{1-x}<2q\sqrt{1-x}$ uniformly in $m,k,q$.

Here are independent checks of the required identities before estimating the trace. Under the prescribed path tilt, $a_t=\mathbb E_{\mathbb Q}[b(W_1)\mid\mathcal F_t]$. Put
$$
\mu=\mathbb E_Qb=wc_+-(1-w)c_-,\quad
S=\mathbb E_Qb^2=wc_+^2+(1-w)c_-^2,\quad
V=\operatorname{Var}_Q(b)=w(1-w)(c_++c_-)^2.
$$
The mark is bounded by $1/H$, so $x\le H^2S\le1$. The entropy identity gives $\mathbb E_{\mathbb Q}\int_0^1\beta_t^2dt=2D$: apply Itô on each interval $[0,\tau]$ to the positive heat-density martingale; its densities are bounded by $1/q$, and dominated convergence of $u\log u$ on $[0,1/q]$ gives the endpoint entropy. The innovation $Z_t=W_t-\int_0^t\beta_sds$ is Brownian under $\mathbb Q$ and extends to time one. Heat calculus and the bounded terminal-mark martingale give
$$
da_t=K_t\,dZ_t,\qquad
\mathbb E_{\mathbb Q}\int_0^1 K_t^2dt=V.
$$
It follows in particular that
$$
\mathbb E_{\mathbb Q}\int_0^1|K_t|dt\le\sqrt V<\infty,\qquad
\mathbb E_{\mathbb Q}\int_0^1|a_t\beta_t|dt\le H^{-1}\sqrt{2D}<\infty.
$$
Also $0\le D=\log(1/F)<\infty$. Since $B$ is bounded, the endpoint integral is absolutely finite; explicitly,
$$
\int zB(z)d\gamma_1(z)=c_+\phi(A)+c_-\phi(L)=qw+q(1-w)=q.
$$
The terminal representation $b(W_1)=\mu+\int_0^1K_t\,dZ_t$ and the cross isometry imply $\mathbb E_{\mathbb Q}[b(W_1)Z_1]=\mathbb E_{\mathbb Q}\int K_tdt$. By conditional expectation and absolute drift integrability,
$$
\mathbb E_{\mathbb Q}\left[b(W_1)\int_0^1\beta_tdt\right]
=\mathbb E_{\mathbb Q}\int_0^1a_t\beta_tdt.
$$
Using $W_1=Z_1+\int\beta$, multiplying by $F=q$, and the displayed endpoint integral proves exactly $M_*=M=\lim_{\tau\uparrow1}M_\tau$, with all absolute-integrability statements established beforehand.

Direct differentiation also gives
$$
K(t,z)=\frac{(c_++c_-)p_+p_-}{(p_++p_-)^2\sqrt s}
\left[h((A-z)/\sqrt s)+h((L+z)/\sqrt s)\right]>0.
$$
Thus this family has positive trace, and the energy bound yields $M_+\le q\sqrt V$.

It remains to compare its variance with the vanishing cutoff deficit uniformly. For $u\ge3$, if $X$ is standard normal conditioned on $X\ge u$, tail translation gives $\mathbb P(X-u\ge y)\le e^{-uy}$ for $y\ge0$ and hence $\mathbb E(X-u)^2\le2/u^2$. The identity $h'(u)=1-\operatorname{Var}(X)$ implies $h'(u)\ge7/9$. Consequently, for every $T\ge U$,
$$
h(T)^2-H^2=\int_U^T2h(u)h'(u)du\ge\frac{14}9\int_U^Th(u)du.
$$
Using the weaker constant $7/9$ therefore gives
$$
h(A)^2-H^2\ge\tfrac79\log(1/w),\qquad
h(L)^2-H^2\ge\tfrac79\log(1/(1-w)).
$$
Write $\delta=1-H^2S$. Since $\log(1/w)\ge1-w$ and $\log(1/(1-w))\ge w$,
$$
\delta
=w c_+^2(h(A)^2-H^2)+(1-w)c_-^2(h(L)^2-H^2)
\ge\frac79w(1-w)(c_+^2+c_-^2).
$$
On the other hand $(c_++c_-)^2\le2(c_+^2+c_-^2)$, so
$$
V\le\frac{18}7\delta\le\frac{18}7(1-x),\qquad
M_+\le\sqrt{18/7}\,q\sqrt{1-x}.
$$
The same disappearing minority weight appears in both variance and the weighted entropy gap. The nonnegative entropy-linear term cannot reverse this bound. This argument is uniform even when the minority multiplicity proportion goes to zero arbitrarily quickly.

## Failure

NOT fails: although the fixed symmetric cutoff gap degenerates, a weighted logarithmic cutoff gap controls terminal-mark variance and yields a uniform square-root budget.
