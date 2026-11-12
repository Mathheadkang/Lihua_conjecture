---
type: candidate
title: Mixed symmetric true and false particle reweighting
status: failed
target_asset: gaussian_bh_private_cutoff_particle_mass_variation
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 5
slot: 2
direction: small_cases
statement_digest: 8345cf59553f81f078aa75b8209e82e7b444527650ffec26a456254734403e01
performed_by: unknown
created_at: '2026-11-09T09:22:18.949Z'
extension_version: 0.0.4
---

## Object

Take the Hilbert space to be the real line and put
$$
\sigma=s=\frac12,\qquad a=\frac1{10},\qquad q=S(1),
\qquad \rho=1,\qquad \lambda=0.
$$
Let the cutoff be zero below $a$, one above $2a$, and $3y^2-2y^3$ between them, where $y=(r-a)/a$. Set
$$
x_-=(-1,0,1),\qquad x_+=(1,0,0),\qquad
\pi=\tfrac12\delta_{x_-}+\tfrac12\delta_{x_+},\qquad
\nu=\delta_{x_-}.
$$
Thus the perturbation transfers mass from a positive-mean false particle to a negative-mean true particle. Their score kernels are distinct. This is neither an all-true population nor a coincident-kernel tag swap from the board.

There is no residual-background dependence because both loadings vanish. Write $c=\sqrt3/2$ and
$$
A(z)=S((z+1)/c),\quad C(z)=S((z-1)/c),\quad
k_-(z)=\phi((z+1)/c)/c,\quad k_+(z)=\phi((z-1)/c)/c.
$$
The exact perturbed kernels are
$$
H_\epsilon(z)=\tfrac{1+\epsilon}{2}A(z)
 +\tfrac{1-\epsilon}{2}C(z),\qquad
V_\epsilon(z)=\tfrac{1+\epsilon}{2}A(z).
$$

## Checks

### H1

The fixed parameters satisfy $\sigma,s>0$, $\sigma^2+s^2=1/2<1$, $0<a<1/4$ and $0<q=q_{\max}$. The specified cutoff is nondecreasing and $C^1$, including at its two joining points.

### H2

Both laws are deterministic Borel probabilities on the lawful marked unit ball: the true particle has mean $-1$, the false particle has mean $1$, and both have loading zero. Their second mean moments equal one. All choices precede the Gaussian variables. Here $c_s(0)^2=3/4$, so the private conditional score variances have the required form.

### H3

For $0<\epsilon<a/2$, the perturbed law is exactly $(1-\epsilon)\pi+\epsilon\nu$ with positive weights $(1+\epsilon)/2$ and $(1-\epsilon)/2$. The level stays at $q_{\max}$ and all stated smallness conditions hold.

### H4

Use the prerequisite's actual globally largest non-strict rank, its full fractional payoff, and its endpoint conventions. Explicitly this is the supremum of the ranks satisfying
$$
H_\epsilon(u_q(r)-\sigma Z)\ge r,
$$
not a chosen root or a local crossing. Its survival is determined by the suffix minimum of $(u_q-Q_\epsilon)/\sigma$. The finite kernels above are smooth, strictly decreasing, and have positive density. Their quantile endpoint is $Q_\epsilon(1)=-\infty$, so rank one has zero probability for finite $Z$.

### NOT

Fail: the proposed missing true-mass response is present in the stated formula, and the full actual-rank response also agrees in this mixed example.

For a fixed interior rank put $z=Q(r)$ and $h=(k_-+k_+)/2$. Direct differentiation of the displayed exact kernels gives
$$
\dot Q(r)=\frac{A(z)-C(z)}{2h(z)},\qquad
\dot f(r)=\frac1r\left\{\frac{A(z)}2
 -\frac{k_-(z)}{2h(z)}\frac{A(z)-C(z)}2\right\}.
$$
These are exactly the target's two fixed-rank derivatives, with both numerator and quantile effects retained. In particular, symmetry gives $Q(1/2)=0$, $C(0)=1-A(0)$ and $k_-(0)=k_+(0)$, hence
$$
\dot Q(1/2)=\frac{2A(0)-1}{2h(0)}<0,
\qquad \dot f(1/2)=\frac12.
$$
This nonzero bulk response is absent from the all-true reductions but is not absent from the asserted formula. The rank-one response also equals the stated true-mass derivative $1/2$.

For completeness, the full rank calculation does not require selecting a unique fold here. For $0\le e\le1/2$, the density $h_e$ satisfies
$$
h_e\ge\tfrac14(k_-+k_+),\qquad
|\partial_e Q_e(r)|\le
\frac{2|A(Q_e(r))-C(Q_e(r))|}{k_-(Q_e(r))+k_+(Q_e(r))}\le K<\infty.
$$
The last ratio is continuous on the real line and tends to zero at both infinities by the Gaussian Mills asymptotics. Thus $|Q_e-Q|\le Ke$ uniformly in rank. The barriers and suffix minima consequently differ by at most $Ke/\sigma$. Minima remain away from rank one, and ordinary compact minimization gives
$$
\dot M(r)=-\frac1\sigma\max_{t\in\mathcal A(r)}\dot Q(t).
$$
This retains every competing active minimum. The survival derivative is $-\phi(M)\dot M$, with difference quotients bounded by $K/(\sigma\sqrt{2\pi})$.

Let $g_e=\chi_a f_e$ and $w=g_0'$. The exact survival integration identity yields
$$
F_e-F_0=\mathbb E[(g_e-g_0)(R_e)]
 +\int_a^1w(r)\{S(M_e(r))-S(M(r))\}\,dr.
$$
The first quotient is bounded by $2/a$ using the affine kernels and the fixed-rank true-mass bound. It converges to $\chi_a(R)\dot f(R)$ almost surely: the barrier perturbations converge uniformly, so the largest rank converges outside the countably many discontinuity levels of its monotone dependence on $Z$; positive limiting ranks use local uniform quantile differentiation, while ranks below $a$ have zero cutoff. The second quotient is dominated by $|w|K/(\sigma\sqrt{2\pi})$, with
$$
|w(r)|\le\chi_a'(r)+1/r,
\qquad \int_a^1|w(r)|\,dr\le1+\log(1/a).
$$
Dominated convergence therefore gives exactly
$$
\dot F=\mathbb E[\chi_a(R)\dot f(R)]
 -\int_a^1w(r)\phi(M(r))\dot M(r)\,dr.
$$
Also $\dot M_2=0=M_2(\nu)-M_2(\pi)$. This candidate is not asserted to be an actual global maximizer and supplies no test of the extremal inequalities. It does not establish the general uniform domination, measurable-background or endpoint-recovery claims of the target.

## Failure

NOT fails: this distinct-kernel mixed-label mass transfer has a nonzero signed bulk derivative and the complete suffix-minimum rank derivative exactly as asserted.
