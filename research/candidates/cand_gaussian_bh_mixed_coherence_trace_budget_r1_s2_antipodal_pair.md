---
type: candidate
title: Two antipodal nulls have trace of order at most q over squared cutoff
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
round: 1
slot: 2
direction: small_cases
statement_digest: 3c4f7eca379603e53ffd48c73869d12508d38f68f5f792a85af33304907ad513
performed_by: unknown
created_at: '2026-11-08T09:57:49.237Z'
extension_version: 0.0.4
---

## Object

For every $0<q\le\overline\Phi(3)$, take $N=2$, $d=1$, $\theta=(0,0)$, and $v_1=1$, $v_2=-1$. Put $u=\overline\Phi^{-1}(q/2)$, $c=1/h(u)$, $U=\overline\Phi^{-1}(q)$ and $H=h(U)$.

## Checks

### H1

The dimensions are positive finite integers and both means are real and zero.

### H2

Both vectors have unit length. The Gram covariance is the admissible singular matrix with diagonal entries $1$ and off-diagonal entries $-1$. The observations are $(G,-G)$.

### H3

The level lies in $(0,\overline\Phi(3)]$, so $u>U\ge3$.

### H4

Both indices are true nulls. Since $p_1+p_2=1$, rank two can never qualify for $q<1/2$. Ordinary BH rejects exactly index one on $\{z\ge u\}$ and exactly index two on $\{z\le-u\}$. Therefore

$$
f(z)=\mathbf1_{\{|z|\ge u\}},\qquad
B(z)=c\,\operatorname{sgn}(z)\mathbf1_{\{|z|\ge u\}},\qquad F=q.
$$

The two tails are disjoint, and the endpoint convention has zero-probability effect only.

### H5

Use exactly the target's tilted measures and heat fields. Here $D=\log(1/q)$. For $s=1-t$, define

$$
p=\overline\Phi((u-z)/\sqrt s),\qquad m=\overline\Phi((u+z)/\sqrt s),
$$

so that $\mathcal H=p+m$ and $a=c(p-m)/(p+m)$. In particular $|a|\le c$, and

$$
0\le x\le H^2c^2<1.
$$

Write $A=\phi((u-z)/\sqrt s)/\sqrt s$ and $B_0=\phi((u+z)/\sqrt s)/\sqrt s$. Direct differentiation gives the nonnegative scalar trace

$$
\mathcal H K=\frac{2c(Am+B_0p)}{p+m}\ge0.
$$

For $z\ge0$, $m/p\le\exp(-2uz/s)=B_0/A$. Indeed, $h(r)\ge r$ for every real $r$, and integrating this inequality from $(u-z)/\sqrt s$ to $(u+z)/\sqrt s$ proves the tail-ratio bound. Hence $\mathcal H K\le4cB_0$ for $z\ge0$. Symmetry and Gaussian convolution now give, for $0<t<1$,

$$
F\mathbb E_{\mathbb Q}K_t
\le8c\int_0^\infty\phi_t(z)\frac{\phi((u+z)/\sqrt s)}{\sqrt s}\,dz
=8c\phi(u)\overline\Phi\left(u\sqrt{t/(1-t)}\right)
=4q\overline\Phi\left(u\sqrt{t/(1-t)}\right),
$$

where $\phi_t$ is the $N(0,t)$ density and $c\phi(u)=q/2$. Consequently

$$
0\le F\mathbb E_{\mathbb Q}\int_0^1|K_t|dt
\le4q\int_0^\infty\overline\Phi(u\sqrt t)dt
=\frac{2q}{u^2}<\infty.
$$

The heat-entropy identity yields $\mathbb E_{\mathbb Q}\int_0^1|\beta_t|^2dt=2\log(1/q)$; boundedness of $a$ gives absolute mixed-drift integrability. The endpoint integral is $\int zB(z)d\gamma_1(z)=2c\phi(u)=q$. Applying the product rule to $W_ta_t$ under the tilted measure, whose drift is $\beta_t$, gives the target's trace identity. Localization is removable using bounded $a$, the preceding absolute-integrability estimates, and $W_t\to W_1$ in tilted $L^2$. Thus $M_*=M$, and every well-posedness assertion holds.

### NOT

Fail. Let $\delta_0(q)=1-H^2/h(u)^2>0$. The explicit bound above implies

$$
\frac{M_+}{q\sqrt{1-x}}\le\frac{2}{u^2\sqrt{\delta_0(q)}}.
$$

The right side is continuous for $q\in(0,\overline\Phi(3)]$. The elementary Mills asymptotics $h(r)=r+r^{-1}+O(r^{-3})$ and the identity $\log2=\int_U^u h(r)dr$ imply

$$
u^2-U^2\longrightarrow2\log2,\qquad
\delta_0(q)\sim\frac{2\log2}{U^2}\quad(q\downarrow0).
$$

Hence this ratio bound tends to zero as $q\downarrow0$ and has a finite supremum on the entire displayed interval. A single finite constant therefore bounds this whole family by the square-root term alone, and adding the target's nonnegative entropy-linear term preserves the estimate. This family cannot defeat any proposed choice of universal constants by a small-level limiting sequence.

## Failure

NOT fails: antipodal cancellation gives $M_+\le2q/u^2$, whereas the coherence deficit is at least of order $u^{-2}$, so the square-root budget is larger.
