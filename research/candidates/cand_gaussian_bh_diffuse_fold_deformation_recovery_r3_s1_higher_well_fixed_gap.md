---
type: candidate
title: >-
  Higher local well with a fixed positive gap preserves both signed fold
  variations
status: failed
target_asset: gaussian_bh_diffuse_fold_deformation_recovery
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  NOT: fail
mode: refute
round: 3
slot: 1
direction: idea_e795dbed36da
statement_digest: c94a3fdf2ffe058f0be84badf476c4d08154e9cac43cf7bcae563b030a494568
performed_by: unknown
created_at: '2026-11-09T01:53:14.149Z'
extension_version: 0.0.4
---

## Object

Set $q=1/4$, $p=1/2$, $\sigma=1/2$, $\mathcal H=\mathbb R$, $v_0=1$, $v_1=-1$. Let
$$
a=1/4,\qquad r(c)=(1+c)/2,\qquad u(r)=S^{-1}(r/4),
$$
$$
h(c)=\frac1{100}(c-1/4)^2\bigl((c-3/4)^2+1/100\bigr),\qquad
g(c)=-1+h(c),\qquad \vartheta(c)=u(r(c))-g(c).
$$
Use the tagged population in the target and any fixed bump $\chi$ satisfying its definition. This is exactly the higher-local-well object assigned in idea_e795dbed36da. All model parameters and its positive well-height gap are fixed independently of $\epsilon$.

## Checks

### H1

The numerical parameters satisfy $q\in(0,1/2)$ and $p,\sigma\in(0,1)$.

### H2

Both directions are unit vectors and are distinct. With independent standard normals $\xi,Z$,
$$
X_0=\frac{\sqrt3}{2}\xi+\frac12Z,\qquad
Y=-\frac{\sqrt3}{2}\xi+\frac12Z.
$$
Their variances are one and their correlation is $-3/4+1/4=-1/2\in(-1,1)$.

### H3

The deterministic law is exactly
$$
\pi=\frac12\delta_{(0,1,1)}+\frac12\int_0^1\delta_{(\vartheta(c),-1,0)}\,dc.
$$
The means are bounded, so it has a finite first moment. H4 verifies that every alternative mean is strictly positive; the true zero-mean atom and all tags therefore have the required meaning.

### H4

The inverse normal function is smooth on $[q p,q]=[1/8,1/4]$, so $\vartheta$ is $C^3$. Write $t=c-1/4$. Then
$$
h'(c)=\frac1{50}t\bigl((t-1/2)^2+1/100\bigr)+\frac1{50}t^2(t-1/2).
$$
On $[0,1]$, both $|t|$ and $|t-1/2|$ are at most $3/4$, giving $|h'|\le0.017025<1/50$. Since $\phi\le1/\sqrt{2\pi}$,
$$
\frac{d}{dc}u(r(c))=-\frac1{8\phi(u(r(c)))}\le-\frac{\sqrt{2\pi}}8.
$$
Consequently $\vartheta'\le-d_0<0$, where $d_0=\sqrt{2\pi}/8-1/50>0$. Also
$$
h(1)=261/640000<1/2,\qquad \vartheta(1)=u(1)+1-h(1)>1/2.
$$
Strict decrease makes every other alternative mean positive as well.

### H5

The factor $((c-3/4)^2+1/100)$ is strictly positive. Thus $h\ge0$, with equality only at $a=1/4$. The unique global minimum of $g$ is $b=-1$, and
$$
g''(a)=\frac1{50}(1/4+1/100)=13/2500>0,\qquad r_*=5/8.
$$
The other critical points are
$$
c_-=(25-\sqrt{17})/40,\qquad c_+=(25+\sqrt{17})/40.
$$
They are respectively a local maximum and a higher local minimum. Put $d=h(c_+)>0$; numerically $d\simeq2.3954250681953\,10^{-5}$. This strict positive gap distinguishes the object from an inadmissible equal-depth double well. On $[a,c_-]$ the barrier increases, on $[c_-,c_+]$ it decreases, and on $[c_+,1]$ it increases. Its other local maximum has height $h(c_-)\simeq4.5858249318047\,10^{-5}$.

### H6

The fixed bump is any $\chi\in C_c^\infty(\mathbb R)$ with $0\le\chi\le1$, $\chi=1$ on $[-1,1]$, and $\chi=0$ outside $[-2,2]$, exactly as assumed. Its first derivative has finite supremum. There are no additional hypotheses on its shape used below. The approved continuity and ordinary finite-approximation theorem supplied in the context pack is used for conclusion 4, rather than inferred from numerical quadrature.

### NOT

NOT fails: all six conclusion clauses hold for this object. The checks below include the higher competing well, actual largest crossings, both deformation signs, and ordinary finite recovery.

**1. Actual full-FDR representation, including false-only crossings.** Fix real scores $x,y$, and let $R=r_\vartheta(y)$. For $r\in[p,1]$, let $c=(r-p)/(1-p)$. If the true atom is inserted, the count is
$$
\widetilde H(r)=p+(1-p)A_y(r),\qquad A_y(r)=\int_0^1\mathbf1_{\{\vartheta(s)+y\ge u(r)\}}\,ds.
$$
Strict decrease and continuity of the quantile imply, for $c>0$, that $\widetilde H(r)\ge r$ is equivalent to $y\ge g(c)$, including equality and $c=1$. Rank $p$ always qualifies for the forced count. Thus its globally largest qualifying rank is exactly $R$, attained by compactness (or by rank $p$ if the sublevel set is empty).

If $x\ge u(R)$, the actual count qualifies at $R$. No $r>R$ can qualify for the actual count, since it is at most the forced count there. Hence the actual largest rank is $R$, and the full FDP is $p/R$. Conversely, if the actual true atom is rejected at its largest rank $r_0$, the attained-count assertion of the approved dependency gives $r_0=H(r_0)\ge p$. It is then a forced crossing, so $r_0\le R$, and $x\ge u(r_0)\ge u(R)$. If $x<u(R)$ the true numerator is therefore zero, even if a positive false-only crossing exists. Conditioning on $Y=y$ gives exactly the target's kernel $k$ and integral for $F$. This argument applies unchanged to both admissible perturbed quantiles.

For completeness, the unperturbed global auxiliary rank can be described without selecting a local root. For $y<b$ it is $p$. For $b\le y<b+d$, its rightmost sublevel point lies on the increasing branch $[a,c_-)$ and is the unique point there of height $y-b$. At $y=b+d$, the rightmost point jumps to $c_+$. For $b+d\le y<g(1)$ it is the unique point on $[c_+,1)$ with $g(c)=y$, and for $y\ge g(1)$ it is $1$. These statements include the equality at the higher local minimum. The left branch and the branch around $c_-$ never yield a larger point than these globally selected points.

**2. Both bumps, their minima, and cost.** The bounds
$$
\alpha(c-a)^2\le h(c)\le\beta(c-a)^2\quad(0\le c\le1),\qquad
\alpha=1/10000,\quad\beta=3/500
$$
follow directly from the polynomial. Choose $K=128$, for which $\alpha K^2=1.6384>1$. For sufficiently small $\epsilon$, the support $|c-a|\le2K\sqrt\epsilon$ is interior to $[0,1]$. The perturbed quantile derivative differs from the original one by at most $\|\chi'\|_\infty\sqrt\epsilon/K$; it is therefore at most $-d_0/2$. Its value is changed by at most $\epsilon$, so positivity is preserved.

For $\delta=+1$, on $|c-a|\le K\sqrt\epsilon$ one has $g_\epsilon^+(c)=b+h(c)+\epsilon$, with unique minimum $b+\epsilon$ at $a$. Outside that core, $h(c)\ge\alpha K^2\epsilon>\epsilon$ and the bump is nonnegative; hence no point outside the core has as low a value. For $\delta=-1$,
$$
g_\epsilon^-(c)-(b-\epsilon)=h(c)+\epsilon(1-\chi((c-a)/(K\sqrt\epsilon)))\ge0,
$$
with equality only at $a$. Thus both global minima have exactly the asserted height and location. The original directions, all tags, and the true atom remain fixed. Coupling each quantile position to itself gives
$$
W_1(\pi_\epsilon^\delta,\pi)\le(1-p)\epsilon\int_0^1\chi((c-a)/(K\sqrt\epsilon))\,dc
\le4K(1-p)\epsilon^{3/2}.
$$

**3. Global crossing window, both signed variations, and all switches.** Put $C_0=400$. Within the bump support,
$$
h(c)\le4\beta K^2\epsilon=393.216\epsilon,\qquad
g_\epsilon^\delta(c)\le b+394.216\epsilon<b+C_0\epsilon.
$$
For $y\ge b+C_0\epsilon$, every support point belongs to both the original and perturbed sublevel sets, and the sets agree off the support. The entire sets, hence their globally largest points, are identical. For $y<b-\epsilon$, both sets are empty. Therefore the auxiliary ranks can differ only in $|y-b|\le400\epsilon$, regardless of how many other roots exist.

In this window, a point feasible for either model satisfies $h(c)\le401\epsilon$, so
$$
|c-a|\le L\sqrt\epsilon,\qquad L=\sqrt{401/\alpha}.
$$
Whenever a fold is active its point $a$ is feasible, so its globally largest sublevel point lies in $[a,a+L\sqrt\epsilon]$. Thus the corresponding rank is within $(1-p)L\sqrt\epsilon$ of $r_*$. The inactive rank is exactly $p$, by the unique global minima just established. This also proves that in the birth/death interval, of exactly length $\epsilon$, the active rank tends to $r_*$ uniformly and the inactive rank equals $p$. At the minimum height itself the non-strict sublevel set includes $a$ and gives rank $r_*$, as required.

In particular, take the small-perturbation threshold also to satisfy $400\epsilon<d/2$ and $2K\sqrt\epsilon<\min\{a,1-a\}$. The higher-well birth at height $b+d$ is outside the possible-change window; it and all higher-root switches are exactly unchanged for both signs, by equality of the complete sublevel sets above $b+400\epsilon$. Fixed positive $d$ is essential here. A finite-$\epsilon$ switch when $\epsilon$ is comparable to $d$ says nothing against this asymptotic conclusion.

The smooth function $k$ has bounded first derivatives on $[b-1,b+1]\times[p,1]$. In the common-active portion of the change window, its two ranks differ by $O(\sqrt\epsilon)$, so its integrated contribution is $O(\epsilon^{3/2})$. In the birth/death interval, its active-minus-inactive value is $\Delta+O(\sqrt\epsilon)$ uniformly, and $\phi(y)=\phi(b)+O(\epsilon)$. For $\delta=+1$ the perturbed fold is absent on $[b,b+\epsilon)$, giving
$$
F(\pi_\epsilon^+)-F(\pi)=-\epsilon\phi(b)\Delta+O(\epsilon^{3/2}).
$$
For $\delta=-1$ the perturbed fold is present on $[b-\epsilon,b)$ while the original fold is absent, giving
$$
F(\pi_\epsilon^-)-F(\pi)=+\epsilon\phi(b)\Delta+O(\epsilon^{3/2}).
$$
The finitely many interval endpoints have zero Gaussian measure, while their pointwise non-strict crossing behavior has already been checked. No jump sign is discarded.

**4. Ordinary finite recovery.** For each fixed sufficiently small $\epsilon>0$ and each sign, apply conclusion 4 of the approved continuity/finite-approximation dependency to $\pi_\epsilon^\delta$. Its canonical finite laws have simultaneously $W_1\to0$ and $F\to F(\pi_\epsilon^\delta)$. Choose an index at which both errors are at most $\epsilon^2$. The dependency realizes the resulting rational weights by positive integer numbers of identical Gaussian copies, with unit marginal variances and canonical true labels; its full population functional is exactly ordinary largest-rank finite BH FDR. There is no restriction on how rapidly that index or the finite test count grows with $\epsilon$. Triangle inequality gives the asserted $4K(1-p)\epsilon^{3/2}+\epsilon^2$ bound to $\pi$, and the FDR error divided by $\epsilon$ is at most $\epsilon$. Hence both recovered signed limits agree with those just computed. This uses function values and does not interchange a finite derivative and a continuum limit.

**5. Conditional comparison balance.** If the finite-comparison inequality in the statement holds for a finite $\lambda$, apply it to each of the two recovered families and divide by $\epsilon$. Its right-hand error tends to zero. The preceding limits yield both $-\phi(b)\Delta\le0$ and $+\phi(b)\Delta\le0$. Since $\phi(b)>0$, $\Delta=0$. This verifies the conditional implication without asserting existence of the premise.

**6. Nonempty-hypothesis clause.** For every $q,p$ in the stated ranges, $u(r)>0$ on $[p,1]$, and
$$
u'(r)=-q/\phi(u(r)),\qquad u''(r)=q^2u(r)/\phi(u(r))^2>0.
$$
Thus for the stated linear quantile, $g''=(1-p)^2u''>0$. The two displayed strict bounds on its slope give $g'(0)<0<g'(1)$, hence its unique interior nondegenerate global minimum. Since $u(p)>u(1)>0$, $\phi(u(p))<\phi(u(1))$ and that slope interval is nonempty. Taking $M>a$ makes all alternative means positive. This conclusion is consistent with, and independent of, the nonlinear object above.

## Failure

NOT fails: the fixed higher local well and all globally largest-root switches preserve the asserted signed variations, sublinear cost, ordinary finite recovery, and remaining conclusion clauses for both deformation signs.
